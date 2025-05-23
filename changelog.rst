.. :changelog:

Changelog
---------

7.0.0-dev
~~~~~~~~~

202x-xx-xx • `full history <https://github.com/gorakhargosh/watchdog/compare/v6.0.0...HEAD>`__

**Breaking Changes**

- [core] Changed pattern matching mechanism from using ``path.match()`` to ``path.full_match()``. Users must update patterns to glob-like syntax: e.g., `*.py` to `**/*.py`. (`#1101 <https://github.com/gorakhargosh/watchdog/pull/1101>`__)

**Other Changes**

- [core] Adjust ``Observer.schedule()`` ``path`` type annotation to reflect the ``pathlib.Path`` support. (`#1096 <https://github.com/gorakhargosh/watchdog/pull/1096>`__)
- [core] Add support for the ``follow_symlink`` keyword argument to ``ObservedWatch``. (`#1086 <https://github.com/gorakhargosh/watchdog/pull/1086>`__)
- [fsevents] Add support for the ``follow_symlink`` keyword argument. (`#1086 <https://github.com/gorakhargosh/watchdog/pull/1086>`__)
- [inotify] Reduce number of created inotify instance. (`#1099 <https://github.com/gorakhargosh/watchdog/pull/1099>`__)
- [inotify] Add support for the ``follow_symlink`` keyword argument. (`#1086 <https://github.com/gorakhargosh/watchdog/pull/1086>`__)
- [utils] Fixed ``repr(EmptyDirectorySnapshot)``, before that it was throwing an ``AttributeError: 'EmptyDirectorySnapshot' object has no attribute '_stat_info'``.
- [utils] Implemented ``len(DirectorySnapshotDiff)`` to return the total number of changes.
- Thanks to our beloved contributors: @BoboTiG, @tybug, @Corentin-pro, @kirkhansen, @JoachimCoenen

6.0.0
~~~~~

2024-11-01 • `full history <https://github.com/gorakhargosh/watchdog/compare/v5.0.3...v6.0.0>`__

- Pin test dependencies.
- [docs] Add typing info to quick start. (`#1082 <https://github.com/gorakhargosh/watchdog/pull/1082>`__)
- [inotify] Use of ``select.poll()`` instead of deprecated ``select.select()``, if available. (`#1078 <https://github.com/gorakhargosh/watchdog/pull/1078>`__)
- [inotify] Fix reading inotify file descriptor after closing it. (`#1081 <https://github.com/gorakhargosh/watchdog/pull/1081>`__)
- [utils] The ``stop_signal`` keyword-argument type of the ``AutoRestartTrick`` class can now be either a ``signal.Signals`` or an ``int``.
- [utils] Added the ``__repr__()`` method to the ``Trick`` class.
- [utils] Removed the unused ``echo_class()`` function from the ``echo`` module.
- [utils] Removed the unused ``echo_instancemethod()`` function from the ``echo`` module.
- [utils] Removed the unused ``echo_module()`` function from the ``echo`` module.
- [utils] Removed the unused ``is_class_private_name()`` function from the ``echo`` module.
- [utils] Removed the unused ``is_classmethod()`` function from the ``echo`` module.
- [utils] Removed the unused ``ic_method(met()`` function from the ``echo`` module.
- [utils] Removed the unused ``method_name()`` function from the ``echo`` module.
- [utils] Removed the unused ``name()`` function from the ``echo`` module.
- [watchmedo] Fixed Mypy issues.
- [watchmedo] Added the ``__repr__()`` method to the ``HelpFormatter`` class.
- [watchmedo] Removed the ``--trace`` CLI argument from the ``watchmedo log`` command, useless since events are logged by default at the ``LoggerTrick`` class level.
- [windows] Fixed Mypy issues.
- Thanks to our beloved contributors: @BoboTiG, @g-pichler, @ethan-vanderheijden, @nhairs

5.0.3
~~~~~

2024-09-27 • `full history <https://github.com/gorakhargosh/watchdog/compare/v5.0.2...v5.0.3>`__

- [inotify] Improve cleaning up ``Inotify`` threads, and add ``eventlet`` test cases (`#1070 <https://github.com/gorakhargosh/watchdog/pull/1070>`__)
- Thanks to our beloved contributors: @BoboTiG, @ethan-vanderheijden

5.0.2
~~~~~

2024-09-03 • `full history <https://github.com/gorakhargosh/watchdog/compare/v5.0.1...v5.0.2>`__

- Enable OS specific Mypy checks (`#1064 <https://github.com/gorakhargosh/watchdog/pull/1064>`__)
- [watchmedo] Fix ``tricks`` argument type of ``schedule_tricks()`` (`#1063 <https://github.com/gorakhargosh/watchdog/pull/1063>`__)
- Thanks to our beloved contributors: @gnought, @BoboTiG

5.0.1
~~~~~

2024-09-02 • `full history <https://github.com/gorakhargosh/watchdog/compare/v5.0.0...v5.0.1>`__

- [kqueue] Fix ``TypeError: kqueue.control() only accepts positional parameters``  (`#1062 <https://github.com/gorakhargosh/watchdog/pull/1062>`__)
- Thanks to our beloved contributors: @apoirier, @BoboTiG

5.0.0
~~~~~

2024-08-26 • `full history <https://github.com/gorakhargosh/watchdog/compare/v4.0.2...v5.0.0>`__

**Breaking Changes**

- Drop support for Python 3.8 (`#1055 <https://github.com/gorakhargosh/watchdog/pull/1055>`__)
- [core] Enforced usage of proper keyword-arguments (`#1057 <https://github.com/gorakhargosh/watchdog/pull/1057>`__)
- [core] Renamed the ``BaseObserverSubclassCallable`` class to ``ObserverType`` (`#1055 <https://github.com/gorakhargosh/watchdog/pull/1055>`__)
- [inotify] Renamed the ``inotify_event_struct`` class to ``InotifyEventStruct`` (`#1055 <https://github.com/gorakhargosh/watchdog/pull/1055>`__)
- [inotify] Renamed the ``UnsupportedLibc`` exception to ``UnsupportedLibcError`` (`#1057 <https://github.com/gorakhargosh/watchdog/pull/1057>`__)
- [inotify] Removed the ``InotifyConstants.IN_CLOSE`` constant (`#1046 <https://github.com/gorakhargosh/watchdog/pull/1046>`__)
- [watchmedo] Renamed the ``LogLevelException`` exception to ``LogLevelError`` (`#1057 <https://github.com/gorakhargosh/watchdog/pull/1057>`__)
- [watchmedo] Renamed the ``WatchdogShutdown`` exception to ``WatchdogShutdownError`` (`#1057 <https://github.com/gorakhargosh/watchdog/pull/1057>`__)
- [windows] Renamed the ``FILE_NOTIFY_INFORMATION`` class to ``FileNotifyInformation`` (`#1055 <https://github.com/gorakhargosh/watchdog/pull/1055>`__)
- [windows] Removed the unused ``WATCHDOG_TRAVERSE_MOVED_DIR_DELAY`` constant (`#1057 <https://github.com/gorakhargosh/watchdog/pull/1057>`__)

**Other Changes**

- [core] Enable ``disallow_untyped_calls`` Mypy rule (`#1055 <https://github.com/gorakhargosh/watchdog/pull/1055>`__)
- [core] Enable ``disallow_untyped_defs`` Mypy rule (`#1060 <https://github.com/gorakhargosh/watchdog/pull/1060>`__)
- [core] Improve typing references for events (`#1040 <https://github.com/gorakhargosh/watchdog/issues/1040>`__)
- [inotify] Add support for ``IN_CLOSE_NOWRITE`` events. A ``FileClosedNoWriteEvent`` event will be fired, and its ``on_closed_no_write()`` dispatcher has been introduced (`#1046 <https://github.com/gorakhargosh/watchdog/pull/1046>`__)
- Thanks to our beloved contributors: @BoboTiG

4.0.2
~~~~~

2024-08-11 • `full history <https://github.com/gorakhargosh/watchdog/compare/v4.0.1...v4.0.2>`__

- Add support for Python 3.13 (`#1052 <https://github.com/gorakhargosh/watchdog/pull/1052>`__)
- [core] Run ``ruff``, apply several fixes (`#1033 <https://github.com/gorakhargosh/watchdog/pull/1033>`__)
- [core] Remove execution rights from ``events.py``
- [documentation] Update ``PatternMatchingEventHandler`` docstrings (`#1048 <https://github.com/gorakhargosh/watchdog/pull/1048>`__)
- [documentation] Simplify the quickstart example (`#1047 <https://github.com/gorakhargosh/watchdog/pull/1047>`__)
- [fsevents] Add missing ``event_filter`` keyword-argument to ``FSEventsObserver.schedule()`` (`#1049 <https://github.com/gorakhargosh/watchdog/pull/1049>`__)
- [utils] Fix a possible race condition in ``AutoRestartTrick`` (`#1002 <https://github.com/gorakhargosh/watchdog/pull/1002>`__)
- [watchmedo] Remove execution rights from ``watchmedo.py``
- Thanks to our beloved contributors: @BoboTiG, @nbelakovski, @ivg

4.0.1
~~~~~

2024-05-23 • `full history <https://github.com/gorakhargosh/watchdog/compare/v4.0.0...v4.0.1>`__

- [inotify] Fix missing ``event_filter`` for the full emitter (`#1032 <https://github.com/gorakhargosh/watchdog/pull/1032>`__)
- Thanks to our beloved contributors: @mraspaud, @BoboTiG

4.0.0
~~~~~

2024-02-06 • `full history <https://github.com/gorakhargosh/watchdog/compare/v3.0.0...v4.0.0>`__

- Drop support for Python 3.7.
- Add support for Python 3.12.
- [snapshot] Add typing to ``dirsnapshot`` (`#1012 <https://github.com/gorakhargosh/watchdog/pull/1012>`__)
- [snapshot] Added ``DirectorySnapshotDiff.ContextManager`` (`#1011 <https://github.com/gorakhargosh/watchdog/pull/1011>`__)
- [events] ``FileSystemEvent``, and subclasses, are now ``dataclass``es, and their ``repr()`` has changed
- [windows] ``WinAPINativeEvent`` is now a ``dataclass``, and its ``repr()`` has changed
- [events] Log ``FileOpenedEvent``, and ``FileClosedEvent``, events in ``LoggingEventHandler``
- [tests] Improve ``FileSystemEvent`` coverage
- [watchmedo] Log all events in ``LoggerTrick``
- [windows] The ``observers.read_directory_changes.WATCHDOG_TRAVERSE_MOVED_DIR_DELAY`` hack was removed. The constant will be kept to prevent breaking other softwares.
- Thanks to our beloved contributors: @BoboTiG, @msabramo

3.0.0
~~~~~

2023-03-20 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.3.1...v3.0.0>`__

- Drop support for Python 3.6.
- ``watchdog`` is now PEP 561 compatible, and tested with ``mypy``
- Fix missing ``>`` in ``FileSystemEvent.__repr__()``  (`#980 <https://github.com/gorakhargosh/watchdog/pull/980>`__)
- [ci] Lots of improvements
- [inotify] Return from ``InotifyEmitter.queue_events()`` if not launched when thread is inactive (`#963 <https://github.com/gorakhargosh/watchdog/pull/963>`__)
- [tests] Stability improvements
- [utils] Remove handling of ``threading.Event.isSet`` spelling (`#962 <https://github.com/gorakhargosh/watchdog/pull/962>`__)
- [watchmedo] Fixed tricks YAML generation (`#965 <https://github.com/gorakhargosh/watchdog/pull/965>`__)
- Thanks to our beloved contributors: @kurtmckee, @altendky, @agroszer, @BoboTiG

2.3.1
~~~~~

2023-02-28 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.3.0...v2.3.1>`__

- Run ``black`` on the entire source code
- Bundle the ``requirements-tests.txt`` file in the source distribution (`#939 <https://github.com/gorakhargosh/watchdog/pull/939>`__)
- [watchmedo] Exclude ``FileOpenedEvent`` events from ``AutoRestartTrick``, and ``ShellCommandTrick``, to restore watchdog < 2.3.0 behavior. A better solution should be found in the future. (`#949 <https://github.com/gorakhargosh/watchdog/pull/949>`__)
- [watchmedo] Log ``FileOpenedEvent``, and ``FileClosedEvent``, events in ``LoggerTrick``
- Thanks to our beloved contributors: @BoboTiG

2.3.0
~~~~~

2023-02-23 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.2.1...v2.3.0>`__

- [inotify] Add support for ``IN_OPEN`` events: a ``FileOpenedEvent`` event will be fired (`#941 <https://github.com/gorakhargosh/watchdog/pull/941>`__)
- [watchmedo] Add optional event debouncing for ``auto-restart``, only restarting once if many events happen in quick succession (``--debounce-interval``) (`#940 <https://github.com/gorakhargosh/watchdog/pull/940>`__)
- [watchmedo] Exit gracefully on ``KeyboardInterrupt`` exception (Ctrl+C) (`#945 <https://github.com/gorakhargosh/watchdog/pull/945>`__)
- [watchmedo] Add option to not auto-restart the command after it exits (``--no-restart-on-command-exit``) (`#946 <https://github.com/gorakhargosh/watchdog/pull/946>`__)
- Thanks to our beloved contributors: @BoboTiG, @dstaple, @taleinat, @cernekj

2.2.1
~~~~~

2023-01-01 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.2.0...v2.2.1>`__

- Enable ``mypy`` to discover type hints as specified in PEP 561 (`#933 <https://github.com/gorakhargosh/watchdog/pull/933>`__)
- [ci] Set the expected Python version when building release files
- [ci] Update actions versions in use
- [watchmedo] [regression] Fix usage of missing ``signal.SIGHUP`` attribute on non-Unix OSes (`#935 <https://github.com/gorakhargosh/watchdog/pull/935>`__)
- Thanks to our beloved contributors: @BoboTiG, @simon04, @piotrpdev

2.2.0
~~~~~

2022-12-05 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.9...v2.2.0>`__

- [build] Wheels are now available for Python 3.11 (`#932 <https://github.com/gorakhargosh/watchdog/pull/932>`__)
- [documentation] HTML documentation builds are now tested for errors (`#902 <https://github.com/gorakhargosh/watchdog/pull/902>`__)
- [documentation] Fix typos here, and there (`#910 <https://github.com/gorakhargosh/watchdog/pull/910>`__)
- [fsevents2] The ``fsevents2`` observer is now deprecated (`#909 <https://github.com/gorakhargosh/watchdog/pull/909>`__)
- [tests] The error message returned by musl libc for error code ``-1`` is now allowed (`#923 <https://github.com/gorakhargosh/watchdog/pull/923>`__)
- [utils] Remove unnecessary code in ``dirsnapshot.py`` (`#930 <https://github.com/gorakhargosh/watchdog/pull/930>`__)
- [watchmedo] Handle shutdown events from ``SIGHUP`` (`#912 <https://github.com/gorakhargosh/watchdog/pull/912>`__)
- Thanks to our beloved contributors: @kurtmckee, @babymastodon, @QuantumEnergyE, @timgates42, @BoboTiG

2.1.9
~~~~~

2022-06-10 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.8...v2.1.9>`__

- [fsevents] Fix flakey test to assert that there are no errors when stopping the emitter.
- [inotify] Suppress occasional ``OSError: [Errno 9] Bad file descriptor`` at shutdown. (`#805 <https://github.com/gorakhargosh/watchdog/issues/805>`__)
- [watchmedo] Make ``auto-restart`` restart the sub-process if it terminates. (`#896 <https://github.com/gorakhargosh/watchdog/pull/896>`__)
- [watchmedo] Avoid zombie sub-processes when running ``shell-command`` without ``--wait``. (`#405 <https://github.com/gorakhargosh/watchdog/issues/405>`__)
- Thanks to our beloved contributors: @samschott, @taleinat, @altendky, @BoboTiG

2.1.8
~~~~~

2022-05-15 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.7...v2.1.8>`__

- Fix adding failed emitters on observer schedule. (`#872 <https://github.com/gorakhargosh/watchdog/issues/872>`__)
- [inotify] Fix hang when unscheduling watch on a path in an unmounted filesystem. (`#869 <https://github.com/gorakhargosh/watchdog/pull/869>`__)
- [watchmedo] Fix broken parsing of ``--kill-after`` argument for the ``auto-restart`` command. (`#870 <https://github.com/gorakhargosh/watchdog/issues/870>`__)
- [watchmedo] Fix broken parsing of boolean arguments. (`#887 <https://github.com/gorakhargosh/watchdog/issues/887>`__)
- [watchmedo] Fix broken parsing of commands from ``auto-restart``, and ``shell-command``. (`#888 <https://github.com/gorakhargosh/watchdog/issues/888>`__)
- [watchmedo] Support setting verbosity level via ``-q/--quiet`` and ``-v/--verbose`` arguments. (`#889 <https://github.com/gorakhargosh/watchdog/pull/889>`__)
- Thanks to our beloved contributors: @taleinat, @kianmeng, @palfrey, @IlayRosenberg, @BoboTiG

2.1.7
~~~~~

2022-03-25 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.6...v2.1.7>`__

- Eliminate timeout in waiting on event queue. (`#861 <https://github.com/gorakhargosh/watchdog/pull/861>`__)
- [inotify] Fix ``not`` equality implementation for ``InotifyEvent``. (`#848 <https://github.com/gorakhargosh/watchdog/pull/848>`__)
- [watchmedo] Fix calling commands from within a Python script. (`#879 <https://github.com/gorakhargosh/watchdog/pull/879>`__)
- [watchmedo] ``PyYAML`` is loaded only when strictly necessary. Simple usages of ``watchmedo`` are possible without the module being installed. (`#847 <https://github.com/gorakhargosh/watchdog/pull/847>`__)
- Thanks to our beloved contributors: @sattlerc, @JanzenLiu, @BoboTiG

2.1.6
~~~~~

2021-10-01 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.5...v2.1.6>`__

- [bsd] Fixed returned paths in ``kqueue.py`` and restored the overall results of the test suite. (`#842 <https://github.com/gorakhargosh/watchdog/pull/842>`__)
- [bsd] Updated FreeBSD CI support .(`#841 <https://github.com/gorakhargosh/watchdog/pull/841>`__)
- [watchmedo] Removed the ``argh`` dependency in favor of the builtin ``argparse`` module. (`#836 <https://github.com/gorakhargosh/watchdog/pull/836>`__)
- [watchmedo] Removed unexistant ``WindowsApiAsyncObserver`` references and ``--debug-force-winapi-async`` arguments.
- [watchmedo] Improved the help output.
- Thanks to our beloved contributors: @knobix, @AndreaRe9, @BoboTiG

2.1.5
~~~~~

2021-08-23 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.4...v2.1.5>`__

- Fix regression introduced in 2.1.4 (reverted "Allow overriding or adding custom event handlers to event dispatch map. (`#814 <https://github.com/gorakhargosh/watchdog/pull/814>`__)"). (`#830 <https://github.com/gorakhargosh/watchdog/pull/830>`__)
- Convert regexes of type ``str`` to ``list``. (`831 <https://github.com/gorakhargosh/watchdog/pull/831>`__)
- Thanks to our beloved contributors: @unique1o1, @BoboTiG

2.1.4
~~~~~

2021-08-19 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.3...v2.1.4>`__

- [watchmedo] Fix usage of ``os.setsid()`` and ``os.killpg()`` Unix-only functions. (`#809 <https://github.com/gorakhargosh/watchdog/pull/809>`__)
- [mac] Fix missing ``FileModifiedEvent`` on permission or ownership changes of a file. (`#815 <https://github.com/gorakhargosh/watchdog/pull/815>`__)
- [mac] Convert absolute watch path in ``FSEeventsEmitter`` with ``os.path.realpath()``. (`#822 <https://github.com/gorakhargosh/watchdog/pull/822>`__)
- Fix a possible ``AttributeError`` in ``SkipRepeatsQueue._put()``. (`#818 <https://github.com/gorakhargosh/watchdog/pull/818>`__)
- Allow overriding or adding custom event handlers to event dispatch map. (`#814 <https://github.com/gorakhargosh/watchdog/pull/814>`__)
- Fix tests on big endian platforms. (`#828 <https://github.com/gorakhargosh/watchdog/pull/828>`__)
- Thanks to our beloved contributors: @replabrobin, @BoboTiG, @SamSchott, @AndreiB97, @NiklasRosenstein, @ikokollari, @mgorny

2.1.3
~~~~~

2021-06-26 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.2...v2.1.3>`__

- Publish macOS ``arm64`` and ``universal2`` wheels. (`#740 <https://github.com/gorakhargosh/watchdog/pull/740>`__)
- Thanks to our beloved contributors: @kainjow, @BoboTiG

2.1.2
~~~~~

2021-05-19 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.1...v2.1.2>`__

- [mac] Fix relative path handling for non-recursive watch. (`#797 <https://github.com/gorakhargosh/watchdog/pull/797>`__)
- [windows] On PyPy, events happening right after ``start()`` were missed. Add a workaround for that. (`#796 <https://github.com/gorakhargosh/watchdog/pull/796>`__)
- Thanks to our beloved contributors: @oprypin, @CCP-Aporia, @BoboTiG

2.1.1
~~~~~

2021-05-10 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.1.0...v2.1.1>`__

- [mac] Fix callback exceptions when the watcher is deleted but still receiving events (`#786 <https://github.com/gorakhargosh/watchdog/pull/786>`__)
- Thanks to our beloved contributors: @rom1win, @BoboTiG, @CCP-Aporia


2.1.0
~~~~~

2021-05-04 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.0.3...v2.1.0>`__

- [inotify] Simplify ``libc`` loading (`#776 <https://github.com/gorakhargosh/watchdog/pull/776>`__)
- [mac] Add support for non-recursive watches in ``FSEventsEmitter`` (`#779 <https://github.com/gorakhargosh/watchdog/pull/779>`__)
- [watchmedo] Add support for ``--debug-force-*`` arguments to ``tricks`` (`#781 <https://github.com/gorakhargosh/watchdog/pull/781>`__)
- Thanks to our beloved contributors: @CCP-Aporia, @aodj, @UnitedMarsupials, @BoboTiG


2.0.3
~~~~~

2021-04-22 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.0.2...v2.0.3>`__

- [mac] Use ``logger.debug()`` instead of ``logger.info()`` (`#774 <https://github.com/gorakhargosh/watchdog/pull/774>`__)
- Updated documentation links (`#777 <https://github.com/gorakhargosh/watchdog/pull/777>`__)
- Thanks to our beloved contributors: @globau, @imba-tjd, @BoboTiG


2.0.2
~~~~~

2021-02-22 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.0.1...v2.0.2>`__

- [mac] Add missing exception objects (`#766 <https://github.com/gorakhargosh/watchdog/pull/766>`__)
- Thanks to our beloved contributors: @CCP-Aporia, @BoboTiG


2.0.1
~~~~~

2021-02-17 • `full history <https://github.com/gorakhargosh/watchdog/compare/v2.0.0...v2.0.1>`__

- [mac] Fix a segmentation fault when dealing with unicode paths (`#763 <https://github.com/gorakhargosh/watchdog/pull/763>`__)
- Moved the CI from Travis-CI to GitHub Actions (`#764 <https://github.com/gorakhargosh/watchdog/pull/764>`__)
- Thanks to our beloved contributors: @SamSchott, @BoboTiG


2.0.0
~~~~~

2021-02-11 • `full history <https://github.com/gorakhargosh/watchdog/compare/v1.0.2...v2.0.0>`__

- Avoid deprecated ``PyEval_InitThreads`` on Python 3.7+ (`#746 <https://github.com/gorakhargosh/watchdog/pull/746>`__)
- [inotify] Add support for ``IN_CLOSE_WRITE`` events. A ``FileCloseEvent`` event will be fired. Note that ``IN_CLOSE_NOWRITE`` events are not handled to prevent much noise. (`#184 <https://github.com/gorakhargosh/watchdog/pull/184>`__, `#245 <https://github.com/gorakhargosh/watchdog/pull/245>`__, `#280 <https://github.com/gorakhargosh/watchdog/pull/280>`__, `#313 <https://github.com/gorakhargosh/watchdog/pull/313>`__, `#690 <https://github.com/gorakhargosh/watchdog/pull/690>`__)
- [inotify] Allow to stop the emitter multiple times (`#760 <https://github.com/gorakhargosh/watchdog/pull/760>`__)
- [mac] Support coalesced filesystem events (`#734 <https://github.com/gorakhargosh/watchdog/pull/734>`__)
- [mac] Drop support for macOS 10.12 and earlier (`#750 <https://github.com/gorakhargosh/watchdog/pull/750>`__)
- [mac] Fix an issue when renaming an item changes only the casing (`#750 <https://github.com/gorakhargosh/watchdog/pull/750>`__)
- Thanks to our beloved contributors: @bstaletic, @lukassup, @ysard, @SamSchott, @CCP-Aporia, @BoboTiG


1.0.2
~~~~~

2020-12-18 • `full history <https://github.com/gorakhargosh/watchdog/compare/v1.0.1...v1.0.2>`__

- Wheels are published for GNU/Linux, macOS and Windows (`#739 <https://github.com/gorakhargosh/watchdog/pull/739>`__)
- [mac] Fix missing ``event_id`` attribute in ``fsevents`` (`#721 <https://github.com/gorakhargosh/watchdog/pull/721>`__)
- [mac] Return byte paths if a byte path was given in ``fsevents`` (`#726 <https://github.com/gorakhargosh/watchdog/pull/726>`__)
- [mac] Add compatibility with old macOS versions (`#733 <https://github.com/gorakhargosh/watchdog/pull/733>`__)
- Uniformize event for deletion of watched dir (`#727 <https://github.com/gorakhargosh/watchdog/pull/727>`__)
- Thanks to our beloved contributors: @SamSchott, @CCP-Aporia, @di, @BoboTiG


1.0.1
~~~~~

2020-12-10 • Fix version with good metadatas.


1.0.0
~~~~~

2020-12-10 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.10.4...v1.0.0>`__

- Versioning is now following the `semver <https://semver.org/>`__
- Drop support for Python 2.7, 3.4 and 3.5
- [mac] Regression fixes for native ``fsevents`` (`#717 <https://github.com/gorakhargosh/watchdog/pull/717>`__)
- [windows] ``winapi.BUFFER_SIZE`` now defaults to ``64000`` (instead of ``2048``) (`#700 <https://github.com/gorakhargosh/watchdog/pull/700>`__)
- [windows] Introduced ``winapi.PATH_BUFFER_SIZE`` (defaults to ``2048``) to keep the old behavior with path-realted functions (`#700 <https://github.com/gorakhargosh/watchdog/pull/700>`__)
- Use ``pathlib`` from the standard library, instead of pathtools (`#556 <https://github.com/gorakhargosh/watchdog/pull/556>`__)
- Allow file paths on Unix that don't follow the file system encoding (`#703 <https://github.com/gorakhargosh/watchdog/pull/703>`__)
- Removed the long-time deprecated ``events.LoggingFileSystemEventHandler`` class, use ``LoggingEventHandler`` instead
- Thanks to our beloved contributors: @SamSchott, @bstaletic, @BoboTiG, @CCP-Aporia


0.10.4
~~~~~~

2020-11-21 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.10.3...v0.10.4>`__

- Add ``logger`` parameter for the ``LoggingEventHandler`` (`#676 <https://github.com/gorakhargosh/watchdog/pull/676>`__)
- Replace mutable default arguments with ``if None`` implementation (`#677 <https://github.com/gorakhargosh/watchdog/pull/677>`__)
- Expand tests to Python 2.7 and 3.5-3.10 for GNU/Linux, macOS and Windows
- [mac] Performance improvements for the ``fsevents`` module (`#680 <https://github.com/gorakhargosh/watchdog/pull/680>`__)
- [mac] Prevent compilation of ``watchdog_fsevents.c`` on non-macOS machines (`#687 <https://github.com/gorakhargosh/watchdog/pull/687>`__)
- [watchmedo] Handle shutdown events from ``SIGTERM`` and ``SIGINT`` more reliably (`#693 <https://github.com/gorakhargosh/watchdog/pull/693>`__)
- Thanks to our beloved contributors: @Sraw, @CCP-Aporia, @BoboTiG, @maybe-sybr


0.10.3
~~~~~~

2020-06-25 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.10.2...v0.10.3>`__

- Ensure ``ObservedWatch.path`` is a string (`#651 <https://github.com/gorakhargosh/watchdog/pull/651>`__)
- [inotify] Allow to monitor single file (`#655 <https://github.com/gorakhargosh/watchdog/pull/655>`__)
- [inotify] Prevent raising an exception when a file in a monitored folder has no permissions (`#669 <https://github.com/gorakhargosh/watchdog/pull/669>`__, `#670 <https://github.com/gorakhargosh/watchdog/pull/670>`__)
- Thanks to our beloved contributors: @brant-ruan, @rec, @andfoy, @BoboTiG


0.10.2
~~~~~~

2020-02-08 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.10.1...v0.10.2>`__

- Fixed the ``build_ext`` command on macOS Catalina (`#628 <https://github.com/gorakhargosh/watchdog/pull/628>`__)
- Fixed the installation of macOS requirements on non-macOS OSes (`#635 <https://github.com/gorakhargosh/watchdog/pull/635>`__)
- Refactored ``dispatch()`` method of ``FileSystemEventHandler``,
  ``PatternMatchingEventHandler`` and ``RegexMatchingEventHandler``
- [bsd] Improved tests support on non Windows/Linux platforms (`#633 <https://github.com/gorakhargosh/watchdog/pull/633>`__, `#639 <https://github.com/gorakhargosh/watchdog/pull/639>`__)
- [bsd] Added FreeBSD CI support (`#532 <https://github.com/gorakhargosh/watchdog/pull/532>`__)
- [bsd] Restored full support (`#638 <https://github.com/gorakhargosh/watchdog/pull/638>`__, `#641 <https://github.com/gorakhargosh/watchdog/pull/641>`__)
- Thanks to our beloved contributors: @BoboTiG, @evilham, @danilobellini


0.10.1
~~~~~~

2020-01-30 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.10.0...v0.10.1>`__

- Fixed Python 2.7 to 3.6 installation when the OS locale is set to POSIX (`#615 <https://github.com/gorakhargosh/watchdog/pull/615>`__)
- Fixed the ``build_ext`` command on macOS  (`#618 <https://github.com/gorakhargosh/watchdog/pull/618>`__, `#620 <https://github.com/gorakhargosh/watchdog/pull/620>`__)
- Moved requirements to ``setup.cfg``  (`#617 <https://github.com/gorakhargosh/watchdog/pull/617>`__)
- [mac] Removed old C code for Python 2.5 in the `fsevents` C implementation
- [snapshot] Added ``EmptyDirectorySnapshot`` (`#613 <https://github.com/gorakhargosh/watchdog/pull/613>`__)
- Thanks to our beloved contributors: @Ajordat, @tehkirill, @BoboTiG


0.10.0
~~~~~~

2020-01-26 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.9.0...v0.10.0>`__

**Breaking Changes**

- Dropped support for Python 2.6, 3.2 and 3.3
- Emitters that failed to start are now removed
- [snapshot] Removed the deprecated ``walker_callback`` argument,
  use ``stat`` instead
- [watchmedo] The utility is no more installed by default but via the extra
  ``watchdog[watchmedo]``

**Other Changes**

- Fixed several Python 3 warnings
- Identify synthesized events with ``is_synthetic`` attribute (`#369 <https://github.com/gorakhargosh/watchdog/pull/369>`__)
- Use ``os.scandir()`` to improve memory usage (`#503 <https://github.com/gorakhargosh/watchdog/pull/503>`__)
- [bsd] Fixed flavors of FreeBSD detection (`#529 <https://github.com/gorakhargosh/watchdog/pull/529>`__)
- [bsd] Skip unprocessable socket files (`#509 <https://github.com/gorakhargosh/watchdog/issue/509>`__)
- [inotify] Fixed events containing non-ASCII characters (`#516 <https://github.com/gorakhargosh/watchdog/issues/516>`__)
- [inotify] Fixed the way ``OSError`` are re-raised (`#377 <https://github.com/gorakhargosh/watchdog/issues/377>`__)
- [inotify] Fixed wrong source path after renaming a top level folder (`#515 <https://github.com/gorakhargosh/watchdog/pull/515>`__)
- [inotify] Removed  delay from non-move events (`#477 <https://github.com/gorakhargosh/watchdog/pull/477>`__)
- [mac] Fixed a bug when calling ``FSEventsEmitter.stop()`` twice (`#466 <https://github.com/gorakhargosh/watchdog/pull/466>`__)
- [mac] Support for unscheduling deleted watch (`#541 <https://github.com/gorakhargosh/watchdog/issue/541>`__)
- [mac] Fixed missing field initializers and unused parameters in
  ``watchdog_fsevents.c``
- [snapshot] Don't walk directories without read permissions (`#408 <https://github.com/gorakhargosh/watchdog/pull/408>`__)
- [snapshot] Fixed a race condition crash when a directory is swapped for a file (`#513 <https://github.com/gorakhargosh/watchdog/pull/513>`__)
- [snasphot] Fixed an ``AttributeError`` about forgotten ``path_for_inode`` attr (`#436 <https://github.com/gorakhargosh/watchdog/issues/436>`__)
- [snasphot] Added the ``ignore_device=False`` parameter to the ctor (`597 <https://github.com/gorakhargosh/watchdog/pull/597>`__)
- [watchmedo] Fixed the path separator used (`#478 <https://github.com/gorakhargosh/watchdog/pull/478>`__)
- [watchmedo] Fixed the use of ``yaml.load()`` for ``yaml.safe_load()`` (`#453 <https://github.com/gorakhargosh/watchdog/issues/453>`__)
- [watchmedo] Handle all available signals (`#549 <https://github.com/gorakhargosh/watchdog/issue/549>`__)
- [watchmedo] Added the ``--debug-force-polling`` argument (`#404 <https://github.com/gorakhargosh/watchdog/pull/404>`__)
- [windows] Fixed issues when the observed directory is deleted (`#570 <https://github.com/gorakhargosh/watchdog/issues/570>`__ and `#601 <https://github.com/gorakhargosh/watchdog/pull/601>`__)
- [windows] ``WindowsApiEmitter`` made easier to subclass (`#344 <https://github.com/gorakhargosh/watchdog/pull/344>`__)
- [windows] Use separate ctypes DLL instances
- [windows] Generate sub created events only if ``recursive=True`` (`#454 <https://github.com/gorakhargosh/watchdog/pull/454>`__)
- Thanks to our beloved contributors: @BoboTiG, @LKleinNux, @rrzaripov,
  @wildmichael, @TauPan, @segevfiner, @petrblahos, @QuantumEnergyE,
  @jeffwidman, @kapsh, @nickoala, @petrblahos, @julianolf, @tonybaloney,
  @mbakiev, @pR0Ps, javaguirre, @skurfer, @exarkun, @joshuaskelly,
  @danilobellini, @Ajordat


0.9.0
~~~~~

2018-08-28 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.3...v0.9.0>`__

- Deleting the observed directory now emits a ``DirDeletedEvent`` event
- [bsd] Improved the platform detection (`#378 <https://github.com/gorakhargosh/watchdog/pull/378>`__)
- [inotify] Fixed a crash when the root directory being watched by was deleted (`#374 <https://github.com/gorakhargosh/watchdog/pull/374>`__)
- [inotify] Handle systems providing uClibc
- [linux] Fixed a possible ``DirDeletedEvent`` duplication when
  deleting a directory
- [mac] Fixed unicode path handling ``fsevents2.py`` (`#298 <https://github.com/gorakhargosh/watchdog/pull/298>`__)
- [watchmedo] Added the ``--debug-force-polling`` argument (`#336 <https://github.com/gorakhargosh/watchdog/pull/336>`__)
- [windows] Fixed the ``FILE_LIST_DIRECTORY`` constant (`#376 <https://github.com/gorakhargosh/watchdog/pull/376>`__)
- Thanks to our beloved contributors: @vulpeszerda, @hpk42, @tamland, @senden9,
  @gorakhargosh, @nolsto, @mafrosis, @DonyorM, @anthrotype, @danilobellini,
  @pierregr, @ShinNoNoir, @adrpar, @gforcada, @pR0Ps, @yegorich, @dhke


0.8.3
~~~~~

2015-02-11 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.2...v0.8.3>`__

- Fixed the use of the root logger (`#274 <https://github.com/gorakhargosh/watchdog/issues/274>`__)
- [inotify] Refactored libc loading and improved error handling in
  ``inotify_c.py``
- [inotify] Fixed a possible unbound local error in ``inotify_c.py``
- Thanks to our beloved contributors: @mmorearty, @tamland, @tony,
  @gorakhargosh


0.8.2
~~~~~

2014-10-29 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.1...v0.8.2>`__

- Event emitters are no longer started on schedule if ``Observer`` is not
  already running
- [mac] Fixed usued arguments to pass clang compilation (`#265 <https://github.com/gorakhargosh/watchdog/pull/265>`__)
- [snapshot] Fixed a possible race condition crash on directory deletion (`#281 <https://github.com/gorakhargosh/watchdog/pull/281>`__)
- [windows] Fixed an error when watching the same folder again (`#270 <https://github.com/gorakhargosh/watchdog/pull/270>`__)
- Thanks to our beloved contributors: @tamland, @apetrone, @Falldog,
  @theospears


0.8.1
~~~~~

2014-07-28 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.8.0...v0.8.1>`__

- Fixed ``anon_inode`` descriptors leakage  (`#249 <https://github.com/gorakhargosh/watchdog/pull/249>`__)
- [inotify] Fixed thread stop dead lock (`#250 <https://github.com/gorakhargosh/watchdog/issues/250>`__)
- Thanks to our beloved contributors: @Witos, @adiroiban, @tamland


0.8.0
~~~~~

2014-07-02 • `full history <https://github.com/gorakhargosh/watchdog/compare/v0.7.1...v0.8.0>`__

- Fixed ``argh`` deprecation warnings (`#242 <https://github.com/gorakhargosh/watchdog/pull/242>`__)
- [snapshot] Methods returning internal stats info were replaced by
  ``mtime()``, ``inode()`` and ``path()`` methods
- [snapshot] Deprecated the ``walker_callback`` argument
- [watchmedo] Fixed ``auto-restart`` to terminate all children processes (`#225 <https://github.com/gorakhargosh/watchdog/pull/225>`__)
- [watchmedo] Added the ``--no-parallel`` argument (`#227 <https://github.com/gorakhargosh/watchdog/issues/227>`__)
- [windows] Fixed the value of ``INVALID_HANDLE_VALUE`` (`#123 <https://github.com/gorakhargosh/watchdog/issues/123>`__)
- [windows] Fixed octal usages to work with Python 3 as well (`#223 <https://github.com/gorakhargosh/watchdog/issues/223>`__)
- Thanks to our beloved contributors: @tamland, @Ormod, @berdario, @cro,
  @BernieSumption, @pypingou, @gotcha, @tommorris, @frewsxcv
