# Generate unit test
# UT_SOURCE_FILES: Sources for unit test
# UT_MODULES: List of modules linked in unit tests

set(UT_SOURCE_FILES
  "${FPRIME_CORE_DIR}/Svc/FileDownlink/FileDownlinkComponentAi.xml"
  "${CMAKE_CURRENT_LIST_DIR}/Tester.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Main.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/FileBuffer.cpp"
)

set(UT_MODULES
  "${FPRIME_CORE_DIR}/Svc/FileDownlink"
  "${FPRIME_CORE_DIR}/Fw/Tlm"
  "${FPRIME_CORE_DIR}/Fw/Log"
  "${FPRIME_CORE_DIR}/Fw/Time"
  "${FPRIME_CORE_DIR}/Fw/FilePacket"
  "${FPRIME_CORE_DIR}/Fw/Cmd"
  "${FPRIME_CORE_DIR}/Fw/Com"
  "${FPRIME_CORE_DIR}/Fw/Buffer"
  "${FPRIME_CORE_DIR}/Fw/Port"
  "${FPRIME_CORE_DIR}/Fw/Comp"
  "${FPRIME_CORE_DIR}/Os"
  "${FPRIME_CORE_DIR}/Fw/Obj"
  "${FPRIME_CORE_DIR}/Utils/Hash"
  "${FPRIME_CORE_DIR}/CFDP/Checksum"
  "${FPRIME_CORE_DIR}/Fw/Types"
  "${FPRIME_CORE_DIR}/Svc/Ping"
)

#add_unit_test("${UT_SOURCE_FILES}" "${UT_MODULES}")
