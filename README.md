
# Removing GRUP from a UEFI Dual Boot 

#### This problem happes after removing a dual boot OS.

This guide provides step-by-step instructions for managing system partitions using the Command Prompt (cmd).

## Steps

1. Open Command Prompt as an administrator.

2. List all disks and select the desired disk:
    ```cmd
    diskpart
    list disk
    select disk 0
    list partition
    ```

3. Identify and select the system partition by its number:
    ```cmd
    select partition [number]
    ```
    *Replace `[number]` with the system partition number found in the previous step.*

4. Assign a drive letter to the selected partition and exit `diskpart`:
    ```cmd
    assign letter=x
    exit
    ```

5. Access the newly assigned drive:
    ```cmd
    x:
    dir
    cd efi
    dir
    rd [system-name] /s
    ```
    *Replace `[system-name]` with the target system's name.*

6. Confirm the deletion:
    ```cmd
    Y
    exit
    ```

7. Restart your system.

---

Ensure you follow these steps carefully to avoid any unintended changes to your system.

## Author

- [@Islam_Gomaa](https://github.com/iislamgom3a)

