# C++ examples Meson Build File

executable('circular_buffer',
	'circular_buffer.cpp',
)

executable('dispatch',
	'dispatch.cpp',
)

executable('shared_ptr',
	'shared_ptr.cpp',
)

executable('aligned_ptr',
	[
		'smart_ptr_aligned.cpp',
		'../libc/malloc_aligned.c'
	],
)

executable('array_demo',
	'array.cpp',
)

executable('vector_demo',
	'vector.cpp',
)

executable('string_demo',
	'string.cpp',
)

executable('callbacks',
	'callbacks.cpp',
)

executable('bounce',
	'bounce.cpp',
)

executable('c_sbrm',
	'c_sbrm.cpp',
)

libdispatch_threadx = static_library('dispatch_threadx',
	'dispatch_threadx.cpp',
	include_directories: include_directories('../rtos/threadx'),
)

libdispatch_threadx_stdmutex = static_library('dispatch_threadx_stdmutex',
	[
		'dispatch_threadx_stdmutex.cpp',
		'../libcpp/mutex.cpp'
	],
	include_directories: [
		include_directories('../rtos'),
		include_directories('../libcpp'),
	],
	cpp_args: [
		'-DTHREADX=1',
		'-D_LIBCPP_NO_EXCEPTIONS',
		'-DTHREADING=1',
		'-D_LIBCPP_HAS_THREAD_API_EXTERNAL',
		'-fno-builtin',
		'-static',
		'-nodefaultlibs'
	],
	link_args: [
		'-static',
		'-nodefaultlibs',
		'-nostartfiles',
		'-Wl,-preload',
		'-Wl,-all_load',
		'-Wl,-dead_strip',
		'-Wl,-prebind'
	]
)

libdispatch_freertos = static_library('dispatch_freertos',
	'dispatch_freertos.cpp',
	include_directories: include_directories('../rtos')
)
