- Portability: Capacity to run an application in different enviroments without changing the source code.

## Codebase
Have a single code base for a single application.
Multiple apps sharing the same code is a violation of twelve-factor

## Dependecies
Explicity declare and isolate dependecies
A twelve-factor app never relies on implicit existence of system-wide packages.

## Config
Store config in enviroment variables.
This allows to open source the app code without exposing sensitive information.

## Backing Services
Treat backing services as attached resources.


## Build, release, run
Strict separation between build, release and run stages.

Build stage: Converts code repo into an executable bundle known as a build.
Release stage: Takes the build produced in build stage and combines it with deploy's current config.
Run stage: Runs the app in the execution enviroment.

Releases can not me mutated.  Any change must create a new release.
![[Pasted image 20230423230157.png]]
Image taken from twelve-factor app documentation

## Processes
Twelve-factor processes are stateless and share-nothing.
Sticky sessions are a violation of twelve-factor and should never be used or relied upon.

## Port binding
The twelve-factor app is completely self-contained

## Concurrency
Processes are a first class citizen. Applications should scale out horizontaly by running multiple instances of the application concurrently.
Example: 
![[Pasted image 20230423224121.png]]
Credits to kodekloud

## Disposability
Processes are disposable, meaning they can be started or stopped at a moment notice.
Processes should shutdown gracefully when they receive a SIGTERM signal from process manager.

## Dev / prod parity
The twelve-factor app is designed for continuos deployment by keeping the gap between development and production small. Resists the urge to use different backing services between development and production.

## Logs
Never concerns itself with routing or storage of its output stream. Store logs in a centralized location in a specific format.

## Admin Processes
Admin tasks should be separated from application processes in identical setups.