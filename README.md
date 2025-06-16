
## Chip Integrated Development Environment

Chip IDE is being developed to realise the full multi target capabilities of the [dbu](https://github.com/brucebiotech/dbu) debug adapter.
Chip loads Dwarf debug info for each target to provide debug functionality normally provided by gdb.
Hence Chip connectects directly to multiple dbu's and multiple CPU's without the overhead of running gdb tools in separate processes.

```mermaid
graph LR;
 ide["Chip IDE"]
 dbu1["dbu"]
 dbu2["dbu"]

  c1["CPU1 Core 1"]
  c2["CPU1 Core 2"]
 CPU2
 CPU3
 CPU4
 ide <--> dbu1

 dbu1 <--> c1
 dbu1 <--> c2
 dbu1 <--> CPU2
 ide <--> dbu2
 dbu2 <--> CPU3
 dbu2 <--> CPU4
```

 ## Conventional IDE's

Conventional IDE's must use gdb and gdb-servers (e.g. openOCD) to connect to each CPU.

![Other](https://github.com/brucebiotech/chip/blob/main/docs/conventional_ide.png)

