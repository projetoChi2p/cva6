# CVA6 documentation

CVA6 documentation is published as a Read the Docs documentation.
It can be generated by running `make html` in this directory.

## Configuration-specific manuals

For each supported target (e.g. `cv32a65x`), there are two manuals included in the main documentation: a tailored RISC-V instruction set manual, and a design documentation.
These documents are generated as HTML files, are committed to the repository, and are included when generating the main documentation.

### Instruction set manual

Instruction set manuals (privileged & unprivileged) are based on the official RISC-V Instruction Set Manual repository.
Some parts are stripped down or annotated to only include what's relevant for each specific configuration.

These manuals can be generated with: `make -C 04_cv32a65x/riscv priv-html unpriv-html`.
Replace `04_cv32a65x` with the desired target.

### Design documentation

Design documentation describes the internal architecture of the CVA6 processor.

It can be generated with: `make -C 04_cv32a65x/design design-html`.

Some of the files used in this documentation (`port_*.adoc`) are directly generated from the RTL.
They can be updated by running `python3 scripts/spec_builder.py`.