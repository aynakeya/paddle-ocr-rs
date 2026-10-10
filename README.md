# rapid-ocr-rs

`rapid-ocr-rs` is a Rust OCR project that runs PaddleOCR-family ONNX models with ONNX Runtime.
It provides:

## Runtime compatibility

This version is tested with `ort 2.0.0-rc.13` and `ndarray 0.17`. The default
`download-binaries` feature uses the ONNX Runtime 1.28.0 distribution supplied
by `ort`; applications sharing an ONNX Runtime instance should use the same
`ort` version.

CUDA and CANN support require the `cuda-provider` and `cann-provider` features,
respectively. DirectML is enabled on Windows. If a provider is not compiled in
or is unavailable, the existing CPU fallback and `fail_if_provider_unavailable`
setting still apply.

For offline inference, supply the detection, classification, and recognition
model paths and set each stage's `allow_download` to `false`. Recognition also
needs an embedded character list or a local `rec_keys_path`.

## Implementation Reference

This project's implementation and behavior parity are based on:

- https://github.com/RapidAI/RapidOCR
