# Contributing to git repositories shared by development teams

The objectives of this exercise are:

- contribute to a repository shared by a development team.
- understand what a conflict is in git, why they happen and how they are resolved.

We have to fill in the following programming language popularity table. For each language, we have to look up its popularity indexes in [TIOBE Index](https://www.tiobe.com/tiobe-index/) and [IEEE Spectrum ranking](https://spectrum.ieee.org/top-programming-languages/) and update them in the table.

|   Author   | Programming language | TIOBE index | IEEE Spectrum ranking |
| :--------: | :------------------: | :---------: | :-------------------: |
|  Alfonso   |      Javascript      |    2.12%    |         88.1          |
|   Álvaro   |        Python        |   12.74%    |         100.0         |
|  Augusto   |         Java         |   10.99%    |         95.4          |
|   Darío    |          C           |   11.59%    |         94.7          |
|   Davina   |         C++          |    8.83%    |         92.4          |
|   Denise   |          C#          |    6.39%    |         82.4          |
| Juan Diego |          R           |    1.22%    |         81.7          |
|  Julieta   |         PHP          |    0.0%     |         68.0          |
|   Kevin    |          Go          |    1.11%    |         77.7          |
|   Lucía    |        Delphi        |    0.0%     |          0.0          |
|  Macarena  |     Objective-C      |    1.03%    |         44.4          |
|   Matias   |         Perl         |    0.99%    |         37.2          |
|  Natalia   |         Ruby         |    0.86%    |         63.6          |
|  Victoria  |         Rust         |    0.39%    |         63.1          |
|   JoseMi   |        Kotlin        |    0.39%    |         58.5          |
|   Frida    |        Scala         |    0.0%     |          0.0          |
|    Rui     |       Haskell        |    0.21%    |          0.0          |
|  Patrick   |     Visual Basic     |    5.42%    |         55.1          |
|   David    |         Lua          |    0.77%    |          0.0          |
|            |       Clojure        |    0.0%     |          0.0          |
|            |         Lisp         |    0.0%     |          0.0          |
|            |        Prolog        |    0.0%     |          0.0          |
|            |        Swift         |    0.0%     |          0.0          |

Each of you has to do the following for your row (see column _Author_):

1. Create two branches from the main one. One for updating the TIOBE index, and one for the other index. Choose names for your branches that clearly express which cell of the table is to be modified. Think that your colleagues will also create 2 other branches. We should be able to see all the names of the branches in a list and be able to relate them without difficulty to the table cell to be modified.
2. Go to the TIOBE branch and modify the value of the cell with the value you have found on the web.
3. Commit the change with a descriptive message (see [How to write a good _commit_ message](https://cbea.ms/git-commit/)).
4. Push your change
5. Go to the web page of this repository and create a pull request from your branch to the _main_ branch.
6. Accept the pull request yourself to integrate the changes into main.
   1. Do steps 3 to 6 again to do the same but with the "IEEE Spectrum ranking" branch. If everything went as expected, you will not have been able to complete step 6. This is because you are trying to modify the same line that has been modified in _main_ and that you have not yet downloaded it into your branch.
7. Pull _main_ into your branch to resolve the conflict and decide how the line should finally look. Do this with the command terminal.
8. When you have succeeded, repeat the process again to cause a conflict, but this time record it on video while explaining it and recording your screen. This time you can try doing it with the help of a graphical tool such as an IDE to see the difference in the experience of resolving a git conflict. If you don't have experience recording videos, we recommend two quick and easy options:
   1. [Loom](https://www.loom.com/)
   2. [Zoom](https://zoom.us/). Create a video call where you are alone, share your screen and start recording the video call.
