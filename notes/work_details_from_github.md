# Work Details From GitHub Projects

These notes summarize resume-ready evidence from Harpreet Singh's recent
GitHub engineering and research projects.

## QLIF_QSNN_FPGA

- Built a software-to-hardware FPGA research flow for PC-DDM-SNN and Quantum
  Leaky-Integrate-and-Fire models on matched MNIST/N-MNIST 14x14 protocols.
- Used 196-feature MNIST inputs and 12 x 196 N-MNIST temporal inputs packed as
  32-bit BRAM words with lower 16-bit `ap_fixed<16,6>` payloads.
- Automated dataset-matched training, HLS weight export, software checks,
  Vitis HLS, Vivado, XSA/bitstream generation, and UART board-test workflows.
- Diagnosed low UART accuracy by separating metadata reporting defects from
  classifier score vectors and documenting when hardware-weight rebuilds are
  required.

## QSNN_EarlyExit_FPGA_Research

- Built a reproducible Arty A7-35T QSNN MicroBlaze system with AXI4-Lite
  control, BRAM input/output buffers, UART diagnostics, and MNIST board tests.
- Recorded implementation evidence including 0.698-0.699 ms HLS latency at
  100 MHz, 9.87% LUT utilization, 5.13% FF utilization, 41.0% BRAM tile
  utilization, 3.33% DSP utilization, zero routing errors, and positive routed
  timing slack.
- Defined an adaptive early-exit QSNN research plan comparing ANN, SNN,
  fixed-step QSNN, and early-exit QSNN on accuracy, latency, energy, FPGA
  utilization, and robustness.

## snn_qisnn_rodent_raster

- Prepared a rodent neural-raster decision pipeline for no-lick, left-lick, and
  right-lick prediction from neural population dynamics.
- Adapted the temporal QiSNN hardware interface to 2352-word input BRAM,
  AXI4-Lite `ap_ctrl_hs`, fixed-point payloads, MicroBlaze readback, and
  debug-visible state BRAM planning.
- Documented active QiSNN fixed-point evaluation with deployed HLS weights,
  reporting 96.34% MNIST14 accuracy and robustness outputs for noise, dropout,
  salt-pepper, and quantization conditions.

## arty_z7_50m_llm

- Designed a staged Arty Z7-20 accelerator contract for a 50.35M-parameter
  decoder-only transformer with 16 layers, width 512, 8 heads, vocabulary
  8,192, and INT8/INT4 weight payloads.
- Defined architecture where Cortex-A9 Linux handles tokenization and layer
  scheduling while programmable logic accelerates DDR-backed INT8 matrix-vector
  operations over AXI HP with AXI4-Lite control.
- Documented validation gates for XSA/BOOT.BIN creation, 115200-baud UART proof
  tests, expected `mismatches=0`, 1,000 repeated launches, audio PWM, and a
  microphone-to-response proof path.

## 8eeg8fNIRS

- Integrated ADS1299 8-channel EEG, ADS8688 fNIRS analog acquisition, DAC8565
  output control, watchdog PWM, and TDM MUX sequencing on Raspberry Pi.
- Built Python scripts for shared SPI/GPIO concurrency, standalone hardware
  validation, live plotting, and CSV logging for offline analysis.

## Sheeg

- Built research-session orchestration for CGX EEG plus behavioural game
  recording.
- Integrated UDP-to-LSL marker bridging, LSL stream probing, LabRecorder remote
  control, XDF session recording, manifests, stream logs, and session summaries.
- Defined the marker contract for synchronized behavioural events such as
  session start, trial start, stimulus direction, response window, response key,
  and session end.
