---
agent: agent
model: Claude Sonnet 4
description: 'Generate instructions for a subfolder in a repository'
---
Your task is to "onboard" this subfolder to Copilot coding agent by adding an AGENTS.md file in the subfolder that contains information describing how a coding agent seeing this subfolder for the first time can work most efficiently within its scope.

You will do this task only one time per subfolder and doing a good job can SIGNIFICANTLY improve the quality of the agent's work within this specific area, so take your time, think carefully, and search thoroughly before writing the instructions.

<Goals>
- Reduce the likelihood of a coding agent pull request getting rejected by the user due to
generating code that fails subfolder-specific validation, build processes, or
having misbehavior within this component.
- Minimize bash command and build failures when working within this subfolder.
- Allow the agent to complete its task more quickly by minimizing the need for exploration using grep, find, str_replace_editor, and code search tools within this subfolder's scope.
</Goals>

<Limitations>
- Instructions must be no longer than 2 pages.
- Instructions must not be task specific.
- Focus only on this subfolder's scope and responsibilities.
</Limitations>

<WhatToAdd>

Add the following high level details about this subfolder to reduce the amount of searching the agent has to do to understand the subfolder each time:
<HighLevelDetails>

- A summary of what this subfolder does and its role within the larger repository.
- High level subfolder information, such as the size, the type of components, the languages, frameworks, or target runtimes in use within this subfolder.
- How this subfolder relates to or depends on other parts of the repository.
</HighLevelDetails>

Add information about how to build and validate changes within this subfolder so the agent does not need to search and find it each time.
<BuildInstructions>

- For each of bootstrap, build, test, run, lint, and any other scripted step specific to this subfolder, document the sequence of steps to take to run it successfully as well as the versions of any runtime or build tools used.
- Document any commands that should be run from the repository root vs. within this subfolder.
- Each command should be validated by running it to ensure that it works correctly as well as any preconditions and postconditions.
- Try cleaning the subfolder environment and running commands in different orders and document errors and misbehavior observed as well as any steps used to mitigate the problem.
- Run subfolder-specific tests and document the order of steps required to run them.
- Make a change to code within this subfolder. Document any unexpected build issues as well as the workarounds.
- Document environment setup steps that seem optional but that you have validated are actually required for this subfolder.
- Document the time required for commands that failed due to timing out.
- When you find a sequence of commands that work for a particular purpose within this subfolder, document them in detail.
- Use language to indicate when something should always be done. For example: "always run npm install in the root before building this subfolder".
- Record any validation steps from documentation that apply to this subfolder.
</BuildInstructions>

List key facts about the layout and architecture of this subfolder to help the agent find where to make changes with minimal searching.
<SubfolderLayout>

- A description of the major architectural elements within this subfolder, including the relative paths to the main files, the location
of configuration files for linting, compilation, testing, and preferences specific to this subfolder.
- A description of the checks run prior to check in that are specific to this subfolder, including any workflows, builds, or validation pipelines that target this area.
- Document the steps so that the agent can replicate these itself within the subfolder scope.
- Any explicit validation steps that the agent can consider to have further confidence in changes made within this subfolder.
- Dependencies that aren't obvious from the subfolder layout or file structure, including dependencies on other parts of the repository.
- Finally, fill in any remaining space with detailed lists of the following, in order of priority: the list of files in this subfolder root, the
contents of any README specific to this subfolder, the contents of any key source files within this subfolder, the list of files in the next level down of directories within this subfolder, giving priority to the more structurally important files and snippets of code from key source files, such as entry points or main modules.
</SubfolderLayout>
</WhatToAdd>

<StepsToFollow>
- Perform a comprehensive inventory of this subfolder. Search for and view:
- README.md, CONTRIBUTING.md, and all other documentation files within this subfolder.
- Search this subfolder for build steps and indications of workarounds like 'HACK', 'TODO', etc.
- All scripts within this subfolder, particularly those pertaining to build and environment setup.
- All build and actions pipelines that specifically target this subfolder.
- All project files within this subfolder.
- All configuration and linting files within this subfolder.
- Key files in the repository root that affect this subfolder (e.g., package.json, .gitignore, CI configs).
- For each file:
- think: are the contents or the existence of the file information that the coding agent will need to implement, build, test, validate, or demo a code change within this subfolder?
- If yes:
   - Document the command or information in detail.
   - Explicitly indicate which commands work and which do not and the order in which commands should be run.
   - Note whether commands should be run from the repository root or from within this subfolder.
   - Document any errors encountered as well as the steps taken to workaround them.
- Document any other steps or information that the agent can use to reduce time spent exploring or trying and failing to run bash commands within this subfolder's scope.
- Finally, explicitly instruct the agent to trust the instructions and only perform a search if the information in the instructions is incomplete or found to be in error.
</StepsToFollow>
