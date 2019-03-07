## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by winson2004aa@gmail.com, please send email to winson2004aa@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5FL__fac_gc_list_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack outputFuzz/crashes/H5FL__fac_gc_list_invalid-read-memory-access test
==111569== Memcheck, a memory error detector
==111569== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==111569== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==111569== Command: ./h5repack outputFuzz/crashes/H5FL__fac_gc_list_invalid-read-memory-access test
==111569== 
--111569-- Valgrind options:
--111569--    -v
--111569--    --tool=memcheck
--111569--    --leak-check=full
--111569-- Contents of /proc/version:
--111569--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--111569-- 
--111569-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--111569-- Page sizes: currently 4096, max supported 4096
--111569-- Valgrind library directory: /usr/lib/valgrind
--111569-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--111569--    object doesn't have a symbol table
--111569-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--111569--   Considering /usr/lib/debug/.build-id/dc/5cb16f5e644116cac64a4c3f5da4d081b81a4f.debug ..
--111569--   .. build-id is valid
--111569-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--111569--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--111569--   .. CRC mismatch (computed 7680f3df wanted 92e0f93c)
--111569--   Considering /usr/lib/debug/usr/lib/valgrind/memcheck-amd64-linux ..
--111569--   .. CRC is valid
--111569--    object doesn't have a dynamic symbol table
--111569-- Scheduler: using generic scheduler lock implementation.
--111569-- Reading suppressions file: /usr/lib/valgrind/default.supp
==111569== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-111569-by-root-on-???
==111569== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-111569-by-root-on-???
==111569== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-111569-by-root-on-???
==111569== 
==111569== TO CONTROL THIS PROCESS USING vgdb (which you probably
==111569== don't want to do, unless you know exactly what you're doing,
==111569== or are doing some strange experiment):
==111569==   /usr/lib/valgrind/../../bin/vgdb --pid=111569 ...command...
==111569== 
==111569== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==111569==   /path/to/gdb ./h5repack
==111569== and then give GDB the following command
==111569==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=111569
==111569== --pid is optional if only one valgrind process is running
==111569== 
--111569-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x58061781 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--111569-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x5806179b (vgPlain_amd64_linux_REDIR_FOR_index)
--111569-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--111569--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--111569--   .. CRC mismatch (computed 66a2a561 wanted 3789c7eb)
--111569--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--111569--   .. CRC is valid
--111569-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--111569--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--111569--   .. CRC mismatch (computed 8487a070 wanted 8af30a91)
--111569--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--111569--   .. CRC is valid
==111569== WARNING: new redirection conflicts with existing -- ignoring it
--111569--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x58061781 vgPlain_amd64_linux_REDIR_FOR_strlen
--111569--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838a60 strlen
--111569-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839b90 (strcmp)
--111569-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d1a0 (mempcpy)
--111569-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--111569-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--111569--    object doesn't have a symbol table
--111569-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--111569--   Considering /usr/lib/debug/.build-id/b7/883b3fc771cfa5fcb452861bbb97a5b646259b.debug ..
--111569--   .. build-id is valid
--111569-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--111569--   Considering /usr/lib/debug/.build-id/fa/b2857727406caccd7ab22e1729b09ccf2c3eb7.debug ..
--111569--   .. build-id is valid
--111569-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--111569--   Considering /usr/lib/debug/.build-id/dc/87cd1e2b171a4c51139cb4e1f2ec630e711de3.debug ..
--111569--   .. build-id is valid
--111569-- REDIR: 0x598d050 (libc.so.6:memmove) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598c280 (libc.so.6:strncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d330 (libc.so.6:strcasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598bcd0 (libc.so.6:strcat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598c2b0 (libc.so.6:rindex) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598e900 (libc.so.6:rawmemchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d1c0 (libc.so.6:mempcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598cff0 (libc.so.6:bcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598c240 (libc.so.6:strncmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598bd40 (libc.so.6:strcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d120 (libc.so.6:memset) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x59a6b60 (libc.so.6:wcschr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598c1e0 (libc.so.6:strnlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598bdb0 (libc.so.6:strcspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d380 (libc.so.6:strncasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598bd80 (libc.so.6:strcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d4c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598c2e0 (libc.so.6:strpbrk) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598bd00 (libc.so.6:index) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598c1b0 (libc.so.6:strlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x59931b0 (libc.so.6:memrchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d3d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598cfc0 (libc.so.6:memchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x59a7920 (libc.so.6:wcslen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598c590 (libc.so.6:strspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d300 (libc.so.6:stpncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d2d0 (libc.so.6:stpcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598e930 (libc.so.6:strchrnul) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x598d420 (libc.so.6:strncasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x5a5f700 (libc.so.6:__strrchr_avx2) redirected to 0x48383e0 (rindex)
--111569-- REDIR: 0x5a5f8d0 (libc.so.6:__strlen_avx2) redirected to 0x48389a0 (strlen)
--111569-- REDIR: 0x59885c0 (libc.so.6:malloc) redirected to 0x4835750 (malloc)
--111569-- REDIR: 0x5a60290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c280 (memset)
--111569-- REDIR: 0x5a5f510 (libc.so.6:__strchrnul_avx2) redirected to 0x483ccd0 (strchrnul)
--111569-- REDIR: 0x5a4cc90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838a80 (strcpy)
--111569-- REDIR: 0x5988d60 (libc.so.6:realloc) redirected to 0x4837960 (realloc)
--111569-- REDIR: 0x5a5fe10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c390 (memmove)
--111569-- REDIR: 0x5988c50 (libc.so.6:free) redirected to 0x4836980 (free)
--111569-- REDIR: 0x5a4e440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838c60 (strncpy)
--111569-- REDIR: 0x5a3b0a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839a50 (strcmp)
--111569-- REDIR: 0x59892a0 (libc.so.6:calloc) redirected to 0x4837720 (calloc)
--111569-- REDIR: 0x598c210 (libc.so.6:strncat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111569-- REDIR: 0x599e0f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838840 (strncat)
--111569-- REDIR: 0x5a5b3b0 (libc.so.6:__strcspn_sse42) redirected to 0x483d580 (strcspn)
==111569== Invalid read of size 1
==111569==    at 0x483C5FC: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e4d72f is 1 bytes before a block of size 65,535 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
--111569-- REDIR: 0x5a5f2e0 (libc.so.6:__strchr_avx2) redirected to 0x4838600 (index)
==111569== Invalid read of size 2
==111569==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x5e42ea8 is 0 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== Invalid read of size 2
==111569==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x5e42eae is 6 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== Invalid read of size 1
==111569==    at 0x483C438: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x5e52df2 is 22,210 bytes inside a block of size 65,535 free'd
==111569==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111569==    by 0x4C98630: H5MM_xfree (H5MM.c:560)
==111569==    by 0x4D2D1E3: H5O__layout_reset (H5Olayout.c:844)
==111569==    by 0x4D379B8: H5O__msg_reset_real (H5Omessage.c:620)
==111569==    by 0x4D379B8: H5O__msg_free_real (H5Omessage.c:717)
==111569==    by 0x4D37D5F: H5O__msg_free_mesg (H5Omessage.c:688)
==111569==    by 0x4D22797: H5O__free (H5Oint.c:3172)
==111569==    by 0x4CD9838: H5O__cache_free_icr (H5Ocache.c:665)
==111569==    by 0x4954BAD: H5C__flush_single_entry (H5C.c:6396)
==111569==    by 0x495DA1B: H5C__make_space_in_cache (H5C.c:7001)
==111569==    by 0x4961201: H5C_protect (H5C.c:2455)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==  Block was alloc'd at
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== Invalid read of size 2
==111569==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e42ea8 is 0 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== Invalid read of size 2
==111569==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e42eae is 6 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== Invalid read of size 1
==111569==    at 0x483C438: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e52df2 is 22,210 bytes inside a block of size 65,535 free'd
==111569==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111569==    by 0x4C98630: H5MM_xfree (H5MM.c:560)
==111569==    by 0x4D2D1E3: H5O__layout_reset (H5Olayout.c:844)
==111569==    by 0x4D379B8: H5O__msg_reset_real (H5Omessage.c:620)
==111569==    by 0x4D379B8: H5O__msg_free_real (H5Omessage.c:717)
==111569==    by 0x4D37D5F: H5O__msg_free_mesg (H5Omessage.c:688)
==111569==    by 0x4D22797: H5O__free (H5Oint.c:3172)
==111569==    by 0x4CD9838: H5O__cache_free_icr (H5Ocache.c:665)
==111569==    by 0x4954BAD: H5C__flush_single_entry (H5C.c:6396)
==111569==    by 0x495DA1B: H5C__make_space_in_cache (H5C.c:7001)
==111569==    by 0x4961201: H5C_protect (H5C.c:2455)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==  Block was alloc'd at
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
--111569-- REDIR: 0x5a5fdf0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483cde0 (mempcpy)
==111569== Invalid write of size 2
==111569==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D261C4: H5O__layout_encode (H5Olayout.c:580)
==111569==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==111569==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==111569==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==111569==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==111569==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==111569==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==111569==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==111569==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==111569==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==111569==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==111569==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==111569==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==111569==  Address 0x5ea0368 is 0 bytes after a block of size 136 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==111569==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569== 
==111569== Invalid write of size 1
==111569==    at 0x483C43B: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D261C4: H5O__layout_encode (H5Olayout.c:580)
==111569==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==111569==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==111569==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==111569==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==111569==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==111569==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==111569==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==111569==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==111569==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==111569==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==111569==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==111569==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==111569==  Address 0x5eb0342 is 54,962 bytes inside a block of size 65,535 free'd
==111569==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111569==    by 0x4C98630: H5MM_xfree (H5MM.c:560)
==111569==    by 0x4D2D1E3: H5O__layout_reset (H5Olayout.c:844)
==111569==    by 0x4D379B8: H5O__msg_reset_real (H5Omessage.c:620)
==111569==    by 0x4D379B8: H5O__msg_free_real (H5Omessage.c:717)
==111569==    by 0x4D37D5F: H5O__msg_free_mesg (H5Omessage.c:688)
==111569==    by 0x4D22797: H5O__free (H5Oint.c:3172)
==111569==    by 0x4CD9838: H5O__cache_free_icr (H5Ocache.c:665)
==111569==    by 0x4954BAD: H5C__flush_single_entry (H5C.c:6396)
==111569==    by 0x49576C3: H5C_flush_invalidate_ring (H5C.c:5560)
==111569==    by 0x49576C3: H5C__flush_invalidate_cache (H5C.c:5154)
==111569==    by 0x4958189: H5C_dest (H5C.c:850)
==111569==    by 0x48E268F: H5AC_dest (H5AC.c:524)
==111569==    by 0x4AD1387: H5F__dest (H5Fint.c:1251)
==111569==  Block was alloc'd at
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== Invalid read of size 8
==111569==    at 0x4B518E0: H5FL__fac_gc_list (H5FL.c:2260)
==111569==    by 0x4B518E0: H5FL_fac_term (H5FL.c:2352)
==111569==    by 0x4EE6C6C: H5SL_term_package (H5SL.c:658)
==111569==    by 0x488E894: H5_term_library.part.0 (H5.c:356)
==111569==    by 0x4890850: H5close (H5.c:875)
==111569==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x50 is not stack'd, malloc'd or (recently) free'd
==111569== 
==111569== 
==111569== Process terminating with default action of signal 11 (SIGSEGV)
==111569==  Access not within mapped region at address 0x50
==111569==    at 0x4B518E0: H5FL__fac_gc_list (H5FL.c:2260)
==111569==    by 0x4B518E0: H5FL_fac_term (H5FL.c:2352)
==111569==    by 0x4EE6C6C: H5SL_term_package (H5SL.c:658)
==111569==    by 0x488E894: H5_term_library.part.0 (H5.c:356)
==111569==    by 0x4890850: H5close (H5.c:875)
==111569==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  If you believe this happened as a result of a stack
==111569==  overflow in your program's main thread (unlikely but
==111569==  possible), you can try to increase the size of the
==111569==  main thread stack using the --main-stacksize= flag.
==111569==  The main thread stack size used in this run was 8388608.
==111569== 
==111569== HEAP SUMMARY:
==111569==     in use at exit: 189,676 bytes in 2,149 blocks
==111569==   total heap usage: 3,717 allocs, 1,568 frees, 4,177,013 bytes allocated
==111569== 
==111569== Searching for pointers to 2,149 not-freed blocks
==111569== Checked 313,776 bytes
==111569== 
==111569== 15 bytes in 1 blocks are definitely lost in loss record 12 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4BA9A6C: H5G_build_fullpath (H5Gname.c:318)
==111569==    by 0x4BA9A6C: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111569==    by 0x4BAA72B: H5G_name_set (H5Gname.c:478)
==111569==    by 0x4C67FB3: H5L__link_cb (H5L.c:1662)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569==    by 0x4C5EF49: H5L__create_real.part.2 (H5L.c:1812)
==111569==    by 0x4C6C18E: H5L__create_real (H5L.c:1765)
==111569==    by 0x4C6C18E: H5L_link (H5L.c:1528)
==111569==    by 0x4CEA6A5: H5O__copy_obj (H5Ocopy.c:1228)
==111569==    by 0x4CEA6A5: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA6A5: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== 16 bytes in 1 blocks are definitely lost in loss record 101 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B53CA4: H5FL_reg_malloc (H5FL.c:441)
==111569==    by 0x4E37B6C: H5RS_own (H5RS.c:189)
==111569==    by 0x4BA9B55: H5G_build_fullpath (H5Gname.c:328)
==111569==    by 0x4BA9B55: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111569==    by 0x4BAA72B: H5G_name_set (H5Gname.c:478)
==111569==    by 0x4C67FB3: H5L__link_cb (H5L.c:1662)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569==    by 0x4C5EF49: H5L__create_real.part.2 (H5L.c:1812)
==111569==    by 0x4C6C18E: H5L__create_real (H5L.c:1765)
==111569==    by 0x4C6C18E: H5L_link (H5L.c:1528)
==111569==    by 0x4CEA6A5: H5O__copy_obj (H5Ocopy.c:1228)
==111569==    by 0x4CEA6A5: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA6A5: H5Ocopy (H5Ocopy.c:232)
==111569== 
==111569== 16 bytes in 1 blocks are definitely lost in loss record 102 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5781A: H5FL_fac_malloc (H5FL.c:2158)
==111569==    by 0x4EE4B94: H5SL_insert_common (H5SL.c:787)
==111569==    by 0x4EE73A8: H5SL_insert (H5SL.c:1121)
==111569==    by 0x4DE8051: H5P_copy_plist (H5Pint.c:882)
==111569==    by 0x4A152C1: H5D__new (H5Dint.c:489)
==111569==    by 0x4A277EA: H5D__open_oid (H5Dint.c:1459)
==111569==    by 0x4A277EA: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== 16 bytes in 1 blocks are definitely lost in loss record 103 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5781A: H5FL_fac_malloc (H5FL.c:2158)
==111569==    by 0x4EE4B94: H5SL_insert_common (H5SL.c:787)
==111569==    by 0x4EE73A8: H5SL_insert (H5SL.c:1121)
==111569==    by 0x4DE6BCF: H5P_add_prop (H5Pint.c:1177)
==111569==    by 0x4DE6E76: H5P__do_prop_cb1.part.13 (H5Pint.c:636)
==111569==    by 0x4DE7FC7: H5P__do_prop_cb1 (H5Pint.c:611)
==111569==    by 0x4DE7FC7: H5P_copy_plist (H5Pint.c:876)
==111569==    by 0x4A152C1: H5D__new (H5Dint.c:489)
==111569==    by 0x4A277EA: H5D__open_oid (H5Dint.c:1459)
==111569==    by 0x4A277EA: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569== 
==111569== 30 (15 direct, 15 indirect) bytes in 1 blocks are definitely lost in loss record 555 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4BA9A6C: H5G_build_fullpath (H5Gname.c:318)
==111569==    by 0x4BA9A6C: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111569==    by 0x4BAA65F: H5G_name_set (H5Gname.c:471)
==111569==    by 0x4BA2685: H5G__link_to_loc (H5Glink.c:390)
==111569==    by 0x4BCFC28: H5G__traverse_real.isra.0 (H5Gtraverse.c:593)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569==    by 0x4BA7C03: H5G_loc_info (H5Gloc.c:730)
==111569==    by 0x4D1DB8C: H5O__get_info_by_name (H5Oint.c:2375)
==111569==    by 0x4C9F4FC: H5Oget_info_by_name2 (H5O.c:518)
==111569==    by 0x190570: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== 32 (16 direct, 16 indirect) bytes in 1 blocks are definitely lost in loss record 638 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B53CA4: H5FL_reg_malloc (H5FL.c:441)
==111569==    by 0x4E37B6C: H5RS_own (H5RS.c:189)
==111569==    by 0x4BA9B55: H5G_build_fullpath (H5Gname.c:328)
==111569==    by 0x4BA9B55: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111569==    by 0x4BAA65F: H5G_name_set (H5Gname.c:471)
==111569==    by 0x4BA2685: H5G__link_to_loc (H5Glink.c:390)
==111569==    by 0x4BCFC28: H5G__traverse_real.isra.0 (H5Gtraverse.c:593)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569==    by 0x4BA7C03: H5G_loc_info (H5Gloc.c:730)
==111569==    by 0x4D1DB8C: H5O__get_info_by_name (H5Oint.c:2375)
==111569==    by 0x4C9F4FC: H5Oget_info_by_name2 (H5O.c:518)
==111569== 
==111569== 32 (16 direct, 16 indirect) bytes in 1 blocks are definitely lost in loss record 639 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5781A: H5FL_fac_malloc (H5FL.c:2158)
==111569==    by 0x4EE0E44: H5SL_insert_common (H5SL.c:787)
==111569==    by 0x4EE73A8: H5SL_insert (H5SL.c:1121)
==111569==    by 0x4DE3E80: H5P_close (H5Pint.c:4969)
==111569==    by 0x4C56332: H5I_dec_ref (H5I.c:1263)
==111569==    by 0x4A2328C: H5D_close (H5Dint.c:1777)
==111569==    by 0x4A23D48: H5D__close_cb (H5Dint.c:1627)
==111569==    by 0x4C56332: H5I_dec_ref (H5I.c:1263)
==111569==    by 0x4C56893: H5I_dec_app_ref (H5I.c:1308)
==111569==    by 0x4C57348: H5I_dec_app_ref_always_close (H5I.c:1352)
==111569== 
==111569== 80 (16 direct, 64 indirect) bytes in 1 blocks are definitely lost in loss record 1,063 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5781A: H5FL_fac_malloc (H5FL.c:2158)
==111569==    by 0x4EE0E44: H5SL_insert_common (H5SL.c:787)
==111569==    by 0x4EE73A8: H5SL_insert (H5SL.c:1121)
==111569==    by 0x4DE8051: H5P_copy_plist (H5Pint.c:882)
==111569==    by 0x4AA994C: H5Fget_create_plist (H5F.c:185)
==111569==    by 0x12BE57: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569== 
==111569== 424 bytes in 1 blocks are definitely lost in loss record 1,788 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B53CA4: H5FL_reg_malloc (H5FL.c:441)
==111569==    by 0x4B53F8F: H5FL_reg_calloc (H5FL.c:498)
==111569==    by 0x4CD9C3D: H5O__prefix_deserialize.part.2 (H5Ocache.c:1149)
==111569==    by 0x4CDAF7F: H5O__prefix_deserialize (H5Ocache.c:205)
==111569==    by 0x4CDAF7F: H5O__cache_get_final_load_size (H5Ocache.c:218)
==111569==    by 0x496309E: H5C_load_entry (H5C.c:6643)
==111569==    by 0x496309E: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D38CA6: H5O_msg_exists (H5Omessage.c:882)
==111569==    by 0x4BC03C2: H5G_mkroot (H5Groot.c:238)
==111569==    by 0x4ADD0B1: H5F_open (H5Fint.c:1708)
==111569== 
==111569== 768 (16 direct, 752 indirect) bytes in 1 blocks are definitely lost in loss record 1,796 of 1,814
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B53BE9: H5FL_reg_init (H5FL.c:283)
==111569==    by 0x4B53BE9: H5FL_reg_malloc (H5FL.c:422)
==111569==    by 0x4B53F8F: H5FL_reg_calloc (H5FL.c:498)
==111569==    by 0x4A3F7FB: H5O__dset_get_copy_file_udata (H5Doh.c:113)
==111569==    by 0x4CE1C55: H5O__copy_header_real (H5Ocopy.c:394)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569== 
==111569== LEAK SUMMARY:
==111569==    definitely lost: 566 bytes in 10 blocks
==111569==    indirectly lost: 863 bytes in 54 blocks
==111569==      possibly lost: 0 bytes in 0 blocks
==111569==    still reachable: 188,247 bytes in 2,085 blocks
==111569==         suppressed: 0 bytes in 0 blocks
==111569== Reachable blocks (those to which a pointer was found) are not shown.
==111569== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==111569== 
==111569== ERROR SUMMARY: 142780 errors from 20 contexts (suppressed: 0 from 0)
==111569== 
==111569== 1 errors in context 1 of 20:
==111569== Invalid read of size 8
==111569==    at 0x4B518E0: H5FL__fac_gc_list (H5FL.c:2260)
==111569==    by 0x4B518E0: H5FL_fac_term (H5FL.c:2352)
==111569==    by 0x4EE6C6C: H5SL_term_package (H5SL.c:658)
==111569==    by 0x488E894: H5_term_library.part.0 (H5.c:356)
==111569==    by 0x4890850: H5close (H5.c:875)
==111569==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x50 is not stack'd, malloc'd or (recently) free'd
==111569== 
==111569== 
==111569== 1 errors in context 2 of 20:
==111569== Invalid write of size 1
==111569==    at 0x483C43B: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D261C4: H5O__layout_encode (H5Olayout.c:580)
==111569==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==111569==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==111569==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==111569==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==111569==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==111569==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==111569==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==111569==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==111569==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==111569==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==111569==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==111569==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==111569==  Address 0x5eb0342 is 54,962 bytes inside a block of size 65,535 free'd
==111569==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111569==    by 0x4C98630: H5MM_xfree (H5MM.c:560)
==111569==    by 0x4D2D1E3: H5O__layout_reset (H5Olayout.c:844)
==111569==    by 0x4D379B8: H5O__msg_reset_real (H5Omessage.c:620)
==111569==    by 0x4D379B8: H5O__msg_free_real (H5Omessage.c:717)
==111569==    by 0x4D37D5F: H5O__msg_free_mesg (H5Omessage.c:688)
==111569==    by 0x4D22797: H5O__free (H5Oint.c:3172)
==111569==    by 0x4CD9838: H5O__cache_free_icr (H5Ocache.c:665)
==111569==    by 0x4954BAD: H5C__flush_single_entry (H5C.c:6396)
==111569==    by 0x49576C3: H5C_flush_invalidate_ring (H5C.c:5560)
==111569==    by 0x49576C3: H5C__flush_invalidate_cache (H5C.c:5154)
==111569==    by 0x4958189: H5C_dest (H5C.c:850)
==111569==    by 0x48E268F: H5AC_dest (H5AC.c:524)
==111569==    by 0x4AD1387: H5F__dest (H5Fint.c:1251)
==111569==  Block was alloc'd at
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== 
==111569== 1 errors in context 3 of 20:
==111569== Invalid read of size 1
==111569==    at 0x483C438: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e52df2 is 22,210 bytes inside a block of size 65,535 free'd
==111569==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111569==    by 0x4C98630: H5MM_xfree (H5MM.c:560)
==111569==    by 0x4D2D1E3: H5O__layout_reset (H5Olayout.c:844)
==111569==    by 0x4D379B8: H5O__msg_reset_real (H5Omessage.c:620)
==111569==    by 0x4D379B8: H5O__msg_free_real (H5Omessage.c:717)
==111569==    by 0x4D37D5F: H5O__msg_free_mesg (H5Omessage.c:688)
==111569==    by 0x4D22797: H5O__free (H5Oint.c:3172)
==111569==    by 0x4CD9838: H5O__cache_free_icr (H5Ocache.c:665)
==111569==    by 0x4954BAD: H5C__flush_single_entry (H5C.c:6396)
==111569==    by 0x495DA1B: H5C__make_space_in_cache (H5C.c:7001)
==111569==    by 0x4961201: H5C_protect (H5C.c:2455)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==  Block was alloc'd at
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== 
==111569== 1 errors in context 4 of 20:
==111569== Invalid read of size 1
==111569==    at 0x483C438: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x5e52df2 is 22,210 bytes inside a block of size 65,535 free'd
==111569==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111569==    by 0x4C98630: H5MM_xfree (H5MM.c:560)
==111569==    by 0x4D2D1E3: H5O__layout_reset (H5Olayout.c:844)
==111569==    by 0x4D379B8: H5O__msg_reset_real (H5Omessage.c:620)
==111569==    by 0x4D379B8: H5O__msg_free_real (H5Omessage.c:717)
==111569==    by 0x4D37D5F: H5O__msg_free_mesg (H5Omessage.c:688)
==111569==    by 0x4D22797: H5O__free (H5Oint.c:3172)
==111569==    by 0x4CD9838: H5O__cache_free_icr (H5Ocache.c:665)
==111569==    by 0x4954BAD: H5C__flush_single_entry (H5C.c:6396)
==111569==    by 0x495DA1B: H5C__make_space_in_cache (H5C.c:7001)
==111569==    by 0x4961201: H5C_protect (H5C.c:2455)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==  Block was alloc'd at
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== 
==111569== 6437 errors in context 5 of 20:
==111569== Invalid read of size 2
==111569==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e42eae is 6 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== 
==111569== 6437 errors in context 6 of 20:
==111569== Invalid read of size 2
==111569==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x5e42eae is 6 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== 
==111569== 19306 errors in context 7 of 20:
==111569== Invalid read of size 2
==111569==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x120B10: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e42ea8 is 0 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== 
==111569== 19306 errors in context 8 of 20:
==111569== Invalid read of size 2
==111569==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4CE242F: H5O__copy_header_real (H5Ocopy.c:532)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569==  Address 0x5e42ea8 is 0 bytes after a block of size 280 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111569==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111569==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111569==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111569==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111569==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111569==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==111569==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==111569==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111569==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111569== 
==111569== 
==111569== 26552 errors in context 9 of 20:
==111569== Invalid read of size 1
==111569==    at 0x483C5FC: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==  Address 0x5e4d72f is 1 bytes before a block of size 65,535 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4D2A774: H5O__layout_decode (H5Olayout.c:209)
==111569==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111569==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111569==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111569==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111569==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111569==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111569==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111569==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569== 
==111569== 
==111569== 64728 errors in context 10 of 20:
==111569== Invalid write of size 2
==111569==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==111569==    by 0x4D261C4: H5O__layout_encode (H5Olayout.c:580)
==111569==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==111569==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==111569==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==111569==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==111569==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==111569==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==111569==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==111569==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==111569==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==111569==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==111569==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==111569==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==111569==  Address 0x5ea0368 is 0 bytes after a block of size 136 alloc'd
==111569==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111569==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111569==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111569==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==111569==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==111569==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111569==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111569==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111569==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111569==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111569==    by 0x5927B16: (below main) (libc-start.c:310)
==111569== 
==111569== ERROR SUMMARY: 142780 errors from 20 contexts (suppressed: 0 from 0)
Segmentation fault


```
---
