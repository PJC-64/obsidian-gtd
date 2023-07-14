# Obsidian Project Management Starter Kit
> A thousand miles journey is started by taking the first step.

This is a clone of duoani/obsidian-gtd with updates to handle breaking changes in Dataview.

This codebase is released under the GPL V3.0

This is the workflow to manage scheduled tasks in Obsidian. The [obsidian-dataview](https://blacksmithgu.github.io/obsidian-dataview/docs/intro) plugin is required to list projects/actions automatically.

**Project View**
![project view](./images/project-view.png)

* `N/A` means there is no action in this project.
* `Blocked` means there is no *Active* action in this project. Telling that you shoud put some actions into active state.

**Action View**
![action view](./images/action-view.png)

**A project**
![project](./images/project.png)

**An action**
![action](./images/action.png)

**Archived Projects**
![archived projects](./images/archived-projects-and-actions.png)

## Features
- √ Project View: Show all projects in a view.
- √ Action Views: Show all actions in a view.
- √ Archive Projects and Actions: Making *Project View* and *Action Views* more focusable.
- √ Tag name customizable: If you don't like the tag below, you can rename them!
- √ Display the progress of action for an program
- √ Display progress of task for an action

First of all, this is **NOT** a fully implemented GTD system, but a project management system. It manages your projects, project-related actions (like "Tasks" in GTD), and simple actions (actions do not belong to any project.)

```
- Project A
	- Project-related Action 1
	- project-related Action 2
- Project B
	- Project-related Action 3
- Simple Action 1
- Simple Action 2
```

## Projects are stored in markdown files

In this workflow, an `.md` file containing a `#project` tag represents a project.

There are also some properties stored as [Inline Fields](https://blacksmithgu.github.io/obsidian-dataview/docs/where-data-comes-from) which are used in a project file.

- `start_date::`：The date when this project has been started.
- `end_date::`: The date when this project is finished.
- `state::`: [Obsidian Nested tags](https://help.obsidian.md/Plugins/Tag+pane#Nested+tags) are used to manage the states of a project. The available tags are as follows:
	1. `#project/active`: when a project is active it has this state.
	2. `#project/archived`: when a project is completed it has this state.

## Actions are also markdown files

Actions are different from tasks `- [ ]` being stored in an `.md` file containing the `#action` tag.

Actions also contain some inline fields:

- `project::`: If an action contains this inline field, it's an project-related action. The value of this field *SHOULD* be an [Internal link](https://help.obsidian.md/How+to/Internal+link) to the project. If the value is not given, then this is a simple action.
- `due_date::`: The due date of this action.
- `start_date::`: The start date of this action.
- `end_date::`: The completion date of this action.
- `priority::`: A > B > C, or 1 > 2 > 3.
- `state::`: Just like the `state` field in a project, all action states are as follows:
	1. `#action/active`: when this action is active.
	2. `#action/waiting`: when this action relies on another action or is awaiting someone's response.
	3. `#action/done`: when this action is finished. The `end_date` should be updated to the current date.
	4. `#action/canceled`: when this action has been canceled (will not be completed).
	5. `#action/maybe`: when this action is optional.
	6. `#action/archived`: when this action no longer needs to be displayed.  This is also done for Single Actions.

## Priority

A > B > C > D ..., or 1 > 2 > 3 > 4 ... (using default sort method)

## About dataviewjs

`dataviewsjs` blocks are used instead of `dataview` blocks to allow Javascript code inside the block, which can do much complex actions than Dataview Query Language.

All JS code is stored in the `/tools/dv-script/` folder.

---
Thanks for the awesome plugin [obsidian-dataview](https://blacksmithgu.github.io/obsidian-dataview/docs/intro)!
