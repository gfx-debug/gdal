cmake_minimum_required(VERSION 2.8)

project(my-osg)




set(JSON_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/arraylist.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/debug.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/json_object.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/json_tokener.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/json_util.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/linkhash.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/printbuf.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/json_object_iterator.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/json_c_version.c
    )


file(GLOB PORT_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/port/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/port/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/port/*.h
    )



list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_alibaba_oss.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_alibaba_oss.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_google_cloud.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_google_cloud.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_google_oauth2.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_minizip_ioapi.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_minizip_ioapi.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_minizip_unzip.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_minizip_unzip.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_minizip_zip.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_minizip_zip.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_odbc.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_odbc.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_swift.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_swift.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_az.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_curl_class.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_curl.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_curl_priv.h")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_curl_streaming.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_gs.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_gzip.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_oss.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_s3.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_simple.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_swift.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_webhdfs.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/xmlreformat.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/vsipreload.cpp")
list(REMOVE_ITEM PORT_SRC "${CMAKE_CURRENT_SOURCE_DIR}/port/cpl_vsil_win32.cpp")

file(GLOB ALG_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/alg/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/alg/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/alg/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/alg/marching_squares/*.h
    )

file(GLOB OGR_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/generic/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/generic/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/generic/ogrregisterall.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/mitab/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/mitab/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/mem/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/mem/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/csv/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/csv/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/kml/ogrkmllayer.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/kml/ogrkmldriver.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/kml/ogrkmldatasource.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/kml/ogr2kmlgeometry.cpp
    )
list(REMOVE_ITEM OGR_SRC "${CMAKE_CURRENT_SOURCE_DIR}/ogr/test_geo_utils.cpp")
list(REMOVE_ITEM OGR_SRC "${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogr_capi_test.cpp")
list(REMOVE_ITEM OGR_SRC "${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogr_capi_test.cpp")
list(REMOVE_ITEM OGR_SRC "${CMAKE_CURRENT_SOURCE_DIR}/ogr/generate_encoding_table.c")


file(GLOB GCORE_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/gcore/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/gcore/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/gcore/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/gcore/mdreader/*h
    ${CMAKE_CURRENT_SOURCE_DIR}/gcore/mdreader/*cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtdataset.h
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtdataset.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtrasterband.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtsources.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtsourcedrasterband.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtdriver.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtderivedrasterband.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtwarped.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/pixelfunctions.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtrawrasterband.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtpansharpened.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt/vrtfilters.cpp

    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/derived/derivedlist.c

    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/mem/memdataset.cpp

    ${CMAKE_CURRENT_SOURCE_DIR}/apps/gdalbuildvrt_lib.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/apps/ogr2ogr_lib.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/apps/commonutils.cpp

    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/raw/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/raw/*.cpp

    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/hfa/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/hfa/*.cpp

    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/libgeotiff/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/libgeotiff/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/libtiff/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/libtiff/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/derived/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/derived/*.c
    ${CMAKE_CURRENT_SOURCE_DIR}/frmts/derived/*.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/third_party/LercLib/*.h
    ${CMAKE_CURRENT_SOURCE_DIR}/third_party/LercLib/*.cpp
    )
list(REMOVE_ITEM GCORE_SRC "${CMAKE_CURRENT_SOURCE_DIR}/frmts/hfa/hfatest.cpp")
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})

add_definitions(-DGDAL_COMPILATION)
add_definitions(-DINTERNAL_LIBGEOTIFF)
add_definitions(-DINTERNAL_LIBTIFF)
add_definitions(-DFRMT_gtiff)
add_definitions(-DFRMT_mem)
add_definitions(-DFRMT_hfa)
add_definitions(-DFRMT_vrt)
add_definitions(-DRENAME_INTERNAL_LIBTIFF_SYMBOLS)
add_definitions(-DRENAME_INTERNAL_LIBGEOTIFF_SYMBOLS)
add_definitions(-DLOAD_NOCHECK_WITH_NAME)
add_definitions(-DGTIFF_POINT_GEO_IGNORE=true)
add_definitions(-DNOMINMAX)


INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/port)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/alg)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/alg/marching_squares)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/gcore)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/libjson/)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/geojson/)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/mem)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/ogr/ogrsf_frmts/generic)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/ogr)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/frmts)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff)

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/libgeotiff)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/frmts/gtiff/libtiff)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/frmts/raw)

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/frmts/vrt)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/frmts/mem)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/apps)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR}/third_party/LercLib)

add_library(GDAL SHARED
    ${PORT_SRC}
    ${OGR_SRC}
    ${JSON_SRC}
    ${GCORE_SRC}
    ${ALG_SRC}
    )





add_executable(${PROJECT_NAME}
    "main.cpp")
add_dependencies(${PROJECT_NAME} GDAL)
target_link_libraries(${PROJECT_NAME} ${GDAL} )
