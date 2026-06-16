# DTLonCodex

French documentation for OpenAI Codex, prepared in the DEC/VSI spirit and presented with the NetDTL visual identity.

This repository brings together a user guide, a reference manual, and a complete HTML version to help understand, use, and frame Codex for software development work.

## Available Documents

- [Complete documentation](OpenAI_Codex_Documentation_NetDTL.html): single-page HTML version, with navigation and search.
- [Reference manual](https://www.netdtl.com/doc/DTLonCodex_Reference_Manual.html): functional description of Codex surfaces, objects, mechanisms, and capabilities.
- [User guide](https://www.netdtl.com/doc/DTLonCodex_User_Guide.html): practical instructions for getting started, guiding Codex, checking results, and handling common scenarios.

## What This Documentation Is For

DTLonCodex helps answer three questions:

1. What features does Codex provide?
2. Which surface should be used depending on the need: App, CLI, IDE extension, Web, or Cloud?
3. How should a Codex task be phrased, monitored, verified, and finalized?

The reference manual describes durable concepts: execution surfaces, models, context, tools, Git, integrated terminal, integrated browser, customization, permissions, sandboxing, automations, MCP, skills, plugins, hooks, and subagents.

The user guide turns these concepts into procedures: preparing a project, writing a request, choosing a work mode, reviewing a diff, running tests, correcting course, adding durable instructions, or setting up an automation.

## Recommended Reading

To discover Codex, start with the user guide:

1. Choose the appropriate surface.
2. Prepare the project and Git state.
3. Write a short, bounded, verifiable request.
4. Follow the work, commands, and approvals.
5. Review the diff and run the checks.

To administer or document a Codex usage pattern, use the reference manual instead:

1. Identify the available surfaces and modes.
2. Understand the reference objects: project, thread, worktree, chat, skill, plugin, MCP server, hook, automation.
3. Define configuration, permission, and sandboxing rules.
4. Choose the required customization or integration mechanisms.

## Operational Summary

Before assigning a task to Codex:

- open the correct project folder;
- check the Git state;
- state the objective, constraints, and affected files;
- specify the expected tests or evidence;
- explicitly limit refactoring when the change should remain minimal.

During the work:

- watch which files are read and modified;
- redirect Codex if the scope drifts;
- grant permissions with the narrowest reasonable scope;
- ask for analysis before a fix when the cause of a problem is unclear.

Before finalizing:

- read the summary;
- review the diff;
- run the relevant tests;
- check that no unrelated file was modified;
- document remaining limits or risks.

## Covered Scenarios

The documentation covers, among other things:

- understanding an unfamiliar codebase;
- fixing a bug with a minimal change;
- adding a small feature;
- reviewing a pull request;
- working on a web interface with the integrated browser;
- producing a document or artifact;
- setting up an automation;
- adding an external integration;
- cleaning up after a task;
- writing durable instructions in `AGENTS.md`.

## Customization and Security

Codex can be guided by project instructions, `AGENTS.md` files, skills, plugins, MCP servers, hooks, and automations.

Operations remain governed by permissions, approvals, sandboxing, network access, and the policies of the organization or local environment. Requests should therefore specify file limits, authorized commands, and expected checks when the context is sensitive.

## Sources

This README is translated from `README_Fr.md`, which was synthesized from:

- `OpenAI_Codex_Ref_Man_FR.md`
- `OpenAI_Codex_UG_FR.md`
- `DTLonCodex_Manuel_de_reference.html`
- `DTLonCodex_Guide_utilisateur.html`

The documents themselves list the main sources as the OpenAI Developers pages for Codex Overview, Codex Quickstart, Codex App features, Codex CLI features, Codex customization, and the documentation related to configuration, permissions, sandboxing, MCP, skills, and automation.
