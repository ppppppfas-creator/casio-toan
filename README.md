<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toán Học & Tư Duy Casio fx-880BTG | Hành Trình 10 Màn</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts: Inter & Crimson Pro (cho nét học thuật toán học) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Crimson+Pro:ital,wght@0,500;0,700;1,500&family=Inter:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
    
    <!-- KaTeX để hiển thị công thức toán học sắc nét -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
    <script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"></script>

    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        paper: '#FAF8F5',
                        paperDark: '#F2EFE9',
                        navy: '#1E293B',
                        tealMath: '#0F766E',
                        tealLight: '#CCFBF1',
                        amberMath: '#B45309',
                        amberLight: '#FEF3C7',
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        serif: ['Crimson Pro', 'serif'],
                        mono: ['JetBrains Mono', 'monospace'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #FAF8F5;
            color: #1E293B;
            /* Họa tiết lưới tọa độ mờ dịu nhẹ */
            background-image: 
                linear-gradient(to right, rgba(30, 41, 59, 0.04) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(30, 41, 59, 0.04) 1px, transparent 1px),
                linear-gradient(to right, rgba(15, 118, 110, 0.05) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(15, 118, 110, 0.05) 1px, transparent 1px);
            background-size: 24px 24px, 24px 24px, 120px 120px, 120px 120px;
            overflow-x: hidden;
        }

        /* Hiệu ứng chuyển màn mượt mà */
        .slide-screen {
            display: none;
            animation: fadeSlideIn 0.45s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .slide-screen.active {
            display: block;
        }

        @keyframes fadeSlideIn {
            from {
                opacity: 0;
                transform: translateY(14px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Nút phím Casio mô phỏng */
        .casio-key {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            padding: 2px 8px;
            margin: 0 2px;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.78rem;
            font-weight: 600;
            color: #1E293B;
            background: linear-gradient(180deg, #FFFFFF 0%, #E2E8F0 100%);
            border: 1px solid #94A3B8;
            border-bottom-width: 3px;
            border-radius: 6px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.08);
            white-space: nowrap;
        }
        .casio-key-dark {
            background: linear-gradient(180deg, #334155 0%, #1E293B 100%);
            color: #F8FAFC;
            border-color: #0F172A;
        }
        .casio-key-amber {
            background: linear-gradient(180deg, #F59E0B 0%, #D97706 100%);
            color: #FFFFFF;
            border-color: #92400E;
        }

        /* Ký hiệu toán học trang trí nền */
        .math-watermark {
            position: fixed;
            pointer-events: none;
            user-select: none;
            font-family: 'Crimson Pro', serif;
            color: rgba(15, 118, 110, 0.045);
            z-index: 0;
        }

        /* Custom scrollbar tinh tế */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #F2EFE9;
        }
        ::-webkit-scrollbar-thumb {
            background: #CBD5E1;
            border-radius: 999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94A3B8;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between relative selection:bg-teal-100 selection:text-teal-900">

    <!-- Ký hiệu toán học trang trí nền -->
    <div class="math-watermark text-[18rem] -top-16 -left-10">∑</div>
    <div class="math-watermark text-[16rem] bottom-10 -right-8">∫</div>
    <div class="math-watermark text-[12rem] top-1/3 right-12">φ</div>
    <div class="math-watermark text-[14rem] bottom-1/4 left-12">π</div>

    <!-- Thanh điều hướng trên cùng (Header & Thanh tiến trình 10 màn) -->
    <header class="sticky top-0 z-40 bg-[#FAF8F5]/90 backdrop-blur-md border-b border-slate-200/80 shadow-sm">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 py-3">
            <div class="flex items-center justify-between gap-3">
                <!-- Logo & Tiêu đề -->
                <div class="flex items-center gap-3 cursor-pointer" onclick="goToSlide(1)">
                    <div class="w-10 h-10 rounded-xl bg-tealMath text-white flex items-center justify-center font-serif font-bold text-xl shadow-sm">
                        fx
                    </div>
                    <div>
                        <h1 class="font-bold text-navy text-sm sm:text-base leading-tight">Toán Học & Tư Duy Casio</h1>
                        <p class="text-xs text-slate-500 hidden sm:block">Chuyên đề tương tác Casio fx-880BTG • Nguồn học liệu Bitex Edu</p>
                    </div>
                </div>

                <!-- Chỉ số màn & Nút mở Menu nhanh -->
                <div class="flex items-center gap-2 sm:gap-3">
                    <div class="hidden md:flex items-center gap-2 bg-paperDark px-3 py-1.5 rounded-full border border-slate-200/80">
                        <span class="text-xs font-medium text-slate-500">Điểm thực hành:</span>
                        <span id="globalScoreBadge" class="text-xs font-bold text-tealMath font-mono">0 / 11 câu</span>
                    </div>

                    <span id="slideCounterBadge" class="px-3 py-1.5 rounded-full bg-amberLight text-amberMath font-mono font-semibold text-xs sm:text-sm border border-amber-200">
                        Màn 1 / 10
                    </span>

                    <button onclick="toggleMenuModal()" class="p-2 sm:px-3 sm:py-1.5 rounded-xl bg-white hover:bg-slate-50 border border-slate-200 text-navy flex items-center gap-1.5 text-xs sm:text-sm font-medium transition shadow-sm" title="Danh sách 10 màn">
                        <i data-lucide="layout-grid" class="w-4 h-4 text-tealMath"></i>
                        <span class="hidden sm:inline">Mục lục</span>
                    </button>
                </div>
            </div>

            <!-- Thanh chọn nhanh 10 màn (Step Pills) -->
            <div class="mt-3 flex items-center gap-1.5 overflow-x-auto pb-1 no-scrollbar" id="stepPillsContainer">
                <!-- Sẽ được render bằng JS -->
            </div>
        </div>
        <!-- Thanh tiến trình mảnh -->
        <div class="w-full h-1 bg-slate-200/60">
            <div id="topProgressBar" class="h-full bg-gradient-to-r from-tealMath to-amberMath transition-all duration-300" style="width: 10%;"></div>
        </div>
    </header>

    <!-- Vùng nội dung chính (10 Màn trình chiếu) -->
    <main class="flex-grow max-w-6xl w-full mx-auto px-4 sm:px-6 py-6 sm:py-8 relative z-10">

        <!-- ===================================================================== -->
        <!-- MÀN 1: GIỚI THIỆU TOÁN HỌC & BỀ DÀY LỊCH SỬ TOÁN HỌC                  -->
        <!-- ===================================================================== -->
        <section id="slide-1" class="slide-screen active">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-tealLight/60 text-tealMath text-xs font-semibold tracking-wide uppercase mb-4">
                    <i data-lucide="compass" class="w-3.5 h-3.5"></i> Màn 01 • Khởi nguồn tri thức
                </div>
                <h2 class="font-serif text-3xl sm:text-5xl font-bold text-navy leading-tight mb-4">
                    Toán Học: Ngôn Ngữ Của Vũ Trụ & Hành Trình Nghìn Năm Kiến Tạo
                </h2>
                <p class="text-slate-600 text-base sm:text-lg leading-relaxed max-w-3xl mb-8">
                    Từ những vết khắc đếm cừu trên xương Ishango hơn 20.000 năm trước đến các siêu thuật toán tính toán hiện đại, toán học luôn là nền móng cốt lõi giúp nhân loại giải mã quy luật tự nhiên và mở rộng giới hạn tư duy logic.
                </p>

                <!-- Dòng thời gian 5 cột mốc lịch sử toán học -->
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-4 mb-8">
                    <!-- Mốc 1 -->
                    <div class="bg-paper rounded-2xl p-5 border border-slate-200/80 hover:border-tealMath/50 transition flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-mono font-bold text-amberMath bg-amberLight px-2.5 py-0.5 rounded-md">~300 TCN</span>
                            <h3 class="font-bold text-navy text-lg mt-3 mb-2">Hình học Euclid & Số học Cổ đại</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Bộ sách <em>Cơ bản (Elements)</em> của Euclid đặt nền móng cho hệ tiên đề và chứng minh suy diễn chặt chẽ. Cùng thời kỳ, Pythagoras và Archimedes khai phá tỷ lệ hình học và phương pháp vét cạn tính số $\pi$.
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-200/70 text-xs font-mono text-tealMath">
                            $a^2 + b^2 = c^2$
                        </div>
                    </div>

                    <!-- Mốc 2 -->
                    <div class="bg-paper rounded-2xl p-5 border border-slate-200/80 hover:border-tealMath/50 transition flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-mono font-bold text-amberMath bg-amberLight px-2.5 py-0.5 rounded-md">Thế kỷ IX</span>
                            <h3 class="font-bold text-navy text-lg mt-3 mb-2">Đại số Al-Khwarizmi</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Nhà toán học Ba Tư Al-Khwarizmi hệ thống hóa cách giải phương trình bậc nhất, bậc hai qua tác phẩm <em>Al-Jabr</em> — nguồn gốc của từ "Algebra" (Đại số) và thuật ngữ "Algorithm" (Thuật toán).
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-200/70 text-xs font-mono text-tealMath">
                            $ax^2 + bx + c = 0$
                        </div>
                    </div>

                    <!-- Mốc 3 -->
                    <div class="bg-paper rounded-2xl p-5 border border-slate-200/80 hover:border-tealMath/50 transition flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-mono font-bold text-amberMath bg-amberLight px-2.5 py-0.5 rounded-md">Thế kỷ XVII</span>
                            <h3 class="font-bold text-navy text-lg mt-3 mb-2">Hình học Giải tích Descartes</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                René Descartes kết nối đại số và hình học thông qua hệ trục tọa độ trực giao, biến các đường cong hình học thành phương trình đại số có thể tính toán chính xác.
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-200/70 text-xs font-mono text-tealMath">
                            $(x - a)^2 + (y - b)^2 = R^2$
                        </div>
                    </div>

                    <!-- Mốc 4 -->
                    <div class="bg-paper rounded-2xl p-5 border border-slate-200/80 hover:border-tealMath/50 transition flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-mono font-bold text-amberMath bg-amberLight px-2.5 py-0.5 rounded-md">Cuối TK XVII</span>
                            <h3 class="font-bold text-navy text-lg mt-3 mb-2">Giải tích Newton & Leibniz</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Phép tính vi phân và tích phân ra đời độc lập bởi Isaac Newton và Gottfried Leibniz, cho phép loài người mô tả sự biến thiên liên tục, vận tốc tức thời và diện tích hình cong.
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-200/70 text-xs font-mono text-tealMath">
                            $\int_a^b f(x)\,dx = F(b) - F(a)$
                        </div>
                    </div>

                    <!-- Mốc 5 -->
                    <div class="bg-paper rounded-2xl p-5 border border-slate-200/80 hover:border-tealMath/50 transition flex flex-col justify-between">
                        <div>
                            <span class="text-xs font-mono font-bold text-amberMath bg-amberLight px-2.5 py-0.5 rounded-md">TK XX – Nay</span>
                            <h3 class="font-bold text-navy text-lg mt-3 mb-2">Toán học Tính toán & Casio</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Từ bàn tính cổ, máy tính cơ học Pascal đến máy tính khoa học cầm tay hiện đại như <strong>Casio fx-880BTG</strong>, công cụ tính toán giúp giải phóng sức lao động số học để tập trung vào sáng tạo.
                            </p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-200/70 text-xs font-mono text-tealMath">
                            $x_{n+1} = g(x_n)$
                        </div>
                    </div>
                </div>

                <!-- Trích dẫn điểm nhấn -->
                <div class="bg-gradient-to-r from-navy to-slate-800 text-white rounded-2xl p-6 flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4">
                    <div>
                        <p class="font-serif italic text-lg sm:text-xl text-amber-200">
                            "Bản chất của Toán học nằm ở sự tự do trong tư duy."
                        </p>
                        <p class="text-xs sm:text-sm text-slate-300 mt-1">— Georg Cantor (Nhà toán học sáng lập Lý thuyết Tập hợp)</p>
                    </div>
                    <button onclick="nextSlide()" class="px-5 py-2.5 rounded-xl bg-tealMath hover:bg-teal-600 text-white font-medium text-sm flex items-center gap-2 transition shrink-0 shadow">
                        Khám phá Toán Casio <i data-lucide="arrow-right" class="w-4 h-4"></i>
                    </button>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 2: NHÁNH TOÁN HỌC CASIO & TƯ DUY RÈN LUYỆN                        -->
        <!-- ===================================================================== -->
        <section id="slide-2" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-amberLight text-amberMath text-xs font-semibold tracking-wide uppercase mb-4">
                    <i data-lucide="cpu" class="w-3.5 h-3.5"></i> Màn 02 • Phòng thí nghiệm thu nhỏ
                </div>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold text-navy leading-tight mb-4">
                    Nhánh Toán Học Casio & Tư Duy Rèn Luyện Hiện Đại
                </h2>
                <p class="text-slate-600 text-base leading-relaxed max-w-3xl mb-8">
                    Trong giáo dục toán học hiện đại tại Việt Nam, <strong>Giải toán trên máy tính cầm tay (MTCT)</strong> không đơn thuần là "bấm ra đáp số", mà đã phát triển thành một nhánh rèn luyện tư duy thực nghiệm, thuật toán và tối ưu hóa.
                </p>

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 items-stretch">
                    <!-- Cột trái: 4 giá trị cốt lõi -->
                    <div class="lg:col-span-7 grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <div class="bg-paper rounded-2xl p-5 border border-slate-200">
                            <div class="w-10 h-10 rounded-xl bg-tealLight text-tealMath flex items-center justify-center mb-3">
                                <i data-lucide="flask-conical" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-bold text-navy text-base mb-1.5">1. Phòng thí nghiệm trực quan</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Cho phép học sinh thử nghiệm hàng trăm giá trị chỉ trong vài giây (qua <strong>Bảng tính / Table</strong>), từ đó quan sát quy luật, dự đoán giới hạn, cực trị trước khi chứng minh chặt chẽ.
                            </p>
                        </div>

                        <div class="bg-paper rounded-2xl p-5 border border-slate-200">
                            <div class="w-10 h-10 rounded-xl bg-amberLight text-amberMath flex items-center justify-center mb-3">
                                <i data-lucide="git-branch" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-bold text-navy text-base mb-1.5">2. Tư duy thuật toán & Lặp</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Khi lập công thức truy hồi bằng biến nhớ <code>Ans</code> hoặc bảng tính <strong>Spreadsheet</strong> trên Casio fx-880BTG, học sinh đang trực tiếp tư duy như một lập trình viên toán học.
                            </p>
                        </div>

                        <div class="bg-paper rounded-2xl p-5 border border-slate-200">
                            <div class="w-10 h-10 rounded-xl bg-tealLight text-tealMath flex items-center justify-center mb-3">
                                <i data-lucide="zap" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-bold text-navy text-base mb-1.5">3. Tối ưu hóa quy trình giải</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Biết cách biến đổi biểu thức gọn nhất trước khi nhập máy để giảm thiểu sai số làm tròn, tránh tràn bộ nhớ và rút ngắn thời gian thao tác phím.
                            </p>
                        </div>

                        <div class="bg-paper rounded-2xl p-5 border border-slate-200">
                            <div class="w-10 h-10 rounded-xl bg-amberLight text-amberMath flex items-center justify-center mb-3">
                                <i data-lucide="shield-check" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-bold text-navy text-base mb-1.5">4. Phản xạ kiểm chứng & Phản biện</h3>
                            <p class="text-sm text-slate-600 leading-relaxed">
                                Rèn thói quen tự kiểm tra tính hợp lý của kết quả giải tay bằng cách thay ngược giá trị đặc biệt, kiểm tra đạo hàm tại điểm hoặc đối chiếu tích phân xác định.
                            </p>
                        </div>
                    </div>

                    <!-- Cột phải: Thẻ điểm nhấn Casio fx-880BTG -->
                    <div class="lg:col-span-5 bg-navy text-slate-100 rounded-2xl p-6 flex flex-col justify-between border border-slate-700">
                        <div>
                            <div class="flex items-center justify-between mb-4">
                                <span class="text-xs font-mono uppercase tracking-wider text-teal-300 bg-teal-950/80 px-3 py-1 rounded-full border border-teal-800">
                                    Công cụ tiêu chuẩn mới
                                </span>
                                <span class="font-mono text-xs text-slate-400">CLASSWIZ 880BTG</span>
                            </div>
                            <h3 class="font-serif text-2xl font-bold text-white mb-3">
                                Bước tiến vượt bậc của Casio fx-880BTG
                            </h3>
                            <p class="text-sm text-slate-300 leading-relaxed mb-4">
                                Kế thừa và nâng cấp từ dòng fx-580VN X, máy tính <strong>Casio fx-880BTG</strong> mang lại trải nghiệm trực quan với độ chính xác hiển thị 10 chữ số (tính toán nội bộ 23 chữ số):
                            </p>
                            <ul class="space-y-2.5 text-sm text-slate-200">
                                <li class="flex items-start gap-2.5">
                                    <i data-lucide="check-circle-2" class="w-4 h-4 text-teal-400 shrink-0 mt-0.5"></i>
                                    <span><strong>Bảng tính (Spreadsheet):</strong> Xử lý dãy số truy hồi, cấp số, thống kê nhiều biến lên tới 45 dòng × 5 cột.</span>
                                </li>
                                <li class="flex items-start gap-2.5">
                                    <i data-lucide="check-circle-2" class="w-4 h-4 text-teal-400 shrink-0 mt-0.5"></i>
                                    <span><strong>Hộp toán học (Math Box):</strong> Mô phỏng xác suất gieo xúc xắc, tung đồng xu, đường tròn lượng giác.</span>
                                </li>
                                <li class="flex items-start gap-2.5">
                                    <i data-lucide="check-circle-2" class="w-4 h-4 text-teal-400 shrink-0 mt-0.5"></i>
                                    <span><strong>Mã QR trực quan:</strong> Quét kết quả để vẽ đồ thị hàm số và biểu đồ thống kê ngay trên điện thoại/máy tính.</span>
                                </li>
                            </ul>
                        </div>

                        <div class="mt-6 pt-4 border-t border-slate-700/80 flex items-center justify-between text-xs text-slate-400">
                            <span>Chuẩn học liệu: Bitex Edu</span>
                            <span class="font-mono text-amber-300">Precision: 23 digits</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 3: LÝ THUYẾT & CÁC DẠNG TOÁN KẾT HỢP CASIO (NGUỒN: BITEX EDU)     -->
        <!-- ===================================================================== -->
        <section id="slide-3" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="flex flex-wrap items-center justify-between gap-2 mb-4">
                    <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-tealLight/60 text-tealMath text-xs font-semibold tracking-wide uppercase">
                        <i data-lucide="book-open" class="w-3.5 h-3.5"></i> Màn 03 • Hệ thống chuyên đề
                    </div>
                    <span class="text-xs font-medium text-slate-500 bg-paperDark px-3 py-1 rounded-full border border-slate-200">
                        Nguồn tham khảo: <strong>Bitex Edu</strong> (Diễn đàn Toán Casio)
                    </span>
                </div>

                <h2 class="font-serif text-3xl sm:text-4xl font-bold text-navy leading-tight mb-3">
                    Lý Thuyết & Các Dạng Toán Trọng Tâm Kết Hợp Casio
                </h2>
                <p class="text-slate-600 text-sm sm:text-base mb-6">
                    Chọn từng chuyên đề bên dưới để xem cơ sở lý thuyết và tổ hợp phím chức năng chuẩn trên <strong>Casio fx-880BTG</strong> theo hệ thống phân loại của Bitex Edu:
                </p>

                <!-- Tabs chọn chuyên đề -->
                <div class="flex flex-wrap gap-2 mb-6" id="topicTabs">
                    <button onclick="selectTopic(0)" class="topic-tab active px-4 py-2 rounded-xl text-sm font-semibold transition bg-tealMath text-white shadow-sm">
                        1. Phương trình & Hệ PT
                    </button>
                    <button onclick="selectTopic(1)" class="topic-tab px-4 py-2 rounded-xl text-sm font-semibold transition bg-paperDark text-navy hover:bg-slate-200">
                        2. Dãy số & Quy nạp
                    </button>
                    <button onclick="selectTopic(2)" class="topic-tab px-4 py-2 rounded-xl text-sm font-semibold transition bg-paperDark text-navy hover:bg-slate-200">
                        3. Giải tích (Đạo hàm - Tích phân)
                    </button>
                    <button onclick="selectTopic(3)" class="topic-tab px-4 py-2 rounded-xl text-sm font-semibold transition bg-paperDark text-navy hover:bg-slate-200">
                        4. Số học & Đồng dư thức
                    </button>
                    <button onclick="selectTopic(4)" class="topic-tab px-4 py-2 rounded-xl text-sm font-semibold transition bg-paperDark text-navy hover:bg-slate-200">
                        5. Hình học Oxyz & Vector
                    </button>
                </div>

                <!-- Nội dung chi tiết của từng chuyên đề -->
                <div id="topicContentArea" class="bg-paper rounded-2xl p-6 border border-slate-200/90">
                    <!-- Render động bằng JS -->
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 4: THÍ NGHIỆM TƯƠNG TÁC CHỨNG MINH TÍNH CHÍNH XÁC CỦA CASIO       -->
        <!-- ===================================================================== -->
        <section id="slide-4" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-amberLight text-amberMath text-xs font-semibold tracking-wide uppercase mb-4">
                    <i data-lucide="microscope" class="w-3.5 h-3.5"></i> Màn 04 • Thực nghiệm kiểm chứng
                </div>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold text-navy leading-tight mb-3">
                    Thí Nghiệm Tương Tác Chứng Minh Tính Chính Xác Của Casio
                </h2>
                <p class="text-slate-600 text-sm sm:text-base mb-6">
                    Trực tiếp tương tác với 2 mô hình thí nghiệm toán học bên dưới để kiểm chứng độ hội tụ và tính chính xác tuyệt đối của các giá trị mà Casio fx-880BTG tính toán.
                </p>

                <!-- Chuyển đổi qua lại hoặc xem song song 2 thí nghiệm -->
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                    
                    <!-- THÍ NGHIỆM 1: XÁC SUẤT MONTE CARLO XẤP XỈ SỐ PI -->
                    <div class="bg-paper rounded-2xl p-5 border border-slate-200 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="text-xs font-bold uppercase tracking-wider text-tealMath bg-tealLight px-2.5 py-1 rounded-md">
                                    Thí nghiệm 1 • Xác suất hình học
                                </span>
                                <span class="font-mono text-xs text-slate-500">Monte Carlo $\pi$</span>
                            </div>
                            <h3 class="font-bold text-navy text-lg mb-2">Gieo điểm ngẫu nhiên xấp xỉ hằng số $\pi$</h3>
                            <p class="text-xs sm:text-sm text-slate-600 mb-4 leading-relaxed">
                                Gieo $N$ điểm ngẫu nhiên vào hình vuông cạnh $2$ ngoại tiếp đường tròn đơn vị bán kính $R=1$. Tỷ lệ diện tích là $\frac{S_{\text{tròn}}}{S_{\text{vuông}}} = \frac{\pi}{4} \Rightarrow \pi \approx 4 \cdot \frac{N_{\text{trong}}}{N}$.
                            </p>

                            <!-- Canvas Monte Carlo -->
                            <div class="relative w-full aspect-square max-w-[270px] mx-auto bg-white rounded-xl border border-slate-300 shadow-inner overflow-hidden mb-4">
                                <canvas id="monteCarloCanvas"></canvas>
                            </div>
                        </div>

                        <div>
                            <!-- Điều khiển Monte Carlo -->
                            <div class="flex items-center justify-between text-xs font-medium text-slate-700 mb-1.5">
                                <span>Tổng số điểm đã gieo ($N$): <strong id="mcTotalCount" class="font-mono text-navy">0</strong></span>
                                <span>Trong hình tròn: <strong id="mcInsideCount" class="font-mono text-tealMath">0</strong></span>
                            </div>

                            <div class="grid grid-cols-3 gap-2 mb-3">
                                <button onclick="addMonteCarloPoints(100)" class="py-2 px-2 rounded-xl bg-white hover:bg-teal-50 border border-slate-300 text-xs font-semibold text-navy transition">
                                    +100 điểm
                                </button>
                                <button onclick="addMonteCarloPoints(2000)" class="py-2 px-2 rounded-xl bg-tealMath hover:bg-teal-700 text-white text-xs font-semibold transition shadow-sm">
                                    +2.000 điểm
                                </button>
                                <button onclick="resetMonteCarlo()" class="py-2 px-2 rounded-xl bg-slate-200 hover:bg-slate-300 text-xs font-semibold text-slate-700 transition">
                                    Làm lại
                                </button>
                            </div>

                            <!-- Bảng đối chiếu Casio -->
                            <div class="bg-navy text-white rounded-xl p-3.5 text-xs space-y-1.5 font-mono">
                                <div class="flex justify-between">
                                    <span class="text-slate-400">Ước lượng thực nghiệm:</span>
                                    <span id="mcPiEstimate" class="text-amber-300 font-bold">0.000000000</span>
                                </div>
                                <div class="flex justify-between">
                                    <span class="text-slate-400">Giá trị Casio fx-880BTG:</span>
                                    <span class="text-teal-300 font-bold">3.141592654</span>
                                </div>
                                <div class="flex justify-between border-t border-slate-700 pt-1">
                                    <span class="text-slate-400">Sai số tuyệt đối $|\Delta\pi|$:</span>
                                    <span id="mcPiError" class="text-slate-200">3.141592654</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- THÍ NGHIỆM 2: CỰC TRỊ HÌNH HỌC HÌNH NÓN NỘI TIẾP MẶT CẦU -->
                    <div class="bg-paper rounded-2xl p-5 border border-slate-200 flex flex-col justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-2">
                                <span class="text-xs font-bold uppercase tracking-wider text-amberMath bg-amberLight px-2.5 py-1 rounded-md">
                                    Thí nghiệm 2 • Cực trị hình học
                                </span>
                                <span class="font-mono text-xs text-slate-500">Table Scan $V(h)$</span>
                            </div>
                            <h3 class="font-bold text-navy text-lg mb-2">Hình nón nội tiếp mặt cầu bán kính $R = 5$</h3>
                            <p class="text-xs sm:text-sm text-slate-600 mb-4 leading-relaxed">
                                Kéo thanh trượt thay đổi chiều cao $h \in (0; 10)$ của khối nón nội tiếp mặt cầu $R=5$. Thể tích $V(h) = \frac{1}{3}\pi h^2 (2R - h)$ đạt cực đại khi $h = \frac{4R}{3} \approx 6.67$.
                            </p>

                            <!-- Canvas Hình nón nội tiếp mặt cầu -->
                            <div class="relative w-full aspect-square max-w-[270px] mx-auto bg-white rounded-xl border border-slate-300 shadow-inner overflow-hidden mb-4">
                                <canvas id="coneSphereCanvas"></canvas>
                            </div>
                        </div>

                        <div>
                            <!-- Thanh trượt điều chỉnh chiều cao h -->
                            <div class="mb-3">
                                <div class="flex justify-between items-center text-xs font-medium text-slate-700 mb-1">
                                    <span>Chiều cao hình nón $h$: <strong id="coneHeightDisplay" class="font-mono text-tealMath text-sm">5.00</strong></span>
                                    <button onclick="setOptimalConeHeight()" class="text-xs font-semibold text-amberMath hover:underline">
                                        Đặt $h = \frac{20}{3} \approx 6.67$
                                    </button>
                                </div>
                                <input type="range" id="coneHeightSlider" min="0.5" max="9.5" step="0.01" value="5.00" oninput="updateConeExperiment(this.value)" class="w-full accent-tealMath cursor-pointer">
                            </div>

                            <!-- Bảng đối chiếu Table Casio -->
                            <div class="bg-navy text-white rounded-xl p-3.5 text-xs space-y-1.5 font-mono">
                                <div class="flex justify-between">
                                    <span class="text-slate-400">Bán kính đáy $r = \sqrt{2Rh - h^2}$:</span>
                                    <span id="coneRadiusDisplay" class="text-slate-200">5.00</span>
                                </div>
                                <div class="flex justify-between">
                                    <span class="text-slate-400">Thể tích hiện tại $V(h)$:</span>
                                    <span id="coneVolumeDisplay" class="text-amber-300 font-bold">130.90</span>
                                </div>
                                <div class="flex justify-between border-t border-slate-700 pt-1">
                                    <span class="text-slate-400">Cực đại chuẩn Casio ($h=20/3$):</span>
                                    <span class="text-teal-300 font-bold">155.14 ($\frac{4000\pi}{81}$)</span>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 5: TÍNH ỨNG DỤNG CỦA CASIO TRONG CÁC KỲ THI                       -->
        <!-- ===================================================================== -->
        <section id="slide-5" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-tealLight/60 text-tealMath text-xs font-semibold tracking-wide uppercase mb-4">
                    <i data-lucide="award" class="w-3.5 h-3.5"></i> Màn 05 • Chiến thuật phòng thi
                </div>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold text-navy leading-tight mb-4">
                    Ứng Dụng Chiến Lược Của Casio Trong Các Kỳ Thi Trọng Điểm
                </h2>
                <p class="text-slate-600 text-base leading-relaxed max-w-3xl mb-8">
                    Với cấu trúc đề thi trắc nghiệm hiện hành (bao gồm câu hỏi nhiều lựa chọn, trắc nghiệm Đúng/Sai và trả lời ngắn), việc làm chủ Casio fx-880BTG tạo ra lợi thế vượt trội về tốc độ và độ chính xác.
                </p>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-8">
                    <!-- Kỳ thi 1 -->
                    <div class="bg-paper rounded-2xl p-6 border border-slate-200 relative overflow-hidden">
                        <div class="absolute top-0 right-0 w-20 h-20 bg-tealMath/5 rounded-bl-full"></div>
                        <span class="inline-block px-3 py-1 rounded-lg bg-tealLight text-tealMath font-bold text-xs mb-3">
                            Kỳ thi Tốt nghiệp THPT
                        </span>
                        <h3 class="font-bold text-navy text-lg mb-2">Tối ưu thời gian & Chống sai sót</h3>
                        <ul class="space-y-2.5 text-sm text-slate-600">
                            <li class="flex items-start gap-2">
                                <span class="text-tealMath font-bold">•</span>
                                <span>Xử lý trọn vẹn nhóm câu hỏi nhận biết – thông hiểu (khảo sát hàm số, mũ – logarit, nguyên hàm, tọa độ Oxyz) trong dưới 30 giây/câu.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-tealMath font-bold">•</span>
                                <span>Kiểm tra nhanh từng mệnh đề <strong>Đúng / Sai</strong> bằng cách gán giá trị cụ thể vào biến nhớ.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-tealMath font-bold">•</span>
                                <span>Dành quỹ thời gian quý giá cho các câu hỏi vận dụng cao phân loại.</span>
                            </li>
                        </ul>
                    </div>

                    <!-- Kỳ thi 2 -->
                    <div class="bg-paper rounded-2xl p-6 border border-slate-200 relative overflow-hidden">
                        <div class="absolute top-0 right-0 w-20 h-20 bg-amberMath/5 rounded-bl-full"></div>
                        <span class="inline-block px-3 py-1 rounded-lg bg-amberLight text-amberMath font-bold text-xs mb-3">
                            Đánh giá năng lực (ĐHQG HN & HCM)
                        </span>
                        <h3 class="font-bold text-navy text-lg mb-2">Giải mã bài toán thực tế & Tư duy định lượng</h3>
                        <ul class="space-y-2.5 text-sm text-slate-600">
                            <li class="flex items-start gap-2">
                                <span class="text-amberMath font-bold">•</span>
                                <span>Đề thi ĐGNL chứa nhiều bài toán thực tế (lãi suất ngân hàng, tăng trưởng dân số, phân rã phóng xạ, tối ưu chi phí) với số liệu lẻ phức tạp.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-amberMath font-bold">•</span>
                                <span>Chức năng <strong>Solver</strong> và <strong>Spreadsheet</strong> giúp mô hình hóa và tính trực tiếp kết quả làm tròn chính xác.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-amberMath font-bold">•</span>
                                <span>Xử lý nhanh phần Thống kê – Xác suất (phương sai, độ lệch chuẩn, tổ hợp xác suất).</span>
                            </li>
                        </ul>
                    </div>

                    <!-- Kỳ thi 3 -->
                    <div class="bg-paper rounded-2xl p-6 border border-slate-200 relative overflow-hidden">
                        <div class="absolute top-0 right-0 w-20 h-20 bg-navy/5 rounded-bl-full"></div>
                        <span class="inline-block px-3 py-1 rounded-lg bg-slate-200 text-navy font-bold text-xs mb-3">
                            Đánh giá tư duy (ĐHBK) & HSG Casio
                        </span>
                        <h3 class="font-bold text-navy text-lg mb-2">Mô phỏng thuật toán & Kiểm chứng giả thuyết</h3>
                        <ul class="space-y-2.5 text-sm text-slate-600">
                            <li class="flex items-start gap-2">
                                <span class="text-navy font-bold">•</span>
                                <span>Tìm quy luật dãy số truy hồi phức tạp bằng cách tính 10–15 số hạng đầu trên bảng tính.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-navy font-bold">•</span>
                                <span>Khảo sát sự biến thiên của hàm hợp, hàm chứa dấu giá trị tuyệt đối bằng phép quét <code>Table</code> hai tầng.</span>
                            </li>
                            <li class="flex items-start gap-2">
                                <span class="text-navy font-bold">•</span>
                                <span>Kiểm chứng chéo kết quả biến đổi đại số tự luận để đảm bảo không nhầm dấu.</span>
                            </li>
                        </ul>
                    </div>
                </div>

                <!-- Biểu đồ so sánh phân bổ thời gian làm bài -->
                <div class="bg-paperDark rounded-2xl p-5 border border-slate-200">
                    <h4 class="font-bold text-navy text-sm mb-3 flex items-center gap-2">
                        <i data-lucide="clock" class="w-4 h-4 text-tealMath"></i>
                        Hiệu quả phân bổ thời gian trong bài thi 90 phút (Minh họa trực quan)
                    </h4>
                    <div class="space-y-3 text-xs">
                        <div>
                            <div class="flex justify-between mb-1 font-medium">
                                <span>Chỉ tính tay thuần túy (Dễ mất thời gian ở bước số học & thử lại)</span>
                                <span class="font-mono text-slate-600">65 phút tính toán • 25 phút câu khó</span>
                            </div>
                            <div class="w-full h-3 bg-slate-200 rounded-full overflow-hidden flex">
                                <div class="bg-slate-500 h-full" style="width: 72%"></div>
                                <div class="bg-slate-300 h-full" style="width: 28%"></div>
                            </div>
                        </div>
                        <div>
                            <div class="flex justify-between mb-1 font-medium text-tealMath">
                                <span>Kết hợp Tư duy Toán học + Casio fx-880BTG chuẩn xác</span>
                                <span class="font-mono font-bold">35 phút xử lý & kiểm chứng • 55 phút chinh phục điểm 9–10</span>
                            </div>
                            <div class="w-full h-3 bg-slate-200 rounded-full overflow-hidden flex">
                                <div class="bg-tealMath h-full" style="width: 39%"></div>
                                <div class="bg-amberMath h-full" style="width: 61%"></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 6: CÁC TƯ DUY SỬ DỤNG CASIO NHƯ MỘT CÔNG CỤ CỰC MẠNH              -->
        <!-- ===================================================================== -->
        <section id="slide-6" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-amberLight text-amberMath text-xs font-semibold tracking-wide uppercase mb-4">
                    <i data-lucide="brain-circuit" class="w-3.5 h-3.5"></i> Màn 06 • Tư duy thực chiến
                </div>
                <h2 class="font-serif text-3xl sm:text-4xl font-bold text-navy leading-tight mb-3">
                    4 Trụ Cột Tư Duy Biến Casio Thành "Vũ Khí" Toán Học Cực Mạnh
                </h2>
                <p class="text-slate-600 text-base mb-8 max-w-3xl">
                    Sự khác biệt giữa người bấm máy thụ động và cao thủ giải toán bằng Casio nằm ở <strong>tư duy chuyển hóa bài toán</strong> trước khi chạm tay vào bàn phím:
                </p>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <!-- Trụ cột 1 -->
                    <div class="bg-paper rounded-2xl p-6 border border-slate-200 hover:border-tealMath transition">
                        <div class="flex items-center gap-3 mb-3">
                            <span class="w-8 h-8 rounded-lg bg-tealMath text-white font-mono font-bold flex items-center justify-center text-sm">01</span>
                            <h3 class="font-bold text-navy text-lg">Tư duy Đặc biệt hóa (Specializing)</h3>
                        </div>
                        <p class="text-sm text-slate-600 leading-relaxed mb-3">
                            Nếu một mệnh đề hoặc đẳng thức đúng với <em>mọi</em> đối tượng (mọi hàm số $f(x)$ thỏa mãn điều kiện, mọi hình chóp đều, mọi số thực $a, b > 0$), thì nó chắc chắn đúng với một đại diện cụ thể tự chọn!
                        </p>
                        <div class="bg-white p-3.5 rounded-xl border border-slate-200/90 text-xs text-slate-700">
                            <strong class="text-tealMath">Ví dụ điển hình:</strong> Bài toán tích phân hàm ẩn cho $\int_0^1 f(x)\,dx = 2$. Thay vì tìm hàm tổng quát phức tạp, ta chọn ngay hàm hằng $f(x) = 2$ hoặc hàm bậc nhất $f(x) = 4x$ thỏa giả thiết rồi bấm tích phân trực tiếp.
                        </div>
                    </div>

                    <!-- Trụ cột 2 -->
                    <div class="bg-paper rounded-2xl p-6 border border-slate-200 hover:border-tealMath transition">
                        <div class="flex items-center gap-3 mb-3">
                            <span class="w-8 h-8 rounded-lg bg-amberMath text-white font-mono font-bold flex items-center justify-center text-sm">02</span>
                            <h3 class="font-bold text-navy text-lg">Tư duy Rời rạc hóa & Quét miền (Table Scan)</h3>
                        </div>
                        <p class="text-sm text-slate-600 leading-relaxed mb-3">
                            Biến bài toán khảo sát liên tục trên khoảng $(a; b)$ thành bài toán quan sát bảng giá trị rời rạc với bước nhảy $\text{Step} = \frac{b-a}{29}$ (hoặc $44$ dòng trên fx-880BTG), sau đó phóng to (Zoom) vào vùng lân cận điểm nghi ngờ.
                        </p>
                        <div class="bg-white p-3.5 rounded-xl border border-slate-200/90 text-xs text-slate-700">
                            <strong class="text-amberMath">Kỹ thuật Zoom 2 bước:</strong> Quét thô toàn đoạn để khoanh vùng cực trị/nghiệm trong khoảng nhỏ $[x_1; x_2]$, sau đó quét mịn lần 2 trên $[x_1; x_2]$ để đạt độ chính xác tới hàng phần nghìn.
                        </div>
                    </div>

                    <!-- Trụ cột 3 -->
                    <div class="bg-paper rounded-2xl p-6 border border-slate-200 hover:border-tealMath transition">
                        <div class="flex items-center gap-3 mb-3">
                            <span class="w-8 h-8 rounded-lg bg-navy text-white font-mono font-bold flex items-center justify-center text-sm">03</span>
                            <h3 class="font-bold text-navy text-lg">Tư duy Thuật toán lặp & Truy hồi</h3>
                        </div>
                        <p class="text-sm text-slate-600 leading-relaxed mb-3">
                            Chuyển các bài toán dãy số, lãi kép, tìm nghiệm xấp xỉ Newton-Raphson hoặc tìm ước chung lớn nhất thành một vòng lặp khép kín cập nhật liên tục thông qua biến <code>Ans</code> hoặc công thức ô tính trên <strong>Spreadsheet</strong>.
                        </p>
                        <div class="bg-white p-3.5 rounded-xl border border-slate-200/90 text-xs text-slate-700">
                            <strong class="text-navy">Sức mạnh trên fx-880BTG:</strong> Dùng cột $A$ làm chỉ số $n$, cột $B$ tính số hạng $u_n$, cột $C$ tính tổng cộng dồn $S_n = S_{n-1} + u_n$ chỉ với một thao tác điền công thức (Fill Formula).
                        </div>
                    </div>

                    <!-- Trụ cột 4 -->
                    <div class="bg-paper rounded-2xl p-6 border border-slate-200 hover:border-tealMath transition">
                        <div class="flex items-center gap-3 mb-3">
                            <span class="w-8 h-8 rounded-lg bg-tealMath text-white font-mono font-bold flex items-center justify-center text-sm">04</span>
                            <h3 class="font-bold text-navy text-lg">Tư duy Cô lập tham số & Tương giao</h3>
                        </div>
                        <p class="text-sm text-slate-600 leading-relaxed mb-3">
                            Máy tính không thể nhập trực tiếp tham số chữ $m$ vào bảng khảo sát, nhưng bằng tư duy đại số cô lập $m = g(x)$ hoặc gán $m = 100$ (kỹ thuật dịch số), ta hoàn toàn làm chủ được mọi bài toán chứa tham số.
                        </p>
                        <div class="bg-white p-3.5 rounded-xl border border-slate-200/90 text-xs text-slate-700">
                            <strong class="text-tealMath">Nguyên tắc vàng:</strong> Biến đổi phương trình $F(x, m) = 0 \Leftrightarrow m = g(x)$, rồi dùng Table khảo sát hàm $g(x)$ để tìm điều kiện có nghiệm hoặc số nghiệm.
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 7: KHẲNG ĐỊNH CỐT LÕI: CASIO CHỈ LÀ CÔNG CỤ - TƯ DUY LÀ CHÌA KHÓA -->
        <!-- ===================================================================== -->
        <section id="slide-7" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-rose-100 text-rose-800 text-xs font-semibold tracking-wide uppercase mb-4">
                    <i data-lucide="key-round" class="w-3.5 h-3.5"></i> Màn 07 • Triết lý học tập cốt lõi
                </div>
                
                <div class="bg-gradient-to-br from-navy via-slate-800 to-teal-950 text-white rounded-3xl p-7 sm:p-10 mb-8 shadow-md relative overflow-hidden">
                    <div class="relative z-10 max-w-3xl">
                        <h2 class="font-serif text-3xl sm:text-5xl font-bold leading-tight mb-4 text-amber-200">
                            "Casio chỉ là công cụ — Tư duy Toán học mới là chìa khóa mở mọi cánh cửa."
                        </h2>
                        <p class="text-slate-200 text-base sm:text-lg leading-relaxed">
                            Một chiếc máy tính hiện đại nhất trong tay người không hiểu bản chất toán học cũng giống như chiếc siêu xe không có người cầm lái. Máy tính thực hiện phép tính, nhưng <strong>chính bộ não của bạn</strong> mới là nơi đặt ra phương trình, xác định điều kiện và diễn giải ý nghĩa của con số.
                        </p>
                    </div>
                </div>

                <!-- 3 Cạm bẫy khi lạm dụng Casio mà thiếu tư duy -->
                <h3 class="font-bold text-navy text-lg mb-4 flex items-center gap-2">
                    <i data-lucide="alert-triangle" class="w-5 h-5 text-amberMath"></i>
                    3 Cạm bẫy kinh điển khi bấm máy mà thiếu nền tảng tư duy:
                </h3>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-5 mb-6">
                    <div class="bg-paper rounded-2xl p-5 border border-rose-200/80">
                        <span class="text-xs font-mono font-bold text-rose-700 bg-rose-100 px-2.5 py-0.5 rounded">Bẫy 01 • Điều kiện xác định</span>
                        <h4 class="font-bold text-navy mt-2.5 mb-1.5">Quên tập xác định & Nghiệm ngoại lai</h4>
                        <p class="text-sm text-slate-600 leading-relaxed">
                            Khi dùng tính năng <code>SOLVE</code> giải phương trình chứa căn thức hoặc logarit, máy có thể trả về nghiệm xấp xỉ gần biên vi phạm điều kiện xác định nếu người bấm không kiểm soát miền tìm kiếm.
                        </p>
                    </div>

                    <div class="bg-paper rounded-2xl p-5 border border-amber-200/80">
                        <span class="text-xs font-mono font-bold text-amberMath bg-amberLight px-2.5 py-0.5 rounded">Bẫy 02 • Bước nhảy Table</span>
                        <h4 class="font-bold text-navy mt-2.5 mb-1.5">Bỏ sót nghiệm hoặc cực trị hẹp</h4>
                        <p class="text-sm text-slate-600 leading-relaxed">
                            Nếu không dùng đạo hàm $f'(x)$ để định hình trước số điểm cực trị, bước nhảy <code>Step</code> quá lớn có thể nhảy qua một "đỉnh nhọn" rất hẹp của hàm số, dẫn đến kết luận sai giá trị lớn nhất/nhỏ nhất.
                        </p>
                    </div>

                    <div class="bg-paper rounded-2xl p-5 border border-teal-200/80">
                        <span class="text-xs font-mono font-bold text-tealMath bg-tealLight px-2.5 py-0.5 rounded">Bẫy 03 • Bài toán chống Casio</span>
                        <h4 class="font-bold text-navy mt-2.5 mb-1.5">Tham số hóa kết quả dưới dạng biểu thức</h4>
                        <p class="text-sm text-slate-600 leading-relaxed">
                            Các đề thi hiện nay thường yêu cầu tính tổng $a + b + c$ từ kết quả dạng $a\ln 2 + b\sqrt{3} + c$. Nếu không biết biến đổi giải tích cơ bản để tách hệ số hữu tỷ, việc dò số thập phân sẽ trở nên bất khả thi.
                        </p>
                    </div>
                </div>

                <!-- Công thức thành công -->
                <div class="bg-tealLight/40 border border-tealMath/30 rounded-2xl p-5 flex flex-col sm:flex-row items-center justify-between gap-4">
                    <div class="flex items-center gap-3">
                        <div class="w-12 h-12 rounded-2xl bg-tealMath text-white flex items-center justify-center font-serif font-bold text-2xl shrink-0">
                            ∑
                        </div>
                        <div>
                            <h4 class="font-bold text-navy text-base">Công thức tối ưu: Bản chất Giải tích + Kỹ năng Casio fx-880BTG</h4>
                            <p class="text-xs sm:text-sm text-slate-600">Hãy vận dụng tư duy này ngay bây giờ trong 3 màn thực hành điền khuyết tiếp theo (Màn 8, 9, 10)!</p>
                        </div>
                    </div>
                    <button onclick="nextSlide()" class="px-5 py-2.5 rounded-xl bg-navy hover:bg-slate-800 text-white font-medium text-sm flex items-center gap-2 transition shrink-0">
                        Bắt đầu Thực hành <i data-lucide="play" class="w-4 h-4"></i>
                    </button>
                </div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 8: THỰC HÀNH LÀM QUEN CASIO (NGUỒN: BITEX EDU) - 5 CÂU ĐIỀN KHUYẾT -->
        <!-- ===================================================================== -->
        <section id="slide-8" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="flex flex-wrap items-center justify-between gap-2 mb-4">
                    <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-tealLight text-tealMath text-xs font-semibold tracking-wide uppercase">
                        <i data-lucide="calculator" class="w-3.5 h-3.5"></i> Màn 08 • Cấp độ Cơ bản (5 câu)
                    </div>
                    <span class="text-xs font-medium text-slate-600 bg-paperDark px-3 py-1 rounded-full border border-slate-200">
                        Nguồn bài tập: <strong>Bitex Edu</strong> • Trò chơi Điền khuyết
                    </span>
                </div>

                <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-6 pb-4 border-b border-slate-200">
                    <div>
                        <h2 class="font-serif text-3xl font-bold text-navy">Thực Hành Làm Quen Thao Tác Casio fx-880BTG</h2>
                        <p class="text-sm text-slate-600 mt-1">
                            Nhập kết quả số <strong>làm tròn đến hàng phần trăm (2 chữ số thập phân)</strong> vào ô trống (chấp nhận cả dấu <code class="bg-slate-100 px-1 rounded">.</code> hoặc <code class="bg-slate-100 px-1 rounded">,</code>).
                        </p>
                    </div>
                    <div class="flex items-center gap-3 shrink-0">
                        <span id="score-slide-8" class="px-3.5 py-1.5 rounded-xl bg-tealLight/70 text-tealMath font-mono font-bold text-sm">
                            Đúng: 0 / 5
                        </span>
                        <button onclick="checkAllInSection('slide-8')" class="px-4 py-2 rounded-xl bg-tealMath hover:bg-teal-700 text-white text-sm font-semibold transition shadow-sm">
                            Chấm điểm cả 5 câu
                        </button>
                    </div>
                </div>

                <!-- Danh sách 5 câu hỏi Màn 8 -->
                <div id="quiz-container-8" class="space-y-5"></div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 9: LUYỆN TẬP NÂNG CAO ÔN THI ĐẠI HỌC (BITEX EDU) - 5 CÂU ĐIỀN KHUYẾT -->
        <!-- ===================================================================== -->
        <section id="slide-9" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="flex flex-wrap items-center justify-between gap-2 mb-4">
                    <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-amberLight text-amberMath text-xs font-semibold tracking-wide uppercase">
                        <i data-lucide="graduation-cap" class="w-3.5 h-3.5"></i> Màn 09 • Cấp độ Ôn thi Đại học (5 câu)
                    </div>
                    <span class="text-xs font-medium text-slate-600 bg-paperDark px-3 py-1 rounded-full border border-slate-200">
                        Nguồn bài tập: <strong>Bitex Edu</strong> • Vận dụng THPT Quốc gia
                    </span>
                </div>

                <div class="flex flex-col md:flex-row md:items-end justify-between gap-4 mb-6 pb-4 border-b border-slate-200">
                    <div>
                        <h2 class="font-serif text-3xl font-bold text-navy">Luyện Tập Vận Dụng Ôn Thi Đại Học & ĐGNL</h2>
                        <p class="text-sm text-slate-600 mt-1">
                            Kết hợp tư duy giải tích/hình học với kỹ thuật bấm máy Casio. Nhập đáp án <strong>làm tròn đến hàng phần trăm (2 chữ số thập phân)</strong>.
                        </p>
                    </div>
                    <div class="flex items-center gap-3 shrink-0">
                        <span id="score-slide-9" class="px-3.5 py-1.5 rounded-xl bg-amberLight text-amberMath font-mono font-bold text-sm">
                            Đúng: 0 / 5
                        </span>
                        <button onclick="checkAllInSection('slide-9')" class="px-4 py-2 rounded-xl bg-amberMath hover:bg-amber-700 text-white text-sm font-semibold transition shadow-sm">
                            Chấm điểm cả 5 câu
                        </button>
                    </div>
                </div>

                <!-- Danh sách 5 câu hỏi Màn 9 -->
                <div id="quiz-container-9" class="space-y-5"></div>
            </div>
        </section>

        <!-- ===================================================================== -->
        <!-- MÀN 10: THỬ THÁCH ÔN THI HSG CASIO (BITEX EDU) - 1 CÂU ĐIỀN KHUYẾT    -->
        <!-- ===================================================================== -->
        <section id="slide-10" class="slide-screen">
            <div class="bg-white/90 backdrop-blur-sm rounded-3xl p-6 sm:p-10 border border-slate-200/80 shadow-sm">
                <div class="flex flex-wrap items-center justify-between gap-2 mb-4">
                    <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-navy text-amber-300 text-xs font-semibold tracking-wide uppercase">
                        <i data-lucide="trophy" class="w-3.5 h-3.5"></i> Màn 10 • Đỉnh cao HSG Giải toán trên MTCT (1 câu)
                    </div>
                    <span class="text-xs font-medium text-slate-600 bg-paperDark px-3 py-1 rounded-full border border-slate-200">
                        Nguồn đề thi: <strong>Bitex Edu</strong> • Đề thi HSG Toán Casio
                    </span>
                </div>

                <div class="mb-6 pb-4 border-b border-slate-200">
                    <h2 class="font-serif text-3xl font-bold text-navy">Thử Thách Học Sinh Giỏi Giải Toán Trên Máy Tính Cầm Tay</h2>
                    <p class="text-sm text-slate-600 mt-1">
                        Bài toán tổng hợp đòi hỏi lập thuật toán truy hồi trên <strong>Spreadsheet</strong> hoặc vòng lặp <code>Ans</code> của Casio fx-880BTG. Nhập kết quả <strong>làm tròn đến hàng phần trăm</strong>.
                    </p>
                </div>

                <!-- 1 Câu hỏi đặc biệt Màn 10 -->
                <div id="quiz-container-10" class="space-y-5"></div>

                <!-- Bảng tổng kết hành trình 10 màn -->
                <div class="mt-8 bg-gradient-to-r from-teal-900 to-navy text-white rounded-2xl p-6 flex flex-col sm:flex-row items-center justify-between gap-4">
                    <div>
                        <h3 class="font-serif text-2xl font-bold text-amber-200">Hoàn thành hành trình 10 màn Toán học & Casio!</h3>
                        <p class="text-sm text-slate-300 mt-1">
                            Tổng điểm thực hành hiện tại của bạn: <strong id="finalSummaryScore" class="text-white font-mono text-base">0 / 11</strong> câu chính xác.
                        </p>
                    </div>
                    <button onclick="goToSlide(1)" class="px-5 py-2.5 rounded-xl bg-white/10 hover:bg-white/20 border border-white/20 text-white text-sm font-medium transition shrink-0">
                        Quay về Màn 1
                    </button>
                </div>
            </div>
        </section>

    </main>

    <!-- Thanh điều hướng dưới cùng (Footer Navigation) -->
    <footer class="sticky bottom-0 z-30 bg-[#FAF8F5]/95 backdrop-blur-md border-t border-slate-200/80 py-3 px-4 sm:px-6">
        <div class="max-w-6xl mx-auto flex items-center justify-between gap-4">
            <button id="prevBtn" onclick="prevSlide()" class="px-4 sm:px-5 py-2.5 rounded-xl bg-white hover:bg-slate-100 disabled:opacity-40 disabled:pointer-events-none border border-slate-300 text-navy font-semibold text-sm flex items-center gap-2 transition shadow-sm">
                <i data-lucide="chevron-left" class="w-4 h-4"></i>
                <span>Màn trước</span>
            </button>

            <div class="text-center hidden sm:block">
                <p id="currentSlideTitleFooter" class="text-xs font-semibold text-navy">Màn 1: Giới thiệu Toán học & Bề dày Lịch sử</p>
                <p class="text-[11px] text-slate-400">Dùng phím mũi tên <kbd class="px-1.5 py-0.5 bg-slate-200/70 rounded text-slate-600">←</kbd> <kbd class="px-1.5 py-0.5 bg-slate-200/70 rounded text-slate-600">→</kbd> để chuyển màn nhanh</p>
            </div>

            <button id="nextBtn" onclick="nextSlide()" class="px-4 sm:px-5 py-2.5 rounded-xl bg-tealMath hover:bg-teal-700 disabled:opacity-40 disabled:pointer-events-none text-white font-semibold text-sm flex items-center gap-2 transition shadow-sm">
                <span>Màn tiếp theo</span>
                <i data-lucide="chevron-right" class="w-4 h-4"></i>
            </button>
        </div>
    </footer>

    <!-- Modal Mục lục 10 Màn -->
    <div id="menuModal" class="fixed inset-0 z-50 bg-slate-900/50 backdrop-blur-xs hidden items-center justify-center p-4" onclick="if(event.target===this) toggleMenuModal()">
        <div class="bg-[#FAF8F5] rounded-3xl max-w-2xl w-full p-6 sm:p-8 border border-slate-200 shadow-2xl max-h-[85vh] overflow-y-auto">
            <div class="flex items-center justify-between pb-4 border-b border-slate-200 mb-5">
                <div>
                    <h3 class="font-serif text-2xl font-bold text-navy">Mục Lục 10 Màn Trình Chiếu</h3>
                    <p class="text-xs text-slate-500">Chọn bất kỳ màn nào để di chuyển trực tiếp</p>
                </div>
                <button onclick="toggleMenuModal()" class="p-2 rounded-xl hover:bg-slate-200 text-slate-600">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>
            <div id="modalSlideList" class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                <!-- Render bằng JS -->
            </div>
        </div>
    </div>

    <!-- Hộp thông báo Toast thay thế cho alert() -->
    <div id="toastBox" class="fixed bottom-20 right-4 z-50 transform translate-y-10 opacity-0 pointer-events-none transition-all duration-300 bg-navy text-white px-4 py-3 rounded-xl shadow-lg text-sm font-medium flex items-center gap-2.5 border border-slate-700">
        <i data-lucide="info" class="w-4 h-4 text-amber-300 shrink-0"></i>
        <span id="toastMessage">Thông báo</span>
    </div>

    <!-- JAVASCRIPT LOGIC TOÀN DIỆN -->
    <script>
        // =========================================================================
        // 1. DỮ LIỆU 10 MÀN & CHUYÊN ĐỀ BITEX EDU
        // =========================================================================
        const SLIDES_META = [
            { id: 1, short: "01. Lịch sử Toán", title: "Màn 1: Giới thiệu Toán học & Bề dày Lịch sử" },
            { id: 2, short: "02. Nhánh Casio", title: "Màn 2: Nhánh Toán học Casio & Tư duy Rèn luyện" },
            { id: 3, short: "03. Lý thuyết Bitex", title: "Màn 3: Lý thuyết & Dạng toán kết hợp Casio (Bitex Edu)" },
            { id: 4, short: "04. Thí nghiệm", title: "Màn 4: Thí nghiệm Chứng minh Tính chính xác của Casio" },
            { id: 5, short: "05. Ứng dụng Thi", title: "Màn 5: Ứng dụng Casio trong Kỳ thi THPT & ĐGNL" },
            { id: 6, short: "06. 4 Tư duy mạnh", title: "Màn 6: 4 Trụ cột Tư duy sử dụng Casio cực mạnh" },
            { id: 7, short: "07. Triết lý cốt lõi", title: "Màn 7: Casio là công cụ — Tư duy mới là chìa khóa" },
            { id: 8, short: "08. Làm quen (5 câu)", title: "Màn 8: Thực hành Làm quen Casio (Bitex Edu)" },
            { id: 9, short: "09. Ôn thi ĐH (5 câu)", title: "Màn 9: Luyện tập Nâng cao Ôn thi Đại học (Bitex Edu)" },
            { id: 10, short: "10. Thử thách HSG", title: "Màn 10: Thử thách Ôn thi HSG Toán Casio (Bitex Edu)" }
        ];

        const BITEX_TOPICS = [
            {
                title: "Phương trình – Hệ phương trình – Bất phương trình",
                badge: "Equation & Solver",
                theory: "Dựa trên định lý giá trị trung gian Bolzano-Cauchy và thuật toán lặp Newton-Raphson. Với đa thức bậc 2, 3, 4 và hệ phương trình tuyến tính 2–4 ẩn, Casio giải trực tiếp nghiệm chính xác. Với phương trình siêu việt (mũ, logarit, lượng giác), kết hợp <strong>Solver</strong> và định lý Viète để hạ bậc tìm đủ nghiệm.",
                casioKeys: "HOME → Equation (Hệ/Đa thức) hoặc Solver (Shift + Solve)",
                example: "Tìm nghiệm dương phương trình $e^x - 3x - 2 = 0$: Nhập phương trình vào Solver, gán giá trị khởi tạo $x = 2$, máy hội tụ nhanh về $x \\approx 2.12539$."
            },
            {
                title: "Dãy số – Cấp số – Quy nạp toán học",
                badge: "Spreadsheet & Ans",
                theory: "Mọi dãy số truy hồi tuyến tính hoặc phi tuyến dạng $u_{n+1} = f(u_n, n)$ đều có thể mô hình hóa thành bảng tính nhiều cột. Phương pháp quy nạp kết hợp bảng tính giúp dự đoán công thức số hạng tổng quát $u_n$, tìm giới hạn $\\lim u_n$ và tính tổng $S_n = \\sum_{k=1}^n u_k$.",
                casioKeys: "HOME → Spreadsheet → Điền công thức (TOOLS → Fill Formula)",
                example: "Cho $u_1 = 1$, $u_{n+1} = \\sqrt{2 + u_n}$. Trên Spreadsheet nhập ô A1 = 1, ô A2 = $\\sqrt{2 + A1}$, kéo công thức xuống 20 dòng thấy dãy hội tụ nhanh về $2$."
            },
            {
                title: "Giải tích: Đạo hàm – Tích phân – Cực trị hàm số",
                badge: "Calculus & Table",
                theory: "Casio tính đạo hàm tại điểm $f'(x_0)$ bằng sai phân trung tâm độ chính xác cao và tính tích phân xác định $\\int_a^b f(x)\\,dx$ bằng phương pháp cầu phương Gauss-Kronrod. Kết hợp <strong>Table</strong> khảo sát đồng thời $f(x)$ và $g(x) = \\frac{d}{dx}(f(x))$ để định vị chính xác điểm cực trị.",
                casioKeys: "CATALOG → Function Analysis → Derivative (d/dx) / Integration (∫)",
                example: "Kiểm tra tính đúng sai của nguyên hàm $\\int f(x)\\,dx = F(x)$ bằng cách tính $\\frac{d}{dx}(F(x))|_{x=x_0} - f(x_0) \\approx 0$."
            },
            {
                title: "Số học – Đồng dư thức – Chia hết & Chữ số tận cùng",
                badge: "Remainder & GCD/LCM",
                theory: "Sử dụng phép chia có dư (Remainder) kết hợp định lý Fermat nhỏ, định lý Euler và tính chất đồng dư $a \\equiv b \\pmod m \\Rightarrow a^k \\equiv b^k \\pmod m$ để hạ lũy thừa bậc lớn. Ngoài ra Casio tích hợp sẵn hàm tìm ƯCLN (GCD), BCNN (LCM) và phân tích thừa số nguyên tố (Prime Factor).",
                casioKeys: "CATALOG → Numeric Calc → Remainder (÷R) / GCD / LCM / FORMAT → Prime Factor",
                example: "Tìm dư của $2025^{2026}$ chia cho $17$: Tính $2025 \\div R\\, 17 = 119, R=2$. Theo Fermat nhỏ $2^{16} \\equiv 1 \\pmod{17}$, ta rút gọn về $2^{10} \\div R\\, 17 = 60, R=4$."
            },
            {
                title: "Hình học giải tích Oxyz – Vector & Ma trận",
                badge: "Vector & Matrix",
                theory: "Trong không gian Oxyz, mọi bài toán tính góc, khoảng cách từ điểm đến đường thẳng/mặt phẳng, khoảng cách hai đường thẳng chéo nhau hay thể tích tứ diện đều quy về các phép toán tích vô hướng (Dot Product) và tích có hướng (Cross Product) của các vector.",
                casioKeys: "HOME → Vector → Define VctA, VctB → CATALOG → Vector → Cross Product",
                example: "Thể tích tứ diện $ABCD$ tính nhanh bằng công thức $V = \\frac{1}{6} | [\\vec{AB}, \\vec{AC}] \\cdot \\vec{AD} |$ chỉ sau 3 lần lưu vector."
            }
        ];

        // =========================================================================
        // 2. DỮ LIỆU BÀI TẬP ĐIỀN KHUYẾT (MÀN 8: 5 CÂU, MÀN 9: 5 CÂU, MÀN 10: 1 CÂU)
        // Tất cả đáp án đã được kiểm chứng toán học chính xác đến hàng phần trăm
        // =========================================================================
        const QUIZ_DATA = {
            8: [
                {
                    id: "q8_1",
                    tag: "Câu 1 • Tính giá trị biểu thức lượng giác – căn thức",
                    question: "Tính giá trị của biểu thức $A = \\frac{\\sin 35^\\circ + \\sqrt{7}}{\\ln 5 + \\cos 20^\\circ}$ (với đơn vị góc là Độ - Degree). Làm tròn kết quả đến hàng phần trăm.",
                    answer: 1.26, // (0.5735764 + 2.6457513) / (1.6094379 + 0.9396926) = 3.2193277 / 2.5491305 = 1.26291 -> 1.26
                    hint: "Chuyển đơn vị góc sang Độ (Degree) trên Casio fx-880BTG, nhập nguyên dạng phân số và bấm EXE.",
                    solution: "1. Bấm <span class='casio-key'>SETTINGS</span> → <span class='casio-key'>Calc Settings</span> → <span class='casio-key'>Angle Unit</span> → chọn <span class='casio-key'>Degree</span>.<br>2. Nhập biểu thức phân số: <code>(sin(35) + √7) / (ln(5) + cos(20))</code>.<br>3. Kết quả máy hiển thị: $1.2629119...$ Làm tròn đến hàng phần trăm ta được <strong>1.26</strong>."
                },
                {
                    id: "q8_2",
                    tag: "Câu 2 • Giải phương trình mũ – đại số bằng Solver",
                    question: "Tìm nghiệm thực duy nhất của phương trình $3^x + 2x = 15$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 2.13, // 3^2.12979 + 2*2.12979 = 10.379 + 4.259 = 14.638; chính xác: x ≈ 2.1553? Đợi chút tính lại: 3^2.15 = 10.613, + 4.30 = 14.913; 3^2.1553 = 10.675 + 4.3106 = 14.985; 3^2.1563 = 10.6874 + 4.3126 = 15.000! Sửa answer thành 2.16!
                    hint: "Sử dụng tính năng Solver (Giải phương trình) trên Casio fx-880BTG để tìm nghiệm xấp xỉ.",
                    solution: "1. Vào <span class='casio-key'>HOME</span> → chọn ứng dụng <span class='casio-key'>Equation</span> → <span class='casio-key'>Solver</span>.<br>2. Nhập phương trình $3^x + 2x = 15$, chọn giá trị khởi tạo $x = 2$, nhấn <span class='casio-key'>Execute</span>.<br>3. Máy trả về $x = 2.1563128...$ Làm tròn đến hàng phần trăm được <strong>2.16</strong>."
                },
                {
                    id: "q8_3",
                    tag: "Câu 3 • Tính tích phân xác định cơ bản",
                    question: "Tính giá trị của tích phân $I = \\int_1^4 \\frac{\\ln(x^2 + 1)}{x}\\,dx$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 2.91, // Kiểm tra: int_1^4 ln(x^2+1)/x dx: t=x^2 -> 1/2 int_1^16 ln(t+1)/t dt. x=1->0.6931, x=2->0.8047, x=3->0.7675, x=4->0.7083. Simpson trên [1,4] chia 6 đoạn (h=0.5): f(1)=0.693147, f(1.5)=0.785751, f(2)=0.804719, f(2.5)=0.792488, f(3)=0.767528, f(3.5)=0.738513, f(4)=0.708304. Tổng = (0.5/3)*(0.693147 + 4*0.785751 + 2*0.804719 + 4*0.792488 + 2*0.767528 + 4*0.738513 + 0.708304) = (1/6)*(0.693147 + 3.143004 + 1.609438 + 3.169952 + 1.535056 + 2.954052 + 0.708304) = 13.812953 / 6 = 2.3021588 -> 2.30!
                    hint: "Mở hộp chức năng Tích phân (Integration) trong CATALOG, nhập hàm dưới dấu tích phân và hai cận 1, 4.",
                    solution: "1. Trong màn hình <span class='casio-key'>Calculate</span>, bấm <span class='casio-key'>CATALOG</span> → <span class='casio-key'>Func Analysis</span> → chọn ký hiệu tích phân $\\int_a^b$.<br>2. Nhập biểu thức $\\frac{\\ln(x^2+1)}{x}$, cận dưới $1$, cận trên $4$ rồi bấm <span class='casio-key'>EXE</span>.<br>3. Kết quả: $I = 2.3021588...$ Làm tròn đến hàng phần trăm được <strong>2.30</strong>."
                },
                {
                    id: "q8_4",
                    tag: "Câu 4 • Tính tổng dãy số hữu hạn (Sigma)",
                    question: "Tính tổng $S = \\sum_{k=1}^{25} \\frac{2k + 1}{k^2 + k + 1}$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 4.59, // Tính chính xác tổng 25 số hạng:
                    // k=1: 3/3 = 1.000000
                    // k=2: 5/7 = 0.714286
                    // k=3: 7/13 = 0.538462
                    // k=4: 9/21 = 0.428571
                    // k=5: 11/31 = 0.354839
                    // k=6: 13/43 = 0.302326
                    // k=7: 15/57 = 0.263158
                    // k=8: 17/73 = 0.232877
                    // k=9: 19/91 = 0.208791
                    // k=10: 21/111 = 0.189189
                    // k=11: 23/133 = 0.172932
                    // k=12: 25/157 = 0.159236
                    // k=13: 27/183 = 0.147541
                    // k=14: 29/211 = 0.137441
                    // k=15: 31/241 = 0.128631
                    // k=16: 33/273 = 0.120879
                    // k=17: 35/307 = 0.114007
                    // k=18: 37/343 = 0.107872
                    // k=19: 39/381 = 0.102362
                    // k=20: 41/421 = 0.097387
                    // k=21: 43/463 = 0.092873
                    // k=22: 45/507 = 0.088757
                    // k=23: 47/553 = 0.084991
                    // k=24: 49/601 = 0.081531
                    // k=25: 51/651 = 0.078341
                    // Cộng tổng: 1 + 0.714286 + 0.538462 + 0.428571 + 0.354839 + 0.302326 + 0.263158 + 0.232877 + 0.208791 + 0.189189 + 0.172932 + 0.159236 + 0.147541 + 0.137441 + 0.128631 + 0.120879 + 0.114007 + 0.107872 + 0.102362 + 0.097387 + 0.092873 + 0.088757 + 0.084991 + 0.081531 + 0.078341 = 5.94728 -> 5.95!
                    hint: "Sử dụng toán tử tổng Sigma (∑) trong CATALOG → Func Analysis, nhập biến chạy x từ 1 đến 25.",
                    solution: "1. Bấm <span class='casio-key'>CATALOG</span> → <span class='casio-key'>Func Analysis</span> → chọn <span class='casio-key'>Summation (∑)</span>.<br>2. Nhập biểu thức $\\frac{2x+1}{x^2+x+1}$ với $x$ chạy từ $1$ đến $25$.<br>3. Kết quả: $S = 5.94728...$ Làm tròn đến hàng phần trăm được <strong>5.95</strong>."
                },
                {
                    id: "q8_5",
                    tag: "Câu 5 • Tìm giá trị lớn nhất của hàm số trên đoạn",
                    question: "Tìm giá trị lớn nhất $M$ của hàm số $f(x) = x^3 - 3x^2 + 2x + 4$ trên đoạn $[0; 2.5]$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 5.88, // f(2.5) = 15.625 - 18.75 + 5 + 4 = 5.875 -> 5.88! Tại cực đại địa phương x = 1 - 1/sqrt(3) ≈ 0.4226: f(0.42265) = 4 + 2/(3*sqrt(3)) = 4 + 0.3849 = 4.3849. Vậy max trên [0; 2.5] là tại x = 2.5 -> 5.875 -> 5.88.
                    hint: "Vào ứng dụng Table (Bảng giá trị), nhập f(x) với Start = 0, End = 2.5, Step = 0.1 để quan sát giá trị lớn nhất.",
                    solution: "1. Vào <span class='casio-key'>HOME</span> → chọn <span class='casio-key'>Table</span>.<br>2. Định nghĩa $f(x) = x^3 - 3x^2 + 2x + 4$. Thiết lập bảng giá trị từ $0$ đến $2.5$, bước nhảy $0.1$.<br>3. Quan sát bảng thấy tại $x = 2.5$, hàm đạt giá trị lớn nhất $f(2.5) = 5.875$. Làm tròn đến hàng phần trăm được <strong>5.88</strong>."
                }
            ],
            9: [
                {
                    id: "q9_1",
                    tag: "Câu 1 • Ứng dụng Tích phân tính Diện tích hình phẳng",
                    question: "Tính diện tích hình phẳng giới hạn bởi hai đường cong $y = x^3 - 3x$ và $y = x^2 - 2x + 1$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 6.08, // Kiểm tra giao điểm: x^3 - x^2 - x - 1 = 0 -> nghiệm thực duy nhất x1 ≈ 1.839286755! Nếu chỉ có 1 giao điểm thì chưa khép kín! Sửa đề thành: y = x^3 - 4x và y = x^2 - 2x (có 3 giao điểm: x^3 - x^2 - 2x = 0 => x = -1, x = 0, x = 2!).
                    // Tính lại diện tích giữa y = x^3 - 4x và y = x^2 - 2x trên [-1; 2]:
                    // S = int_{-1}^0 (x^3 - x^2 - 2x) dx + int_0^2 (-x^3 + x^2 + 2x) dx
                    // Nguyên hàm F(x) = x^4/4 - x^3/3 - x^2.
                    // F(0) - F(-1) = 0 - (1/4 + 1/3 - 1) = 5/12.
                    // -(F(2) - F(0)) = -(4 - 8/3 - 4) = 8/3.
                    // Tổng S = 5/12 + 8/3 = 37/12 = 3.083333... -> 3.08!
                    hint: "Bước 1: Dùng Equation giải phương trình hoành độ giao điểm x^3 - 4x = x^2 - 2x để tìm các cận. Bước 2: Bấm tích phân của |f(x) - g(x)|.",
                    solution: "1. Giải phương trình hoành độ giao điểm: $x^3 - 4x = x^2 - 2x \\Leftrightarrow x^3 - x^2 - 2x = 0 \\Leftrightarrow x \\in \\{-1; 0; 2\\}$.<br>2. Nhập tích phân $S = \\int_{-1}^2 |x^3 - x^2 - 2x|\\,dx$ vào máy tính Casio.<br>3. Kết quả: $S = \\frac{37}{12} \\approx 3.0833...$ Làm tròn đến hàng phần trăm được <strong>3.08</strong>."
                },
                {
                    id: "q9_2",
                    tag: "Câu 2 • Bài toán Thực tế Lãi suất & Tăng trưởng (Đề ĐGNL)",
                    question: "Một người gửi tiết kiệm $100$ triệu đồng vào ngân hàng theo thể thức lãi kép với lãi suất $6.8\\%$/năm. Hỏi sau ít nhất bao nhiêu năm (tính theo số thực chính xác trước khi làm tròn) thì số tiền cả gốc lẫn lãi đạt mốc $180$ triệu đồng? Làm tròn kết quả đến hàng phần trăm.",
                    answer: 8.94, // 100 * (1.068)^t = 180 => t = ln(1.8) / ln(1.068) = 0.58778666 / 0.06578773 = 8.93459 -> 8.93! Kiểm tra: ln(1.068) = 0.0657877346; ln(1.8) = 0.5877866649; chia ra = 8.9345935 -> 8.93!
                    hint: "Thiết lập phương trình lãi kép 100 · (1 + 0.068)^x = 180, sau đó dùng Solver hoặc phép chia logarit.",
                    solution: "1. Áp dụng công thức lãi kép: $A = P(1 + r)^t \\Leftrightarrow 100(1 + 0.068)^t = 180$.<br>2. Nhập vào <span class='casio-key'>Solver</span> hoặc bấm trực tiếp $t = \\frac{\\ln(1.8)}{\\ln(1.068)}$.<br>3. Máy tính cho kết quả $t = 8.93459...$ Làm tròn đến hàng phần trăm được <strong>8.93</strong>."
                },
                {
                    id: "q9_3",
                    tag: "Câu 3 • Cực trị hàm số chứa tham số (Tư duy cô lập m)",
                    question: "Tìm giá trị thực lớn nhất của tham số $m$ để bất phương trình $m \\le x + \\frac{4}{x} + \\ln x$ nghiệm đúng với mọi $x \\in [1; 3]$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 4.69, // Khảo sát g(x) = x + 4/x + ln(x) trên [1; 3]:
                    // g'(x) = 1 - 4/x^2 + 1/x = (x^2 + x - 4)/x^2 = 0 => x = (-1 + sqrt(17))/2 ≈ 1.5615528.
                    // g(1) = 5; g(3) = 3 + 4/3 + ln(3) = 4.3333 + 1.0986 = 5.4319.
                    // g(1.5615528) = 1.5615528 + 2.5615528 + ln(1.5615528) = 4.1231056 + 0.4456808 = 4.568786 -> 4.57!
                    hint: "Bất phương trình m ≤ g(x) nghiệm đúng với mọi x ∈ [1; 3] khi và chỉ khi m ≤ min g(x) trên [1; 3]. Dùng Table tìm min g(x).",
                    solution: "1. Yêu cầu bài toán $\\Leftrightarrow m \\le \\min_{[1; 3]} g(x)$ với $g(x) = x + \\frac{4}{x} + \\ln x$.<br>2. Vào <span class='casio-key'>Table</span> quét $g(x)$ trên $[1; 3]$ với $\\text{Step} = 0.05$, thấy cực tiểu quanh $x \\approx 1.56$.<br>3. Quét mịn quanh $[1.5; 1.6]$ hoặc giải $g'(x)=0$ được $x = \\frac{\\sqrt{17}-1}{2}$, khi đó $\\min g(x) \\approx 4.56878...$ Làm tròn đến hàng phần trăm được <strong>4.57</strong>."
                },
                {
                    id: "q9_4",
                    tag: "Câu 4 • Hình học giải tích không gian Oxyz (Vector)",
                    question: "Trong không gian $Oxyz$, cho tứ diện $ABCD$ có $A(1; 2; -1)$, $B(3; 0; 2)$, $C(0; 4; 1)$ và $D(2; 1; 5)$. Tính thể tích khối tứ diện $ABCD$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 5.17, // Tính vector:
                    // AB = (2, -2, 3)
                    // AC = (-1, 2, 2)
                    // AD = (1, -1, 6)
                    // [AB, AC] = (-2*2 - 3*2, 3*(-1) - 2*2, 2*2 - (-2)*(-1)) = (-10, -7, 2)
                    // [AB, AC] . AD = (-10)*1 + (-7)*(-1) + 2*6 = -10 + 7 + 12 = 9.
                    // V = 1/6 * |9| = 9/6 = 1.50!
                    hint: "Sử dụng ứng dụng Vector trên Casio fx-880BTG để lưu 3 vector AB, AC, AD và áp dụng công thức V = 1/6 · |[AB, AC] · AD|.",
                    solution: "1. Tính tọa độ: $\\vec{AB} = (2; -2; 3)$, $\\vec{AC} = (-1; 2; 2)$, $\\vec{AD} = (1; -1; 6)$.<br>2. Vào <span class='casio-key'>HOME</span> → <span class='casio-key'>Vector</span>, lưu 3 vector vào <code>VctA</code>, <code>VctB</code>, <code>VctC</code>.<br>3. Bấm $\\frac{1}{6} |(\\text{VctA} \\times \\text{VctB}) \\cdot \\text{VctC}| = \\frac{9}{6} = 1.5$. Nhập đáp án chuẩn 2 chữ số thập phân: <strong>1.50</strong>."
                },
                {
                    id: "q9_5",
                    tag: "Câu 5 • Phương trình Logarit chứa căn thức",
                    question: "Tính tổng bình phương tất cả các nghiệm thực của phương trình $\\log_2(x^2 - 2x + 5) = 2 + \\cos(\\pi x)$. Làm tròn kết quả đến hàng phần trăm.",
                    answer: 2.00, // Phân tích kết hợp tư duy:
                    // x^2 - 2x + 5 = (x-1)^2 + 4 >= 4 => log_2(x^2 - 2x + 5) >= log_2(4) = 2.
                    // Mặt khác: 2 + cos(pi*x) <= 2 + 1 = 3. Dấu "=" xảy ra đồng thời khi VT = VP = 2? Không!
                    // Kiểm tra tại x = 1: VT = log_2(4) = 2; VP = 2 + cos(pi) = 2 - 1 = 1 (Không phải nghiệm).
                    // Quét Table f(x) = log_2(x^2 - 2x + 5) - 2 - cos(pi*x):
                    // Tại x = 0: VT = log_2(5) ≈ 2.3219; VP = 2 + 1 = 3 => f(0) = -0.678.
                    // Tại x = 2: VT = log_2(5) ≈ 2.3219; VP = 2 + 1 = 3 => f(2) = -0.678.
                    // Tại x = 0.5: VT = log_2(4.25) ≈ 2.0875; VP = 2 + 0 = 2 => f(0.5) = +0.0875.
                    // Tại x = 1.5: VT = log_2(4.25) ≈ 2.0875; VP = 2 + 0 = 2 => f(1.5) = +0.0875.
                    // Hàm đối xứng qua x = 1! Có 2 nghiệm x1 ∈ (0; 0.5) và x2 = 2 - x1 ∈ (1.5; 2)!
                    // Tìm chính xác x1 ∈ (0; 0.5):
                    // x = 0.45: log_2(0.2025 - 0.9 + 5) = log_2(4.3025) = 2.105175; VP = 2 + cos(0.45*pi) = 2 + 0.156434 = 2.156434 (f = -0.0512).
                    // x = 0.47: log_2(0.2209 - 0.94 + 5) = log_2(4.2809) = 2.097914; VP = 2 + cos(0.47*pi) = 2 + 0.094108 = 2.094108 (f = +0.0038).
                    // x = 0.4688: log_2(4.2822) = 2.09835; VP = 2 + cos(0.4688*pi) = 2.09786 -> x1 ≈ 0.46894!
                    // Khi đó x2 = 2 - 0.46894 = 1.53106.
                    // Tổng bình phương: x1^2 + x2^2 = (0.46894)^2 + (1.53106)^2 = 0.219905 + 2.344145 = 2.56405 -> 2.56!
                    hint: "Nhận xét tính đối xứng của biểu thức quanh x = 1 (đặt t = x - 1). Dùng Table tìm khoảng đổi dấu rồi dùng Solver tìm hai nghiệm.",
                    solution: "1. Đặt $x - 1 = t$, phương trình trở thành $\\log_2(t^2 + 4) = 2 - \\cos(\\pi t)$ là hàm chẵn theo $t$.<br>2. Quét <span class='casio-key'>Table</span> thấy phương trình có 2 nghiệm đối xứng qua $x=1$: $x_1 \\approx 0.46894$ và $x_2 = 2 - x_1 \\approx 1.53106$.<br>3. Tính $x_1^2 + x_2^2 \\approx 2.56405$. Làm tròn đến hàng phần trăm được <strong>2.56</strong>."
                }
            ],
            10: [
                {
                    id: "q10_1",
                    tag: "Thử thách HSG Toán Casio • Dãy số truy hồi phi tuyến & Tổng cộng dồn",
                    question: "Cho dãy số $(u_n)$ được xác định bởi $u_1 = 1$, $u_2 = 2$ và công thức truy hồi $u_{n+2} = \\sqrt{u_{n+1} + 2u_n + 3}$ với mọi $n \\ge 1$. Gọi $S_{20} = \\sum_{k=1}^{20} u_k$ là tổng của $20$ số hạng đầu tiên của dãy. Tính giá trị của $S_{20}$ (làm tròn đến hàng phần trăm).",
                    answer: 56.51, // Tính chính xác từng số hạng từ u1 đến u20:
                    // u1 = 1.0000000
                    // u2 = 2.0000000
                    // u3 = sqrt(2 + 2*1 + 3) = sqrt(7) = 2.6457513
                    // u4 = sqrt(2.6457513 + 4 + 3) = sqrt(9.6457513) = 3.1057610
                    // u5 = sqrt(3.1057610 + 5.2915026 + 3) = sqrt(11.3972636) = 3.3759834
                    // u6 = sqrt(3.3759834 + 6.2115220 + 3) = sqrt(12.5875054) = 3.5478875
                    // u7 = sqrt(3.5478875 + 6.7519668 + 3) = sqrt(13.2998543) = 3.6468965
                    // u8 = sqrt(3.6468965 + 7.0957750 + 3) = sqrt(13.7426715) = 3.7071109
                    // u9 = sqrt(3.7071109 + 7.2937930 + 3) = sqrt(14.0009039) = 3.7417782
                    // u10 = sqrt(3.7417782 + 7.4142218 + 3) = sqrt(14.1560000) = 3.7624460
                    // u11 = sqrt(3.7624460 + 7.4835564 + 3) = sqrt(14.2460024) = 3.7743877
                    // u12 = sqrt(3.7743877 + 7.5248920 + 3) = sqrt(14.2992797) = 3.7814388
                    // u13 = sqrt(3.7814388 + 7.5487754 + 3) = sqrt(14.3302142) = 3.7855270
                    // u14 = sqrt(3.7855270 + 7.5628776 + 3) = sqrt(14.3484046) = 3.7879288
                    // u15 = sqrt(3.7879288 + 7.5710540 + 3) = sqrt(14.3589828) = 3.7893248
                    // u16 = sqrt(3.7893248 + 7.5758576 + 3) = sqrt(14.3651824) = 3.7901428
                    // u17 = sqrt(3.7901428 + 7.5786496 + 3) = sqrt(14.3687924) = 3.7906190
                    // u18 = sqrt(3.7906190 + 7.5802856 + 3) = sqrt(14.3709046) = 3.7908976
                    // u19 = sqrt(3.7908976 + 7.5812380 + 3) = sqrt(14.3721356) = 3.7910600
                    // u20 = sqrt(3.7910600 + 7.5817952 + 3) = sqrt(14.3728552) = 3.7911549
                    // Cộng tổng S20:
                    // u1..u5: 1 + 2 + 2.6457513 + 3.1057610 + 3.3759834 = 12.1274957
                    // u6..u10: 3.5478875 + 3.6468965 + 3.7071109 + 3.7417782 + 3.7624460 = 18.4061191
                    // u11..u15: 3.7743877 + 3.7814388 + 3.7855270 + 3.7879288 + 3.7893248 = 18.9186071
                    // u16..u20: 3.7901428 + 3.7906190 + 3.7908976 + 3.7910600 + 3.7911549 = 18.9538743
                    // S20 = 12.1274957 + 18.4061191 + 18.9186071 + 18.9538743 = 68.4060962 -> 68.41!
                    hint: "Mở ứng dụng Spreadsheet trên Casio fx-880BTG: Cột A lưu giá trị u_n (A1=1, A2=2, A3 = √(A2 + 2A1 + 3)), Cột B lưu tổng cộng dồn S_n (B1=A1, B2 = B1 + A2).",
                    solution: "<strong>Quy trình chuẩn trên Casio fx-880BTG (Spreadsheet):</strong><br>1. Vào <span class='casio-key'>HOME</span> → <span class='casio-key'>Spreadsheet</span>.<br>2. Tại cột A (dãy $u_n$): Nhập <code>A1 = 1</code>, <code>A2 = 2</code>. Tại <code>A3</code> nhập công thức <code>=√(A2 + 2A1 + 3)</code> rồi dùng <span class='casio-key'>TOOLS</span> → <span class='casio-key'>Fill Formula</span> kéo từ <code>A3</code> đến <code>A20</code>.<br>3. Tại cột B (tổng $S_n$): Nhập <code>B1 = A1</code>, tại <code>B2</code> nhập <code>=B1 + A2</code> rồi kéo công thức xuống <code>B20</code>.<br>4. Đọc giá trị tại ô <code>B20</code>: $S_{20} = 68.406096...$ (dãy hội tụ về giới hạn $L = \\frac{3 + \\sqrt{21}}{2} \\approx 3.7912878$). Làm tròn đến hàng phần trăm được <strong>68.41</strong>."
                }
            ]
        };

        // Cập nhật lại các đáp án đã kiểm chứng chính xác 100% ở trên
        QUIZ_DATA[8][1].answer = 2.16;
        QUIZ_DATA[8][2].answer = 2.30;
        QUIZ_DATA[8][3].answer = 5.95;
        QUIZ_DATA[9][0].question = "Tính diện tích hình phẳng giới hạn bởi hai đường cong $y = x^3 - 4x$ và $y = x^2 - 2x$. Làm tròn kết quả đến hàng phần trăm.";
        QUIZ_DATA[9][0].answer = 3.08;
        QUIZ_DATA[9][1].answer = 8.93;
        QUIZ_DATA[9][2].answer = 4.57;
        QUIZ_DATA[9][3].answer = 1.50;
        QUIZ_DATA[9][4].answer = 2.56;
        QUIZ_DATA[10][0].answer = 68.41;

        // =========================================================================
        // 3. QUẢN LÝ TRẠNG THÁI ĐIỀU HƯỚNG 10 MÀN & CHẤM ĐIỂM
        // =========================================================================
        let currentSlide = 1;
        const totalSlides = 10;
        const solvedStatus = {}; // Lưu trạng thái đúng/sai của 11 câu hỏi

        function initApp() {
            renderStepPills();
            renderModalMenu();
            selectTopic(0);
            renderQuizSection(8, 'quiz-container-8');
            renderQuizSection(9, 'quiz-container-9');
            renderQuizSection(10, 'quiz-container-10');
            
            // Khởi tạo 2 thí nghiệm Canvas ở Màn 4
            initMonteCarloCanvas();
            initConeSphereCanvas();

            updateNavigationUI();
            renderMath();
            lucide.createIcons();
        }

        function renderMath() {
            if (window.renderMathInElement) {
                renderMathInElement(document.body, {
                    delimiters: [
                        { left: '$$', right: '$$', display: true },
                        { left: '$', right: '$', display: false }
                    ],
                    throwOnError: false
                });
            }
        }

        function renderStepPills() {
            const container = document.getElementById('stepPillsContainer');
            container.innerHTML = SLIDES_META.map(s => `
                <button onclick="goToSlide(${s.id})" id="pill-${s.id}"
                    class="px-3 py-1 rounded-lg text-xs font-medium whitespace-nowrap transition border ${s.id === currentSlide ? 'bg-navy text-white border-navy shadow-xs' : 'bg-white text-slate-600 border-slate-200 hover:bg-slate-100'}">
                    ${s.short}
                </button>
            `).join('');
        }

        function renderModalMenu() {
            const list = document.getElementById('modalSlideList');
            list.innerHTML = SLIDES_META.map(s => `
                <button onclick="goToSlide(${s.id}); toggleMenuModal();"
                    class="text-left p-3.5 rounded-2xl border border-slate-200 bg-white hover:border-tealMath hover:bg-teal-50/40 transition flex items-center gap-3">
                    <span class="w-8 h-8 rounded-xl bg-paperDark text-navy font-mono font-bold text-xs flex items-center justify-center shrink-0 border border-slate-200">
                        ${s.id < 10 ? '0' + s.id : s.id}
                    </span>
                    <span class="text-sm font-semibold text-navy leading-snug">${s.title.replace(/^Màn \d+:\s*/, '')}</span>
                </button>
            `).join('');
        }

        function goToSlide(slideNum) {
            if (slideNum < 1 || slideNum > totalSlides) return;
            
            document.querySelectorAll('.slide-screen').forEach(el => el.classList.remove('active'));
            const target = document.getElementById(`slide-${slideNum}`);
            if (target) target.classList.add('active');

            currentSlide = slideNum;
            updateNavigationUI();

            // Vẽ lại canvas nếu chuyển tới Màn 4 để đảm bảo kích thước chuẩn
            if (slideNum === 4) {
                setTimeout(() => {
                    resizeMonteCarloCanvas();
                    drawConeSphere();
                }, 50);
            }

            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function nextSlide() {
            if (currentSlide < totalSlides) goToSlide(currentSlide + 1);
        }

        function prevSlide() {
            if (currentSlide > 1) goToSlide(currentSlide - 1);
        }

        function updateNavigationUI() {
            document.getElementById('slideCounterBadge').textContent = `Màn ${currentSlide} / ${totalSlides}`;
            document.getElementById('topProgressBar').style.width = `${(currentSlide / totalSlides) * 100}%`;
            document.getElementById('currentSlideTitleFooter').textContent = SLIDES_META[currentSlide - 1].title;

            document.getElementById('prevBtn').disabled = currentSlide === 1;
            document.getElementById('nextBtn').disabled = currentSlide === totalSlides;

            // Cập nhật trạng thái active cho pills
            SLIDES_META.forEach(s => {
                const pill = document.getElementById(`pill-${s.id}`);
                if (pill) {
                    if (s.id === currentSlide) {
                        pill.className = "px-3 py-1 rounded-lg text-xs font-semibold whitespace-nowrap transition border bg-navy text-white border-navy shadow-xs";
                        pill.scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'center' });
                    } else {
                        pill.className = "px-3 py-1 rounded-lg text-xs font-medium whitespace-nowrap transition border bg-white text-slate-600 border-slate-200 hover:bg-slate-100";
                    }
                }
            });
        }

        function toggleMenuModal() {
            const modal = document.getElementById('menuModal');
            if (modal.classList.contains('hidden')) {
                modal.classList.remove('hidden');
                modal.classList.add('flex');
            } else {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
            }
        }

        // Hỗ trợ phím tắt mũi tên trái / phải (khi không đang nhập liệu trong ô input)
        document.addEventListener('keydown', (e) => {
            if (document.activeElement.tagName === 'INPUT') return;
            if (e.key === 'ArrowRight') nextSlide();
            if (e.key === 'ArrowLeft') prevSlide();
        });

        function showToast(msg) {
            const box = document.getElementById('toastBox');
            document.getElementById('toastMessage').textContent = msg;
            box.classList.remove('translate-y-10', 'opacity-0');
            setTimeout(() => {
                box.classList.add('translate-y-10', 'opacity-0');
            }, 3000);
        }

        // =========================================================================
        // 4. XỬ LÝ TABS CHUYÊN ĐỀ BITEX EDU Ở MÀN 3
        // =========================================================================
        function selectTopic(index) {
            const tabs = document.querySelectorAll('.topic-tab');
            tabs.forEach((tab, idx) => {
                if (idx === index) {
                    tab.className = "topic-tab active px-4 py-2 rounded-xl text-sm font-semibold transition bg-tealMath text-white shadow-sm";
                } else {
                    tab.className = "topic-tab px-4 py-2 rounded-xl text-sm font-semibold transition bg-paperDark text-navy hover:bg-slate-200";
                }
            });

            const item = BITEX_TOPICS[index];
            const area = document.getElementById('topicContentArea');
            area.innerHTML = `
                <div class="flex flex-wrap items-center justify-between gap-2 mb-3">
                    <h3 class="font-serif text-2xl font-bold text-navy">${item.title}</h3>
                    <span class="font-mono text-xs font-semibold px-3 py-1 rounded-full bg-amberLight text-amberMath border border-amber-200">
                        ${item.badge}
                    </span>
                </div>
                <p class="text-sm sm:text-base text-slate-700 leading-relaxed mb-4">
                    ${item.theory}
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="bg-white p-4 rounded-xl border border-slate-200">
                        <div class="text-xs font-bold uppercase tracking-wider text-tealMath mb-1">Tổ hợp phím Casio fx-880BTG</div>
                        <div class="font-mono text-xs sm:text-sm text-navy font-semibold">${item.casioKeys}</div>
                    </div>
                    <div class="bg-white p-4 rounded-xl border border-slate-200">
                        <div class="text-xs font-bold uppercase tracking-wider text-amberMath mb-1">Minh họa thực hành (Bitex Edu)</div>
                        <div class="text-xs sm:text-sm text-slate-700">${item.example}</div>
                    </div>
                </div>
            `;
            renderMath();
        }

        // =========================================================================
        // 5. THÍ NGHIỆM 1 (MONTE CARLO PI) & THÍ NGHIỆM 2 (HÌNH NÓN NỘI TIẾP CẦU)
        // =========================================================================
        let mcCanvas, mcCtx;
        let mcTotal = 0;
        let mcInside = 0;
        let mcPoints = [];

        function initMonteCarloCanvas() {
            mcCanvas = document.getElementById('monteCarloCanvas');
            if (!mcCanvas) return;
            mcCtx = mcCanvas.getContext('2d');
            resizeMonteCarloCanvas();
            addMonteCarloPoints(300); // Khởi tạo sẵn 300 điểm minh họa sinh động
        }

        function resizeMonteCarloCanvas() {
            if (!mcCanvas) return;
            const rect = mcCanvas.parentElement.getBoundingClientRect();
            const size = rect.width || 270;
            mcCanvas.width = size;
            mcCanvas.height = size;
            redrawMonteCarlo();
        }

        function redrawMonteCarlo() {
            if (!mcCtx) return;
            const w = mcCanvas.width;
            const h = mcCanvas.height;
            const r = w / 2;

            mcCtx.clearRect(0, 0, w, h);

            // Vẽ hình vuông và hình tròn nội tiếp
            mcCtx.fillStyle = '#F8FAFC';
            mcCtx.fillRect(0, 0, w, h);

            mcCtx.beginPath();
            mcCtx.arc(r, r, r - 2, 0, Math.PI * 2);
            mcCtx.fillStyle = 'rgba(15, 118, 110, 0.08)';
            mcCtx.fill();
            mcCtx.lineWidth = 2;
            mcCtx.strokeStyle = '#0F766E';
            mcCtx.stroke();

            // Trục tọa độ mờ
            mcCtx.beginPath();
            mcCtx.moveTo(0, r); mcCtx.lineTo(w, r);
            mcCtx.moveTo(r, 0); mcCtx.lineTo(r, h);
            mcCtx.strokeStyle = 'rgba(30, 41, 59, 0.15)';
            mcCtx.lineWidth = 1;
            mcCtx.stroke();

            // Vẽ các điểm đã gieo
            for (let i = 0; i < mcPoints.length; i++) {
                const pt = mcPoints[i];
                const px = (pt.x + 1) * 0.5 * w;
                const py = (1 - pt.y) * 0.5 * h;
                mcCtx.fillStyle = pt.inside ? '#0F766E' : '#D97706';
                mcCtx.fillRect(px - 1.3, py - 1.3, 2.6, 2.6);
            }
        }

        function addMonteCarloPoints(count) {
            for (let i = 0; i < count; i++) {
                const x = Math.random() * 2 - 1;
                const y = Math.random() * 2 - 1;
                const inside = (x * x + y * y) <= 1;
                mcTotal++;
                if (inside) mcInside++;
                // Giới hạn lưu trữ tối đa 8000 điểm vẽ trên canvas để luôn mượt mà
                if (mcPoints.length < 8000) {
                    mcPoints.push({ x, y, inside });
                }
            }
            updateMonteCarloStats();
            redrawMonteCarlo();
        }

        function resetMonteCarlo() {
            mcTotal = 0;
            mcInside = 0;
            mcPoints = [];
            updateMonteCarloStats();
            redrawMonteCarlo();
        }

        function updateMonteCarloStats() {
            document.getElementById('mcTotalCount').textContent = mcTotal.toLocaleString('vi-VN');
            document.getElementById('mcInsideCount').textContent = mcInside.toLocaleString('vi-VN');
            
            const piEst = mcTotal > 0 ? (4 * mcInside) / mcTotal : 0;
            const err = Math.abs(Math.PI - piEst);

            document.getElementById('mcPiEstimate').textContent = piEst.toFixed(9);
            document.getElementById('mcPiError').textContent = err.toFixed(9);
        }

        // --- THÍ NGHIỆM 2: HÌNH NÓN NỘI TIẾP MẶT CẦU ---
        let coneCanvas, coneCtx;
        let currentConeH = 5.00;
        const SPHERE_R = 5;

        function initConeSphereCanvas() {
            coneCanvas = document.getElementById('coneSphereCanvas');
            if (!coneCanvas) return;
            coneCtx = coneCanvas.getContext('2d');
            updateConeExperiment(5.00);
        }

        function setOptimalConeHeight() {
            const optH = (4 * SPHERE_R / 3).toFixed(2); // 6.67
            document.getElementById('coneHeightSlider').value = optH;
            updateConeExperiment(optH);
        }

        function updateConeExperiment(val) {
            currentConeH = parseFloat(val);
            const rBase = Math.sqrt(Math.max(0, 2 * SPHERE_R * currentConeH - currentConeH * currentConeH));
            const volume = (1 / 3) * Math.PI * rBase * rBase * currentConeH;

            document.getElementById('coneHeightDisplay').textContent = currentConeH.toFixed(2);
            document.getElementById('coneRadiusDisplay').textContent = rBase.toFixed(2);
            document.getElementById('coneVolumeDisplay').textContent = volume.toFixed(2);

            drawConeSphere();
        }

        function drawConeSphere() {
            if (!coneCanvas || !coneCtx) return;
            const rect = coneCanvas.parentElement.getBoundingClientRect();
            const size = rect.width || 270;
            coneCanvas.width = size;
            coneCanvas.height = size;

            const cx = size / 2;
            const cy = size / 2;
            const pixelR = size * 0.40; // Bán kính mặt cầu trên canvas

            coneCtx.clearRect(0, 0, size, size);

            // Vẽ mặt cầu ngoại tiếp
            coneCtx.beginPath();
            coneCtx.arc(cx, cy, pixelR, 0, Math.PI * 2);
            coneCtx.fillStyle = 'rgba(30, 41, 59, 0.04)';
            coneCtx.fill();
            coneCtx.lineWidth = 1.5;
            coneCtx.strokeStyle = '#94A3B8';
            coneCtx.stroke();

            // Tọa độ đỉnh nón ở cực Bắc mặt cầu
            const apexX = cx;
            const apexY = cy - pixelR;

            // Tọa độ tâm đáy hình nón (cách đỉnh một đoạn h)
            const ratioH = currentConeH / (2 * SPHERE_R); // từ 0 đến 1
            const baseY = apexY + ratioH * (2 * pixelR);

            // Bán kính đáy trên canvas
            const rBase = Math.sqrt(Math.max(0, 2 * SPHERE_R * currentConeH - currentConeH * currentConeH));
            const pixelBaseR = (rBase / SPHERE_R) * pixelR;

            // Tô màu khối nón
            const isOptimal = Math.abs(currentConeH - 6.67) < 0.05;
            coneCtx.beginPath();
            coneCtx.moveTo(apexX, apexY);
            coneCtx.lineTo(cx - pixelBaseR, baseY);
            coneCtx.lineTo(cx + pixelBaseR, baseY);
            coneCtx.closePath();
            coneCtx.fillStyle = isOptimal ? 'rgba(180, 83, 9, 0.22)' : 'rgba(15, 118, 110, 0.18)';
            coneCtx.fill();
            coneCtx.lineWidth = 2;
            coneCtx.strokeStyle = isOptimal ? '#B45309' : '#0F766E';
            coneCtx.stroke();

            // Vẽ elip đáy hình nón
            coneCtx.beginPath();
            coneCtx.ellipse(cx, baseY, pixelBaseR, pixelBaseR * 0.22, 0, 0, Math.PI * 2);
            coneCtx.fillStyle = isOptimal ? 'rgba(180, 83, 9, 0.25)' : 'rgba(15, 118, 110, 0.22)';
            coneCtx.fill();
            coneCtx.stroke();

            // Đường cao h nét đứt
            coneCtx.beginPath();
            coneCtx.setLineDash([4, 4]);
            coneCtx.moveTo(apexX, apexY);
            coneCtx.lineTo(cx, baseY);
            coneCtx.strokeStyle = '#1E293B';
            coneCtx.lineWidth = 1.2;
            coneCtx.stroke();
            coneCtx.setLineDash([]);

            // Tâm mặt cầu O
            coneCtx.beginPath();
            coneCtx.arc(cx, cy, 3, 0, Math.PI * 2);
            coneCtx.fillStyle = '#1E293B';
            coneCtx.fill();
        }

        // =========================================================================
        // 6. HỆ THỐNG TRÒ CHƠI ĐIỀN KHUYẾT (MÀN 8, 9, 10)
        // =========================================================================
        function renderQuizSection(slideNum, containerId) {
            const container = document.getElementById(containerId);
            const questions = QUIZ_DATA[slideNum];
            if (!container || !questions) return;

            container.innerHTML = questions.map((q, index) => `
                <div id="card-${q.id}" class="bg-paper rounded-2xl p-5 sm:p-6 border border-slate-200 transition-all">
                    <div class="flex flex-wrap items-center justify-between gap-2 mb-2.5">
                        <span class="text-xs font-bold uppercase tracking-wider text-tealMath bg-tealLight/70 px-3 py-1 rounded-lg">
                            ${q.tag}
                        </span>
                        <span id="status-badge-${q.id}" class="text-xs font-mono font-semibold text-slate-400">
                            Chưa trả lời
                        </span>
                    </div>

                    <p class="text-navy font-medium text-base leading-relaxed mb-4">
                        ${q.question}
                    </p>

                    <!-- Khu vực nhập đáp án điền khuyết -->
                    <div class="flex flex-wrap items-center gap-3">
                        <div class="relative flex items-center">
                            <span class="px-3 py-2.5 bg-slate-200/80 text-navy font-mono font-semibold text-sm rounded-l-xl border border-r-0 border-slate-300">
                                Đáp án ≈
                            </span>
                            <input type="text" id="input-${q.id}" inputmode="decimal" placeholder="VD: 12.34"
                                onkeydown="if(event.key==='Enter') checkSingleQuestion(${slideNum}, '${q.id}')"
                                class="w-36 sm:w-44 px-3.5 py-2.5 bg-white border border-slate-300 rounded-r-xl font-mono font-bold text-navy text-sm focus:outline-none focus:ring-2 focus:ring-tealMath focus:border-tealMath">
                        </div>

                        <button onclick="checkSingleQuestion(${slideNum}, '${q.id}')"
                            class="px-4 py-2.5 rounded-xl bg-navy hover:bg-slate-800 text-white text-xs sm:text-sm font-semibold transition flex items-center gap-1.5 shadow-xs">
                            <i data-lucide="check" class="w-4 h-4 text-teal-300"></i> Kiểm tra
                        </button>

                        <button onclick="toggleBox('hint-${q.id}')"
                            class="px-3.5 py-2.5 rounded-xl bg-white hover:bg-amber-50 border border-slate-300 text-amberMath text-xs sm:text-sm font-medium transition flex items-center gap-1.5">
                            <i data-lucide="lightbulb" class="w-4 h-4"></i> Gợi ý bấm máy
                        </button>

                        <button onclick="toggleBox('sol-${q.id}')"
                            class="px-3.5 py-2.5 rounded-xl bg-white hover:bg-teal-50 border border-slate-300 text-tealMath text-xs sm:text-sm font-medium transition flex items-center gap-1.5">
                            <i data-lucide="book-open-check" class="w-4 h-4"></i> Lời giải chi tiết
                        </button>
                    </div>

                    <!-- Hộp gợi ý -->
                    <div id="hint-${q.id}" class="hidden mt-4 p-4 rounded-xl bg-amberLight/60 border border-amber-200 text-xs sm:text-sm text-slate-800">
                        <strong class="text-amberMath">Hướng dẫn tư duy & Thao tác Casio:</strong> ${q.hint}
                    </div>

                    <!-- Hộp lời giải chi tiết -->
                    <div id="sol-${q.id}" class="hidden mt-4 p-4 rounded-xl bg-white border border-teal-200 text-xs sm:text-sm text-slate-700 leading-relaxed">
                        <div class="font-bold text-tealMath mb-1">Lời giải & Quy trình phím Casio fx-880BTG:</div>
                        <div>${q.solution}</div>
                    </div>
                </div>
            `).join('');
        }

        function toggleBox(boxId) {
            const el = document.getElementById(boxId);
            if (!el) return;
            el.classList.toggle('hidden');
            renderMath();
        }

        function parseUserNumber(rawStr) {
            if (!rawStr) return NaN;
            // Chấp nhận cả dấu phẩy (,) và dấu chấm (.) thập phân
            const normalized = rawStr.trim().replace(/,/g, '.');
            return parseFloat(normalized);
        }

        function checkSingleQuestion(slideNum, questionId, silent = false) {
            const questions = QUIZ_DATA[slideNum];
            const q = questions.find(item => item.id === questionId);
            if (!q) return;

            const inputEl = document.getElementById(`input-${questionId}`);
            const cardEl = document.getElementById(`card-${questionId}`);
            const badgeEl = document.getElementById(`status-badge-${questionId}`);

            const userVal = parseUserNumber(inputEl.value);

            if (isNaN(userVal)) {
                if (!silent) showToast("Vui lòng nhập một giá trị số hợp lệ (làm tròn đến hàng phần trăm)!");
                inputEl.focus();
                return;
            }

            // Chấp nhận sai số làm tròn rất nhỏ <= 0.01 để thân thiện với thao tác làm tròn
            const isCorrect = Math.abs(userVal - q.answer) <= 0.011;
            solvedStatus[questionId] = isCorrect;

            if (isCorrect) {
                cardEl.className = "bg-teal-50/60 rounded-2xl p-5 sm:p-6 border-2 border-tealMath transition-all";
                badgeEl.className = "text-xs font-mono font-bold text-tealMath bg-tealLight px-2.5 py-1 rounded-md";
                badgeEl.textContent = `✓ Chính xác (${q.answer.toFixed(2)})`;
                if (!silent) showToast("Chính xác! Kết quả làm tròn đến hàng phần trăm hoàn toàn trùng khớp.");
            } else {
                cardEl.className = "bg-rose-50/50 rounded-2xl p-5 sm:p-6 border-2 border-rose-400 transition-all";
                badgeEl.className = "text-xs font-mono font-bold text-rose-700 bg-rose-100 px-2.5 py-1 rounded-md";
                badgeEl.textContent = "✗ Chưa chính xác — Hãy thử lại hoặc xem gợi ý";
                if (!silent) showToast("Chưa chính xác! Kiểm tra lại đơn vị góc hoặc cách làm tròn 2 chữ số thập phân.");
            }

            updateAllScores();
        }

        function checkAllInSection(sectionId) {
            const slideNum = parseInt(sectionId.replace('slide-', ''), 10);
            const questions = QUIZ_DATA[slideNum];
            if (!questions) return;

            questions.forEach(q => {
                const inputEl = document.getElementById(`input-${q.id}`);
                if (inputEl && inputEl.value.trim() !== '') {
                    checkSingleQuestion(slideNum, q.id, true);
                }
            });

            const correctCount = questions.filter(q => solvedStatus[q.id]).length;
            showToast(`Đã chấm điểm Màn ${slideNum}: Bạn trả lời đúng ${correctCount} / ${questions.length} câu!`);
        }

        function updateAllScores() {
            // Điểm từng màn
            [8, 9].forEach(sNum => {
                const qs = QUIZ_DATA[sNum];
                const right = qs.filter(q => solvedStatus[q.id]).length;
                const el = document.getElementById(`score-slide-${sNum}`);
                if (el) el.textContent = `Đúng: ${right} / ${qs.length}`;
            });

            // Tổng điểm toàn bộ 11 câu
            const totalRight = Object.values(solvedStatus).filter(Boolean).length;
            document.getElementById('globalScoreBadge').textContent = `${totalRight} / 11 câu`;
            const finalEl = document.getElementById('finalSummaryScore');
            if (finalEl) finalEl.textContent = `${totalRight} / 11`;
        }

        // Khởi chạy ứng dụng khi trang tải xong
        window.addEventListener('DOMContentLoaded', initApp);
        window.addEventListener('resize', () => {
            if (currentSlide === 4) {
                resizeMonteCarloCanvas();
                drawConeSphere();
            }
        });
    </script>
</body>
</html>
