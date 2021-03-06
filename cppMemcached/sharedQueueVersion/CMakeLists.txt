CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(TransMaster_0_5)
SET( CMAKE_BUILD_TYPE Debug )

#CMAKE选项：平台
SET(CMAKE_ALLOW_LOOSE_LOOP_CONSTRUCTS ON)
#SET(MAKE_PLATFORM_WIN64 "WIN64")
#SET(MAKE_PLATFORM_WIN32 "WIN32")
SET(MAKE_PLATFORM_LINUX64 "LINUX64")

#编译选项：平台
#ADD_DEFINITIONS( -DWINDOWS )

#编译选项：软件加密保护
ADD_DEFINITIONS( -DENABLE_SOFT_PROTECT )
#ADD_DEFINITIONS( -DSOFT_PROTECT_MODE_BJXXJS )

#编译选项：日志输出相信详细信息，如调用代码行号
#ADD_DEFINITIONS( -DLOG_CODE_DETAIL )

#编译选项: 输出运行时间统计
#ADD_DEFINITIONS( -DENABLE_TIME_LOG )

#编译选项：打开用户计费
#ADD_DEFINITIONS( -DUSR_CHARGING )

#编译选项：对齐信息输出
#ADD_DEFINITIONS( -DALIGMENT_OUTPUT )

#编译选项
ADD_DEFINITIONS( -std=c++0x )
ADD_DEFINITIONS( -fpermissive -g )

set( CMAKE_VERBOSE_MAKEFILE on )

IF(MAKE_PLATFORM_LINUX64)
	MESSAGE(STATUS "Make on " ${MAKE_PLATFORM_LINUX64})
    #INCLUDE_DIRECTORIES("/home/david/Desktop/Project57/BuildSystem/boost/boost_1_49/include/")
    INCLUDE_DIRECTORIES("/home/mapred/Desktop/BuildSystem/tool/myGcc/include")
	INCLUDE_DIRECTORIES("/home/mapred/Desktop/BuildSystem/Trans/mysql/include/")
	INCLUDE_DIRECTORIES("/home/mapred/Desktop/BuildSystem/Trans/mysql++-3.1.0/")
	INCLUDE_DIRECTORIES("/home/mapred/Desktop/BuildSystem/icu/include/linux64/")

	SET(ICU_LIB_PATH "/home/mapred/Desktop/BuildSystem/icu/lib/linux64/")
	
    #SET(LIB_MYSQL_PATH   "/home/david/Downloads/mysql-5.6.16/cqw_install/lib")
    SET(LIB_MYSQL_NAME   "/home/mapred/Desktop/BuildSystem/tool/mysql-5.6.16/cqw_install/lib/libmysqlclient_r.a")
    #SET(LIB_MYSQL_NAME   "mysqlclient_r")
    #SET(LIB_MYSQLPP_PATH "/home/david/Downloads/mysql++-3.2.1/cqw_install/lib/")
    SET(LIB_MYSQLPP_NAME   "/home/mapred/Desktop/BuildSystem/tool/mysql++-3.2.1/cqw_install/lib/libmysqlpp.a")
    #SET(LIB_MYSQLPP_NAME   "mysqlpp")
	
    SET(LIB_Z_NAME   "/usr/lib/x86_64-linux-gnu/libz.a")

	SET(LIB_BOOST_THREAD_NAME "libboost_thread.a")
	SET(LIB_BOOST_REGEX_NAME "libboost_regex.a")
	SET(LIB_BOOST_DATETIME_NAME "libboost_date_time.a")
	SET(LIB_BOOST_SYSTEM_NAME "libboost_system.a")
	
    #SET(LIB_BOOST_PATH "/home/david/Desktop/Project57/BuildSystem/boost/boost_1_49/lib/linux64/")
    SET(LIB_BOOST_PATH "/home/mapred/Desktop/BuildSystem/tool/myGcc/lib/")

	SET(LIB_PBCLAS_NAME "liblpbclas.a")
	SET(LIB_PBCLAS_PATH "/bwdata160/fcl/workspace/TransSystem/TransSys_0_5/component_0_5/pbclas/build_linux64/bin/")
	SET(LIB_EN_TOKEN_NAME "liblib_zdqtokenizer.a")
    SET(LIB_EN_TOKEN_PATH "/home/mapred/Desktop/BuildSystem/Trans/entokenizer/bin/")
    SET(LIB_LM_PATH "/home/mapred/Desktop/BuildSystem/Trans/lm/linux64/")
	SET(LIB_LM_NAME "libfsrilm.a")

	SET(LIB_KOREAN_NAME "/home/mapred/Desktop/BuildSystem/Trans/master/src/LanguageTools/libKMAnalyzer.a")
	SET(LIB_TIBET_PATH "/home/mapred/Desktop/BuildSystem/Trans/master/src/LanguageTools/tibet/CodeDect/lib/")
	
    #SET(LIB_JSON_PATH "/xy/lib/")
    #SET(LIB_JSON_NAME "libjson_linux-gcc-4.2.4_libmt.a")
	
    SET(LIB_JSON_PATH "/home/mapred/Desktop/BuildSystem/tool/jsoncpp-src-0.5.0/libs/linux-gcc-4.6.1/")
	SET(LIB_JSON_NAME "libjson_linux-gcc-4.6.1_libmt.a")
	
    SET(LIB_SOFT_PROTECT "/home/mapred/Desktop/BuildSystem/Trans/SoftProtect/bin/liblsoftprotect.a")
    #SET(LIB_SOFT_PROTECT "/home/david/Desktop/Project57/BuildSystem/Trans/master/src/SoftProtect/liblsoftprotect.a")
    SET(LIB_SOFT_PROTECT_SYSINFO "/home/mapred/Desktop/BuildSystem/Trans/SoftProtect/src/softprotect/linux/liblsysteminfo.a")
    #SET(LIB_SOFT_PROTECT_SYSINFO "/home/david/Desktop/Project57/BuildSystem/Trans/master/src/SoftProtect/liblsysteminfo.a")
	
ELSEIF(MAKE_PLATFORM_WIN64)

	SET(BASE_INCLUDE_PATH "F:/TRTrans/master/src/")
	INCLUDE_DIRECTORIES("F:/TRTrans/boost_1_48_0/")
	INCLUDE_DIRECTORIES(F:/TRTrans/mysql/include/)
	INCLUDE_DIRECTORIES(F:/TRTrans/mysql++-3.1.0/)
	INCLUDE_DIRECTORIES(F:/TRTrans/icu/include/win64/)

	SET(ICU_LIB_PATH "F:/TRTrans/icu/lib/win64/")
	
	SET(LIB_MYSQL_PATH   "F:/TRTrans/mysql/lib/opt/libmysql.lib")
	SET(LIB_MYSQLPP_PATH "F:/TRTrans/mysql++-3.1.0/vc2008/Release/mysqlpp.lib")

	SET(LIB_BOOST_PATH "F:/TRTrans/boost_1_48_0/stage/lib/")
	SET(LIB_BOOST_THREAD_NAME "libboost_thread-vc100-mt-1_48.lib")
	SET(LIB_BOOST_REGEX_NAME  "libboost_regex-vc100-mt-1_48.lib")
	SET(LIB_BOOST_DATETIME_NAME "libboost_date_time-vc100-mt-1_48.lib")
	SET(LIB_BOOST_SYSTEM_NAME "libboost_system-vc100-mt-1_48.lib")
	SET(LIB_JSON_NAME "ljson.lib")
	SET(LIB_JSON_PATH "F:/TRTrans/json/build_x64/src/Release/")
	
	#SET(LIB_PBCLAS_NAME "lpbclas.lib")
	#SET(LIB_PBCLAS_PATH "F:/work/pbclas/build_x64/bin/Release/")
	SET(LIB_EN_TOKEN_NAME "lib_zdqtokenizer.lib")
	SET(LIB_EN_TOKEN_PATH "F:/TRTrans/entokenizer/build_x64/bin/Release/")
	SET(LIB_LM_PATH "F:/TRTrans/lm/win64/")
	SET(LIB_LM_NAME "lmdll.lib")
	SET(LIB_SOFT_PROTECT "F:/TRTrans/SoftProtect/build64/bin/Release/lsoftprotect.lib")
	SET(LIB_SOFT_PROTECT_SYSINFO "F:/TRTrans/SoftProtect/build64/bin/Release/lsysteminfo.lib")
ELSEIF(MAKE_PLATFORM_WIN32)

	INCLUDE_DIRECTORIES("E:/boost/boost_1_48_0/boost_1_48_0/")
	INCLUDE_DIRECTORIES("C:/Users/Acer/Desktop/master_0_5/lib/mysql++.3.1.0/include/")
	INCLUDE_DIRECTORIES("C:/Users/Acer/Desktop/master_0_5/lib/mysql/Win32/include/")
	INCLUDE_DIRECTORIES("C:/Users/Acer/Desktop/master_0_5/lib/icu/include32/")

	SET(ICU_LIB_PATH "C:/Users/Acer/Desktop/master_0_5/lib/icu/lib32/")
	SET(LIB_MYSQL_PATH "C:/Users/Acer/Desktop/master_0_5/lib/mysql/win32/lib/libmysql.lib")
	SET(LIB_MYSQLPP_PATH "C:/Users/Acer/Desktop/master_0_5/lib/mysql++.3.1.0/lib/win32/mysqlpp.lib")
	
	SET(LIB_BOOST_PATH "")
	SET(LIB_BOOST_THREAD_NAME "E:/boost/boost_1_48_0/boost_1_48_0/bin.v2/libs/thread/build/msvc-10.0/release/link-static/threading-multi/libboost_thread-vc100-mt-1_48.lib")
	SET(LIB_BOOST_REGEX_NAME  "E:/boost/boost_1_48_0/boost_1_48_0/bin.v2/libs/regex/build/msvc-10.0/release/link-static/threading-multi/libboost_regex-vc100-mt-1_48.lib")
	SET(LIB_BOOST_DATETIME_NAME "E:/boost/boost_1_48_0/boost_1_48_0/bin.v2/libs/date_time/build/msvc-10.0/release/link-static/threading-multi/libboost_date_time-vc100-mt-1_48.lib")
	SET(LIB_BOOST_SYSTEM_NAME "E:/boost/boost_1_48_0/boost_1_48_0/bin.v2/libs/system/build/msvc-10.0/release/link-static/threading-multi/libboost_system-vc100-mt-1_48.lib")
	SET(LIB_BOOST_FILESYSTEM_NAME "E:/boost/boost_1_48_0/boost_1_48_0/bin.v2/libs/filesystem/build/msvc-10.0/release/link-static/threading-multi/libboost_filesystem-vc100-mt-1_48.lib")
	
	SET(LIB_PBCLAS_PATH "F:/work/pbclas/build_win32/bin/Release/lpbclas.lib")
	SET(LIB_EN_TOKEN_PATH "F:/work/entokenizer/build_x32/bin/Release/lib_zdqtokenizer.lib")
	SET(LIB_LM_PATH "C:/Users/Acer/Desktop/master_0_5/lib/lm/win32/lmdll.lib")
	
	SET(LIB_SOFT_PROTECT "F:/work/SoftProtect/build32/bin/Release/lsoftprotect.lib")
	SET(LIB_SOFT_PROTECT_SYSINFO "F:/work/SoftProtect/build32/bin/Release/lsysteminfo.lib")
	SET(LIB_JSON_NAME "ljson.lib")
	SET(LIB_JSON_PATH "F:/work/json/build_x32/src/Release/")
	
ENDIF()

ADD_SUBDIRECTORY(src)
MESSAGE(STATUS "This is SOURCE dir " ${PROJECT_SOURCE_DIR})
MESSAGE(STATUS "This is BINARY dir " ${PROJECT_BINARY_DIR})
