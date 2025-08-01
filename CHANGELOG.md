# Changelog

## v0.25.0 - 2025-04-29

### Breaking changes
- Drop support for Python 3.8 (#312) [[f008399]](https://github.com/aiidateam/plumpy/commit/f0083995ae9204eb35c32c006a944168dd1029b2)

### Features
-  Add support of Python 3.13 (#312) [[f008399]](https://github.com/aiidateam/plumpy/commit/f0083995ae9204eb35c32c006a944168dd1029b2)
- Add option to forcefully (not gracefully) killing a process [[8703d4b]](https://github.com/aiidateam/plumpy/commit/8703d4b4ce17afc7687335c19b348c3a3ce1657f)
- Kill task are cancelled and requeued when a new kill message is received [[8703d4b]](https://github.com/aiidateam/plumpy/commit/8703d4b4ce17afc7687335c19b348c3a3ce1657f)
- Handle Uuid FullLoader with yaml de/serializer in message passing (#310)[[98b3e93]](https://github.com/aiidateam/plumpy/commit/98b3e9380fd2fce437fe1cef906ef075832bf30f)

### Devops
- Update the the readthedocs yaml to v2 and py13 (#313) [[538c824]](538c8240d8fe46d9ea93a5ca3b6cc31dad20ad2f)


## v0.24.0 - 2025-01-08

### Breaking changes
  - Direct message constants (`KILL_MSG`, `PAUSE_MSG`, `PLAY_MSG`, `STATUS_MSG`) are replaced with the `MessageBuilder` class methods.

### Features
- Message builder for constructing message with carrying more information (#291) [[f760b4a]](https://github.com/aiidateam/plumpy/commit/f760b4aaf6a46bbfc13bab88e36271aab122a641)
- Make Message interface is hidden inside function call (#301) [[a4b896]](https://github.com/aiidateam/plumpy/commit/a4b896255a4d92cef7ff3494e915acabd64d97c1)

### Devops
- Make rpc callback exception more explicit and wind up to show more infos (#305) [[ecef9b9]](https://github.com/aiidateam/plumpy/commit/ecef9b9a4ebbeafacd3b6a84952ad770972f2814)


## v0.23.0 - 2024-12-13

### Breaking changes
  - All the `run()` methods across the interface are now asynchronous (async def).
  - Changes from `Coroutine` to `Awaitable` in function signatures.

### Bug fixes
- Make `Waiting.resume()` idempotent (#285) [[20e5898]](https://github.com/aiidateam/plumpy/commit/20e5898e0c9037624988fe321e784f4fe38a2e8d)

### Devops
- Make `Process.run` async (#272) [[4611154]](https://github.com/aiidateam/plumpy/commit/4611154c76ac0991bcf7371b21488f4390648c28)
- Switch to ruff and other devops improvements (#289) [[55e05e9]](https://github.com/aiidateam/plumpy/commit/55e05e956c9715fb69785d83d0194b65811b4720)
- Bump Python version in CI: 3.8 to 3.12 (Increase python version used in continuous deployment git-workflow from 3.8 to 3.12 (#304) [[bb32edb]](https://github.com/aiidateam/plumpy/pull/304)


## v0.22.3 - 2024-02-02

### Bug fixes
- Catch `ChannelInvalidStateError` in process state change [[fda244a]](https://github.com/aiidateam/plumpy/commit/fda244a139e26472c37f698d7d64f3d6e13ad57b)
- Make `ProcessListener` instances persistable [[fc66001]](https://github.com/aiidateam/plumpy/commit/fc660017e4d21a1122dc1236e4ade2f54d146500)

### Dependencies
- Add support for Python 3.12 [[8043a63]](https://github.com/aiidateam/plumpy/commit/8043a630c50b60d599d3d8e7d85aefbb3ff46ade)
- Drop support for Python 3.7 [[14b7c1a]](https://github.com/aiidateam/plumpy/commit/14b7c1a83026699fcc9f01c56a85872a8dd3c25c)

### Devops
- Update ReadTheDocs configuration file [[5ddba0f]](https://github.com/aiidateam/plumpy/commit/5ddba0f0136994a4703d507d7de98062c26928e7)


## v0.22.2 - 2023-06-23

This release applies the fixes that were released on the support branch of `v0.21.x`.

### Bug fixes
- Workchains: Accept but deprecate conditional predicates returning `None` [[#261]](https://github.com/aiidateam/plumpy/pull/261)
- `PortNamespace`: Fix bug in valid type checking of dynamic namespaces [[#255]](https://github.com/aiidateam/plumpy/pull/255)
- `PortNamespace`: Make `dynamic` apply recursively [[#263]](https://github.com/aiidateam/plumpy/pull/263)
- `PortNamespace.get_port`: Only create if `create_dynamically` is `True` [[#268]](https://github.com/aiidateam/plumpy/pull/268)


## v0.22.1 - 2022-11-21

### Dependencies
- Add support for Python 3.11 [[#249]](https://github.com/aiidateam/plumpy/pull/249)
- Update requirement `pyyaml~=6.0` [[#248]](https://github.com/aiidateam/plumpy/pull/248)


## v0.22.0 - 2022-10-31

### Features
- `Process`: Add the `is_excepted` property [[#240]](https://github.com/aiidateam/plumpy/pull/240)

### Bug fixes
- `StateMachine`: transition directly to excepted if transition failed [[#240]](https://github.com/aiidateam/plumpy/pull/240)
- `Process`: Fix incorrect overriding of `transition_failed` [[#240]](https://github.com/aiidateam/plumpy/pull/240)

### Dependencies
- Add support for Python 3.10 [[#242]](https://github.com/aiidateam/plumpy/pull/242)
- Update requirement `kiwipy~=0.8.2` [[#243]](https://github.com/aiidateam/plumpy/pull/243)
- Add lower limit for patch version of `nest-asyncio` [[#241]](https://github.com/aiidateam/plumpy/pull/241)

### Devops
- Fix `auto_persist` decorator typing [[#239]](https://github.com/aiidateam/plumpy/pull/239)
- Fix remaining warnings in unit tests [[#244]](https://github.com/aiidateam/plumpy/pull/244)
- Update the `mypy` pre-commit dependency [[#246]](https://github.com/aiidateam/plumpy/pull/246)


## v0.21.11 - 2024-07-01

### Fixes
- Make `Waiting.resume()` idempotent [[a79497b]](https://github.com/aiidateam/plumpy/commit/a79497ba37cef7bc609cee90535ad86708fc48f9)

### Dependencies
- Add requirement `nbdime<4` [[94df0df]](https://github.com/aiidateam/plumpy/commit/94df0dfd0a3ea93174aa4de83ac5e06246350c27)


## v0.21.10 - 2023-11-13

### Dependencies

- Dependencies: Add support for Python 3.12 [[2af3907]](https://github.com/aiidateam/plumpy/commit/2af390738df3f151c8225c01e265527b65d7a005)


## v0.21.9 - 2023-11-10

### Features
- Make `ProcessListener` instances persistable [[98a375f]](https://github.com/aiidateam/plumpy/commit/98a375f07db0cacaacdc1545d4d12f25dd00bf1d)

### Fixes
- Catch `ChannelInvalidStateError` in process state change [[db2af9a]](https://github.com/aiidateam/plumpy/commit/db2af9acf7c139798a21e574d6308ae21b3b7513)

### Devops
- Update ReadTheDocs configuration file [[31f85c7]](https://github.com/aiidateam/plumpy/commit/31f85c71730b488aafd680f240485a51884722b7)


## v0.21.8 - 2023-06-07

### Devops
- Dependencies: Update requirement `mypy==1.3.0` [[#270]](https://github.com/aiidateam/plumpy/pull/270)


## v0.21.7 - 2023-04-20

### Bug fixes
- `PortNamespace.get_port`: Only create if `create_dynamically` is `True` [[#268]](https://github.com/aiidateam/plumpy/pull/268)


## v0.21.6 - 2023-04-03

### Bug fixes
- `PortNamespace`: Make `dynamic` apply recursively [[#263]](https://github.com/aiidateam/plumpy/pull/263)
- Workchains: Turn exception into warning for incorrect return type in conditional predicates: any type that implements `__bool__` will be accepted [[#265]](https://github.com/aiidateam/plumpy/pull/265)


## v0.21.5 - 2023-03-14

### Bug fixes
- Workchains: Accept but deprecate conditional predicates returning `None` [[#261]](https://github.com/aiidateam/plumpy/pull/261)


## v0.21.4 - 2023-03-09

### Bug fixes
- Workchains: Raise if `if_/while_` predicate does not return boolean [[#259]](https://github.com/aiidateam/plumpy/pull/259)

### Dependencies
- Dependencies: Update pre-commit requirement `isort==5.12.0` [[#260]](https://github.com/aiidateam/plumpy/pull/260)


## v0.21.3 - 2022-12-07

### Bug fixes
- `PortNamespace`: Fix bug in valid type checking of dynamic namespaces [[#255]](https://github.com/aiidateam/plumpy/pull/255)


## v0.21.2 - 2022-11-29

### Bug fixes
`Process`: Ensure that the raw inputs are not mutated [[#251]](https://github.com/aiidateam/plumpy/pull/251)

### Dependencies
- Add support for Python 3.10 and 3.11 [[#254]](https://github.com/aiidateam/plumpy/pull/254)
- Update requirement `pytest-notebook>=0.8.1` [[#254]](https://github.com/aiidateam/plumpy/pull/254)
- Update requirement `pyyaml~=6.0` [[#254]](https://github.com/aiidateam/plumpy/pull/254)
- Update requirement `kiwipy[rmq]~=0.7.7` [[#254]](https://github.com/aiidateam/plumpy/pull/254)
- Update the `myst-nb` and `sphinx` requirements [[#253]](https://github.com/aiidateam/plumpy/pull/253)


## v0.21.1 - 2022-11-21

This is a backport of changes introduced in `v0.22.0`.

### Features
- `Process`: Add the `is_excepted` property [[#240]](https://github.com/aiidateam/plumpy/pull/240)

### Bug fixes
- `StateMachine`: transition directly to excepted if transition failed [[#240]](https://github.com/aiidateam/plumpy/pull/240)
- `Process`: Fix incorrect overriding of `transition_failed` [[#240]](https://github.com/aiidateam/plumpy/pull/240)


## v0.21.0 - 2022-04-08

### Bug fixes
- Fix `UnboundLocalError` in `DefaultObjectLoader.load_object`. [[#225]](https://github.com/aiidateam/plumpy/pull/225)

### Dependencies
- Drop support for Python 3.6. [[#228]](https://github.com/aiidateam/plumpy/pull/228)
- Pin Jinja2 and Markupsafe packages for docs builds. [[#228]](https://github.com/aiidateam/plumpy/pull/228)
- Update requirement `nest-asyncio~=1.5` [[#229]](https://github.com/aiidateam/plumpy/pull/229)
- Pin tests requirements to functional versions. [[#228]](https://github.com/aiidateam/plumpy/pull/228)

### Devops
- Adopt PEP 621 and move build spec to `pyproject.toml` [[#230]](https://github.com/aiidateam/plumpy/pull/230)
- Move package into the `src/` subdirectory [[#234]](https://github.com/aiidateam/plumpy/pull/234)
- Merge separate license files into one [[#232]](https://github.com/aiidateam/plumpy/pull/232)
- Add the `flynt` and `isort` pre-commit hooks [[#233]](https://github.com/aiidateam/plumpy/pull/233)
- Remove obsolete `release.sh` [[#231]](https://github.com/aiidateam/plumpy/pull/231)
- Update the continuous deployment workflow [[#235]](https://github.com/aiidateam/plumpy/pull/235)


## v0.20.0 - 2021-08-10

- 🔧 MAINTAIN: update requirement to `pyyaml~=5.4` (#221)
  The versions of `pyyaml` up to v5.4 contained severe security issues where the default loaders could be abused for arbitrary code execution.
  The default `FullLoader` was patched to no longer allow this behavior, but as a result, data sets that could be successfully deserialized with it, now will fail.
  This required using the unsafe `Loader` in for the deserialization of the exception state of a process.


## v0.19.0 - 2021-03-09

- ‼️ DEPRECATE: `Process.done` method:
  This method is a duplicate of `Process.has_terminated`, and is not used anywhere in plumpy (or aiida-core).

- 🐛 FIX: `Task.cancel` should not set state as `EXCEPTED`
  `asyncio.CancelledError` are generated when an async task is cancelled.
  In python 3.7 this exception class inherits from `Exception`, whereas in python 3.8+ it inherits from `BaseException`.
  This meant it python 3.7 it was being caught by `except Exception`, and setting the process state to `EXCEPTED`,
  whereas in python 3.8+ it was being re-raised to the caller.
  We now ensure in both versions it is re-raised (particularly because aiida-core currently relies on this behaviour).

- 👌 IMPROVE: Process broadcast subscriber
  Filter out `state_changed` broadcasts, and allow these to pass-through without generating a (costly) asynchronous task.
  Note this also required an update in the minimal kiwipy version, to `0.7.4`

## v0.18.6 - 2021-02-24

👌 IMPROVE: Catch state change broadcast timeout

When using an RMQ communicator, the broadcast can timeout on heavy loads to RMQ
(for example see <https://github.com/aiidateam/aiida-core/issues/4745>).
This broadcast is not critical to the running of the process,
and so a timeout should not except it.

Also ensure the process PID is included in all log messages.

## v0.18.5 - 2021-02-15

Minor improvements and bug fixes:

- 🐛 FIX: retrieve future exception on_killed
  The exception set on the future should be retrieved, otherwise it will be caught by the loop's exception handler.
- 🐛 FIX: Clean-up process event hooks:
  On Process close/cleanup event hooks are removed,
  in part to not persist cyclic dependencies of hooks <-> Process.
  Once a process is closed, it will also not raise an Exception if a hook tries to un-register itself (but has already been removed by the clean-up).
- 👌 IMPROVE: Add `Process.is_killing` property
- 👌 IMPROVE: remove RUNNING from allowed states of `resume`:
  Since there is no `resume` method implemented for the `Running` class.
- 🔧 MAINTAIN: Remove frozendict dependency

## v0.18.4 - 2021-01-21

Minor update, to add `py.typed` file to distribution, in accordance with [PEP-561](https://www.python.org/dev/peps/pep-0561/) [[#195]](https://github.com/aiidateam/plumpy/pull/195)

## v0.18.2 - 2021-01-21

### Changes

- Allow for dereferencing of saved instance state [[#191]](https://github.com/aiidateam/plumpy/pull/191)
- Add type checking to code base [[#180]](https://github.com/aiidateam/plumpy/pull/180)
- Improve documentation [[#190]](https://github.com/aiidateam/plumpy/pull/190)

## v0.18.1 - 2020-12-18

### Bug fixes

- Trigger application of nest patch in `set_event_loop_policy` to make it compatible with Jupyter notebooks [[#189]](https://github.com/aiidateam/plumpy/pull/189)

## v0.18.0 - 2020-19-09

### Changes

- Drop support for Python 3.5 [[#187]](https://github.com/aiidateam/plumpy/pull/187)

### Dependencies

- Dependencies: update requirement `kiwipy~=0.7.1` [[#184]](https://github.com/aiidateam/plumpy/pull/184)

## v0.17.1 - 2020-11-25

### Bug fixes

- Dependencies: only require `aiocontextvars` for Python < 3.7 [[#181]](https://github.com/aiidateam/plumpy/pull/181)

## v0.17.0 - 2020-11-13

### Changes

- Add support for Python 3.9 [[#176]](https://github.com/aiidateam/plumpy/pull/176)
- Make application of `nest_asyncio` patch explicit [[#179]](https://github.com/aiidateam/plumpy/pull/179)

### Bug fixes

- `Port`: do not call validator if unspecified and port not required [[#173]](https://github.com/aiidateam/plumpy/pull/173)

## v0.16.1 - 2020-09-04

### Changes

- Dependencies: relax the requirement on `aio-pika` to `aio-pika~=6.6`. [[#171]](https://github.com/aiidateam/plumpy/pull/171)

## v0.16.0 - 2020-08-15

### Changes

- Drop `tornado` as a dependency and replace it fully by `asyncio` [[#166]](https://github.com/aiidateam/plumpy/pull/166)

## v0.15.0 - 2020-06-16

### Changes

- Drop support for Python 2.7 [[#151]](https://github.com/aiidateam/plumpy/pull/151)

### Bug fixes

- `LoopCommunicator`: fix incorrect call through in `remove_broadcast_subscriber` [[#156]](https://github.com/aiidateam/plumpy/pull/156)
- `PortNamespace`: do not add empty optional port namespaces to parsed inputs in the `pre_process` method [[#143]](https://github.com/aiidateam/plumpy/pull/143)
- `PortNamespace`: do not set `dynamic=False` when `valid_type=None` [[#146]](https://github.com/aiidateam/plumpy/pull/146)
- `PortNamespace`: set `dynamic=True` if `valid_type` in constructor [[#145]](https://github.com/aiidateam/plumpy/pull/145)

### Developers

- Migrate CI from Travis to Github Actions [[#152]](https://github.com/aiidateam/plumpy/pull/152)

## v0.14.5 - 2020-01-22

### Features

- `Port`: add context argument to validator method [[#141]](https://github.com/aiidateam/plumpy/pull/141)

### Changes

- Remove unnecessary abstraction layer `ValueSpec` [[#141]](https://github.com/aiidateam/plumpy/pull/141)

## v0.14.4 - 2019-12-12

### Bug fixes

- `ProcessSpec`: do not set `_spec` attribute if an error is raised in `spec` call [[#136]](https://github.com/aiidateam/plumpy/pull/136)

## v0.14.3 - 2019-10-25

### Features

- Allow lambdas for `InputPort` default values[[#133]](https://github.com/aiidateam/plumpy/pull/133)

### Bug fixes

- `PortNamespace`: move namespace validator after port validation [[#129]](https://github.com/aiidateam/plumpy/pull/129)


## v0.14.2 - 2019-07-16

### Features

- `PortNamespace`: add the concept of a "lazy" namespace  [[#121]](https://github.com/aiidateam/plumpy/pull/121)

### Bug fixes

- `PortNamespace`: fix the implementation of `include` in `absorb` [[#120]](https://github.com/aiidateam/plumpy/pull/120)


## v0.14.1 - 2019-06-17

### Features

- `PortNamespace`: add support for nested exclude/include rules in `absorb` [[#116]](https://github.com/aiidateam/plumpy/pull/116)
- Add traceback when setting exception on an excepted `Future` [[#113]](https://github.com/aiidateam/plumpy/pull/113)

## v0.14.0

### Bug fixes

- Fix bug in process spec validation with default and validator [[#106]](https://github.com/aiidateam/plumpy/pull/106)
- Fix call of `Portnamespace.validator` [[#104]](https://github.com/aiidateam/plumpy/pull/104)
