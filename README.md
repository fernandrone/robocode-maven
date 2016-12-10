# Robocode-maven

A framework for easy development and sharing of [Robocode](http://robocode.sourceforge.net/) robots, setup as a [Maven](https://maven.apache.org/) project and adapted to work with the containerized [Robocode-docker](https://github.com/fbcbarbosa/robocode-docker).

## Installation

1. Clone Robocode-maven where you want it installed. A good place to pick is `$HOME/robocode` (but you can install it somewhere else).

  ```
  $ git clone https://github.com/fbcbarbosa/robocode-maven/ ~/robocode
  ```

2. Define the environment variable `ROBO_ROOT` to point to the path where the repo is cloned and add `$ROBO_ROOT` to your $PATH for access to the pyenv command-line utility.

  ```
  $ echo 'export ROBO_ROOT="$HOME/robocode"' >> ~/.bashrc 
  $ echo 'export PATH="$ROBO_ROOT:$PATH"' >> ~/.bashrc
  ```
  
3. Restart your shell so the path changes take effect.

  ```
  $ exec $SHELL
  ```

4. Build the project one time using [Maven](https://maven.apache.org/):

  ```
  $ cd $ROBO_ROOT
  $ mvn clean install
  ```

5. Run 'robo' script to launch [Robocode-docker](https://github.com/fbcbarbosa/robocode-docker):

  ```
  $ robo
  ```

And that's it!
  
## Developing robots

Simply add the repository to your favorite IDE as a Maven Project. Now make sure that every robot is added under the `robots` package, within the `$ROBO_ROOT/src/main/java/robots` folder. Feel free to add subpackages though, e.g. `robots.myrobot` at `$ROBO_ROOT/src/main/java/robots/myrobots`.

To build your robots run Maven on the root of this repository:

```
$ cd $ROBO_ROOT
$ mvn clean install
```

They will then become instantly available on Robocode (even if it is already running) under the `robots.*` package.

Don't forget to commit your robots on a public GitHub repository so that everyone can learn from them :)
