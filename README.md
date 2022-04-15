# leak-report for Hawkeye

The path of a reported entry is /{**kernel-version**}/{**leakage-type**}/{**leakage-num**}-{**leakage-file**}-{**id**}

The **kernel-version** can be 

|Name|Description|
|----|-----------|
|chromiumOS-4.14| The chromiumOS kernel of version 4.14|
|linux 3.16 | The long-term support Linux kernel of version 3.16 |
|linux 4.4  | The long-term support Linux kernel of version 4.4 |
|linux 4.9  | The long-term support Linux kernel of version 4.9 |
|linux 4.14  | The long-term support Linux kernel of version 4.14 |
|linux 4.19  | The long-term support Linux kernel of version 4.19 |
|pixel2  | The Pixel2 kernel |
|pixel3  | The Pixel3 kernel |
|accepted-patches  | The patches accepted in mainline kernel |

The **leakage-type** can be

|Name|Description|
|----|-----------|
|copy_to_user| The leakage via copy_to_user|
|print_dyn| Print the address of a dynamic allocated object|
|print_gv| Print the address of a global object (function, global variable)|

**leakage-num** indicates the sequence number of the leakage of **leakage-type** in the **kernel-version**.

**leakage-file** is the file where the leakage happens.

**id** indicates the sequence number of the leakage in the **leakage-file** of **leakage-type** in the **kernel-version**.

For example,

/linux-4.14/print_gv/007-drivers-scsi-be2iscsi-be_main.c-001

means the leakage is of type *print_gv* in the file drivers/scsi/be2iscsi/be_main.c of linux 4.14 kernel.
It is the 7-th leakge of type *print_gv* in linux 4.14, 
and the 1-st leakage of type *print_gv* in the file drivers/scsi/be2iscsi/be_main.c of linux 4.14 kernel.
