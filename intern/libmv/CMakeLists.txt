# SPDX-FileCopyrightText: 2011 Blender Authors
#
# SPDX-License-Identifier: GPL-2.0-or-later

# NOTE: This file is automatically generated by bundle.sh script
#       If you're doing changes in this file, please update template
#       in that script too

set(INC
  .
)

set(INC_SYS
)

set(SRC
  libmv-capi.h
)

set(LIB

)

if(WITH_LIBMV)
  if(WIN32)
    add_definitions(-D_USE_MATH_DEFINES)
  endif()
  add_definitions(${GFLAGS_DEFINES})
  add_definitions(${GLOG_DEFINES})
  add_definitions(-DLIBMV_GFLAGS_NAMESPACE=${GFLAGS_NAMESPACE})

  if(WITH_TBB)
    add_definitions(-DLIBMV_USE_TBB_THREADS)
  endif()

  list(APPEND INC
    ../guardedalloc
  )

  list(APPEND INC_SYS
    ${GFLAGS_INCLUDE_DIRS}
    ${GLOG_INCLUDE_DIRS}
    ${PNG_INCLUDE_DIRS}
    ${ZLIB_INCLUDE_DIRS}
    ../../extern/ceres/include
    ../../extern/ceres/config
  )

  list(APPEND LIB
    extern_ceres
    PUBLIC bf::dependencies::optional::tbb

    ${GLOG_LIBRARIES}
    ${GFLAGS_LIBRARIES}
    ${PNG_LIBRARIES}

    PRIVATE bf::dependencies::eigen
  )

  add_definitions(
    -DWITH_LIBMV_GUARDED_ALLOC
    -DLIBMV_NO_FAST_DETECTOR=
  )

  list(APPEND SRC
    intern/autotrack.cc
    intern/camera_intrinsics.cc
    intern/detector.cc
    intern/frame_accessor.cc
    intern/homography.cc
    intern/image.cc
    intern/logging.cc
    intern/reconstruction.cc
    intern/track_region.cc
    intern/tracks.cc
    intern/tracksN.cc
    libmv/autotrack/autotrack.cc
    libmv/autotrack/predict_tracks.cc
    libmv/autotrack/tracks.cc
    libmv/base/aligned_malloc.cc
    libmv/image/array_nd.cc
    libmv/image/convolve.cc
    libmv/multiview/conditioning.cc
    libmv/multiview/euclidean_resection.cc
    libmv/multiview/fundamental.cc
    libmv/multiview/homography.cc
    libmv/multiview/panography.cc
    libmv/multiview/panography_kernel.cc
    libmv/multiview/projection.cc
    libmv/multiview/triangulation.cc
    libmv/numeric/numeric.cc
    libmv/numeric/poly.cc
    libmv/simple_pipeline/bundle.cc
    libmv/simple_pipeline/camera_intrinsics.cc
    libmv/simple_pipeline/detect.cc
    libmv/simple_pipeline/distortion_models.cc
    libmv/simple_pipeline/initialize_reconstruction.cc
    libmv/simple_pipeline/intersect.cc
    libmv/simple_pipeline/keyframe_selection.cc
    libmv/simple_pipeline/modal_solver.cc
    libmv/simple_pipeline/packed_intrinsics.cc
    libmv/simple_pipeline/pipeline.cc
    libmv/simple_pipeline/reconstruction.cc
    libmv/simple_pipeline/reconstruction_scale.cc
    libmv/simple_pipeline/resect.cc
    libmv/simple_pipeline/tracks.cc
    libmv/tracking/brute_region_tracker.cc
    libmv/tracking/hybrid_region_tracker.cc
    libmv/tracking/klt_region_tracker.cc
    libmv/tracking/pyramid_region_tracker.cc
    libmv/tracking/retrack_region_tracker.cc
    libmv/tracking/track_region.cc
    libmv/tracking/trklt_region_tracker.cc


    intern/autotrack.h
    intern/camera_intrinsics.h
    intern/detector.h
    intern/frame_accessor.h
    intern/homography.h
    intern/image.h
    intern/logging.h
    intern/reconstruction.h
    intern/region.h
    intern/track_region.h
    intern/tracks.h
    intern/tracksN.h
    intern/utildefines.h
    libmv/autotrack/autotrack.h
    libmv/autotrack/callbacks.h
    libmv/autotrack/frame_accessor.h
    libmv/autotrack/marker.h
    libmv/autotrack/model.h
    libmv/autotrack/predict_tracks.h
    libmv/autotrack/quad.h
    libmv/autotrack/reconstruction.h
    libmv/autotrack/region.h
    libmv/autotrack/tracks.h
    libmv/base/aligned_malloc.h
    libmv/base/array.h
    libmv/base/id_generator.h
    libmv/base/map.h
    libmv/base/scoped_ptr.h
    libmv/base/vector.h
    libmv/base/vector_utils.h
    libmv/build/build_config.h
    libmv/image/array_nd.h
    libmv/image/convolve.h
    libmv/image/correlation.h
    libmv/image/image_converter.h
    libmv/image/image_drawing.h
    libmv/image/image.h
    libmv/image/sample.h
    libmv/image/tuple.h
    libmv/logging/logging.h
    libmv/multiview/conditioning.h
    libmv/multiview/euclidean_resection.h
    libmv/multiview/fundamental.h
    libmv/multiview/homography_error.h
    libmv/multiview/homography.h
    libmv/multiview/homography_parameterization.h
    libmv/multiview/nviewtriangulation.h
    libmv/multiview/panography.h
    libmv/multiview/panography_kernel.h
    libmv/multiview/projection.h
    libmv/multiview/resection.h
    libmv/multiview/triangulation.h
    libmv/multiview/two_view_kernel.h
    libmv/numeric/dogleg.h
    libmv/numeric/function_derivative.h
    libmv/numeric/levenberg_marquardt.h
    libmv/numeric/numeric.h
    libmv/numeric/poly.h
    libmv/simple_pipeline/bundle.h
    libmv/simple_pipeline/callbacks.h
    libmv/simple_pipeline/camera_intrinsics.h
    libmv/simple_pipeline/camera_intrinsics_impl.h
    libmv/simple_pipeline/detect.h
    libmv/simple_pipeline/distortion_models.h
    libmv/simple_pipeline/initialize_reconstruction.h
    libmv/simple_pipeline/intersect.h
    libmv/simple_pipeline/keyframe_selection.h
    libmv/simple_pipeline/modal_solver.h
    libmv/simple_pipeline/packed_intrinsics.h
    libmv/simple_pipeline/pipeline.h
    libmv/simple_pipeline/reconstruction.h
    libmv/simple_pipeline/reconstruction_scale.h
    libmv/simple_pipeline/resect.h
    libmv/simple_pipeline/tracks.h
    libmv/threading/threading.h
    libmv/threading/parallel_for.h
    libmv/tracking/brute_region_tracker.h
    libmv/tracking/hybrid_region_tracker.h
    libmv/tracking/kalman_filter.h
    libmv/tracking/klt_region_tracker.h
    libmv/tracking/pyramid_region_tracker.h
    libmv/tracking/region_tracker.h
    libmv/tracking/retrack_region_tracker.h
    libmv/tracking/track_region.h
    libmv/tracking/trklt_region_tracker.h

    third_party/msinttypes/inttypes.h
    third_party/msinttypes/stdint.h
  )


  if(WITH_GTESTS)
    blender_add_lib(libmv_test_dataset "./libmv/multiview/test_data_sets.cc" "${INC}" "${INC_SYS}" "${LIB}")

    blender_add_test_executable("libmv_predict_tracks" "./libmv/autotrack/predict_tracks_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_tracks" "./libmv/autotrack/tracks_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_scoped_ptr" "./libmv/base/scoped_ptr_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_vector" "./libmv/base/vector_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_array_nd" "./libmv/image/array_nd_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_convolve" "./libmv/image/convolve_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_image" "./libmv/image/image_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_sample" "./libmv/image/sample_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_tuple" "./libmv/image/tuple_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_euclidean_resection" "./libmv/multiview/euclidean_resection_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_fundamental" "./libmv/multiview/fundamental_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_homography" "./libmv/multiview/homography_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_nviewtriangulation" "./libmv/multiview/nviewtriangulation_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_panography" "./libmv/multiview/panography_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_projection" "./libmv/multiview/projection_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_resection" "./libmv/multiview/resection_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_triangulation" "./libmv/multiview/triangulation_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_dogleg" "./libmv/numeric/dogleg_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_function_derivative" "./libmv/numeric/function_derivative_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_levenberg_marquardt" "./libmv/numeric/levenberg_marquardt_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_numeric" "./libmv/numeric/numeric_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_poly" "./libmv/numeric/poly_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_camera_intrinsics" "./libmv/simple_pipeline/camera_intrinsics_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_detect" "./libmv/simple_pipeline/detect_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_intersect" "./libmv/simple_pipeline/intersect_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_keyframe_selection" "./libmv/simple_pipeline/keyframe_selection_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_modal_solver" "./libmv/simple_pipeline/modal_solver_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_resect" "./libmv/simple_pipeline/resect_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_brute_region_tracker" "./libmv/tracking/brute_region_tracker_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_klt_region_tracker" "./libmv/tracking/klt_region_tracker_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_pyramid_region_tracker" "./libmv/tracking/pyramid_region_tracker_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
    blender_add_test_executable("libmv_parallel_for" "./libmv/threading/parallel_for_test.cc" "${INC}" "${INC_SYS}" "libmv_test_dataset;bf_intern_libmv;${LIB}")
  endif()
else()
  list(APPEND SRC
    intern/stub.cc
  )
endif()

blender_add_lib(bf_intern_libmv "${SRC}" "${INC}" "${INC_SYS}" "${LIB}")
