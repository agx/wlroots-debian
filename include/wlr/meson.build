version_array = meson.project_version().split('.')
version_data = configuration_data()
version_data.set_quoted('WLR_VERSION_STR',   meson.project_version())
version_data.set('WLR_VERSION_MAJOR',        version_array[0])
version_data.set('WLR_VERSION_MINOR',        version_array[1])
version_data.set('WLR_VERSION_MICRO',        version_array[2])
version_data.set('WLR_VERSION_API_CURRENT',  so_version[0])
version_data.set('WLR_VERSION_API_REVISION', so_version[1])
version_data.set('WLR_VERSION_API_AGE',      so_version[2])

conf_h = configure_file(
	input: 'config.h.in',
	output: 'config.h',
	configuration: conf_data,
)
ver_h = configure_file(
	input: 'version.h.in',
	output: 'version.h',
	configuration: version_data,
)

install_headers(conf_h, ver_h, subdir: 'wlr')
