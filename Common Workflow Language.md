---
aliases: ["CWL"]
---
CWL is a way to describe command-line tools and connect them together to create workflows. Because CWL is a specification and not a specific piece of software, tools and workflows described using CWL are portable across a variety of platforms that support the CWL standard.

CWL documents are written in [YAML](https://www.commonwl.org/user_guide/topics/index.html) (and/or JSON):
```yaml
# Every file starts with the CWL standard version, for retrocompatibility
# The CWL version foolows SemVer
cwlVersion: v1.2

# What type of CWL process we have in this document.
class: CommandLineTool
# This CommandLineTool executes the linux "echo" command-line tool.
baseCommand: echo

# The inputs for this process.
inputs:
  message:
    type: string
    # A default value that can be overridden, e.g. --message "Hola mundo"
    default: "Hello World"
    # Bind this message value as an argument to "echo".
    inputBinding:
      position: 1
outputs: []
```

`cwltool` is an implementation of the CWL specification. It is also the CWL _Reference Runner_ for the specification, and it is compliant with the latest version of the specification: `v1.2`. You can install `cwltool` using `pip`: `pip install cwltool`.

A process is a computing unit that takes inputs and produces outputs. The behavior of a process can be affected by the inputs, requirements, and hints. There are four types of processes defined in the CWL specification `v1.2`:

- A command-line tool (`class: CommandLineTool`): a wrapper for a command-line utility.
- An expression tool (`class: ExpressionTool`): a wrapper for a JavaScript expression. If you need to perform small, basic task, this can avoid having to write a ton of boilerplate.
- An operation (`class: Operation`).
- A workflow (`class: Workflow`): a process that contains steps. Steps can be other workflows (nested workflows), command-line tools, or expression tools. The inputs of a workflow can be passed to any of its steps, while the outputs produced by its steps can be used in the final output of the workflow.

The CWL can be extended through "requirements" that not all runners may implement. If you specify a requirement, and use an incompatible runner, you will fail early instead of later on.

See the YAML specification at http://yaml.org/
Standards followed in YAML for CWL:
- Special keys are `camelCase` (e.g. `cwlVersion`). Everything else is in `snake_case`.

## CommandLineTool
A CWL command-line tool must also have `inputs` and `outputs`.

To allow a process to access the network, one must give the `NetworkAccess` requirement:
```yaml
class: CommandLineTool

requirements:
  NetworkAccess:
     networkAccess: true
```

---
- [The CWL user guide](https://www.commonwl.org/user_guide/index.html).

#resource