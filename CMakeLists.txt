cmake_minimum_required(VERSION 3.16)
project("Evalvid-2.7")

include_directories("include/")
add_executable("etmp4" 
                "src/bits.c" 
                "src/misc.c" 
                "src/read.c" 
                "src/stat.c" 
                "src/writemp4.c" 
                "src/etmp4.c")
target_link_libraries ("etmp4" "-lgpac_static -lm -lz -ljpeg -lpng -lssl -lcrypto -lpthread -llzma")

add_executable("mp4trace"
                "src/bits.c" 
                "src/error.c" 
                "src/lock.c" 
                "src/misc.c" 
                "src/queue.c"
                "src/socket.c"
                "src/thread.c"
                "src/timing.c"
                "src/mp4trace.c")
target_link_libraries ("mp4trace" "-lgpac -lm -lpthread")

add_executable("hist"
                "src/stat.c" 
                "src/hist.c")
target_link_libraries ("hist" "-lm")

add_executable("mos"
                "src/dir.c" 
                "src/mos.c")
target_link_libraries ("mos" "-lm")

add_executable("miv"
                "src/dir.c" 
                "src/miv.c")
target_link_libraries ("miv" "-lm")

add_executable("eg"
                "src/misc.c" 
                "src/random.c"
                "src/read.c"
                "src/eg.c")
target_link_libraries ("eg" "-lm")

add_executable("vsgen"
                "src/vsgen.c")
target_link_libraries ("vsgen" "-lm")