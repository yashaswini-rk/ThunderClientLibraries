add_executable(player_info main.c)

target_include_directories(player_info 
    PRIVATE
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/../include>
        $<INSTALL_INTERFACE:include/playerinfo.h> 
)

target_link_libraries(player_info
    PRIVATE
        playerinfo)

install(TARGETS player_info 
    DESTINATION bin)