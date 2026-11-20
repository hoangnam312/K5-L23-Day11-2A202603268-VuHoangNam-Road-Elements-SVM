# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): 2A202603296
Người kiểm (học viên): **2A202603268**  
Ngày: **20/11/2026**  Phiên bản guideline: **Road v1.0**  
File được kiểm (tên + `revision` trong manifest):
Số ảnh kiểm: **6** Số nhãn đã kiểm (shape + tag): **40**

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 6 | 1 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 6 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 12 | 1 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 12 | 1 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 8 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 8 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 6 | 1 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 4 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 4 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 4 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 6 | 0 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| ---: | --- | --- | --- | --- | --- |
| 1 | QC1-01 | A02 | `camera`, tag | nặng | Gán `fisheye_front` trong khi ảnh mẫu thuộc camera `front`. |
| 2 | QC1-03 | A03 | `lane`, id 7 | nặng | Gán `position=R1` cho vạch thuộc làn `L1`, làm nhầm làn xe. |
| 3 | QC1-04 | A04 | `lane`, id 12 | chính | Polyline lệch tâm vạch khoảng 9 px, vượt ngưỡng 5 px của guideline. |
| 4 | QC1-07 | B02 | `drivable`, id 3 | chính | Polygon tràn qua phần vỉa hè; cần thu lại theo mép vùng lái được. |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| — | Không có | — |

## Quyết định
Lỗi nặng: **2** Lỗi chính: **2 / 40 nhãn = 5%** Lỗi nhẹ: **0** Ca chờ lead: **0**  
Quyết định: **Rework**  
Lý do: Có lỗi nặng (QC1-01 và QC1-03); chỉ một lỗi nặng cũng đủ để yêu cầu Rework. Tỉ lệ lỗi chính bằng 5%, chưa vượt ngưỡng trên 5%.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); “sai thuộc tính” và “lỗi file” là khóa học thêm. Cách xếp mức: [thang mức lỗi](docs/qc_severity_road_v1.0.md).
