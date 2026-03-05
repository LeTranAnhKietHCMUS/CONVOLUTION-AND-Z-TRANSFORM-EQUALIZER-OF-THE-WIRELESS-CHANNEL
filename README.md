# Zero-Forcing-Equalizer-ZTransform ⚡

## 🇬🇧 English

A Python-based Digital Signal Processing project that designs a Zero-Forcing
(ZF) equalizer using convolution and the Z-Transform to recover an original
signal distorted by a wireless multipath channel, developed as a Digital
Signal Processing course project at Ho Chi Minh City University of Science.

### Overview

In wireless communication systems, transmitted signals are distorted by
multipath fading and channel effects. This project models the problem
mathematically: a known channel impulse response h(n) distorts the original
signal x(n) to produce y(n) = x(n) * h(n). A Zero-Forcing equalizer is then
designed in the Z-domain as H_eq(z) = 1/H(z), converted back to the time
domain, and convolved with the received signal to reconstruct the original.

### Signal Processing Chain
| Step | Operation | Description |
|---|---|---|
| 1 | Channel modeling | y(n) = x(n) * h(n), where h = [1, 3] |
| 2 | Z-Transform | H(z) = 1 + 3z⁻¹ |
| 3 | ZF Equalizer design | H_eq(z) = 1/H(z) |
| 4 | Inverse Z-Transform | h_eq(n) = (−3)ⁿ u(n) |
| 5 | Equalization | x̂(n) = y(n) * h_eq(n) ≈ x(n) |

### Key Theory
| Concept | Formula |
|---|---|
| Convolution (LTI system) | y(n) = Σ x(k)·h(n−k) |
| Z-Transform | X(z) = Σ x(n)·z⁻ⁿ |
| Zero-Forcing Equalizer | H_eq(z) = 1/H(z) |
| Channel used | H(z) = 1 + 3z⁻¹ |
| Equalizer impulse response | h_eq(n) = (−3)ⁿ u(n) |

### Results

The equalized signal xh = y * h_eq successfully recovers the original
signal x = [1, 2, 3], confirming that the ZF equalizer correctly
compensates for the channel distortion.

### Improvements over Original Code
- Added a reusable `inverse_z_transform(Heq, num_terms)` function for
  flexible time-domain conversion with configurable impulse response length
- Code is generalized to support different channel responses beyond the
  fixed example

### Technologies
- Python — NumPy, Matplotlib
- Concepts: Convolution, Z-Transform, Inverse Z-Transform, LTI systems,
  Zero-Forcing equalization

### How to Run
```bash
pip install numpy matplotlib
python project3.py
```

---

## 🇻🇳 Tiếng Việt

Đồ án Xử lý Tín hiệu Số sử dụng Python để thiết kế bộ cân bằng
Zero-Forcing (ZF) dựa trên tích chập và biến đổi Z, nhằm khôi phục tín
hiệu gốc bị biến dạng qua kênh truyền đa đường, thực hiện trong khuôn
khổ môn Xử lý Tín hiệu Số tại Trường Đại học Khoa học Tự nhiên TP.HCM.

### Tổng quan

Trong hệ thống thông tin không dây, tín hiệu phát bị méo do kênh truyền
đa đường. Đồ án mô hình hóa bài toán: kênh truyền h(n) làm biến dạng tín
hiệu gốc x(n) thành y(n) = x(n) * h(n). Bộ cân bằng ZF được thiết kế
trong miền Z theo công thức H_eq(z) = 1/H(z), sau đó chuyển về miền thời
gian và tích chập với tín hiệu nhận để khôi phục tín hiệu gốc.

### Chuỗi xử lý tín hiệu
| Bước | Phép toán | Mô tả |
|---|---|---|
| 1 | Mô hình hóa kênh | y(n) = x(n) * h(n), h = [1, 3] |
| 2 | Biến đổi Z | H(z) = 1 + 3z⁻¹ |
| 3 | Thiết kế bộ cân bằng ZF | H_eq(z) = 1/H(z) |
| 4 | Biến đổi Z ngược | h_eq(n) = (−3)ⁿ u(n) |
| 5 | Cân bằng tín hiệu | x̂(n) = y(n) * h_eq(n) ≈ x(n) |

### Lý thuyết chính
| Khái niệm | Công thức |
|---|---|
| Tích chập (hệ LTI) | y(n) = Σ x(k)·h(n−k) |
| Biến đổi Z | X(z) = Σ x(n)·z⁻ⁿ |
| Bộ cân bằng Zero-Forcing | H_eq(z) = 1/H(z) |
| Kênh truyền | H(z) = 1 + 3z⁻¹ |
| Đáp ứng xung bộ cân bằng | h_eq(n) = (−3)ⁿ u(n) |

### Kết quả

Tín hiệu sau cân bằng xh = y * h_eq khôi phục thành công tín hiệu gốc
x = [1, 2, 3], xác nhận bộ cân bằng ZF bù đắp hiệu quả méo do kênh
truyền gây ra.

### Cải tiến so với code gốc
- Thêm hàm `inverse_z_transform(Heq, num_terms)` có thể tái sử dụng,
  cho phép điều chỉnh linh hoạt số lượng hệ số đáp ứng xung
- Code được tổng quát hóa, có thể áp dụng cho nhiều kênh truyền khác nhau

### Công nghệ
- Python — NumPy, Matplotlib
- Khái niệm: Tích chập, Biến đổi Z, Biến đổi Z ngược, Hệ LTI,
  Bộ cân bằng Zero-Forcing

### Cách chạy
```bash
pip install numpy matplotlib
python project3.py
```
