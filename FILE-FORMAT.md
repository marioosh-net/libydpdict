Note: All multi-byte fields are stored in little-endian.

.idx file header
----------------

| offset | length | description                                     |
| ------ | ------ | ----------------------------------------------- |
| 0      | 4      | file id: 0xD5, 0x11, 0x4E, 0x8D (or 0x8D4E11D5) |
| 4      | 4      | ?                                               |
| 8      | 2      | record count                                    |
| 10     | 2      | ?                                               |
| 12     | 4      | ?                                               |
| 16     | 4      | record table offset                             |

.idx file record
----------------

| offset | length | description                          |
| ------ | ------ | ------------------------------------ |
| n      | 1      | word length + 1                      |
| n+1    | 1      | ?                                    |
| n+2    | 2      | record number (starting from 1)      |
| n+4    | 4      | record offset in .dat file           |
| n+8    | m+1    | null-terminated word                 |

.dat file record
----------------

| offset | length | description                    |
| ------ | ------ | ------------------------------ |
| n      | 4      | definition length in bytes     |
| n+4    | m      | non-null-terminated definition |

