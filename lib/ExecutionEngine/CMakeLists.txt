llvm_map_components_to_libnames(outlibs "nativecodegen" "IPO")
add_llvm_library(MLIRExecutionEngine
  ExecutionEngine.cpp
  MemRefUtils.cpp
  OptUtils.cpp

  ADDITIONAL_HEADER_DIRS
  ${MLIR_MAIN_INCLUDE_DIR}/mlir/ExecutionEngine
  )
target_link_libraries(MLIRExecutionEngine MLIRLLVMIR MLIRPass MLIRTransforms LLVMExecutionEngine LLVMOrcJIT LLVMSupport ${outlibs})
