## Description:

HDF5 is a data model, library, and file format for storing and managing data. It supports an unlimited variety of datatypes, and is designed for flexible and efficient I/O and for high volume and complex data. HDF5 is portable and is extensible, allowing applications to evolve in their use of HDF5. The HDF5 Technology suite includes tools and applications for managing, manipulating, viewing, and analyzing data in the HDF5 format. link: https://portal.hdfgroup.org/display/HDF5/HDF5

## version

h5dump: Version 1.10.4

## others

this bug is reported by winson2004aa@gmail.com, please send email to winson2004aa@gmail.com if you have some quetion.

## Test Target

./h5repack $file1 $file2

---
## H5O_pline_encode_invalid-read-memory-access

```
root@kali:~/hdf5-1.10.4/hdf5/bin# valgrind -v --tool=memcheck --leak-check=full ./h5repack outputFuzz/crashes/H5O_pline_encode_invalid-read-memory-access test
==59570== Memcheck, a memory error detector
==59570== Copyright (C) 2002-2017, and GNU GPL'd, by Julian Seward et al.
==59570== Using Valgrind-3.13.0 and LibVEX; rerun with -h for copyright info
==59570== Command: ./h5repack outputFuzz/crashes/id:000173,sig:11,src:000831,op:flip1,pos:937 test
==59570== 
--59570-- Valgrind options:
--59570--    -v
--59570--    --tool=memcheck
--59570--    --leak-check=full
--59570-- Contents of /proc/version:
--59570--   Linux version 4.18.0-kali2-amd64 (devel@kali.org) (gcc version 7.3.0 (Debian 7.3.0-29)) #1 SMP Debian 4.18.10-2kali1 (2018-10-09)
--59570-- 
--59570-- Arch and hwcaps: AMD64, LittleEndian, amd64-cx16-lzcnt-rdtscp-sse3-avx-avx2-bmi
--59570-- Page sizes: currently 4096, max supported 4096
--59570-- Valgrind library directory: /usr/lib/valgrind
--59570-- Reading syms from /root/hdf5-1.10.4/hdf5/bin/h5repack
--59570--    object doesn't have a symbol table
--59570-- Reading syms from /usr/lib/x86_64-linux-gnu/ld-2.27.so
--59570--   Considering /usr/lib/debug/.build-id/dc/5cb16f5e644116cac64a4c3f5da4d081b81a4f.debug ..
--59570--   .. build-id is valid
--59570-- Reading syms from /usr/lib/valgrind/memcheck-amd64-linux
--59570--   Considering /usr/lib/valgrind/memcheck-amd64-linux ..
--59570--   .. CRC mismatch (computed 7680f3df wanted 92e0f93c)
--59570--   Considering /usr/lib/debug/usr/lib/valgrind/memcheck-amd64-linux ..
--59570--   .. CRC is valid
--59570--    object doesn't have a dynamic symbol table
--59570-- Scheduler: using generic scheduler lock implementation.
--59570-- Reading suppressions file: /usr/lib/valgrind/default.supp
==59570== embedded gdbserver: reading from /tmp/vgdb-pipe-from-vgdb-to-59570-by-root-on-???
==59570== embedded gdbserver: writing to   /tmp/vgdb-pipe-to-vgdb-from-59570-by-root-on-???
==59570== embedded gdbserver: shared mem   /tmp/vgdb-pipe-shared-mem-vgdb-59570-by-root-on-???
==59570== 
==59570== TO CONTROL THIS PROCESS USING vgdb (which you probably
==59570== don't want to do, unless you know exactly what you're doing,
==59570== or are doing some strange experiment):
==59570==   /usr/lib/valgrind/../../bin/vgdb --pid=59570 ...command...
==59570== 
==59570== TO DEBUG THIS PROCESS USING GDB: start GDB like this
==59570==   /path/to/gdb ./h5repack
==59570== and then give GDB the following command
==59570==   target remote | /usr/lib/valgrind/../../bin/vgdb --pid=59570
==59570== --pid is optional if only one valgrind process is running
==59570== 
--59570-- REDIR: 0x401e290 (ld-linux-x86-64.so.2:strlen) redirected to 0x58061781 (vgPlain_amd64_linux_REDIR_FOR_strlen)
--59570-- REDIR: 0x401e070 (ld-linux-x86-64.so.2:index) redirected to 0x5806179b (vgPlain_amd64_linux_REDIR_FOR_index)
--59570-- Reading syms from /usr/lib/valgrind/vgpreload_core-amd64-linux.so
--59570--   Considering /usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59570--   .. CRC mismatch (computed 66a2a561 wanted 3789c7eb)
--59570--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_core-amd64-linux.so ..
--59570--   .. CRC is valid
--59570-- Reading syms from /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so
--59570--   Considering /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59570--   .. CRC mismatch (computed 8487a070 wanted 8af30a91)
--59570--   Considering /usr/lib/debug/usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so ..
--59570--   .. CRC is valid
==59570== WARNING: new redirection conflicts with existing -- ignoring it
--59570--     old: 0x0401e290 (strlen              ) R-> (0000.0) 0x58061781 vgPlain_amd64_linux_REDIR_FOR_strlen
--59570--     new: 0x0401e290 (strlen              ) R-> (2007.0) 0x04838a60 strlen
--59570-- REDIR: 0x401aab0 (ld-linux-x86-64.so.2:strcmp) redirected to 0x4839b90 (strcmp)
--59570-- REDIR: 0x401e7d0 (ld-linux-x86-64.so.2:mempcpy) redirected to 0x483d1a0 (mempcpy)
--59570-- Reading syms from /root/hdf5-1.10.4/hdf5/lib/libhdf5.so.103.0.0
--59570-- Reading syms from /usr/lib/x86_64-linux-gnu/libz.so.1.2.11
--59570--    object doesn't have a symbol table
--59570-- Reading syms from /usr/lib/x86_64-linux-gnu/libdl-2.27.so
--59570--   Considering /usr/lib/debug/.build-id/b7/883b3fc771cfa5fcb452861bbb97a5b646259b.debug ..
--59570--   .. build-id is valid
--59570-- Reading syms from /usr/lib/x86_64-linux-gnu/libm-2.27.so
--59570--   Considering /usr/lib/debug/.build-id/fa/b2857727406caccd7ab22e1729b09ccf2c3eb7.debug ..
--59570--   .. build-id is valid
--59570-- Reading syms from /usr/lib/x86_64-linux-gnu/libc-2.27.so
--59570--   Considering /usr/lib/debug/.build-id/dc/87cd1e2b171a4c51139cb4e1f2ec630e711de3.debug ..
--59570--   .. build-id is valid
--59570-- REDIR: 0x598d050 (libc.so.6:memmove) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598c280 (libc.so.6:strncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d330 (libc.so.6:strcasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598bcd0 (libc.so.6:strcat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598c2b0 (libc.so.6:rindex) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598e900 (libc.so.6:rawmemchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d1c0 (libc.so.6:mempcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598cff0 (libc.so.6:bcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598c240 (libc.so.6:strncmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598bd40 (libc.so.6:strcmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d120 (libc.so.6:memset) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x59a6b60 (libc.so.6:wcschr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598c1e0 (libc.so.6:strnlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598bdb0 (libc.so.6:strcspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d380 (libc.so.6:strncasecmp) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598bd80 (libc.so.6:strcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d4c0 (libc.so.6:memcpy@@GLIBC_2.14) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598c2e0 (libc.so.6:strpbrk) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598bd00 (libc.so.6:index) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598c1b0 (libc.so.6:strlen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x59931b0 (libc.so.6:memrchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d3d0 (libc.so.6:strcasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598cfc0 (libc.so.6:memchr) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x59a7920 (libc.so.6:wcslen) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598c590 (libc.so.6:strspn) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d300 (libc.so.6:stpncpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d2d0 (libc.so.6:stpcpy) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598e930 (libc.so.6:strchrnul) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x598d420 (libc.so.6:strncasecmp_l) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x5a5f700 (libc.so.6:__strrchr_avx2) redirected to 0x48383e0 (rindex)
--59570-- REDIR: 0x5a5f8d0 (libc.so.6:__strlen_avx2) redirected to 0x48389a0 (strlen)
--59570-- REDIR: 0x59885c0 (libc.so.6:malloc) redirected to 0x4835750 (malloc)
--59570-- REDIR: 0x5a60290 (libc.so.6:__memset_avx2_unaligned_erms) redirected to 0x483c280 (memset)
--59570-- REDIR: 0x5a5f510 (libc.so.6:__strchrnul_avx2) redirected to 0x483ccd0 (strchrnul)
--59570-- REDIR: 0x5a4cc90 (libc.so.6:__strcpy_ssse3) redirected to 0x4838a80 (strcpy)
--59570-- REDIR: 0x5988d60 (libc.so.6:realloc) redirected to 0x4837960 (realloc)
--59570-- REDIR: 0x5a5fe10 (libc.so.6:__memcpy_avx_unaligned_erms) redirected to 0x483c390 (memmove)
--59570-- REDIR: 0x5988c50 (libc.so.6:free) redirected to 0x4836980 (free)
--59570-- REDIR: 0x5a4e440 (libc.so.6:__strncpy_ssse3) redirected to 0x4838c60 (strncpy)
--59570-- REDIR: 0x5a3b0a0 (libc.so.6:__strcmp_ssse3) redirected to 0x4839a50 (strcmp)
--59570-- REDIR: 0x59892a0 (libc.so.6:calloc) redirected to 0x4837720 (calloc)
--59570-- REDIR: 0x598c210 (libc.so.6:strncat) redirected to 0x482b1c0 (_vgnU_ifunc_wrapper)
--59570-- REDIR: 0x599e0f0 (libc.so.6:__strncat_ssse3) redirected to 0x4838840 (strncat)
--59570-- REDIR: 0x5a5b3b0 (libc.so.6:__strcspn_sse42) redirected to 0x483d580 (strcspn)
--59570-- REDIR: 0x5a5f2e0 (libc.so.6:__strchr_avx2) redirected to 0x4838600 (index)
--59570-- REDIR: 0x5a5fdf0 (libc.so.6:__mempcpy_avx_unaligned_erms) redirected to 0x483cde0 (mempcpy)
--59570-- REDIR: 0x5a5b640 (libc.so.6:__strspn_sse42) redirected to 0x483d640 (strspn)
==59570== Invalid write of size 1
==59570==    at 0x4D465F3: H5O_pline_encode (H5Opline.c:289)
==59570==    by 0x4D465F3: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbd9 is 0 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== Invalid write of size 1
==59570==    at 0x4D466D0: H5O_pline_encode (H5Opline.c:313)
==59570==    by 0x4D466D0: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbda is 1 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== Invalid write of size 1
==59570==    at 0x4D466DA: H5O_pline_encode (H5Opline.c:313)
==59570==    by 0x4D466DA: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbdb is 2 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== Invalid write of size 1
==59570==    at 0x4D466E2: H5O_pline_encode (H5Opline.c:316)
==59570==    by 0x4D466E2: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbdc is 3 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== Invalid write of size 1
==59570==    at 0x4D466EE: H5O_pline_encode (H5Opline.c:316)
==59570==    by 0x4D466EE: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbdd is 4 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== Invalid write of size 1
==59570==    at 0x4D465EB: H5O_pline_encode (H5Opline.c:289)
==59570==    by 0x4D465EB: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbde is 5 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== 
==59570== HEAP SUMMARY:
==59570==     in use at exit: 0 bytes in 0 blocks
==59570==   total heap usage: 3,954 allocs, 3,954 frees, 1,484,498 bytes allocated
==59570== 
==59570== All heap blocks were freed -- no leaks are possible
==59570== 
==59570== ERROR SUMMARY: 47 errors from 6 contexts (suppressed: 0 from 0)
==59570== 
==59570== 7 errors in context 1 of 6:
==59570== Invalid write of size 1
==59570==    at 0x4D465EB: H5O_pline_encode (H5Opline.c:289)
==59570==    by 0x4D465EB: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbde is 5 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== 
==59570== 8 errors in context 2 of 6:
==59570== Invalid write of size 1
==59570==    at 0x4D466EE: H5O_pline_encode (H5Opline.c:316)
==59570==    by 0x4D466EE: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbdd is 4 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== 
==59570== 8 errors in context 3 of 6:
==59570== Invalid write of size 1
==59570==    at 0x4D466E2: H5O_pline_encode (H5Opline.c:316)
==59570==    by 0x4D466E2: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbdc is 3 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== 
==59570== 8 errors in context 4 of 6:
==59570== Invalid write of size 1
==59570==    at 0x4D466DA: H5O_pline_encode (H5Opline.c:313)
==59570==    by 0x4D466DA: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbdb is 2 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== 
==59570== 8 errors in context 5 of 6:
==59570== Invalid write of size 1
==59570==    at 0x4D466D0: H5O_pline_encode (H5Opline.c:313)
==59570==    by 0x4D466D0: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbda is 1 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== 
==59570== 8 errors in context 6 of 6:
==59570== Invalid write of size 1
==59570==    at 0x4D465F3: H5O_pline_encode (H5Opline.c:289)
==59570==    by 0x4D465F3: H5O_pline_shared_encode (H5Oshared.h:137)
==59570==    by 0x4D3FBB2: H5O_msg_flush (H5Omessage.c:2187)
==59570==    by 0x4CD5509: H5O__chunk_serialize (H5Ocache.c:1660)
==59570==    by 0x4CD5BE2: H5O__cache_serialize (H5Ocache.c:538)
==59570==    by 0x49533A4: H5C__generate_image (H5C.c:8657)
==59570==    by 0x4955A96: H5C__flush_single_entry (H5C.c:6084)
==59570==    by 0x4959AE6: H5C__flush_ring (H5C.c:5871)
==59570==    by 0x4959AE6: H5C_flush_cache (H5C.c:1149)
==59570==    by 0x48E369C: H5AC_flush (H5AC.c:731)
==59570==    by 0x4ACC168: H5F__flush_phase2.part.2 (H5Fint.c:1879)
==59570==    by 0x4AD0F50: H5F__flush_phase2 (H5Fint.c:1873)
==59570==    by 0x4AD0F50: H5F__dest (H5Fint.c:1128)
==59570==    by 0x4AD4458: H5F_try_close (H5Fint.c:2275)
==59570==    by 0x4AD4E50: H5F__close_cb (H5Fint.c:2104)
==59570==  Address 0x5c4cbd9 is 0 bytes after a block of size 153 alloc'd
==59570==    at 0x48357BF: malloc (vg_replace_malloc.c:299)
==59570==    by 0x4B5378B: H5FL_malloc (H5FL.c:243)
==59570==    by 0x4B5580D: H5FL_blk_malloc (H5FL.c:921)
==59570==    by 0x4B55D9F: H5FL_blk_calloc (H5FL.c:989)
==59570==    by 0x4CE397F: H5O__copy_header_real (H5Ocopy.c:716)
==59570==    by 0x4CEA468: H5O__copy_header (H5Ocopy.c:1164)
==59570==    by 0x4CEA468: H5O__copy_obj (H5Ocopy.c:1220)
==59570==    by 0x4CEA468: H5O__copy (H5Ocopy.c:316)
==59570==    by 0x4CEA468: H5Ocopy (H5Ocopy.c:232)
==59570==    by 0x120A70: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x12CFB2: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x119B41: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x110EED: ??? (in /root/hdf5-1.10.4/hdf5/bin/h5repack)
==59570==    by 0x5927B16: (below main) (libc-start.c:310)
==59570== 
==59570== ERROR SUMMARY: 47 errors from 6 contexts (suppressed: 0 from 0)


```
---
