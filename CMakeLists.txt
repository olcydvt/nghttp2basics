cmake_minimum_required(VERSION 3.0.0)

project(http_test)

#link_libraries(
#	nghttp2
#	${LIBEVENT_OPENSSL_LIBRARIES}
#	${OPENSSL_LIBRARIES}
#	${APP_LIBRARIES}
#	)

find_library(CRYTPTO NAMES crypto)


add_executable(httpTest main.cpp)

target_include_directories(httpTest PRIVATE
	              		${OPENSSL_INCLUDE_DIRS}
		                ${Boost_INCLUDE_DIRS}
			  )

target_link_libraries(httpTest PRIVATE
			 nghttp2
           	   	 nghttp2_asio
			 pthread
			 ${CRYTPTO}
			 ${JEMALLOC_LIBRARIES}
       			 ${OPENSSL_LIBRARIES}
       			 ${Boost_LIBRARIES}
        		 ${APP_LIBRARIES}
                     )
