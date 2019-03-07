## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by winson2004aa@gmail.com, please send email to winson2004aa@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5FL__blk_gc_list_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack outputFuzz/crashes/H5FL__blk_gc_list_invalid-read-memory-access test 
==111714== Memcheck, a memory error detector
==111714== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==111714== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==111714== Command: ./h5repack outputFuzz/crashes/H5FL__blk_gc_list_invalid-read-memory-access test
==111714== 
--111714-- Valgrind options:
--111714--    -v
--111714--    --tool=memcheck
--111714--    --leak-check=full
--111714-- Contents of /proc/version:
--111714--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--111714-- 
--111714-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--111714-- Page sizes: currently 4096, max supported 4096
--111714-- Valgrind library directory: /usr/lib/valgrind
--111714-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--111714--    object doesn't have a symbol table
--111714-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--111714--   Considering /usr/lib/debug/.build-id/dc/5cb16f5e644116cac64a4c3f5da4d081b81a4f.debug ..
--111714--   .. build-id is valid
--111714-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--111714--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--111714--   .. CRC mismatch (computed 7680f3df wanted 92e0f93c)
--111714--   Considering /usr/lib/debug/usr/lib/valgrind/memcheck-amd64-linux ..
--111714--   .. CRC is valid
--111714--    object doesn't have a dynamic symbol table
--111714-- Scheduler: using generic scheduler lock implementation.
--111714-- Reading suppressions file: /usr/lib/valgrind/default.supp
==111714== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-111714-by-root-on-???
==111714== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-111714-by-root-on-???
==111714== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-111714-by-root-on-???
==111714== 
==111714== TO CONTROL THIS PROCESS USING vgdb (which you probably
==111714== don't want to do, unless you know exactly what you're doing,
==111714== or are doing some strange experiment):
==111714==   /usr/lib/valgrind/../../bin/vgdb --pid=111714 ...command...
==111714== 
==111714== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==111714==   /path/to/gdb ./h5repack
==111714== and then give GDB the following command
==111714==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=111714
==111714== --pid is optional if only one valgrind process is running
==111714== 
--111714-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x58061781 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--111714-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x5806179b (vgPlain_amd64_linux_REDIR_FOR_index)
--111714-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--111714--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--111714--   .. CRC mismatch (computed 66a2a561 wanted 3789c7eb)
--111714--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--111714--   .. CRC is valid
--111714-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--111714--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--111714--   .. CRC mismatch (computed 8487a070 wanted 8af30a91)
--111714--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--111714--   .. CRC is valid
==111714== WARNING: new redirection conflicts with existing -- ignoring it
--111714--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x58061781 vgPlain_amd64_linux_REDIR_FOR_strlen
--111714--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838a60 strlen
--111714-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839b90 (strcmp)
--111714-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d1a0 (mempcpy)
--111714-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--111714-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--111714--    object doesn't have a symbol table
--111714-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--111714--   Considering /usr/lib/debug/.build-id/b7/883b3fc771cfa5fcb452861bbb97a5b646259b.debug ..
--111714--   .. build-id is valid
--111714-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--111714--   Considering /usr/lib/debug/.build-id/fa/b2857727406caccd7ab22e1729b09ccf2c3eb7.debug ..
--111714--   .. build-id is valid
--111714-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--111714--   Considering /usr/lib/debug/.build-id/dc/87cd1e2b171a4c51139cb4e1f2ec630e711de3.debug ..
--111714--   .. build-id is valid
--111714-- REDIR: 0x598d050 (libc.so.6:memmove) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598c280 (libc.so.6:strncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d330 (libc.so.6:strcasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598bcd0 (libc.so.6:strcat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598c2b0 (libc.so.6:rindex) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598e900 (libc.so.6:rawmemchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d1c0 (libc.so.6:mempcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598cff0 (libc.so.6:bcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598c240 (libc.so.6:strncmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598bd40 (libc.so.6:strcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d120 (libc.so.6:memset) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x59a6b60 (libc.so.6:wcschr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598c1e0 (libc.so.6:strnlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598bdb0 (libc.so.6:strcspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d380 (libc.so.6:strncasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598bd80 (libc.so.6:strcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d4c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598c2e0 (libc.so.6:strpbrk) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598bd00 (libc.so.6:index) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598c1b0 (libc.so.6:strlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x59931b0 (libc.so.6:memrchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d3d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598cfc0 (libc.so.6:memchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x59a7920 (libc.so.6:wcslen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598c590 (libc.so.6:strspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d300 (libc.so.6:stpncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d2d0 (libc.so.6:stpcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598e930 (libc.so.6:strchrnul) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x598d420 (libc.so.6:strncasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x5a5f700 (libc.so.6:__strrchr_avx2) redirected to 0x48383e0 (rindex)
--111714-- REDIR: 0x5a5f8d0 (libc.so.6:__strlen_avx2) redirected to 0x48389a0 (strlen)
--111714-- REDIR: 0x59885c0 (libc.so.6:malloc) redirected to 0x4835750 (malloc)
--111714-- REDIR: 0x5a60290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c280 (memset)
--111714-- REDIR: 0x5a5f510 (libc.so.6:__strchrnul_avx2) redirected to 0x483ccd0 (strchrnul)
--111714-- REDIR: 0x5a4cc90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838a80 (strcpy)
--111714-- REDIR: 0x5988d60 (libc.so.6:realloc) redirected to 0x4837960 (realloc)
--111714-- REDIR: 0x5a5fe10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c390 (memmove)
--111714-- REDIR: 0x5988c50 (libc.so.6:free) redirected to 0x4836980 (free)
--111714-- REDIR: 0x5a4e440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838c60 (strncpy)
--111714-- REDIR: 0x5a3b0a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839a50 (strcmp)
--111714-- REDIR: 0x59892a0 (libc.so.6:calloc) redirected to 0x4837720 (calloc)
--111714-- REDIR: 0x598c210 (libc.so.6:strncat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--111714-- REDIR: 0x599e0f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838840 (strncat)
--111714-- REDIR: 0x5a5b3b0 (libc.so.6:__strcspn_sse42) redirected to 0x483d580 (strcspn)
==111714== Invalid read of size 2
==111714==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==111714==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111714==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111714==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111714==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111714==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111714==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111714==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111714==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111714==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==  Address 0x5e47ab8 is 0 bytes after a block of size 280 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111714==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111714==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111714==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111714==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111714==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111714==    by 0x4D19366: H5O_obj_type (H5Oint.c:1706)
==111714==    by 0x4FA090C: H5T__open_name (H5Tcommit.c:821)
==111714==    by 0x4FA0F4E: H5Topen2 (H5Tcommit.c:573)
==111714==    by 0x120257: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
==111714== Invalid read of size 2
==111714==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==111714==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111714==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111714==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111714==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111714==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111714==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111714==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111714==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111714==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==  Address 0x5e47abe is 6 bytes after a block of size 280 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111714==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111714==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111714==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111714==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111714==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111714==    by 0x4D19366: H5O_obj_type (H5Oint.c:1706)
==111714==    by 0x4FA090C: H5T__open_name (H5Tcommit.c:821)
==111714==    by 0x4FA0F4E: H5Topen2 (H5Tcommit.c:573)
==111714==    by 0x120257: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
--111714-- REDIR: 0x5a5f2e0 (libc.so.6:__strchr_avx2) redirected to 0x4838600 (index)
--111714-- REDIR: 0x5a5fdf0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483cde0 (mempcpy)
==111714== Invalid write of size 2
==111714==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==111714==    by 0x4D261C4: H5O__layout_encode (H5Olayout.c:580)
==111714==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==111714==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==111714==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==111714==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==111714==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==111714==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==111714==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==111714==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==111714==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==111714==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==111714==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==111714==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==111714==  Address 0x5e50e90 is 0 bytes after a block of size 112 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==111714==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==111714==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111714==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111714==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111714==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111714==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714== 
==111714== Invalid free() / delete / delete[] / realloc()
==111714==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111714==    by 0x4B522F4: H5FL__blk_gc_list (H5FL.c:1218)
==111714==    by 0x4B522F4: H5FL__blk_gc (H5FL.c:1266)
==111714==    by 0x4B522F4: H5FL_garbage_coll (H5FL.c:2457)
==111714==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==111714==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==111714==    by 0x4890850: H5close (H5.c:875)
==111714==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714==  Address 0x5e47a20 is 128 bytes inside a block of size 280 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111714==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111714==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111714==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111714==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111714==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111714==    by 0x4D19366: H5O_obj_type (H5Oint.c:1706)
==111714==    by 0x4FA090C: H5T__open_name (H5Tcommit.c:821)
==111714==    by 0x4FA0F4E: H5Topen2 (H5Tcommit.c:573)
==111714==    by 0x120257: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
==111714== Invalid read of size 8
==111714==    at 0x4B522DC: H5FL__blk_gc_list (H5FL.c:1208)
==111714==    by 0x4B522DC: H5FL__blk_gc (H5FL.c:1266)
==111714==    by 0x4B522DC: H5FL_garbage_coll (H5FL.c:2457)
==111714==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==111714==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==111714==    by 0x4890850: H5close (H5.c:875)
==111714==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714==  Address 0x4aceadd500000001 is not stack'd, malloc'd or (recently) free'd
==111714== 
==111714== 
==111714== Process terminating with default action of signal 11 (SIGSEGV)
==111714==  General Protection Fault
==111714==    at 0x4B522DC: H5FL__blk_gc_list (H5FL.c:1208)
==111714==    by 0x4B522DC: H5FL__blk_gc (H5FL.c:1266)
==111714==    by 0x4B522DC: H5FL_garbage_coll (H5FL.c:2457)
==111714==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==111714==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==111714==    by 0x4890850: H5close (H5.c:875)
==111714==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714== 
==111714== HEAP SUMMARY:
==111714==     in use at exit: 180,983 bytes in 2,030 blocks
==111714==   total heap usage: 3,703 allocs, 1,674 frees, 3,533,080 bytes allocated
==111714== 
==111714== Searching for pointers to 2,030 not-freed blocks
==111714== Checked 308,216 bytes
==111714== 
==111714== 15 bytes in 1 blocks are definitely lost in loss record 6 of 1,714
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4BA9A6C: H5G_build_fullpath (H5Gname.c:318)
==111714==    by 0x4BA9A6C: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111714==    by 0x4BAA72B: H5G_name_set (H5Gname.c:478)
==111714==    by 0x4C67FB3: H5L__link_cb (H5L.c:1662)
==111714==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111714==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111714==    by 0x4C5EF49: H5L__create_real.part.2 (H5L.c:1812)
==111714==    by 0x4C6C18E: H5L__create_real (H5L.c:1765)
==111714==    by 0x4C6C18E: H5L_link (H5L.c:1528)
==111714==    by 0x4CEA6A5: H5O__copy_obj (H5Ocopy.c:1228)
==111714==    by 0x4CEA6A5: H5O__copy (H5Ocopy.c:316)
==111714==    by 0x4CEA6A5: H5Ocopy (H5Ocopy.c:232)
==111714==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
==111714== 16 bytes in 1 blocks are definitely lost in loss record 86 of 1,714
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B53CA4: H5FL_reg_malloc (H5FL.c:441)
==111714==    by 0x4E37B6C: H5RS_own (H5RS.c:189)
==111714==    by 0x4BA9B55: H5G_build_fullpath (H5Gname.c:328)
==111714==    by 0x4BA9B55: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111714==    by 0x4BAA72B: H5G_name_set (H5Gname.c:478)
==111714==    by 0x4C67FB3: H5L__link_cb (H5L.c:1662)
==111714==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==111714==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111714==    by 0x4C5EF49: H5L__create_real.part.2 (H5L.c:1812)
==111714==    by 0x4C6C18E: H5L__create_real (H5L.c:1765)
==111714==    by 0x4C6C18E: H5L_link (H5L.c:1528)
==111714==    by 0x4CEA6A5: H5O__copy_obj (H5Ocopy.c:1228)
==111714==    by 0x4CEA6A5: H5O__copy (H5Ocopy.c:316)
==111714==    by 0x4CEA6A5: H5Ocopy (H5Ocopy.c:232)
==111714== 
==111714== 30 (15 direct, 15 indirect) bytes in 1 blocks are definitely lost in loss record 540 of 1,714
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4BA9A6C: H5G_build_fullpath (H5Gname.c:318)
==111714==    by 0x4BA9A6C: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111714==    by 0x4BAA65F: H5G_name_set (H5Gname.c:471)
==111714==    by 0x4BA2685: H5G__link_to_loc (H5Glink.c:390)
==111714==    by 0x4BCFC28: H5G__traverse_real.isra.0 (H5Gtraverse.c:593)
==111714==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111714==    by 0x4BA7C03: H5G_loc_info (H5Gloc.c:730)
==111714==    by 0x4D1DB8C: H5O__get_info_by_name (H5Oint.c:2375)
==111714==    by 0x4C9F4FC: H5Oget_info_by_name2 (H5O.c:518)
==111714==    by 0x190570: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
==111714== 32 (16 direct, 16 indirect) bytes in 1 blocks are definitely lost in loss record 568 of 1,714
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B53CA4: H5FL_reg_malloc (H5FL.c:441)
==111714==    by 0x4E37B6C: H5RS_own (H5RS.c:189)
==111714==    by 0x4BA9B55: H5G_build_fullpath (H5Gname.c:328)
==111714==    by 0x4BA9B55: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==111714==    by 0x4BAA65F: H5G_name_set (H5Gname.c:471)
==111714==    by 0x4BA2685: H5G__link_to_loc (H5Glink.c:390)
==111714==    by 0x4BCFC28: H5G__traverse_real.isra.0 (H5Gtraverse.c:593)
==111714==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==111714==    by 0x4BA7C03: H5G_loc_info (H5Gloc.c:730)
==111714==    by 0x4D1DB8C: H5O__get_info_by_name (H5Oint.c:2375)
==111714==    by 0x4C9F4FC: H5Oget_info_by_name2 (H5O.c:518)
==111714== 
==111714== 752 (16 direct, 736 indirect) bytes in 1 blocks are definitely lost in loss record 1,698 of 1,714
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B53BE9: H5FL_reg_init (H5FL.c:283)
==111714==    by 0x4B53BE9: H5FL_reg_malloc (H5FL.c:422)
==111714==    by 0x4B53F8F: H5FL_reg_calloc (H5FL.c:498)
==111714==    by 0x4A3F7FB: H5O__dset_get_copy_file_udata (H5Doh.c:113)
==111714==    by 0x4CE1C55: H5O__copy_header_real (H5Ocopy.c:394)
==111714==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111714==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111714==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111714==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111714==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714== 
==111714== LEAK SUMMARY:
==111714==    definitely lost: 78 bytes in 5 blocks
==111714==    indirectly lost: 767 bytes in 48 blocks
==111714==      possibly lost: 0 bytes in 0 blocks
==111714==    still reachable: 180,138 bytes in 1,977 blocks
==111714==         suppressed: 0 bytes in 0 blocks
==111714== Reachable blocks (those to which a pointer was found) are not shown.
==111714== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==111714== 
==111714== ERROR SUMMARY: 1967 errors from 10 contexts (suppressed: 0 from 0)
==111714== 
==111714== 1 errors in context 1 of 10:
==111714== Invalid read of size 8
==111714==    at 0x4B522DC: H5FL__blk_gc_list (H5FL.c:1208)
==111714==    by 0x4B522DC: H5FL__blk_gc (H5FL.c:1266)
==111714==    by 0x4B522DC: H5FL_garbage_coll (H5FL.c:2457)
==111714==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==111714==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==111714==    by 0x4890850: H5close (H5.c:875)
==111714==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714==  Address 0x4aceadd500000001 is not stack'd, malloc'd or (recently) free'd
==111714== 
==111714== 
==111714== 1 errors in context 2 of 10:
==111714== Invalid free() / delete / delete[] / realloc()
==111714==    at 0x48369EB: free (vg_replace_malloc.c:530)
==111714==    by 0x4B522F4: H5FL__blk_gc_list (H5FL.c:1218)
==111714==    by 0x4B522F4: H5FL__blk_gc (H5FL.c:1266)
==111714==    by 0x4B522F4: H5FL_garbage_coll (H5FL.c:2457)
==111714==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==111714==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==111714==    by 0x4890850: H5close (H5.c:875)
==111714==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714==  Address 0x5e47a20 is 128 bytes inside a block of size 280 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111714==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111714==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111714==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111714==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111714==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111714==    by 0x4D19366: H5O_obj_type (H5Oint.c:1706)
==111714==    by 0x4FA090C: H5T__open_name (H5Tcommit.c:821)
==111714==    by 0x4FA0F4E: H5Topen2 (H5Tcommit.c:573)
==111714==    by 0x120257: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
==111714== 
==111714== 176 errors in context 3 of 10:
==111714== Invalid read of size 2
==111714==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==111714==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111714==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111714==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111714==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111714==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111714==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111714==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111714==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111714==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==  Address 0x5e47abe is 6 bytes after a block of size 280 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111714==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111714==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111714==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111714==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111714==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111714==    by 0x4D19366: H5O_obj_type (H5Oint.c:1706)
==111714==    by 0x4FA090C: H5T__open_name (H5Tcommit.c:821)
==111714==    by 0x4FA0F4E: H5Topen2 (H5Tcommit.c:573)
==111714==    by 0x120257: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
==111714== 
==111714== 528 errors in context 4 of 10:
==111714== Invalid read of size 2
==111714==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==111714==    by 0x4D2A7D3: H5O__layout_decode (H5Olayout.c:213)
==111714==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==111714==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==111714==    by 0x4A3A507: H5D__layout_oh_read (H5Dlayout.c:634)
==111714==    by 0x4A27B85: H5D__open_oid (H5Dint.c:1489)
==111714==    by 0x4A27B85: H5D_open (H5Dint.c:1281)
==111714==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==111714==    by 0x499087F: H5Dopen2 (H5D.c:291)
==111714==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==  Address 0x5e47ab8 is 0 bytes after a block of size 280 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==111714==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==111714==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==111714==    by 0x4960D56: H5C_protect (H5C.c:2357)
==111714==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==111714==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==111714==    by 0x4D19366: H5O_obj_type (H5Oint.c:1706)
==111714==    by 0x4FA090C: H5T__open_name (H5Tcommit.c:821)
==111714==    by 0x4FA0F4E: H5Topen2 (H5Tcommit.c:573)
==111714==    by 0x120257: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714== 
==111714== 
==111714== 1256 errors in context 5 of 10:
==111714== Invalid write of size 2
==111714==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==111714==    by 0x4D261C4: H5O__layout_encode (H5Olayout.c:580)
==111714==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==111714==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==111714==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==111714==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==111714==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==111714==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==111714==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==111714==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==111714==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==111714==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==111714==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==111714==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==111714==  Address 0x5e50e90 is 0 bytes after a block of size 112 alloc'd
==111714==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==111714==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==111714==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==111714==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==111714==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==111714==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==111714==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==111714==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==111714==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==111714==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==111714==    by 0x5927B16: (below main) (libc-start.c:310)
==111714== 
==111714== ERROR SUMMARY: 1967 errors from 10 contexts (suppressed: 0 from 0)
Segmentation fault


```
---
