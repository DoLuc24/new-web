<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Thần Thám Pháp Sư - Tiểu Thuyết Linh Dị</title>
    <!-- Sử dụng thư viện Tailwind CSS để giao diện đẹp và hiện đại nhanh chóng -->
    <script src="https://tailwindcss.com"></script>
    <script>
        // Cấu hình Tailwind hỗ trợ chế độ Dark Mode bằng class
        tailwind.config = { darkMode: 'class' }
    </script>
    <style>
        /* Tối ưu trải nghiệm đọc chữ mượt mà */
        .story-content { font-family: 'Segoe UI', Georgia, serif; line-height: 2; }
    </style>
</head>
<body class="bg-amber-50 text-stone-900 dark:bg-zinc-900 dark:text-zinc-100 transition-colors duration-200">

    <!-- THANH MENU TRÊN CÙNG -->
    <header class="sticky top-0 bg-white/90 dark:bg-zinc-800/90 backdrop-blur border-b border-stone-200 dark:border-zinc-700 z-50">
        <div class="max-w-3xl mx-auto px-4 py-3 flex items-center justify-between">
            <a href="#" class="font-bold text-lg text-amber-700 dark:text-amber-500 tracking-wide">PHÁP SƯ TRUYỆN</a>
            
            <!-- Bộ công cụ chỉnh cỡ chữ và bật tắt Dark Mode -->
            <div class="flex items-center space-x-4">
                <button onclick="changeFontSize(-2)" class="px-2 py-1 bg-stone-200 dark:bg-zinc-700 rounded text-sm font-bold">- A</button>
                <button onclick="changeFontSize(2)" class="px-2 py-1 bg-stone-200 dark:bg-zinc-700 rounded text-sm font-bold">+ A</button>
                <button onclick="toggleDarkMode()" id="darkModeBtn" class="p-2 bg-stone-200 dark:bg-zinc-700 rounded-full text-base">🌙</button>
            </div>
        </div>
    </header>

    <!-- NỘI DUNG CHÍNH CỦA TRUYỆN -->
    <main class="max-w-2xl mx-auto px-4 py-8">
        
        <!-- Thông tin chương -->
        <div class="text-center mb-8">
            <h1 class="text-sm font-semibold text-amber-600 dark:text-amber-400 uppercase tracking-widest mb-2">Chương 1</h1>
            <h2 class="text-2xl md:text-3xl font-bold text-stone-800 dark:text-zinc-100">Bùa Lỗ Ban Trong Cột Nhà Hoang</h2>
            <div class="mt-4 text-xs text-stone-500 dark:text-zinc-400">Tác giả: Chém Gió Đại Sư | Lượt đọc: 9,999</div>
        </div>

        <!-- Chọn chương nhanh -->
        <div class="mb-6 flex justify-center">
            <select onchange="changeChapter(this.value)" class="bg-white dark:bg-zinc-800 border border-stone-300 dark:border-zinc-600 rounded px-3 py-1.5 text-sm focus:outline-none">
                <option value="1" selected>Chương 1: Bùa Lỗ Ban Trong Cột Nhà Hoang</option>
                <option value="2">Chương 2: Long Mạch Đứt Đoạn Tại Thôn Khốn Cùng (VIP)</option>
                <option value="3">Chương 3: Huyết Chiến Mãnh Hổ Tinh (VIP)</option>
            </select>
        </div>

        <!-- Đoạn văn xuôi của truyện -->
        <div id="storyBody" class="story-content text-lg space-y-6 text-justify">
            <p>Đêm muộn, sương muối phủ dày đặc lên những rặng tre già đầu thôn. Tiếng gió rít qua kẽ lá nghe tựa như tiếng khóc than ai oán của một vong hồn khuất tất.</p>
            <p>Hắn đứng im lặng trước ngôi biệt thự bỏ hoang, tay trái cầm chiếc la bàn cổ, ngón tay phải bấm nhanh như chớp trên các đốt ngón túc. Sắc mặt hắn bỗng chốc trở nên nghiêm trọng, chân mày nhíu chặt lại.</p>
            <p>“Càn khôn điên đảo, âm dương hỗn loạn... Quẻ này thuộc Khảm thủy hung hiểm cực độ, đây rõ ràng là một Tuyệt Địa nuôi thây!” - Hắn lẩm bẩm.</p>
            <p>Tiến sâu vào trong gian nhà chính, ánh đèn pin le lói quét qua thanh xà ngang bằng gỗ mun cũ kỹ. Hắn rút từ trong túi áo ra cây thước Lỗ Ban, áp sát vào cốt gỗ rồi biến sắc gằn giọng: "Nguy rồi! Thanh xà này rơi đúng vào cung Tử Tuyệt. Tên thợ mộc làm ngôi nhà này đã yểm một giọt máu oán hận vào mộng gỗ, thảo nào ba đời nhà gia chủ đều nhìn thấy ma khóc ban đêm!"</p>
        </div>

        <!-- KHU VỰC KHÓA CHƯƠNG VIP (Mặc định ẩn, sẽ hiện khi sang chương 2) -->
        <div id="vipLock" class="hidden mt-8 p-6 bg-amber-100 dark:bg-zinc-800 border-2 border-dashed border-amber-500 rounded-lg text-center">
            <span class="text-3xl">🔒</span>
            <h3 class="text-xl font-bold text-amber-800 dark:text-amber-400 mt-2">Chương này thuộc nội dung VIP</h3>
            <p class="text-sm text-stone-600 dark:text-zinc-300 mt-1">Vui lòng ủng hộ tác giả 2,000đ để mở khóa đọc tiếp phân cảnh đấu pháp gay cấn.</p>
            <div class="mt-4 inline-block bg-white dark:bg-zinc-900 p-4 rounded shadow-sm">
                <p class="text-xs text-left font-semibold text-stone-500">THÔNG TIN CHUYỂN KHOẢN:</p>
                <p class="text-sm text-left mt-1">🏦 Ngân hàng: <b>Vietcombank</b></p>
                <p class="text-sm text-left">💳 Số tài khoản: <b>1234567890</b></p>
                <p class="text-sm text-left">✏️ Nội dung: <b>Mở khóa truyện [Tên của bạn]</b></p>
            </div>
            <p class="text-xs text-stone-400 mt-3 italic">*Hệ thống tự động mở chương sau 1-3 phút khi nhận được tiền.</p>
        </div>

        <!-- THANH ĐIỀU HƯỚNG CHƯƠNG TRƯỚC / SAU -->
        <div class="mt-12 pt-6 border-t border-stone-200 dark:border-zinc-700 flex justify-between">
            <button onclick="prevChapter()" class="px-4 py-2 bg-stone-200 dark:bg-zinc-700 rounded-lg hover:bg-stone-300 text-sm font-semibold transition">⏮️ Chương trước</button>
            <button onclick="nextChapter()" class="px-4 py-2 bg-amber-600 text-white rounded-lg hover:bg-amber-700 text-sm font-semibold transition">Chương sau ⏭️</button>
        </div>

    </main>

    <!-- FOOTER -->
    <footer class="bg-stone-100 dark:bg-zinc-900 text-center py-6 text-xs text-stone-500 border-t border-stone-200 dark:border-zinc-800 mt-20">
        © 2026 Bản quyền thuộc về Pháp Sư Truyện. Thiết kế bảo mật, chống sao chép nội dung.
    </footer>

    <!-- ĐOẠN JAVASCRIPT XỬ LÝ CHỨC NĂNG -->
    <script>
        let currentSize = 18; // Kích thước chữ mặc định (18px)
        let currentChap = 1;

        // 1. Chức năng đổi kích thước chữ lớn/nhỏ
        function changeFontSize(delta) {
            currentSize += delta;
            if(currentSize < 14) currentSize = 14; // Không cho chữ nhỏ quá
            if(currentSize > 28) currentSize = 28; // Không cho chữ to quá
            document.getElementById('storyBody').style.fontSize = currentSize + 'px';
        }

        // 2. Chức năng Bật/Tắt chế độ ban đêm (Dark Mode)
        function toggleDarkMode() {
            const html = document.documentElement;
            const btn = document.getElementById('darkModeBtn');
            if (html.classList.contains('dark')) {
                html.classList.remove('dark');
                btn.innerHTML = '🌙';
            } else {
                html.classList.add('dark');
                btn.innerHTML = '☀️';
            }
        }

        // 3. Chức năng Chuyển chương & Giả lập khóa VIP
        function changeChapter(chapNum) {
            currentChap = parseInt(chapNum);
            const storyBody = document.getElementById('storyBody');
            const vipLock = document.getElementById('vipLock');

            if (currentChap === 1) {
                // Hiện nội dung chương 1 công khai
                storyBody.classList.remove('hidden');
                vipLock.classList.add('hidden');
                window.scrollTo({ top: 0, behavior: 'smooth' });
            } else {
                // Nếu sang chương 2 hoặc 3: Ẩn nội dung chữ, Hiện hộp khóa bắt nạp tiền VIP
                storyBody.classList.add('hidden');
                vipLock.classList.remove('hidden');
            }
        }

        function nextChapter() {
            if(currentChap < 3) {
                currentChap++;
                document.querySelector('select').value = currentChap;
                changeChapter(currentChap);
            } else {
                alert('Bạn đang ở chương mới nhất!');
            }
        }

        function prevChapter() {
            if(currentChap > 1) {
                currentChap--;
                document.querySelector('select').value = currentChap;
                changeChapter(currentChap);
            } else {
                alert('Đây là chương đầu tiên!');
            }
        }
    </script>
</body>
</html>
