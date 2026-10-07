# Lab 21 — Phân tích rủi ro AI qua case study thực tế

- Họ và tên: Phan Thị Khánh Linh
- MSSV / mã học viên: 2A202602360
- Lớp: Track 1
- Ngành đã chọn: HR / Tuyển dụng

## 1. Industry Risk Snapshot

| Nội dung | Đánh giá |
|---|---|
| Harm chính | AI trong tuyển dụng có thể loại ứng viên không công bằng, hạn chế cơ hội việc làm và lặp lại phân biệt dựa trên dữ liệu lịch sử. Ngoài ra, AI có thể làm lộ thông tin cá nhân khi hồ sơ và dữ liệu ứng viên được xử lý không an toàn. |
| High-stakes | **High**. Quyết định tuyển dụng có thể trực tiếp ảnh hưởng đến thu nhập, cơ hội nghề nghiệp và tương lai của cá nhân. |
| Dữ liệu nhạy cảm | Hồ sơ cá nhân, CV, kinh nghiệm làm việc, kỹ năng, thông tin liên hệ, ngày sinh, giới tính, tuổi và các dữ liệu có thể cho thấy thuộc tính bảo vệ. Dữ liệu này có thể được dùng để phân loại ứng viên nếu không được kiểm soát. |
| Human review | **High**. Người tuyển dụng hoặc nhân sự cần kiểm tra kết quả AI, giải thích lý do, cho phép ứng viên phản hồi và có quyền hủy kết quả nếu phát hiện sai lệch. AI không nên là người duy nhất quyết định tuyển dụng. |

### Đánh giá tổng thể

AI có thể giúp sàng lọc hồ sơ và giảm khối lượng công việc thủ công, nhưng hệ thống này có rủi ro cao khi dữ liệu lịch sử chứa các mẫu thiên lệch. Nếu model không được kiểm chứng trước khi triển khai, nguyên nhân lỗi có thể nằm ở dữ liệu huấn luyện, cách thuật toán đánh giá hoặc cách hệ thống được sử dụng trong quy trình tuyển dụng.

---

## 2. Case study 1 — Amazon: Công cụ sàng lọc CV bị thiên vị giới tính

### Brief Case

- **Tổ chức / sản phẩm AI:** Công cụ sàng lọc CV nội bộ của Amazon, do công ty tự phát triển để hỗ trợ quy trình tuyển dụng.
- **Bối cảnh:** Từ năm 2014 đến năm 2017, Amazon đã thử nghiệm và phát triển hệ thống đánh giá CV cho một số vị trí.
- **AI được dùng để làm gì:** Hệ thống được thiết kế để xếp hạng hồ sơ ứng viên và dự đoán ứng viên có phù hợp với các vị trí kỹ thuật hay không.
- **Sự kiện đáng chú ý:** Reuters đưa tin công nghệ này đã tự học các mẫu từ những hồ sơ đã được Amazon tuyển dụng trước đó và có xu hướng ưu tiên ứng viên nam. Hệ thống cũng bị cho là đánh giá thấp các hồ sơ có chứa từ như “women’s” hoặc các liên kết đến trường đại học nữ.
- **Số liệu có nguồn:** Reuters báo cáo rằng công ty đã ngừng dự án này vào năm 2018 sau khi nhận thấy hệ thống có thiên vị giới tính. Không có số liệu về số lượng hồ sơ bị ảnh hưởng được công bố công khai trong bài báo này.
- **Nguồn:** Reuters, “Amazon scraps secret AI recruiting tool that showed bias against women,” 10 tháng 10 năm 2018, URL: https://www.reuters.com/article/world/insight-amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK0AG/
- **Fact / Interpretation / Risk:**
  - **Fact:** Reuters xác nhận Amazon đã bỏ dự án sàng lọc CV tự động sau khi phát hiện hệ thống phản ánh thiên vị giới tính.
  - **Interpretation:** Các mẫu trong dữ liệu tuyển dụng lịch sử có thể đã tạo ra sự ưu tiên đối với ứng viên nam, khiến hệ thống đánh giá sai hồ sơ của nữ ứng viên.
  - **Risk:** Nếu hệ thống được triển khai với dữ liệu tương tự mà không có kiểm tra và điều chỉnh, ứng viên nữ có thể tiếp tục bị đánh giá thấp ở quy mô lớn.

### Harm Map Worksheet

| Trường | Phân tích |
|---|---|
| High-risk moment | AI xếp hạng CV khi căn cứ lịch sử tuyển dụng có thể chứa mẫu thiên vị giới tính. |
| Stakeholder bị ảnh hưởng | Ứng viên nữ, đội ngũ tuyển dụng, Amazon và các nhóm cộng đồng bị ảnh hưởng bởi cơ hội việc làm bất công. |
| Failure mode | **Bias / Fairness**; hệ thống ưu tiên hoặc đánh giá thấp các hồ sơ dựa trên giới tính qua dữ liệu lịch sử. |
| Layer bắt đầu lỗi | **Chưa đủ bằng chứng để xác định layer chính xác.** Một giả thuyết khả dĩ là vấn đề nằm ở **Model** hoặc dữ liệu lịch sử dùng để huấn luyện; nguồn công khai không mô tả đầy đủ kiến trúc hệ thống. |
| Harm xảy ra là gì? | Ứng viên nữ có thể bị loại khỏi vòng tuyển dụng hoặc bị đánh giá thấp dù có năng lực phù hợp. |
| Harm lens | **Opportunity loss** và **Dignity loss**. Ứng viên có thể mất cơ hội việc làm và cảm thấy bị đối xử không công bằng. |
| Severity | **High**. Một quyết định tuyển dụng sai có thể ảnh hưởng trực tiếp đến thu nhập và nghề nghiệp của cá nhân. |
| Scale | **Chưa đủ dữ liệu công khai để ước tính số lượng ứng viên bị ảnh hưởng.** Reuters xác nhận vấn đề là một lỗi ở hệ thống, không nêu số lượng hồ sơ cụ thể. |
| Probability | **High** nếu dữ liệu lịch sử tiếp tục chứa mẫu thiên vị và hệ thống được kiểm tra không đầy đủ. Đây là đánh giá dựa trên quy trình AI hiện có, không phải xác suất đã được báo cáo. |
| Frequency | **Chưa đủ bằng chứng để xác định frequency.** Reuters không công bố số lần hệ thống đưa ra kết quả sai hoặc số hồ sơ bị ảnh hưởng. |
| Vì sao? | Mặc dù dự án đã bị dừng, nguồn chỉ xác nhận có thiên vị và không cung cấp dữ liệu về quy mô, tần suất hoặc số liệu ứng viên. Vì vậy, kết luận về mức độ phổ biến cần được giữ ở dạng suy luận có giới hạn. |

---

## 3. Case study 2 — iTutorGroup: Phần mềm tuyển dụng tự động phân biệt độ tuổi

### Brief Case

- **Tổ chức / sản phẩm:** iTutorGroup, Inc.; Shanghai Ping’An Intelligent Education Technology Co., Ltd.; và Tutor Group Limited. Các công ty này vận hành hoạt động tuyển tutor trực tuyến tại Hoa Kỳ.
- **Bối cảnh:** Công ty tuyển tutor để dạy tiếng Anh trực tuyến cho người học ở Trung Quốc. Theo EEOC, hệ thống application/recruitment software yêu cầu ngày sinh và lập trình để tự động từ chối ứng viên theo độ tuổi.
- **Hệ thống được dùng để làm gì:** Phần mềm tuyển dụng tự động xử lý đơn ứng tuyển. EEOC cáo buộc hệ thống tự động từ chối nữ từ 55 tuổi trở lên và nam từ 60 tuổi trở lên.
- **Sự kiện đáng chú ý:** Wendy Pincus nộp đơn với ngày sinh thật và bị từ chối ngay. Cùng thông tin nhưng ngày sinh mới hơn thì bà được mời phỏng vấn. EEOC cho rằng việc đổi ngày sinh làm thay đổi kết quả tuyển dụng là bằng chứng trực tiếp về cơ chế tự động theo tuổi.
- **Số liệu có nguồn:** EEOC xác nhận **hơn 200 ứng viên đủ điều kiện tại Hoa Kỳ** bị từ chối vì tuổi; ngoài ra còn có charging party Wendy Pincus. Khoản dàn xếp trong vụ kiện là **365.000 USD**, không phải số lượng người bị ảnh hưởng.
- **Nguồn:**
  - EEOC, “EEOC Sues iTutorGroup for Age Discrimination,” 5 tháng 5 năm 2022: https://www.eeoc.gov/newsroom/eeoc-sues-itutorgroup-age-discrimination
  - EEOC, “iTutorGroup to Pay $365,000 to Settle EEOC Discriminatory Hiring Suit,” 11 tháng 9 năm 2023: https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-hiring-suit
  - EEOC Amended Complaint, Equal Employment Opportunity Commission v. iTutorGroup, Inc., Case No. 1:22-cv-02565: https://clearinghouse-umich-production.s3.amazonaws.com/media/doc/158461.pdf
- **Fact / Interpretation / Risk:**
  - **Fact:** EEOC xác nhận hệ thống được lập trình để tự động từ chối nữ từ 55 tuổi trở lên và nam từ 60 tuổi trở lên. Hơn 200 ứng viên đủ điều kiện tại Hoa Kỳ bị từ chối vì tuổi, và 365.000 USD được dùng để dàn xếp vụ kiện.
  - **Interpretation:** Đây là trường hợp phần mềm tuyển dụng tự động dùng ngày sinh, một thuộc tính được pháp luật bảo vệ, để loại ứng viên. Thực tế không thể khẳng định hệ thống là machine-learning model vì hồ sơ công khai không công bố kiến trúc bên trong.
  - **Risk:** Nếu cơ chế tự động tương tự được giữ lại mà không có kiểm tra công bằng và human review, các ứng viên lớn tuổi có thể bị loại hàng loạt.

### Harm Map Worksheet

| Trường | Phân tích |
|---|---|
| High-risk moment | Hệ thống xử lý đơn ứng tuyển và tự động quyết định loại ứng viên theo ngày sinh. |
| Stakeholder bị ảnh hưởng | Ứng viên lớn tuổi đủ điều kiện tại Hoa Kỳ, charging party Wendy Pincus, đội ngũ tuyển dụng, iTutorGroup và người học có thể mất cơ hội được học với tutor phù hợp. |
| Failure mode | **Bias / Fairness** do hệ thống loại ứng viên theo tuổi. EEOC cũng cho rằng không có human review phù hợp trước quyết định từ chối, nhưng nguồn không xác nhận toàn bộ quy trình của công ty. |
| Layer bắt đầu lỗi | **Chưa đủ bằng chứng để xác định Model, Grounding, Safety hay UX.** Nguồn xác nhận lỗi nằm ở application/recruitment software được lập trình tự động; kiến trúc bên trong không được công khai. |
| Harm xảy ra là gì? | Người đủ điều kiện bị từ chối vì tuổi, mất cơ hội việc làm và thu nhập, dù có bằng cử nhân hoặc cao hơn. |
| Harm lens | **Opportunity loss** và có thể có **Dignity loss**. |
| Severity | **High**. Quyết định tuyển dụng ảnh hưởng trực tiếp đến cơ hội nghề nghiệp và thu nhập. |
| Scale | **Hơn 200 ứng viên** theo EEOC, cộng charging party Wendy Pincus. Không ghi số lượng chính xác 200 hoặc 201. |
| Probability | **Chưa đủ dữ liệu để xác định xác suất chính xác.** Đây là đánh giá dựa trên bằng chứng pháp lý, không phải thống kê về tần suất. |
| Frequency | **Chưa đủ dữ liệu để xác định frequency.** EEOC xác nhận vụ việc xảy ra trong khoảng cuối tháng 3 đến đầu tháng 4 năm 2020; không công bố số lượng hồ sơ hoặc số lần hệ thống chặn ứng viên. |
| Vì sao? | Complaint cho thấy việc đổi ngày sinh giữ nguyên các thông tin khác đã làm kết quả thay đổi, đồng thời hơn 200 ứng viên bị từ chối đều có bằng cử nhân hoặc cao hơn. |

---

## 4. So sánh và nhận định cá nhân

- **Điểm chung:** Cả hai case đều cho thấy hệ thống tuyển dụng có thể sử dụng dữ liệu cá nhân để loại ứng viên theo mẫu không công bằng.
- **Điểm khác biệt:** Case Amazon là hệ thống AI nội bộ bị Reuters mô tả là ưu tiên ứng viên nam; còn iTutorGroup là application/recruitment software được EEOC xác định tự động từ chối ứng viên lớn tuổi. Không có bằng chứng cho thấy iTutorGroup dùng một machine-learning model cụ thể.
- **Nhận định của bản thân:** Hệ thống tuyển dụng tự động không nên dùng ngày sinh hoặc các thuộc tính được bảo vệ làm tiêu chí lọc. Cần có kiểm tra độ công bằng, hạn chế dữ liệu nhạy cảm, xác minh lại hồ sơ bằng người thật và quyền kháng cáo cho ứng viên.

---

## 5. Nguồn cần kiểm chứng

1. Reuters, “Amazon scraps secret AI recruiting tool that showed bias against women,” 10 tháng 10 năm 2018: https://www.reuters.com/article/world/insight-amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK0AG/
2. EEOC, “EEOC Sues iTutorGroup for Age Discrimination,” 5 tháng 5 năm 2022: https://www.eeoc.gov/newsroom/eeoc-sues-itutorgroup-age-discrimination
3. EEOC, “iTutorGroup to Pay $365,000 to Settle EEOC Discriminatory Hiring Suit,” 11 tháng 9 năm 2023: https://www.eeoc.gov/newsroom/itutorgroup-pay-365000-settle-eeoc-discriminatory-hiring-suit
4. EEOC Amended Complaint, Equal Employment Opportunity Commission v. iTutorGroup, Inc., Case No. 1:22-cv-02565: https://clearinghouse-umich-production.s3.amazonaws.com/media/doc/158461.pdf
5. EEOC, “Equal Employment Opportunity Commission”: https://www.eeoc.gov/

> **Lưu ý:** EEOC xác nhận hệ thống tự động chặn theo tuổi, nhưng không công khai kiến trúc machine-learning. Vì vậy, bài gọi hệ thống là phần mềm tuyển dụng tự động hoặc automated recruitment/application software, đồng thời ghi rõ rằng case thuộc bối cảnh AI/algorithmic hiring.

> **Lưu ý:** Các bài báo và thông cáo trên mới xác nhận hành vi, sự kiện và số liệu công khai. Các đánh giá về layer, xác suất và tần suất là nhận định của tác giả dựa trên bằng chứng hiện có, không phải dữ kiện trực tiếp được nguồn cung cấp.
