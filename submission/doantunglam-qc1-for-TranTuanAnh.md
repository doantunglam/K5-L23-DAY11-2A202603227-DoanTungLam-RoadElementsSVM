

# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Trần Tuấn Anh - 2A202603230    
Người kiểm (học viên): Doãn Tùng Lâm
Ngày: 2026-11-22                         
Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): `trantuananh-front.zip`, `trantuananh-fisheye.zip` (revision 1)  
Số ảnh kiểm: 6 (+ 0 ảnh thêm, ghi riêng)  
Số nhãn đã kiểm (shape + tag): 62 (38 shape + 24 tag)  



## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 1 | nhẹ |
| QC1-02 đủ L1, R1 | bỏ sót | 7 | 1 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 12 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 12 | 1 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 12 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 12 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 14 | 1 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 5 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 12 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 7 | 1 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 14 | 0 | chính |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-01 | A10 | tag weather | nhẹ | Thiếu tag weather |
| 2 | QC1-02 | A07 | lane | nặng | Chưa có R1 dù thấy vạch trắng liền bên phải xe |
| 3 | QC1-04 | A07 | lane (L1, #2) | chính | Polyline lệch khỏi tâm vạch khoảng 9 px ở nửa xa |
| 4 | QC1-07 | A07 | drivable (direct, #8) | chính | Polygon tràn lên vỉa hè bên phải |
| 5 | QC1-10 | A10 | traffic_sign | chính | Thiếu biển phụ ngay dưới biển cấm |


## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| B04 | Vạch đứt xa chỉ thấy hai vệt: có phải lane hay vệt phản chiếu? | (giả lập, chưa có) |

## Quyết định
Lỗi nặng: 1   Lỗi chính: 3 / 62 nhãn = 4,8 %   Lỗi nhẹ: 1   Ca chờ lead: 1  
Quyết định (Release / Hold / Rework): **Rework**  
Lý do (theo luật của phiếu): có một lỗi nặng (QC1-02 thiếu R1 ở A07) → Rework. Lỗi chính 4,8 % thấp hơn ngưỡng 5 % nên không phải lý do. Lỗi nhẹ (thiếu tag weather) chỉ ghi lại, không tính vào tỉ lệ. Ca mơ hồ ở B04 không đổi kết luận, nên không dùng Hold. Nếu người nộp sửa được lỗi QC1-02 này thì lô không còn lỗi nặng và có thể Release ở lần kiểm sau.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../../docs/qc_severity_road_v1.0.md).
