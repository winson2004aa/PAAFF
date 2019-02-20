## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by winson2004aa@gmail.com, please send email to winson2004aa@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5O__layout_decode_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack outputFuzz/crashes/H5O__layout_decode_invalid-read-memory-access test
==59129== Memcheck, a memory error detector
==59129== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==59129== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==59129== Command: ./h5repack outputFuzz/crashes/id:000131,sig:11,src:000488,op:flip1,pos:827 test
==59129== 
--59129-- Valgrind options:
--59129--    -v
--59129--    --tool=memcheck
--59129--    --leak-check=full
--59129-- Contents of /proc/version:
--59129--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--59129-- 
--59129-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--59129-- Page sizes: currently 4096, max supported 4096
--59129-- Valgrind library directory: /usr/lib/valgrind
--59129-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--59129--    object doesn't have a symbol table
--59129-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--59129--   Considering /usr/lib/debug/.build-id/dc/5cb16f5e644116cac64a4c3f5da4d081b81a4f.debug ..
--59129--   .. build-id is valid
--59129-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--59129--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--59129--   .. CRC mismatch (computed 7680f3df wanted 92e0f93c)
--59129--   Considering /usr/lib/debug/usr/lib/valgrind/memcheck-amd64-linux ..
--59129--   .. CRC is valid
--59129--    object doesn't have a dynamic symbol table
--59129-- Scheduler: using generic scheduler lock implementation.
--59129-- Reading suppressions file: /usr/lib/valgrind/default.supp
==59129== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-59129-by-root-on-???
==59129== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-59129-by-root-on-???
==59129== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-59129-by-root-on-???
==59129== 
==59129== TO CONTROL THIS PROCESS USING vgdb (which you probably
==59129== don't want to do, unless you know exactly what you're doing,
==59129== or are doing some strange experiment):
==59129==   /usr/lib/valgrind/../../bin/vgdb --pid=59129 ...command...
==59129== 
==59129== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==59129==   /path/to/gdb ./h5repack
==59129== and then give GDB the following command
==59129==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=59129
==59129== --pid is optional if only one valgrind process is running
==59129== 
--59129-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x58061781 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--59129-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x5806179b (vgPlain_amd64_linux_REDIR_FOR_index)
--59129-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--59129--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59129--   .. CRC mismatch (computed 66a2a561 wanted 3789c7eb)
--59129--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59129--   .. CRC is valid
--59129-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--59129--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59129--   .. CRC mismatch (computed 8487a070 wanted 8af30a91)
--59129--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59129--   .. CRC is valid
==59129== WARNING: new redirection conflicts with existing -- ignoring it
--59129--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x58061781 vgPlain_amd64_linux_REDIR_FOR_strlen
--59129--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838a60 strlen
--59129-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839b90 (strcmp)
--59129-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d1a0 (mempcpy)
--59129-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--59129-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--59129--    object doesn't have a symbol table
--59129-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--59129--   Considering /usr/lib/debug/.build-id/b7/883b3fc771cfa5fcb452861bbb97a5b646259b.debug ..
--59129--   .. build-id is valid
--59129-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--59129--   Considering /usr/lib/debug/.build-id/fa/b2857727406caccd7ab22e1729b09ccf2c3eb7.debug ..
--59129--   .. build-id is valid
--59129-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--59129--   Considering /usr/lib/debug/.build-id/dc/87cd1e2b171a4c51139cb4e1f2ec630e711de3.debug ..
--59129--   .. build-id is valid
--59129-- REDIR: 0x598d050 (libc.so.6:memmove) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598c280 (libc.so.6:strncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d330 (libc.so.6:strcasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598bcd0 (libc.so.6:strcat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598c2b0 (libc.so.6:rindex) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598e900 (libc.so.6:rawmemchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d1c0 (libc.so.6:mempcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598cff0 (libc.so.6:bcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598c240 (libc.so.6:strncmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598bd40 (libc.so.6:strcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d120 (libc.so.6:memset) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x59a6b60 (libc.so.6:wcschr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598c1e0 (libc.so.6:strnlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598bdb0 (libc.so.6:strcspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d380 (libc.so.6:strncasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598bd80 (libc.so.6:strcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d4c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598c2e0 (libc.so.6:strpbrk) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598bd00 (libc.so.6:index) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598c1b0 (libc.so.6:strlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x59931b0 (libc.so.6:memrchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d3d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598cfc0 (libc.so.6:memchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x59a7920 (libc.so.6:wcslen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598c590 (libc.so.6:strspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d300 (libc.so.6:stpncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d2d0 (libc.so.6:stpcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598e930 (libc.so.6:strchrnul) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x598d420 (libc.so.6:strncasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x5a5f700 (libc.so.6:__strrchr_avx2) redirected to 0x48383e0 (rindex)
--59129-- REDIR: 0x5a5f8d0 (libc.so.6:__strlen_avx2) redirected to 0x48389a0 (strlen)
--59129-- REDIR: 0x59885c0 (libc.so.6:malloc) redirected to 0x4835750 (malloc)
--59129-- REDIR: 0x5a60290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c280 (memset)
--59129-- REDIR: 0x5a5f510 (libc.so.6:__strchrnul_avx2) redirected to 0x483ccd0 (strchrnul)
--59129-- REDIR: 0x5a4cc90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838a80 (strcpy)
--59129-- REDIR: 0x5988d60 (libc.so.6:realloc) redirected to 0x4837960 (realloc)
--59129-- REDIR: 0x5a5fe10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c390 (memmove)
--59129-- REDIR: 0x5988c50 (libc.so.6:free) redirected to 0x4836980 (free)
--59129-- REDIR: 0x5a4e440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838c60 (strncpy)
--59129-- REDIR: 0x5a3b0a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839a50 (strcmp)
--59129-- REDIR: 0x59892a0 (libc.so.6:calloc) redirected to 0x4837720 (calloc)
--59129-- REDIR: 0x598c210 (libc.so.6:strncat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59129-- REDIR: 0x599e0f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838840 (strncat)
--59129-- REDIR: 0x5a5b3b0 (libc.so.6:__strcspn_sse42) redirected to 0x483d580 (strcspn)
--59129-- REDIR: 0x5a5f2e0 (libc.so.6:__strchr_avx2) redirected to 0x4838600 (index)
--59129-- REDIR: 0x5a5fdf0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483cde0 (mempcpy)
==59129== Invalid read of size 8
==59129==    at 0x4E39749: H5S_close (H5S.c:448)
==59129==    by 0x48D3BAC: H5A__free (H5Aint.c:1166)
==59129==    by 0x4CC73E7: H5O_attr_decode (H5Oattr.c:253)
==59129==    by 0x4CC73E7: H5O_attr_shared_decode (H5Oshared.h:82)
==59129==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==59129==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59129==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59129==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59129==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59129==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x5927B16: (below main) (libc-start.c:310)
==59129==  Address 0x18 is not stack'd, malloc'd or (recently) free'd
==59129== 
==59129== 
==59129== Process terminating with default action of signal 11 (SIGSEGV)
==59129==  Access not within mapped region at address 0x18
==59129==    at 0x4E39749: H5S_close (H5S.c:448)
==59129==    by 0x48D3BAC: H5A__free (H5Aint.c:1166)
==59129==    by 0x4CC73E7: H5O_attr_decode (H5Oattr.c:253)
==59129==    by 0x4CC73E7: H5O_attr_shared_decode (H5Oshared.h:82)
==59129==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==59129==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59129==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59129==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59129==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59129==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x5927B16: (below main) (libc-start.c:310)
==59129==  If you believe this happened as a result of a stack
==59129==  overflow in your program's main thread (unlikely but
==59129==  possible), you can try to increase the size of the
==59129==  main thread stack using the --main-stacksize= flag.
==59129==  The main thread stack size used in this run was 8388608.
==59129== 
==59129== HEAP SUMMARY:
==59129==     in use at exit: 1,352,890 bytes in 3,192 blocks
==59129==   total heap usage: 3,303 allocs, 111 frees, 1,369,176 bytes allocated
==59129== 
==59129== Searching for pointers to 3,192 not-freed blocks
==59129== Checked 1,457,536 bytes
==59129== 
==59129== LEAK SUMMARY:
==59129==    definitely lost: 0 bytes in 0 blocks
==59129==    indirectly lost: 0 bytes in 0 blocks
==59129==      possibly lost: 0 bytes in 0 blocks
==59129==    still reachable: 1,352,890 bytes in 3,192 blocks
==59129==                       of which reachable via heuristic:
==59129==                         length64           : 5,576 bytes in 31 blocks
==59129==                         newarray           : 16 bytes in 1 blocks
==59129==         suppressed: 0 bytes in 0 blocks
==59129== Reachable blocks (those to which a pointer was found) are not shown.
==59129== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==59129== 
==59129== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
==59129== 
==59129== 1 errors in context 1 of 1:
==59129== Invalid read of size 8
==59129==    at 0x4E39749: H5S_close (H5S.c:448)
==59129==    by 0x48D3BAC: H5A__free (H5Aint.c:1166)
==59129==    by 0x4CC73E7: H5O_attr_decode (H5Oattr.c:253)
==59129==    by 0x4CC73E7: H5O_attr_shared_decode (H5Oshared.h:82)
==59129==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==59129==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59129==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59129==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59129==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59129==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59129==    by 0x5927B16: (below main) (libc-start.c:310)
==59129==  Address 0x18 is not stack'd, malloc'd or (recently) free'd
==59129== 
==59129== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
Segmentation fault


```
---
