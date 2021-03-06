####
# F prime CMakeLists.txt:
#
# SOURCE_FILES: combined list of source and autocoding diles
# MOD_DEPS: (optional) module dependencies
#
####
set(SOURCE_FILES
  "${CMAKE_CURRENT_LIST_DIR}/Linux/File.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Linux/FileSystem.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Linux/InterruptLock.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Linux/IntervalTimer.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Linux/WatchdogTimer.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/LogPrintf.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/MemCommon.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Posix/Mutex.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Posix/Task.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Pthreads/BufferQueueCommon.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Pthreads/MaxHeap/MaxHeap.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Pthreads/PriorityBufferQueue.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Pthreads/Queue.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/QueueCommon.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/QueueString.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/SimpleQueueRegistry.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/TaskCommon.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/TaskString.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/ValidateFileCommon.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/X86/IntervalTimer.cpp"
)
set(MOD_DEPS
  "${CMAKE_THREAD_LIBS_INIT}" 
  Fw/Cfg
  Fw/Types
  Utils/Hash
)

register_fprime_module()

# Add stubs directory
add_fprime_subdirectory("${CMAKE_CURRENT_LIST_DIR}/Stubs/")

### UTS ### Note: 3 separate UTs registered here.
set(UT_SOURCE_FILES
  "${CMAKE_CURRENT_LIST_DIR}/test/ut/OsQueueTest.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/test/ut/TestMain.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/test/ut/IntervalTimerTest.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/test/ut/OsValidateFileTest.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/test/ut/OsTaskTest.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/test/ut/OsFileSystemTest.cpp"
)
## TODO: **BROKEN UT**, validation of File fails
#register_fprime_ut()

# Second UT Pthreads
set(UT_SOURCE_FILES
  "${CMAKE_CURRENT_LIST_DIR}/Pthreads/test/ut/BufferQueueTest.cpp"
)
register_fprime_ut("Os_pthreads")

# Third  UT Pthrads MAX Heap
set(UT_SOURCE_FILES
  "${CMAKE_CURRENT_LIST_DIR}/Pthreads/MaxHeap/test/ut/MaxHeapTest.cpp"
)
register_fprime_ut("Os_pthreads_max_heap")
