# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/).

## Unreleased
### Added
- `reaper-get-entry`, `reaper-entry-id`, `reaper-entry-project-id`,
  `reaper-entry-project`, `reaper-entry-task-id`, `reaper-entry-task`,
  `reaper-entry-is-running`, `reaper-entry-hours` and
  `reaper-entry-notes` macros to handle time entries.
- `reaper-with-selected-timer` for working with the timer at point.
- `reaper-get-project`, `reaper-get-head-project`,
  `reaper-project-id`, `reaper-project-code`, `reaper-project-name`
  and `reaper-project-tasks` for working with projects.
- `reaper-autofile-functions` for automatically set project and/or
  task depending on notes. Implementations should return a cons of
  project id and task id.
- `reaper-insert-project-id` and `reaper-insert-task-id`, for easy
  insertion of project and task ids.

### Changed
- Use `(goto-char (point-min))` instead of `(beginning-of-buffer)`.
- Ask for notes first when starting new timer, in order to support
  `reaper-autofile-functions`.

## 1.3.0 - 2022-04-11
### Added
- `e d` to edit entry description.
- `e t` to edit entry task.
- `e p` to edit entry project.
- Simple calculations in time entry.
- `reaper-get-running-timer-note` for getting note of running timer.
- `!` to clear project/task cache.

### Changed
- `reaper-edit-entry` moved from `e` to `e e`.

### Fixed
- Current running timer indicator not showing up if point is after the
  running timer.

## 1.2.1 - 2020-11-14
### Fixed
- Fix `reaper-goto-date`.

## 1.2.0 - 2020-11-14
### Added
- Display total daily time.
- Add `f`/`b` to go back/forwards a day.

## 1.1.0 - 2019-09-21
### Added
- `reaper-start-timer-and-quit-window`.
- Autoload `reaper`.
- Sort projects/tasks in last used order when using ivy.

### Changed
- Starting new timer now defaults to last used project and task.
- RET now closes the window after starting timer.
- SPC start tracking on entry at point.

### Fixed
- Editing an entry fetches project/tasks first, if not already
  fetched.
- Compatibility with `display-line-numbers-mode`.
- Use a `kill-buffer-hook` to cancel timer.
- Make point stick around when deleting entries.

## 1.0.0 - 2019-08-28
### Added
- Initial implementation.
