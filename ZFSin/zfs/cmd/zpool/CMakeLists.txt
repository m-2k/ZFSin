um_add_executable(zpool
	zpool_iter.c
	zpool_main.c
	zpool_util.c
	zpool_vdev.c
	zpool_util.h
)
target_link_libraries(zpool PRIVATE
	libnvpair
	libuutil
	libuuid
	libzfs
	libzfs_core
	libzpool
)
install(TARGETS zpool RUNTIME DESTINATION "${CMAKE_INSTALL_BINDIR}")
install(FILES $<TARGET_PDB_FILE:zpool>
	DESTINATION "${CMAKE_INSTALL_BINDIR}"
	OPTIONAL
)