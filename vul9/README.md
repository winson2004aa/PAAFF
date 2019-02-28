## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by winson2004aa@gmail.com, please send email to winson2004aa@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5C_flush_invalidate_ring_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack outputFuzz/crashes/H5C_flush_invalidate_ring_invalid-read-memory-access test
==84622== Memcheck, a memory error detector
==84622== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==84622== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==84622== Command: ./h5repack outputFuzz/crashes/H5C_flush_invalidate_ring_invalid-read-memory-access test
==84622== 
--84622-- Valgrind options:
--84622--    -v
--84622--    --tool=memcheck
--84622--    --leak-check=full
--84622-- Contents of /proc/version:
--84622--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--84622-- 
--84622-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--84622-- Page sizes: currently 4096, max supported 4096
--84622-- Valgrind library directory: /usr/lib/valgrind
--84622-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--84622--    object doesn't have a symbol table
--84622-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--84622--   Considering /usr/lib/debug/.build-id/dc/5cb16f5e644116cac64a4c3f5da4d081b81a4f.debug ..
--84622--   .. build-id is valid
--84622-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--84622--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--84622--   .. CRC mismatch (computed 7680f3df wanted 92e0f93c)
--84622--   Considering /usr/lib/debug/usr/lib/valgrind/memcheck-amd64-linux ..
--84622--   .. CRC is valid
--84622--    object doesn't have a dynamic symbol table
--84622-- Scheduler: using generic scheduler lock implementation.
--84622-- Reading suppressions file: /usr/lib/valgrind/default.supp
==84622== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-84622-by-root-on-???
==84622== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-84622-by-root-on-???
==84622== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-84622-by-root-on-???
==84622== 
==84622== TO CONTROL THIS PROCESS USING vgdb (which you probably
==84622== don't want to do, unless you know exactly what you're doing,
==84622== or are doing some strange experiment):
==84622==   /usr/lib/valgrind/../../bin/vgdb --pid=84622 ...command...
==84622== 
==84622== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==84622==   /path/to/gdb ./h5repack
==84622== and then give GDB the following command
==84622==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=84622
==84622== --pid is optional if only one valgrind process is running
==84622== 
--84622-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x58061781 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--84622-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x5806179b (vgPlain_amd64_linux_REDIR_FOR_index)
--84622-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--84622--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--84622--   .. CRC mismatch (computed 66a2a561 wanted 3789c7eb)
--84622--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--84622--   .. CRC is valid
--84622-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--84622--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--84622--   .. CRC mismatch (computed 8487a070 wanted 8af30a91)
--84622--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--84622--   .. CRC is valid
==84622== WARNING: new redirection conflicts with existing -- ignoring it
--84622--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x58061781 vgPlain_amd64_linux_REDIR_FOR_strlen
--84622--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838a60 strlen
--84622-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839b90 (strcmp)
--84622-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d1a0 (mempcpy)
--84622-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--84622-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--84622--    object doesn't have a symbol table
--84622-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--84622--   Considering /usr/lib/debug/.build-id/b7/883b3fc771cfa5fcb452861bbb97a5b646259b.debug ..
--84622--   .. build-id is valid
--84622-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--84622--   Considering /usr/lib/debug/.build-id/fa/b2857727406caccd7ab22e1729b09ccf2c3eb7.debug ..
--84622--   .. build-id is valid
--84622-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--84622--   Considering /usr/lib/debug/.build-id/dc/87cd1e2b171a4c51139cb4e1f2ec630e711de3.debug ..
--84622--   .. build-id is valid
--84622-- REDIR: 0x598d050 (libc.so.6:memmove) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598c280 (libc.so.6:strncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d330 (libc.so.6:strcasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598bcd0 (libc.so.6:strcat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598c2b0 (libc.so.6:rindex) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598e900 (libc.so.6:rawmemchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d1c0 (libc.so.6:mempcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598cff0 (libc.so.6:bcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598c240 (libc.so.6:strncmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598bd40 (libc.so.6:strcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d120 (libc.so.6:memset) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x59a6b60 (libc.so.6:wcschr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598c1e0 (libc.so.6:strnlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598bdb0 (libc.so.6:strcspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d380 (libc.so.6:strncasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598bd80 (libc.so.6:strcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d4c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598c2e0 (libc.so.6:strpbrk) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598bd00 (libc.so.6:index) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598c1b0 (libc.so.6:strlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x59931b0 (libc.so.6:memrchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d3d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598cfc0 (libc.so.6:memchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x59a7920 (libc.so.6:wcslen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598c590 (libc.so.6:strspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d300 (libc.so.6:stpncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d2d0 (libc.so.6:stpcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598e930 (libc.so.6:strchrnul) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x598d420 (libc.so.6:strncasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x5a5f700 (libc.so.6:__strrchr_avx2) redirected to 0x48383e0 (rindex)
--84622-- REDIR: 0x5a5f8d0 (libc.so.6:__strlen_avx2) redirected to 0x48389a0 (strlen)
--84622-- REDIR: 0x59885c0 (libc.so.6:malloc) redirected to 0x4835750 (malloc)
--84622-- REDIR: 0x5a60290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c280 (memset)
--84622-- REDIR: 0x5a5f510 (libc.so.6:__strchrnul_avx2) redirected to 0x483ccd0 (strchrnul)
--84622-- REDIR: 0x5a4cc90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838a80 (strcpy)
--84622-- REDIR: 0x5988d60 (libc.so.6:realloc) redirected to 0x4837960 (realloc)
--84622-- REDIR: 0x5a5fe10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c390 (memmove)
--84622-- REDIR: 0x5988c50 (libc.so.6:free) redirected to 0x4836980 (free)
--84622-- REDIR: 0x5a4e440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838c60 (strncpy)
--84622-- REDIR: 0x5a3b0a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839a50 (strcmp)
--84622-- REDIR: 0x59892a0 (libc.so.6:calloc) redirected to 0x4837720 (calloc)
--84622-- REDIR: 0x598c210 (libc.so.6:strncat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--84622-- REDIR: 0x599e0f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838840 (strncat)
--84622-- REDIR: 0x5a5b3b0 (libc.so.6:__strcspn_sse42) redirected to 0x483d580 (strcspn)
==84622== Invalid read of size 2
==84622==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==84622==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==84622==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==84622==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==84622==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==84622==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==84622==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==84622==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==84622==    by 0x499087F: H5Dopen2 (H5D.c:291)
==84622==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x5927B16: (below main) (libc-start.c:310)
==84622==  Address 0x5c42898 is 0 bytes after a block of size 280 alloc'd
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==84622==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==84622==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==84622==    by 0x4960D56: H5C_protect (H5C.c:2357)
==84622==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==84622==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==84622==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==84622==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==84622==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==84622==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==84622== 
==84622== Invalid read of size 2
==84622==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==84622==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==84622==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==84622==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==84622==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==84622==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==84622==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==84622==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==84622==    by 0x499087F: H5Dopen2 (H5D.c:291)
==84622==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x5927B16: (below main) (libc-start.c:310)
==84622==  Address 0x5c4289a is 2 bytes after a block of size 280 alloc'd
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==84622==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==84622==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==84622==    by 0x4960D56: H5C_protect (H5C.c:2357)
==84622==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==84622==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==84622==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==84622==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==84622==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==84622==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==84622== 
--84622-- REDIR: 0x5a5f2e0 (libc.so.6:__strchr_avx2) redirected to 0x4838600 (index)
--84622-- REDIR: 0x5a5fdf0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483cde0 (mempcpy)
==84622== Invalid write of size 2
==84622==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==84622==    by 0x4D09B0C: H5O_fill_new_encode (H5Ofill.c:462)
==84622==    by 0x4D09B0C: H5O_fill_new_shared_encode (H5Oshared.h:137)
==84622==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==84622==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==84622==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==84622==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==84622==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==84622==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==84622==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==84622==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==84622==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==84622==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==84622==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==84622==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==84622==  Address 0x5c53418 is 0 bytes after a block of size 136 alloc'd
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==84622==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==84622==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==84622==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==84622==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==84622==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==84622==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x5927B16: (below main) (libc-start.c:310)
==84622== 
==84622== Invalid read of size 1
==84622==    at 0x4957130: H5C_flush_invalidate_ring (H5C.c:5520)
==84622==    by 0x4957130: H5C__flush_invalidate_cache (H5C.c:5154)
==84622==    by 0x4958189: H5C_dest (H5C.c:850)
==84622==    by 0x48E268F: H5AC_dest (H5AC.c:524)
==84622==    by 0x4AD1387: H5F__dest (H5Fint.c:1251)
==84622==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==84622==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==84622==    by 0x4C56332: H5I_dec_ref (H5I.c:1263)
==84622==    by 0x4C56893: H5I_dec_app_ref (H5I.c:1308)
==84622==    by 0x4AD3A5B: H5F__close (H5Fint.c:2046)
==84622==    by 0x4AAE0DB: H5Fclose (H5F.c:667)
==84622==    by 0x12D1EA: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==  Address 0x153 is not stack'd, malloc'd or (recently) free'd
==84622== 
==84622== 
==84622== Process terminating with default action of signal 11 (SIGSEGV)
==84622==  Access not within mapped region at address 0x153
==84622==    at 0x4957130: H5C_flush_invalidate_ring (H5C.c:5520)
==84622==    by 0x4957130: H5C__flush_invalidate_cache (H5C.c:5154)
==84622==    by 0x4958189: H5C_dest (H5C.c:850)
==84622==    by 0x48E268F: H5AC_dest (H5AC.c:524)
==84622==    by 0x4AD1387: H5F__dest (H5Fint.c:1251)
==84622==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==84622==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==84622==    by 0x4C56332: H5I_dec_ref (H5I.c:1263)
==84622==    by 0x4C56893: H5I_dec_app_ref (H5I.c:1308)
==84622==    by 0x4AD3A5B: H5F__close (H5Fint.c:2046)
==84622==    by 0x4AAE0DB: H5Fclose (H5F.c:667)
==84622==    by 0x12D1EA: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==  If you believe this happened as a result of a stack
==84622==  overflow in your program's main thread (unlikely but
==84622==  possible), you can try to increase the size of the
==84622==  main thread stack using the --main-stacksize= flag.
==84622==  The main thread stack size used in this run was 8388608.
==84622== 
==84622== HEAP SUMMARY:
==84622==     in use at exit: 845,796 bytes in 3,294 blocks
==84622==   total heap usage: 3,800 allocs, 506 frees, 1,575,483 bytes allocated
==84622== 
==84622== Searching for pointers to 3,294 not-freed blocks
==84622== Checked 948,968 bytes
==84622== 
==84622== 15 bytes in 1 blocks are definitely lost in loss record 386 of 2,736
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4BA9A6C: H5G_build_fullpath (H5Gname.c:318)
==84622==    by 0x4BA9A6C: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==84622==    by 0x4BAA65F: H5G_name_set (H5Gname.c:471)
==84622==    by 0x4C67FB3: H5L__link_cb (H5L.c:1662)
==84622==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==84622==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==84622==    by 0x4C5EF49: H5L__create_real.part.2 (H5L.c:1812)
==84622==    by 0x4C6C18E: H5L__create_real (H5L.c:1765)
==84622==    by 0x4C6C18E: H5L_link (H5L.c:1528)
==84622==    by 0x4CEA6A5: H5O__copy_obj (H5Ocopy.c:1228)
==84622==    by 0x4CEA6A5: H5O__copy (H5Ocopy.c:316)
==84622==    by 0x4CEA6A5: H5Ocopy (H5Ocopy.c:232)
==84622==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622== 
==84622== 16 bytes in 1 blocks are definitely lost in loss record 583 of 2,736
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B53CA4: H5FL_reg_malloc (H5FL.c:441)
==84622==    by 0x4E37B6C: H5RS_own (H5RS.c:189)
==84622==    by 0x4BA9B55: H5G_build_fullpath (H5Gname.c:328)
==84622==    by 0x4BA9B55: H5G_build_fullpath_refstr_str (H5Gname.c:365)
==84622==    by 0x4BAA65F: H5G_name_set (H5Gname.c:471)
==84622==    by 0x4C67FB3: H5L__link_cb (H5L.c:1662)
==84622==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==84622==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==84622==    by 0x4C5EF49: H5L__create_real.part.2 (H5L.c:1812)
==84622==    by 0x4C6C18E: H5L__create_real (H5L.c:1765)
==84622==    by 0x4C6C18E: H5L_link (H5L.c:1528)
==84622==    by 0x4CEA6A5: H5O__copy_obj (H5Ocopy.c:1228)
==84622==    by 0x4CEA6A5: H5O__copy (H5Ocopy.c:316)
==84622==    by 0x4CEA6A5: H5Ocopy (H5Ocopy.c:232)
==84622== 
==84622== 112 (16 direct, 96 indirect) bytes in 1 blocks are definitely lost in loss record 2,202 of 2,736
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5781A: H5FL_fac_malloc (H5FL.c:2158)
==84622==    by 0x4EDF4D4: H5SL_insert_common (H5SL.c:807)
==84622==    by 0x4EE73A8: H5SL_insert (H5SL.c:1121)
==84622==    by 0x4C5323F: H5I_register (H5I.c:741)
==84622==    by 0x4DE85C9: H5P_copy_plist (H5Pint.c:905)
==84622==    by 0x4A152C1: H5D__new (H5Dint.c:489)
==84622==    by 0x4A277EA: H5D__open_oid (H5Dint.c:1459)
==84622==    by 0x4A277EA: H5D_open (H5Dint.c:1281)
==84622==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==84622==    by 0x499087F: H5Dopen2 (H5D.c:291)
==84622==    by 0x120B6C: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622== 
==84622== 328 bytes in 1 blocks are definitely lost in loss record 2,676 of 2,736
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==84622==    by 0x4BB09E6: H5G__node_create.part.6 (H5Gnode.c:340)
==84622==    by 0x4900DC5: H5B__insert_helper (H5B.c:871)
==84622==    by 0x49039D3: H5B_insert (H5B.c:595)
==84622==    by 0x4BC2CC6: H5G__stab_insert_real (H5Gstab.c:285)
==84622==    by 0x4BC30D2: H5G__stab_insert (H5Gstab.c:330)
==84622==    by 0x4BB8CE5: H5G_obj_insert (H5Gobj.c:589)
==84622==    by 0x4C67588: H5L__link_cb (H5L.c:1655)
==84622==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==84622== 
==84622== 752 (16 direct, 736 indirect) bytes in 1 blocks are definitely lost in loss record 2,709 of 2,736
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B53BE9: H5FL_reg_init (H5FL.c:283)
==84622==    by 0x4B53BE9: H5FL_reg_malloc (H5FL.c:422)
==84622==    by 0x4B53F8F: H5FL_reg_calloc (H5FL.c:498)
==84622==    by 0x4A3F7FB: H5O__dset_get_copy_file_udata (H5Doh.c:113)
==84622==    by 0x4CE1C55: H5O__copy_header_real (H5Ocopy.c:394)
==84622==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==84622==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==84622==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==84622==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==84622==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x5927B16: (below main) (libc-start.c:310)
==84622== 
==84622== LEAK SUMMARY:
==84622==    definitely lost: 391 bytes in 5 blocks
==84622==    indirectly lost: 832 bytes in 52 blocks
==84622==      possibly lost: 0 bytes in 0 blocks
==84622==    still reachable: 844,573 bytes in 3,237 blocks
==84622==                       of which reachable via heuristic:
==84622==                         length64           : 2,308 bytes in 8 blocks
==84622==                         newarray           : 16 bytes in 1 blocks
==84622==         suppressed: 0 bytes in 0 blocks
==84622== Reachable blocks (those to which a pointer was found) are not shown.
==84622== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==84622== 
==84622== ERROR SUMMARY: 9363 errors from 9 contexts (suppressed: 0 from 0)
==84622== 
==84622== 1 errors in context 1 of 9:
==84622== Invalid read of size 1
==84622==    at 0x4957130: H5C_flush_invalidate_ring (H5C.c:5520)
==84622==    by 0x4957130: H5C__flush_invalidate_cache (H5C.c:5154)
==84622==    by 0x4958189: H5C_dest (H5C.c:850)
==84622==    by 0x48E268F: H5AC_dest (H5AC.c:524)
==84622==    by 0x4AD1387: H5F__dest (H5Fint.c:1251)
==84622==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==84622==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==84622==    by 0x4C56332: H5I_dec_ref (H5I.c:1263)
==84622==    by 0x4C56893: H5I_dec_app_ref (H5I.c:1308)
==84622==    by 0x4AD3A5B: H5F__close (H5Fint.c:2046)
==84622==    by 0x4AAE0DB: H5Fclose (H5F.c:667)
==84622==    by 0x12D1EA: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==  Address 0x153 is not stack'd, malloc'd or (recently) free'd
==84622== 
==84622== 
==84622== 540 errors in context 2 of 9:
==84622== Invalid read of size 2
==84622==    at 0x483C400: memmove (vg_replace_strmem.c:1258)
==84622==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==84622==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==84622==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==84622==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==84622==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==84622==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==84622==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==84622==    by 0x499087F: H5Dopen2 (H5D.c:291)
==84622==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x5927B16: (below main) (libc-start.c:310)
==84622==  Address 0x5c42898 is 0 bytes after a block of size 280 alloc'd
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==84622==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==84622==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==84622==    by 0x4960D56: H5C_protect (H5C.c:2357)
==84622==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==84622==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==84622==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==84622==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==84622==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==84622==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==84622== 
==84622== 
==84622== 1621 errors in context 3 of 9:
==84622== Invalid read of size 2
==84622==    at 0x483C40F: memmove (vg_replace_strmem.c:1258)
==84622==    by 0x4D0A3FE: H5O_fill_new_decode (H5Ofill.c:273)
==84622==    by 0x4D0A3FE: H5O_fill_new_shared_decode (H5Oshared.h:82)
==84622==    by 0x4D368DF: H5O_msg_read_oh (H5Omessage.c:541)
==84622==    by 0x4D37144: H5O_msg_read (H5Omessage.c:480)
==84622==    by 0x4A27E3F: H5D__open_oid (H5Dint.c:1506)
==84622==    by 0x4A27E3F: H5D_open (H5Dint.c:1281)
==84622==    by 0x4A29D4A: H5D__open_name (H5Dint.c:1215)
==84622==    by 0x499087F: H5Dopen2 (H5D.c:291)
==84622==    by 0x12067B: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x5927B16: (below main) (libc-start.c:310)
==84622==  Address 0x5c4289a is 2 bytes after a block of size 280 alloc'd
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4CD6B32: H5O__chunk_deserialize (H5Ocache.c:1350)
==84622==    by 0x4CDAB35: H5O__cache_deserialize (H5Ocache.c:355)
==84622==    by 0x4960D56: H5C_load_entry (H5C.c:6725)
==84622==    by 0x4960D56: H5C_protect (H5C.c:2357)
==84622==    by 0x48E7CD3: H5AC_protect (H5AC.c:1624)
==84622==    by 0x4D16BDD: H5O_protect (H5Oint.c:1099)
==84622==    by 0x4D1C6AE: H5O_get_info (H5Oint.c:2243)
==84622==    by 0x4BA3E2A: H5G_loc_info_cb (H5Gloc.c:687)
==84622==    by 0x4BD04CE: H5G__traverse_real.isra.0 (H5Gtraverse.c:626)
==84622==    by 0x4BD1244: H5G_traverse (H5Gtraverse.c:850)
==84622== 
==84622== 
==84622== 7196 errors in context 4 of 9:
==84622== Invalid write of size 2
==84622==    at 0x483C403: memmove (vg_replace_strmem.c:1258)
==84622==    by 0x4D09B0C: H5O_fill_new_encode (H5Ofill.c:462)
==84622==    by 0x4D09B0C: H5O_fill_new_shared_encode (H5Oshared.h:137)
==84622==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==84622==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==84622==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==84622==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==84622==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==84622==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==84622==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==84622==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==84622==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==84622==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==84622==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==84622==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==84622==  Address 0x5c53418 is 0 bytes after a block of size 136 alloc'd
==84622==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==84622==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==84622==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==84622==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==84622==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==84622==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==84622==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==84622==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==84622==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==84622==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==84622==    by 0x5927B16: (below main) (libc-start.c:310)
==84622== 
==84622== ERROR SUMMARY: 9363 errors from 9 contexts (suppressed: 0 from 0)
Segmentation fault


```
---
