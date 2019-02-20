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
==59266== Memcheck, a memory error detector
==59266== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==59266== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==59266== Command: ./h5repack outputFuzz/crashes/id:000156,sig:11,src:000684,op:int16,pos:808,val:+64 test
==59266== 
--59266-- Valgrind options:
--59266--    -v
--59266--    --tool=memcheck
--59266--    --leak-check=full
--59266-- Contents of /proc/version:
--59266--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--59266-- 
--59266-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--59266-- Page sizes: currently 4096, max supported 4096
--59266-- Valgrind library directory: /usr/lib/valgrind
--59266-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--59266--    object doesn't have a symbol table
--59266-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--59266--   Considering /usr/lib/debug/.build-id/dc/5cb16f5e644116cac64a4c3f5da4d081b81a4f.debug ..
--59266--   .. build-id is valid
--59266-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--59266--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--59266--   .. CRC mismatch (computed 7680f3df wanted 92e0f93c)
--59266--   Considering /usr/lib/debug/usr/lib/valgrind/memcheck-amd64-linux ..
--59266--   .. CRC is valid
--59266--    object doesn't have a dynamic symbol table
--59266-- Scheduler: using generic scheduler lock implementation.
--59266-- Reading suppressions file: /usr/lib/valgrind/default.supp
==59266== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-59266-by-root-on-???
==59266== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-59266-by-root-on-???
==59266== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-59266-by-root-on-???
==59266== 
==59266== TO CONTROL THIS PROCESS USING vgdb (which you probably
==59266== don't want to do, unless you know exactly what you're doing,
==59266== or are doing some strange experiment):
==59266==   /usr/lib/valgrind/../../bin/vgdb --pid=59266 ...command...
==59266== 
==59266== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==59266==   /path/to/gdb ./h5repack
==59266== and then give GDB the following command
==59266==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=59266
==59266== --pid is optional if only one valgrind process is running
==59266== 
--59266-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x58061781 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--59266-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x5806179b (vgPlain_amd64_linux_REDIR_FOR_index)
--59266-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--59266--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59266--   .. CRC mismatch (computed 66a2a561 wanted 3789c7eb)
--59266--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59266--   .. CRC is valid
--59266-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--59266--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59266--   .. CRC mismatch (computed 8487a070 wanted 8af30a91)
--59266--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59266--   .. CRC is valid
==59266== WARNING: new redirection conflicts with existing -- ignoring it
--59266--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x58061781 vgPlain_amd64_linux_REDIR_FOR_strlen
--59266--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838a60 strlen
--59266-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839b90 (strcmp)
--59266-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d1a0 (mempcpy)
--59266-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--59266-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--59266--    object doesn't have a symbol table
--59266-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--59266--   Considering /usr/lib/debug/.build-id/b7/883b3fc771cfa5fcb452861bbb97a5b646259b.debug ..
--59266--   .. build-id is valid
--59266-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--59266--   Considering /usr/lib/debug/.build-id/fa/b2857727406caccd7ab22e1729b09ccf2c3eb7.debug ..
--59266--   .. build-id is valid
--59266-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--59266--   Considering /usr/lib/debug/.build-id/dc/87cd1e2b171a4c51139cb4e1f2ec630e711de3.debug ..
--59266--   .. build-id is valid
--59266-- REDIR: 0x598d050 (libc.so.6:memmove) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598c280 (libc.so.6:strncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d330 (libc.so.6:strcasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598bcd0 (libc.so.6:strcat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598c2b0 (libc.so.6:rindex) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598e900 (libc.so.6:rawmemchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d1c0 (libc.so.6:mempcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598cff0 (libc.so.6:bcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598c240 (libc.so.6:strncmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598bd40 (libc.so.6:strcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d120 (libc.so.6:memset) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x59a6b60 (libc.so.6:wcschr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598c1e0 (libc.so.6:strnlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598bdb0 (libc.so.6:strcspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d380 (libc.so.6:strncasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598bd80 (libc.so.6:strcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d4c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598c2e0 (libc.so.6:strpbrk) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598bd00 (libc.so.6:index) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598c1b0 (libc.so.6:strlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x59931b0 (libc.so.6:memrchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d3d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598cfc0 (libc.so.6:memchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x59a7920 (libc.so.6:wcslen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598c590 (libc.so.6:strspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d300 (libc.so.6:stpncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d2d0 (libc.so.6:stpcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598e930 (libc.so.6:strchrnul) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x598d420 (libc.so.6:strncasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x5a5f700 (libc.so.6:__strrchr_avx2) redirected to 0x48383e0 (rindex)
--59266-- REDIR: 0x5a5f8d0 (libc.so.6:__strlen_avx2) redirected to 0x48389a0 (strlen)
--59266-- REDIR: 0x59885c0 (libc.so.6:malloc) redirected to 0x4835750 (malloc)
--59266-- REDIR: 0x5a60290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c280 (memset)
--59266-- REDIR: 0x5a5f510 (libc.so.6:__strchrnul_avx2) redirected to 0x483ccd0 (strchrnul)
--59266-- REDIR: 0x5a4cc90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838a80 (strcpy)
--59266-- REDIR: 0x5988d60 (libc.so.6:realloc) redirected to 0x4837960 (realloc)
--59266-- REDIR: 0x5a5fe10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c390 (memmove)
--59266-- REDIR: 0x5988c50 (libc.so.6:free) redirected to 0x4836980 (free)
--59266-- REDIR: 0x5a4e440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838c60 (strncpy)
--59266-- REDIR: 0x5a3b0a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839a50 (strcmp)
--59266-- REDIR: 0x59892a0 (libc.so.6:calloc) redirected to 0x4837720 (calloc)
--59266-- REDIR: 0x598c210 (libc.so.6:strncat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59266-- REDIR: 0x599e0f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838840 (strncat)
--59266-- REDIR: 0x5a5b3b0 (libc.so.6:__strcspn_sse42) redirected to 0x483d580 (strcspn)
==59266== Invalid read of size 1
==59266==    at 0x4D290A0: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c42758 is 0 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== Invalid read of size 1
==59266==    at 0x4D290BF: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c42759 is 1 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== Invalid read of size 1
==59266==    at 0x4D290D7: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275a is 2 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== Invalid read of size 1
==59266==    at 0x4D290F0: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275b is 3 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== Invalid read of size 1
==59266==    at 0x4D2910D: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275c is 4 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== Invalid read of size 1
==59266==    at 0x4D2911B: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275d is 5 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== Invalid read of size 1
==59266==    at 0x4D2912E: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275e is 6 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== Invalid read of size 1
==59266==    at 0x4D29140: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275f is 7 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
--59266-- REDIR: 0x5a5f2e0 (libc.so.6:__strchr_avx2) redirected to 0x4838600 (index)
--59266-- REDIR: 0x5a5fdf0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483cde0 (mempcpy)
==59266== Invalid read of size 4
==59266==    at 0x4F72D3C: H5T_close_real (H5T.c:3684)
==59266==    by 0x4A3E154: H5O__dset_free_copy_file_udata (H5Doh.c:150)
==59266==    by 0x4CE2A9F: H5O__copy_header_real (H5Ocopy.c:931)
==59266==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59266==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59266==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59266==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59266==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x8 is not stack'd, malloc'd or (recently) free'd
==59266== 
==59266== 
==59266== Process terminating with default action of signal 11 (SIGSEGV)
==59266==  Access not within mapped region at address 0x8
==59266==    at 0x4F72D3C: H5T_close_real (H5T.c:3684)
==59266==    by 0x4A3E154: H5O__dset_free_copy_file_udata (H5Doh.c:150)
==59266==    by 0x4CE2A9F: H5O__copy_header_real (H5Ocopy.c:931)
==59266==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59266==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59266==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59266==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59266==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  If you believe this happened as a result of a stack
==59266==  overflow in your program's main thread (unlikely but
==59266==  possible), you can try to increase the size of the
==59266==  main thread stack using the --main-stacksize= flag.
==59266==  The main thread stack size used in this run was 8388608.
==59266== 
==59266== HEAP SUMMARY:
==59266==     in use at exit: 1,403,326 bytes in 3,208 blocks
==59266==   total heap usage: 3,321 allocs, 113 frees, 1,419,768 bytes allocated
==59266== 
==59266== Searching for pointers to 3,208 not-freed blocks
==59266== Checked 1,489,552 bytes
==59266== 
==59266== LEAK SUMMARY:
==59266==    definitely lost: 0 bytes in 0 blocks
==59266==    indirectly lost: 0 bytes in 0 blocks
==59266==      possibly lost: 0 bytes in 0 blocks
==59266==    still reachable: 1,403,326 bytes in 3,208 blocks
==59266==                       of which reachable via heuristic:
==59266==                         length64           : 34,286 bytes in 33 blocks
==59266==                         newarray           : 16 bytes in 1 blocks
==59266==         suppressed: 0 bytes in 0 blocks
==59266== Reachable blocks (those to which a pointer was found) are not shown.
==59266== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==59266== 
==59266== ERROR SUMMARY: 33 errors from 9 contexts (suppressed: 0 from 0)
==59266== 
==59266== 1 errors in context 1 of 9:
==59266== Invalid read of size 4
==59266==    at 0x4F72D3C: H5T_close_real (H5T.c:3684)
==59266==    by 0x4A3E154: H5O__dset_free_copy_file_udata (H5Doh.c:150)
==59266==    by 0x4CE2A9F: H5O__copy_header_real (H5Ocopy.c:931)
==59266==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59266==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59266==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59266==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59266==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x8 is not stack'd, malloc'd or (recently) free'd
==59266== 
==59266== 
==59266== 4 errors in context 2 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D29140: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275f is 7 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== 
==59266== 4 errors in context 3 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D2912E: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275e is 6 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== 
==59266== 4 errors in context 4 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D2911B: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275d is 5 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== 
==59266== 4 errors in context 5 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D2910D: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275c is 4 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== 
==59266== 4 errors in context 6 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D290F0: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275b is 3 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== 
==59266== 4 errors in context 7 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D290D7: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c4275a is 2 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== 
==59266== 4 errors in context 8 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D290BF: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c42759 is 1 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== 
==59266== 4 errors in context 9 of 9:
==59266== Invalid read of size 1
==59266==    at 0x4D290A0: H5O__layout_decode (H5Olayout.c:180)
==59266==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59266==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59266==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==59266==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==59266==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==59266==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59266==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59266==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59266==    by 0x5927B16: (below main) (libc-start.c:310)
==59266==  Address 0x5c42758 is 0 bytes after a block of size 88 alloc'd
==59266==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59266==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59266==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59266==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59266==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59266==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59266==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59266==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59266==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59266==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59266==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59266==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59266==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59266== 
==59266== ERROR SUMMARY: 33 errors from 9 contexts (suppressed: 0 from 0)
Segmentation fault

```
---
