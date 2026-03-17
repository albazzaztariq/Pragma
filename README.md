# Pragma

**[albazzaztariq.github.io/UniLogic/pragma.html](https://albazzaztariq.github.io/UniLogic/pragma.html)**

Declarative pipeline language for data movement, transformation, and automation.

A Pragma pipeline is a flat sequence of named actions — `fetch`, `convert`, `save`, `notify`, `query`, `delete`, `schedule`, `input`, `output`, `auth`. Each action takes key-value attributes. The output of one step is referenced by name in the next. There is no control flow, no variables in the programming sense, and no business logic. When a pipeline needs branching or computation, that work belongs in UniLogic.

Pragma sits above UniLogic — it generates UniLogic code, and changes to the generated code fold back into the Pragma representation.

## Example

```
fetch:
      source=https://api.openalex.org/works
      auth=openalex_auth
      format=json
      structure=openalex.map
      name=records

convert:
      content=records
      from=json
      to=csv
      name=report

save:
      to=file
      dest=output/records.csv
      content=report
      format=csv
      mode=overwrite
```

Part of the [LANG Project](https://lang-language-project.github.io/).
