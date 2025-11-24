


# Anonymous Repository for Double-Blind Review

![Configuration examples](ReadMeImages/demo.png)

  > **Note**: This anonymous repository will be ready before Nov. 24 (authors need to remove personal information for double-blind review).
  > README may be continuously updated to serve as a tutorial.
  > If accepted, the codes will be open-source for the public.

  ---

  ## Development Environment

  This work was developed with the **Eclipse IDE**.

  ---

  ## Configuration Guide

  To run different configurations, comment/uncomment the settings in `parameters.hpp`, then build and run.

  ### Example Configuration

  ```cpp
  #define AUTHORLLMSwitchON
  //#define AUTHORLLMSwitchON

  #define NOCSIZEMC8_8X8
  #define LLM_TOKEN_SIZE 1
  #define case1_default

  This runs an attention matrix in an 8×8 NoC with 8-token (sentence-level) using the baseline configuration.

  ---
  Configuration Options

  1. Workload Selection

  Choose between attention matrix or LeNet:

  #define AUTHORLLMSwitchON   // Enable LLM attention workload
  //#define AUTHORLLMSwitchON  // Disable for LeNet workload

  2. NoC Size Options

  Select the mesh size and memory controller configuration:

  //#define NOCSIZEMC2_4X4      // 2 MCs in 4×4 mesh (base tile pattern)
  #define NOCSIZEMC8_8X8       // 8 MCs in 8×8 mesh (2×2 tiles)
  //#define NOCSIZEMC32_16X16   // 32 MCs in 16×16 mesh (4×4 tiles)
  //#define NOCSIZEMC128_32X32  // 128 MCs in 32×32 mesh (8×8 tiles)

  3. Token Length Options

  Note: Only applicable when #define AUTHORLLMSwitchON is enabled.

  #define LLM_TOKEN_SIZE 1     // 8 tokens (~50 seconds on Intel 10700)
  //#define LLM_TOKEN_SIZE 2    // 128 tokens (~20+ minutes)

  4. Optimization Configurations

  Select the optimization strategy:

  #define case1_default                    // Baseline
  //#define case2_samos                    // SAMOS
  //#define case3_affiliatedordering       // Affiliated Ordering
  //#define case4_seperratedordering       // Separated Ordering
  //#define case5_COMBO1                   // Combo-1
  //#define case6_COMBO2                   // Combo-2
  //#define case7_FireAdvance              // Fire Advance
  //#define case8_BinarySwitch             // Binary Switch
  //#define case9_MOSAIC1                  // MOSAIC-1
  //#define case10_MOSAIC2                 // MOSAIC-2

  ---


  Performance Note

  - 8 tokens: ~50 seconds on Intel Core i7-10700
  - 128 tokens: ~20 minutes on Intel Core i7-10700

  ---





