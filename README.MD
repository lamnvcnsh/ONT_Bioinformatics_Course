# Introduction to Bioinformatics with Oxford Nanopore Sequencing

**Van L Nguyen**  
**St. Jude**  
**Bioinformatics Research Scientist**

## Lịch học và yêu cầu chuẩn bị trước khóa học

Chào các bạn,

Khóa học này được thiết kế cho các bạn có nền tảng sinh học và muốn bắt đầu làm quen với bioinformatics, đặc biệt tập trung vào dữ liệu **Oxford Nanopore Technologies (ONT) sequencing**.

Mục tiêu là giúp các bạn:

- Hiểu được dữ liệu sequencing đi qua những bước nào.
- Biết đọc các file quan trọng.
- Đánh giá chất lượng dữ liệu.
- Xem alignment.
- Gọi variant.
- Hiểu bước annotation cơ bản.

---

# 1. Lịch học dự kiến

Mỗi buổi học dự kiến khoảng **2 tiếng**, gồm phần lý thuyết và thực hành.

> **Lưu ý:** Đây là lịch trình cơ bản, nội dung chi tiết có thể thay đổi trong quá trình học.

## Tiến độ khóa học

- [ ] **Buổi 1 — Bioinformatics foundation và file formats**
- [ ] **Buổi 2 — ONT sequencing và basecalling**
- [ ] **Buổi 3 — ONT read quality control**
- [ ] **Buổi 4 — Alignment, BAM QC và IGV**
- [ ] **Buổi 5 — Variant calling**
- [ ] **Buổi 6 — Variant annotation và final report**

---

## [ ] Buổi 1 — Bioinformatics foundation và file formats

**Thời lượng:** ~2 giờ

### Nội dung chính

- Giới thiệu bioinformatics.
- Variant calling and annotation workflow.
- Genome/reference.
- Read.
- Coverage.
- Variant.
- Làm quen với các file format:
  - FASTA
  - FASTQ
  - BAM
  - VCF
  - BED
- Giới thiệu môi trường tính toán trong bioinformatics:
  - Laptop
  - Server
  - HPC
  - Login node
  - Compute node

---

## [ ] Buổi 2 — ONT sequencing và basecalling

**Thời lượng:** ~2 giờ

### Nội dung chính

- ONT sequencing.
- POD5 là gì.
- POD5 khác FASTQ/BAM như thế nào.
- Giới thiệu **Dorado basecalling**.

---

## [ ] Buổi 3 — ONT read quality control

**Thời lượng:** ~2 giờ

### Nội dung chính

- Đánh giá read quality.
- Read length.
- N50.
- Total yield.
- Dùng **SeqKit** để kiểm tra dữ liệu.
- Dùng **NanoPlot** để đọc QC report.

---

## [ ] Buổi 4 — Alignment, BAM QC và IGV

**Thời lượng:** ~2 giờ

### Nội dung chính

- Mapping reads vào reference genome.
- Hiểu BAM.
- BAM index / BAI.
- MAPQ.
- CIGAR.
- Coverage.
- Mở BAM trong **IGV**.
- Mở VCF trong **IGV**.

---

## [ ] Buổi 5 — Variant calling

**Thời lượng:** ~2 giờ

### Nội dung chính

- Giới thiệu các loại variant:
  - SNV
  - Indel
  - SV
  - CNV
- Đọc VCF.
- Hiểu output từ **ONT human variation workflow**.
- Giới thiệu cách chạy workflow trên server/HPC:
  - Nextflow
  - Docker
  - Singularity

---

## [ ] Buổi 6 — Variant annotation và final report

**Thời lượng:** ~2 giờ

### Nội dung chính

- Annotation khác interpretation như thế nào.
- Đọc gene consequence.
- ClinVar.
- Annotation table.
- Final report.

---

# 2. Data sử dụng trong khóa học

Khóa học sẽ sử dụng một bộ dữ liệu **demo/subset** đã được chuẩn bị sẵn từ **ONT human variation workflow**.

Các bạn **không cần tải full human whole-genome sequencing data**.

Bộ data thực hành sẽ bao gồm:

- FASTQ subset nhỏ để học QC.
- BAM và BAM index để học alignment/IGV.
- Reference FASTA và BED regions.
- Variant calling VCF.

---

# 3. Yêu cầu cần chuẩn bị

## 3.1. Yêu cầu máy tính tối thiểu

Các bạn nên chuẩn bị laptop với cấu hình tối thiểu:

- **CPU:** 4 cores hoặc hơn.
- **RAM:** tối thiểu 8 GB; khuyến nghị 16 GB.
- **Storage trống:** ít nhất 50–100 GB.
- **Ổ cứng:** SSD được khuyến nghị.
- **Hệ điều hành:**
  - Linux
  - macOS
  - Windows 10/11 với WSL2
- Internet để tải phần mềm/data nhỏ nếu cần.

> **Lưu ý:** Các bạn không cần máy mạnh để chạy full ONT human WGS workflow.  
> Các bước nặng như chạy workflow với toàn bộ hệ gen người hoặc basecalling từ POD5 yêu cầu GPU. Những phần này sẽ được giới thiệu trong khóa học nhưng sẽ không thực hành.

---

## 3.2. Phần mềm cần chuẩn bị trước

Nếu có thể, các bạn vui lòng cài trước:

### 1. Terminal environment

**macOS/Linux**

- Terminal mặc định.

**Windows**

- WSL2 + Ubuntu.

Tài liệu tham khảo:

- https://blog.crfnetwork.com/operating-system/windows/huong-dan-cai-dat-wsl-2-chay-song-song-linux-voi-windows/
- https://www.youtube.com/watch?v=lY_ZyniMIgs

### 2. Basic command-line tools

- `wget` hoặc `curl`
- `gzip`
- `samtools`
- `bcftools`
- `seqkit`
- `NanoPlot`

### 3. Visualization tool

- IGV Desktop

### 4. Optional

- Conda

Nếu chưa cài được trước khóa học, các bạn vẫn có thể tham gia phần lý thuyết và đọc output đã chuẩn bị sẵn.

Link dữ liệu sẽ được chia sẻ trong khóa học.

Để thực hành tốt nhất, nên có ít nhất:

- Terminal
- samtools
- bcftools
- seqkit
- NanoPlot
- IGV

---

## 3.3. Kiến thức cần chuẩn bị trước

Không yêu cầu kinh nghiệm bioinformatics trước đó.

Tuy nhiên, các bạn nên xem trước hoặc làm quen với:

- Khái niệm DNA, gene, genome, variant.
- FASTQ là gì.
- Reference genome là gì.
- Khái niệm coverage/depth.
- Một vài lệnh terminal cơ bản:
  - `ls`
  - `cd`
  - `pwd`
  - `head`
  - `less`

---

## 3.4. Kết quả mong đợi sau khóa học

Sau khóa học, các bạn nên có thể:

- Hiểu một workflow ONT sequencing cơ bản từ reads đến variant annotation.
- Phân biệt POD5, FASTQ, BAM, VCF và BED.
- Đọc QC report của ONT reads.
- Hiểu alignment và xem BAM/VCF trong IGV.
- Đọc VCF ở mức cơ bản.
- Hiểu ý nghĩa của variant annotation.
- Tạo một báo cáo ngắn gồm:
  - QC
  - Coverage
  - Variant summary
  - Limitation

---

Hẹn gặp các bạn trong khóa học!
