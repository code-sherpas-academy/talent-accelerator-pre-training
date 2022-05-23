![FTL: Faster Than Light](images/FTL-logo.jpg "FTL: Faster Than Light")

[![Code Sherpas](images/code-sherpas.png "Code Sherpas")](https://code-sherpas.rocks)

***Project designed by*** [Code Sherpas](https://code-sherpas.rocks)

# Qué habilidades se pretende poner en práctica

- Poner en práctica el diseño e implementación de una API siguiendo el estilo arquitectónico REST. Las APIs que aplican REST reciben el nombre de RESTful APIs.
- Creación de una aplicación web con una interfaz HTTP.
- Creación de una aplicación un dominio complejo (no trivial). Un ejemplo de dominio trivial es un CRUD sin reglas ni restricciones de negocio como el take-home project que ya habéis hecho. Un ejemplo de dominio complejo es un dominio con reglas y restricciones de negocio como puede ser el modelado del videojuego (con sus reglas y mecánicas de juego) de la sesión de pair programming.
- Experimentar procesos de desarrollo de software iterativos e incrementales.

# Recursos sobre los conceptos que hay que aplicar

- RESTful APIs: WIP

## Introducción

Este proyecto trata de crear una aplicación web interactiva con una RESTful API (sobre el protocolo HTTP) cuyo dominio modela un simulador de naves espaciales que luchan entre sí.

Las reglas y restricciones del dominio están inspiradas en el videojuego [FTL: Faster Than Light](https://store.steampowered.com/app/212680/FTL_Faster_Than_Light/). Aunque estén inspiradas en ese videojuego, solo debemos tener en cuenta las especificaciones y comportamientos que se piden en este documento.

![FTL: Faster Than Light](images/FTL-image.jpg "FTL: Faster Than Light")

## Proceso de desarrollo

A lo largo de este proyecto, se irá pidiendo desarrollar una serie de pequeños comportamientos paso a paso para experimentar un proceso de desarrollo de software incremental. Por favor, sigue los pasos en el orden que se muestran para maximizar la facilidad de la evolución de la aplicación.




### 3.1 How to simulate a battle

1. First, at least two ships must be created (each with its own particular configuration) by invoking the [Create a ship](src/main/java/fasterthanlight/CreateShipController.java) endpoint twice. But you can add as many ships as you want to the battle!
   You can initiate your ships with any desired state that is compliant with the game's rules stated below.

2. Then we can make the ships fire at each other by invoking the endpoint [Firing a ship's weapon at a target (another ship)](src/main/java/fasterthanlight/FireWeaponController.java). Also alter the shooting with invocations to the [Advance game (moves time forward one second)](src/main/java/fasterthanlight/AdvanceGameController.java) endpoint to see how the battle evolves over time.

## 3. Game mechanics

### 3.1 Time

Time moves forward by 1 second on every tick.

### A ship's representation in JSON format.

Example of a JSON document representing a ship:

```json
{
    "id":"bc247dgf23476",
    "attributes":{
        "hull":30,
        "weapons":[
            {
                "id":"dfhn8273r",
                "charge-time-in-seconds":6,
                "countdown":3
            },
            {
                "id":"897gh0f43",
                "charge-time-in-seconds":9,
                "countdown":0
            },
            {
                "id":"bc62345423",
                "charge-time-in-seconds":4,
                "countdown":4
            }
        ],
        "barriers-charge-time-in-seconds":5,
        "shields-barriers":[
            {
                "position":1,
                "countdown":2
            },
            {
                "position":2,
                "countdown":0
            },
            {
                "position":3,
                "countdown":5
            },
            {
                "position":4,
                "countdown":3
            }
        ]
    }
}
```
### Rules

#### 3.1 Hull

The hull is the body of the ship that maintains structural integrity (key `hull`).

#### 3.2 Systems

Systems are equipment that provides your ship with capabilities. The ship has the following systems:

- Weapon Control
- Shields

##### 3.2.1 Weapon Control System

The weapon control system has a certain number of weapons. Each weapon has a unique id (key `id`).

All weapons have an associated charge time in seconds (key `charge-time-in-seconds`), which is the time it takes for a weapon to fire again after a shot has been fired. When a weapon is recharging, `countdown` indicates how much time is left until it is fully recharged and ready to fire.

Just at the instant a weapon starts to recharge, `countdown` is equal to `charge-time-in-seconds`. When `countdown` reaches 0, the weapon is ready to fire and `countdown` will remain at 0 unless it fires.

When a weapon fires, the resulting shot travels through the space between the two ships instantaneously. So if a weapon fires at a certain instant, the shot will hit the other ship at the same moment without needing to advance the battle a second further.

##### 3.2.2 Shields System

The shields system is composed of a stack of shot-absorbing barriers surrounding the hull (key `shields-barriers`).

Each barrier has a position (key `position`) within the stack. No two barriers can be in the same position in the stack. In other words, the barrier closest to the hull is in position 1, the next furthest barrier is in position 2, and so on.

When a shot hits a barrier, the shot is absorbed by the barrier. Every time a barrier absorbs a shot, it disappears for `barriers-charge-time-in-seconds` until it recharges completely and appears again.

When a barrier is recharging, `countdown` indicates how much time is left until it is fully recharged and appears around the hull (`countdown = 0` means that the barrier is fully recharged and present).

Just at the instant a barrier starts to recharge, `countdown` is equal to `barriers-charge-time-in-seconds`. When `countdown` reaches 0, the barrier appears and `countdown` will remain at 0 unless the barrier is hit by a shot.

#### 3.3 Making Damage

A shot can impact the hull when there is no barrier present to absorb it. When a shot hits the hull, its structural integrity (key `hull`) is reduced by one. When the structural integrity of the hull is 0, the ship is considered destroyed.

#### 3.4 When multiple shots hit a barrier in the same second

When multiple shots hit a barrier in the same second, the behaviour is as follows:

1. the barrier absorbs one of the shots and the rest of the shots continue on their way to the hull of the ship.

2.
    1. **If there are no more barriers**, the shots will hit the hull of the ship reducing the structural integrity by as many units as shots hit the hull.
    2. **If there is one more barrier**, go to step 1.