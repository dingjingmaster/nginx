cmake_minimum_required(VERSION 3.0)

project (nginx)

INCLUDE_DIRECTORIES(
        "src"
        "src/core/"
        "src/imap"
        "src/os/unix/"
        "src/event/" "src/event/modules"
        "src/http" "src/http/modules" "src/http/modules/proxy"
)

#aux_source_directory(src/core CORE_SRC)

SET(CORE_SRC
        src/core/nginx.c;
        src/core/ngx_log.c;
        src/core/ngx_palloc.c;
        src/core/ngx_array.c;
        src/core/ngx_list.c;
        src/core/ngx_buf.c;
        src/core/ngx_output_chain.c;
        src/core/ngx_string.c;
        src/core/ngx_parse.c;
        src/core/ngx_inet.c;
        src/core/ngx_file.c;
        src/core/ngx_rbtree.c;
        src/core/ngx_times.c;
        src/core/ngx_connection.c;
        src/core/ngx_cycle.c;
        src/core/ngx_spinlock.c;
        src/core/ngx_conf_file.c;
        src/core/ngx_garbage_collector.c;
        src/event/ngx_event.c;
        src/event/ngx_event_timer.c;
        src/event/ngx_event_posted.c;
        src/event/ngx_event_busy_lock.c;
        src/event/ngx_event_accept.c;
        src/event/ngx_event_connect.c;
        src/event/ngx_event_pipe.c;
        src/os/unix/ngx_time.c;
        src/os/unix/ngx_errno.c;
        src/os/unix/ngx_alloc.c;
        src/os/unix/ngx_files.c;
        src/os/unix/ngx_socket.c;
        src/os/unix/ngx_recv.c;
        src/os/unix/ngx_readv_chain.c;
        src/os/unix/ngx_send.c;
        src/os/unix/ngx_writev_chain.c;
        src/os/unix/ngx_channel.c;
        src/os/unix/ngx_shared.c;
        src/os/unix/ngx_process.c;
        src/os/unix/ngx_daemon.c;
        src/os/unix/ngx_posix_init.c;
        src/os/unix/ngx_process_cycle.c;
        src/os/unix/ngx_linux_init.c;
        src/event/modules/ngx_rtsig_module.c;
        src/event/modules/ngx_epoll_module.c;
        src/event/modules/ngx_poll_module.c;
        src/os/unix/ngx_linux_sendfile_chain.c;
        src/core/ngx_regex.c;
        src/http/ngx_http.c;
        src/http/ngx_http_core_module.c;
        src/http/ngx_http_special_response.c;
        src/http/ngx_http_request.c;
        src/http/ngx_http_parse.c;
        src/http/ngx_http_header_filter.c;
        src/http/ngx_http_write_filter.c;
        src/http/ngx_http_copy_filter.c;
        src/http/ngx_http_log_handler.c;
        src/http/ngx_http_request_body.c;
        src/http/ngx_http_parse_time.c;
        src/http/modules/ngx_http_static_handler.c;
        src/http/modules/ngx_http_index_handler.c;
        src/http/modules/ngx_http_chunked_filter.c;
        src/http/modules/ngx_http_range_filter.c;
        src/http/modules/ngx_http_headers_filter.c;
        src/http/modules/ngx_http_not_modified_filter.c;
        src/http/ngx_http_busy_lock.c;
        src/http/modules/ngx_http_gzip_filter.c;
        src/http/modules/ngx_http_charset_filter.c;
        src/http/modules/ngx_http_userid_filter.c;
        src/http/modules/ngx_http_access_handler.c;
        src/http/modules/ngx_http_rewrite_handler.c;
        src/http/modules/proxy/ngx_http_proxy_handler.c;
        src/http/modules/proxy/ngx_http_proxy_upstream.c;
        src/http/modules/proxy/ngx_http_proxy_parse.c;
        src/http/modules/proxy/ngx_http_proxy_header.c;
        src/ngx_modules.c;
)

# nginx
link_libraries(pcre)
link_libraries(z)
add_executable(nginx ${CORE_SRC})
