## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by winson2004aa@gmail.com, please send email to winson2004aa@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## memmove_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack outputFuzz/crashes/memmove_invalid-read-memory-access test
==59036== Memcheck, a memory error detector
==59036== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==59036== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==59036== Command: ./h5repack outputFuzz/crashes/id:000118,sig:06,src:000436,op:flip1,pos:825 test
==59036== 
--59036-- Valgrind options:
--59036--    -v
--59036--    --tool=memcheck
--59036--    --leak-check=full
--59036-- Contents of /proc/version:
--59036--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--59036-- 
--59036-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--59036-- Page sizes: currently 4096, max supported 4096
--59036-- Valgrind library directory: /usr/lib/valgrind
--59036-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--59036--    object doesn't have a symbol table
--59036-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--59036--   Considering /usr/lib/debug/.build-id/dc/5cb16f5e644116cac64a4c3f5da4d081b81a4f.debug ..
--59036--   .. build-id is valid
--59036-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--59036--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--59036--   .. CRC mismatch (computed 7680f3df wanted 92e0f93c)
--59036--   Considering /usr/lib/debug/usr/lib/valgrind/memcheck-amd64-linux ..
--59036--   .. CRC is valid
--59036--    object doesn't have a dynamic symbol table
--59036-- Scheduler: using generic scheduler lock implementation.
--59036-- Reading suppressions file: /usr/lib/valgrind/default.supp
==59036== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-59036-by-root-on-???
==59036== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-59036-by-root-on-???
==59036== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-59036-by-root-on-???
==59036== 
==59036== TO CONTROL THIS PROCESS USING vgdb (which you probably
==59036== don't want to do, unless you know exactly what you're doing,
==59036== or are doing some strange experiment):
==59036==   /usr/lib/valgrind/../../bin/vgdb --pid=59036 ...command...
==59036== 
==59036== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==59036==   /path/to/gdb ./h5repack
==59036== and then give GDB the following command
==59036==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=59036
==59036== --pid is optional if only one valgrind process is running
==59036== 
--59036-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x58061781 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--59036-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x5806179b (vgPlain_amd64_linux_REDIR_FOR_index)
--59036-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--59036--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59036--   .. CRC mismatch (computed 66a2a561 wanted 3789c7eb)
--59036--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59036--   .. CRC is valid
--59036-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--59036--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59036--   .. CRC mismatch (computed 8487a070 wanted 8af30a91)
--59036--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59036--   .. CRC is valid
==59036== WARNING: new redirection conflicts with existing -- ignoring it
--59036--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x58061781 vgPlain_amd64_linux_REDIR_FOR_strlen
--59036--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838a60 strlen
--59036-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839b90 (strcmp)
--59036-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d1a0 (mempcpy)
--59036-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--59036-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--59036--    object doesn't have a symbol table
--59036-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--59036--   Considering /usr/lib/debug/.build-id/b7/883b3fc771cfa5fcb452861bbb97a5b646259b.debug ..
--59036--   .. build-id is valid
--59036-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--59036--   Considering /usr/lib/debug/.build-id/fa/b2857727406caccd7ab22e1729b09ccf2c3eb7.debug ..
--59036--   .. build-id is valid
--59036-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--59036--   Considering /usr/lib/debug/.build-id/dc/87cd1e2b171a4c51139cb4e1f2ec630e711de3.debug ..
--59036--   .. build-id is valid
--59036-- REDIR: 0x598d050 (libc.so.6:memmove) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598c280 (libc.so.6:strncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d330 (libc.so.6:strcasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598bcd0 (libc.so.6:strcat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598c2b0 (libc.so.6:rindex) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598e900 (libc.so.6:rawmemchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d1c0 (libc.so.6:mempcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598cff0 (libc.so.6:bcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598c240 (libc.so.6:strncmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598bd40 (libc.so.6:strcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d120 (libc.so.6:memset) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x59a6b60 (libc.so.6:wcschr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598c1e0 (libc.so.6:strnlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598bdb0 (libc.so.6:strcspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d380 (libc.so.6:strncasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598bd80 (libc.so.6:strcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d4c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598c2e0 (libc.so.6:strpbrk) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598bd00 (libc.so.6:index) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598c1b0 (libc.so.6:strlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x59931b0 (libc.so.6:memrchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d3d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598cfc0 (libc.so.6:memchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x59a7920 (libc.so.6:wcslen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598c590 (libc.so.6:strspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d300 (libc.so.6:stpncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d2d0 (libc.so.6:stpcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598e930 (libc.so.6:strchrnul) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x598d420 (libc.so.6:strncasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x5a5f700 (libc.so.6:__strrchr_avx2) redirected to 0x48383e0 (rindex)
--59036-- REDIR: 0x5a5f8d0 (libc.so.6:__strlen_avx2) redirected to 0x48389a0 (strlen)
--59036-- REDIR: 0x59885c0 (libc.so.6:malloc) redirected to 0x4835750 (malloc)
--59036-- REDIR: 0x5a60290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c280 (memset)
--59036-- REDIR: 0x5a5f510 (libc.so.6:__strchrnul_avx2) redirected to 0x483ccd0 (strchrnul)
--59036-- REDIR: 0x5a4cc90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838a80 (strcpy)
--59036-- REDIR: 0x5988d60 (libc.so.6:realloc) redirected to 0x4837960 (realloc)
--59036-- REDIR: 0x5a5fe10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c390 (memmove)
--59036-- REDIR: 0x5988c50 (libc.so.6:free) redirected to 0x4836980 (free)
--59036-- REDIR: 0x5a4e440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838c60 (strncpy)
--59036-- REDIR: 0x5a3b0a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839a50 (strcmp)
--59036-- REDIR: 0x59892a0 (libc.so.6:calloc) redirected to 0x4837720 (calloc)
--59036-- REDIR: 0x598c210 (libc.so.6:strncat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59036-- REDIR: 0x599e0f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838840 (strncat)
--59036-- REDIR: 0x5a5b3b0 (libc.so.6:__strcspn_sse42) redirected to 0x483d580 (strcspn)
==59036== Invalid read of size 2
==59036==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==59036==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==59036==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==59036==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59036==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59036==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==59036==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==59036==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59036==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59036==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036==  Address 0x5c42898 is 0 bytes after a block of size 280 alloc'd
==59036==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59036==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59036==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59036==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59036==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59036==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59036==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59036==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59036==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59036==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59036==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59036==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59036==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59036== 
==59036== Invalid read of size 2
==59036==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==59036==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==59036==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==59036==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59036==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59036==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==59036==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==59036==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59036==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59036==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036==  Address 0x5c4289a is 2 bytes after a block of size 280 alloc'd
==59036==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59036==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59036==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59036==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59036==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59036==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59036==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59036==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59036==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59036==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59036==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59036==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59036==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59036== 
--59036-- REDIR: 0x5a5f2e0 (libc.so.6:__strchr_avx2) redirected to 0x4838600 (index)
--59036-- REDIR: 0x5a5fdf0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483cde0 (mempcpy)
==59036== Invalid write of size 2
==59036==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==59036==    by 0x4D09B0C: H5O_fill_new_encode (H5Ofill.c:462)
==59036==    by 0x4D09B0C: H5O_fill_new_shared_encode (H5Oshared.h:137)
==59036==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59036==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59036==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59036==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59036==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59036==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59036==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59036==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59036==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59036==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59036==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59036==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59036==  Address 0x5c4b818 is 0 bytes after a block of size 136 alloc'd
==59036==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59036==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59036==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59036==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59036==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59036==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59036==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59036==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59036==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59036==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036== 
==59036== Invalid read of size 8
==59036==    at 0x4B5010C: H5FL__reg_gc_list (H5FL.c:535)
==59036==    by 0x4B5010C: H5FL__reg_gc (H5FL.c:589)
==59036==    by 0x4B51F88: H5FL_garbage_coll (H5FL.c:2461)
==59036==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==59036==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==59036==    by 0x4890850: H5close (H5.c:875)
==59036==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036==  Address 0x20 is not stack'd, malloc'd or (recently) free'd
==59036== 
==59036== 
==59036== Process terminating with default action of signal 11 (SIGSEGV)
==59036==  Access not within mapped region at address 0x20
==59036==    at 0x4B5010C: H5FL__reg_gc_list (H5FL.c:535)
==59036==    by 0x4B5010C: H5FL__reg_gc (H5FL.c:589)
==59036==    by 0x4B51F88: H5FL_garbage_coll (H5FL.c:2461)
==59036==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==59036==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==59036==    by 0x4890850: H5close (H5.c:875)
==59036==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036==  If you believe this happened as a result of a stack
==59036==  overflow in your program's main thread (unlikely but
==59036==  possible), you can try to increase the size of the
==59036==  main thread stack using the --main-stacksize= flag.
==59036==  The main thread stack size used in this run was 8388608.
==59036== 
==59036== HEAP SUMMARY:
==59036==     in use at exit: 180,592 bytes in 2,006 blocks
==59036==   total heap usage: 3,650 allocs, 1,644 frees, 1,425,375 bytes allocated
==59036== 
==59036== Searching for pointers to 2,006 not-freed blocks
==59036== Checked 307,208 bytes
==59036== 
==59036== 752 (16 direct, 736 indirect) bytes in 1 blocks are definitely lost in loss record 1,670 of 1,688
==59036==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59036==    by 0x4B53BE9: H5FL_reg_init (H5FL.c:283)
==59036==    by 0x4B53BE9: H5FL_reg_malloc (H5FL.c:422)
==59036==    by 0x4B53F8F: H5FL_reg_calloc (H5FL.c:498)
==59036==    by 0x4A3F7FB: H5O__dset_get_copy_file_udata (H5Doh.c:113)
==59036==    by 0x4CE1C55: H5O__copy_header_real (H5Ocopy.c:394)
==59036==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59036==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59036==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59036==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59036==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036== 
==59036== LEAK SUMMARY:
==59036==    definitely lost: 16 bytes in 1 blocks
==59036==    indirectly lost: 736 bytes in 46 blocks
==59036==      possibly lost: 0 bytes in 0 blocks
==59036==    still reachable: 179,840 bytes in 1,959 blocks
==59036==         suppressed: 0 bytes in 0 blocks
==59036== Reachable blocks (those to which a pointer was found) are not shown.
==59036== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==59036== 
==59036== ERROR SUMMARY: 145 errors from 5 contexts (suppressed: 0 from 0)
==59036== 
==59036== 1 errors in context 1 of 5:
==59036== Invalid read of size 8
==59036==    at 0x4B5010C: H5FL__reg_gc_list (H5FL.c:535)
==59036==    by 0x4B5010C: H5FL__reg_gc (H5FL.c:589)
==59036==    by 0x4B51F88: H5FL_garbage_coll (H5FL.c:2461)
==59036==    by 0x4B52854: H5FL_term_package (H5FL.c:184)
==59036==    by 0x488E944: H5_term_library.part.0 (H5.c:359)
==59036==    by 0x4890850: H5close (H5.c:875)
==59036==    by 0x14BB5A: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x10F13C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036==  Address 0x20 is not stack'd, malloc'd or (recently) free'd
==59036== 
==59036== 
==59036== 2 errors in context 2 of 5:
==59036== Invalid read of size 2
==59036==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==59036==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==59036==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==59036==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59036==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59036==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==59036==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==59036==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59036==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59036==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036==  Address 0x5c42898 is 0 bytes after a block of size 280 alloc'd
==59036==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59036==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59036==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59036==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59036==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59036==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59036==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59036==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59036==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59036==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59036==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59036==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59036==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59036== 
==59036== 
==59036== 5 errors in context 3 of 5:
==59036== Invalid read of size 2
==59036==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==59036==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==59036==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==59036==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==59036==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==59036==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==59036==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==59036==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==59036==    by 0x499087F: H5Dopen2 (H5D.c:291)
==59036==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036==  Address 0x5c4289a is 2 bytes after a block of size 280 alloc'd
==59036==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59036==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59036==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59036==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==59036==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==59036==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==59036==    by 0x4960D56: H5C_protect (H5C.c:2357)
==59036==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==59036==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==59036==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==59036==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==59036==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==59036==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==59036== 
==59036== 
==59036== 136 errors in context 4 of 5:
==59036== Invalid write of size 2
==59036==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==59036==    by 0x4D09B0C: H5O_fill_new_encode (H5Ofill.c:462)
==59036==    by 0x4D09B0C: H5O_fill_new_shared_encode (H5Oshared.h:137)
==59036==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59036==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59036==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59036==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59036==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59036==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59036==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59036==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59036==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59036==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59036==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59036==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59036==  Address 0x5c4b818 is 0 bytes after a block of size 136 alloc'd
==59036==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59036==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59036==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59036==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59036==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59036==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59036==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59036==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59036==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59036==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59036==    by 0x5927B16: (below main) (libc-start.c:310)
==59036== 
==59036== ERROR SUMMARY: 145 errors from 5 contexts (suppressed: 0 from 0)
Segmentation fault


```
---
