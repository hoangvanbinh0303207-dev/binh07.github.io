<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sơ Đồ Lớp Học - Luxury Edition</title>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-base: #0b0f19;
            --glass-bg: rgba(30, 41, 59, 0.7);
            --glass-border: rgba(255, 255, 255, 0.08);
            --accent-glow: linear-gradient(135deg, #6366f1 0%, #a855f7 100%);
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: var(--bg-base);
            color: var(--text-main);
            min-height: 100vh;
            padding: 30px 20px;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(99, 102, 241, 0.15) 0%, transparent 40%),
                radial-gradient(circle at 90% 80%, rgba(168, 85, 247, 0.15) 0%, transparent 40%);
            background-attachment: fixed;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        /* Header Style */
        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--glass-bg);
            backdrop-filter: blur(16px);
            border: 1px solid var(--glass-border);
            padding: 20px 30px;
            border-radius: 20px;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .header h1 {
            font-size: 24px;
            font-weight: 700;
            background: linear-gradient(to right, #818cf8, #c084fc);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .header-tools {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .search-box {
            background: rgba(15, 23, 42, 0.6);
            border: 1px solid var(--glass-border);
            padding: 10px 16px;
            border-radius: 12px;
            color: white;
            font-family: inherit;
            font-size: 14px;
            width: 250px;
            outline: none;
            transition: all 0.3s ease;
        }

        .search-box:focus {
            border-color: #818cf8;
            box-shadow: 0 0 15px rgba(129, 140, 248, 0.2);
        }

        .status-badge {
            background: rgba(16, 185, 129, 0.15);
            color: #34d399;
            border: 1px solid rgba(52, 211, 153, 0.3);
            padding: 8px 14px;
            border-radius: 10px;
            font-size: 13px;
            font-weight: 600;
        }

        /* Podium / Blackboard */
        .blackboard {
            background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
            border: 1px solid var(--glass-border);
            text-align: center;
            padding: 18px;
            border-radius: 16px;
            font-weight: 600;
            font-size: 15px;
            letter-spacing: 3px;
            margin-bottom: 35px;
            color: #cbd5e1;
            box-shadow: 0 10px 25px rgba(0,0,0,0.4);
            text-transform: uppercase;
        }

        /* Classroom Grid Layout */
        .classroom-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }

        .column-wrapper {
            background: rgba(15, 23, 42, 0.4);
            border: 1px solid var(--glass-border);
            border-radius: 20px;
            padding: 20px;
            backdrop-filter: blur(10px);
        }

        .column-header {
            text-align: center;
            font-size: 14px;
            font-weight: 700;
            color: #818cf8;
            padding: 12px;
            margin-bottom: 20px;
            background: rgba(99, 102, 241, 0.1);
            border-radius: 12px;
            border: 1px solid rgba(99, 102, 241, 0.2);
            letter-spacing: 1px;
        }

        .desk-card {
            background: var(--glass-bg);
            border: 1px solid var(--glass-border);
            border-radius: 14px;
            padding: 14px;
            margin-bottom: 16px;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .desk-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
            border-color: rgba(255,255,255,0.15);
        }

        .desk-title {
            font-size: 12px;
            color: var(--text-muted);
            font-weight: 600;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
        }

        .seats-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        /* Student Seat */
        .seat {
            background: rgba(15, 23, 42, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            padding: 8px 6px;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s ease;
            position: relative;
        }

        .seat:hover {
            background: rgba(99, 102, 241, 0.15);
            border-color: rgba(129, 140, 248, 0.4);
            transform: scale(1.03);
        }

        .seat.empty {
            border-style: dashed;
            opacity: 0.6;
        }

        .avatar-container {
            position: relative;
            width: 46px;
            height: 46px;
            margin: 0 auto 6px;
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 2px solid rgba(255, 255, 255, 0.1);
            transition: transform 0.2s;
        }

        .avatar:hover {
            transform: scale(1.08);
            border-color: #818cf8;
        }

        .student-name {
            font-size: 11px;
            font-weight: 500;
            color: #e2e8f0;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        /* Modals Glassmorphism */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(5, 7, 12, 0.8);
            backdrop-filter: blur(12px);
            justify-content: center;
            align-items: center;
            z-index: 1000;
            padding: 20px;
        }

        .modal-content {
            background: #111827;
            border: 1px solid rgba(255, 255, 255, 0.12);
            padding: 30px;
            border-radius: 24px;
            width: 420px;
            box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.7);
            text-align: center;
            animation: modalIn 0.3s cubic-bezier(0.16, 1, 0.3, 1);
        }

        @keyframes modalIn {
            from { transform: scale(0.95); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .modal-avatar-preview {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            object-fit: cover;
            margin: 0 auto 20px;
            border: 3px solid #818cf8;
            box-shadow: 0 0 20px rgba(129, 140, 248, 0.4);
            cursor: pointer;
        }

        .form-group {
            margin-bottom: 18px;
            text-align: left;
        }

        .form-group label {
            display: block;
            font-size: 12px;
            font-weight: 600;
            margin-bottom: 6px;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 10px 14px;
            background: rgba(30, 41, 59, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            color: white;
            font-family: inherit;
            font-size: 14px;
            outline: none;
            transition: all 0.2s;
        }

        .form-group input:focus, .form-group select:focus {
            border-color: #818cf8;
            box-shadow: 0 0 10px rgba(129, 140, 248, 0.2);
        }

        .modal-actions {
            display: flex;
            gap: 10px;
            margin-top: 25px;
        }

        .btn {
            flex: 1;
            padding: 10px 16px;
            border-radius: 10px;
            border: none;
            font-family: inherit;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
        }

        .btn-primary {
            background: var(--accent-glow);
            color: white;
            box-shadow: 0 4px 15px rgba(99, 102, 241, 0.4);
        }

        .btn-primary:hover {
            opacity: 0.9;
            transform: translateY(-1px);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.08);
            color: #cbd5e1;
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.12);
        }

        .btn-danger {
            background: rgba(239, 68, 68, 0.15);
            color: #f87171;
            border: 1px solid rgba(239, 68, 68, 0.3);
            margin-bottom: 15px;
            width: 100%;
        }

        .btn-danger:hover {
            background: rgba(239, 68, 68, 0.25);
        }

        /* Lightbox Fullscreen Image Viewer */
        .lightbox {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(3, 7, 18, 0.92);
            backdrop-filter: blur(16px);
            justify-content: center;
            align-items: center;
            z-index: 2000;
            flex-direction: column;
            cursor: zoom-out;
        }

        .lightbox img {
            max-width: 85vw;
            max-height: 75vh;
            border-radius: 16px;
            border: 2px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 25px 60px rgba(0,0,0,0.8);
            object-fit: contain;
        }

        .lightbox-caption {
            margin-top: 20px;
            font-size: 18px;
            font-weight: 600;
            color: #f8fafc;
            letter-spacing: 0.5px;
        }

        /* Responsive */
        @media(max-width: 900px) {
            .classroom-grid {
                grid-template-columns: 1fr;
            }
            .header {
                flex-direction: column;
                gap: 15px;
                align-items: stretch;
            }
            .search-box {
                width: 100%;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>✨ Sơ Đồ Lớp Học Luxury</h1>
            <div class="header-tools">
                <input type="text" id="searchInput" class="search-box" placeholder="🔍 Tìm kiếm học sinh..." oninput="handleSearch()">
                <div class="status-badge">⚡ Đã lưu tự động</div>
            </div>
        </div>

        <!-- Blackboard -->
        <div class="blackboard">
            🎓 Bảng Đen / Bục Giảng Giáo Viên
        </div>

        <!-- Classroom Layout -->
        <div class="classroom-grid">
            <div class="column-wrapper">
                <div class="column-header">DÃY BÊN TRÁI</div>
                <div id="leftColumn"></div>
            </div>
            <div class="column-wrapper">
                <div class="column-header">DÃY BÊN PHẢI</div>
                <div id="rightColumn"></div>
            </div>
        </div>
    </div>

    <!-- Edit Modal -->
    <div class="modal" id="editModal">
        <div class="modal-content">
            <h3 style="margin-bottom: 15px; font-weight: 700;">Tùy Chỉnh Chỗ Ngồi</h3>
            <img id="modalAvatarPreview" class="modal-avatar-preview" src="" alt="Avatar" title="Nhấp để xem ảnh lớn" onclick="openLightboxFromModal()">
            
            <button class="btn btn-danger" onclick="clearSeat()">🗑️ Xóa học sinh (Để trống ghế)</button>

            <div class="form-group">
                <label>Họ và tên học sinh</label>
                <input type="text" id="modalNameInput" placeholder="Nhập tên học sinh...">
            </div>

            <div class="form-group">
                <label>Liên kết ảnh đại diện (URL)</label>
                <input type="text" id="modalAvatarUrl" placeholder="Dán link ảnh https://..." oninput="updatePreviewFromUrl()">
            </div>

            <div class="form-group">
                <label>Hoặc tải ảnh từ máy tính</label>
                <input type="file" id="modalAvatarFile" accept="image/*" onchange="previewFileAvatar(event)">
            </div>

            <div class="form-group">
                <label>Hoán đổi chỗ ngồi với</label>
                <select id="modalSwapSelect">
                    <option value="">-- Chọn học sinh để đổi chỗ --</option>
                </select>
            </div>

            <div class="modal-actions">
                <button class="btn btn-secondary" onclick="closeModal()">Hủy</button>
                <button class="btn btn-primary" onclick="saveChanges()">Lưu thay đổi</button>
            </div>
        </div>
    </div>

    <!-- Lightbox Fullscreen Viewer -->
    <div class="lightbox" id="lightbox" onclick="closeLightbox()">
        <img id="lightboxImg" src="" alt="Full Avatar">
        <div class="lightbox-caption" id="lightboxCaption"></div>
    </div>

    <script>
        const TOTAL_DESKS = 20;
        const SEATS_PER_DESK = 4;
        const TOTAL_STUDENTS = TOTAL_DESKS * SEATS_PER_DESK;

        // Load từ localStorage hoặc tạo dữ liệu mẫu
        let studentsData = JSON.parse(localStorage.getItem('luxury_classroom_data')) || Array.from({ length: TOTAL_STUDENTS }, (_, i) => ({
            id: i + 1,
            name: `Học sinh ${i + 1}`,
            avatar: `https://i.pravatar.cc/150?img=${(i % 70) + 1}`
        }));

        let currentEditingId = null;
        let searchQuery = '';

        function saveToLocalStorage() {
            localStorage.setItem('luxury_classroom_data', JSON.stringify(studentsData));
        }

        function renderClassroom() {
            const leftCol = document.getElementById('leftColumn');
            const rightCol = document.getElementById('rightColumn');
            
            leftCol.innerHTML = '';
            rightCol.innerHTML = '';

            for (let i = 0; i < TOTAL_DESKS; i++) {
                const deskNum = i + 1;
                const deskCard = document.createElement('div');
                deskCard.className = 'desk-card';

                let seatsHTML = '';
                for (let j = 0; j < SEATS_PER_DESK; j++) {
                    const studentIndex = i * SEATS_PER_DESK + j;
                    const student = studentsData[studentIndex];
                    
                    const isEmpty = !student.name || student.name.trim() === '';
                    const displayName = isEmpty ? 'Ghế trống' : student.name;
                    const displayAvatar = isEmpty ? 'https://via.placeholder.com/150?text=Empty' : student.avatar;
                    
                    // Kiểm tra bộ lọc tìm kiếm
                    const matchesSearch = searchQuery === '' || displayName.toLowerCase().includes(searchQuery.toLowerCase());
                    const opacityStyle = matchesSearch ? 'opacity: 1;' : 'opacity: 0.25;';

                    seatsHTML += `
                        <div class="seat ${isEmpty ? 'empty' : ''}" style="${opacityStyle}" onclick="openModal(${student.id})">
                            <div class="avatar-container">
                                <img class="avatar" src="${displayAvatar}" alt="Avatar" 
                                     onclick="event.stopPropagation(); openLightbox('${displayAvatar}', '${displayName} - Ghế ${student.id}')"
                                     onerror="this.src='https://via.placeholder.com/150'">
                            </div>
                            <div class="student-name" title="${displayName}">${displayName}</div>
                        </div>
                    `;
                }

                deskCard.innerHTML = `
                    <div class="desk-title">
                        <span>BÀN DÀI ${deskNum}</span>
                        <span>4 chỗ</span>
                    </div>
                    <div class="seats-grid">${seatsHTML}</div>
                `;

                if (i < 10) {
                    leftCol.appendChild(deskCard);
                } else {
                    rightCol.appendChild(deskCard);
                }
            }
        }

        function handleSearch() {
            searchQuery = document.getElementById('searchInput').value.trim();
            renderClassroom();
        }

        function openModal(id) {
            currentEditingId = id;
            const student = studentsData.find(s => s.id === id);

            document.getElementById('modalNameInput').value = student.name || '';
            document.getElementById('modalAvatarUrl').value = student.avatar.startsWith('data:') ? '' : student.avatar;
            document.getElementById('modalAvatarPreview').src = student.avatar || 'https://via.placeholder.com/150';
            document.getElementById('modalAvatarFile').value = '';

            const swapSelect = document.getElementById('modalSwapSelect');
            swapSelect.innerHTML = '<option value="">-- Chọn học sinh để đổi chỗ --</option>';
            studentsData.forEach(s => {
                if (s.id !== id) {
                    const option = document.createElement('option');
                    option.value = s.id;
                    option.textContent = `Ghế ${s.id}: ${s.name || 'Trống'}`;
                    swapSelect.appendChild(option);
                }
            });

            document.getElementById('editModal').style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('editModal').style.display = 'none';
        }

        function updatePreviewFromUrl() {
            const url = document.getElementById('modalAvatarUrl').value.trim();
            if (url) {
                document.getElementById('modalAvatarPreview').src = url;
            }
        }

        function previewFileAvatar(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('modalAvatarPreview').src = e.target.result;
                    document.getElementById('modalAvatarUrl').value = '';
                };
                reader.readAsDataURL(file);
            }
        }

        function clearSeat() {
            const student = studentsData.find(s => s.id === currentEditingId);
            student.name = '';
            student.avatar = 'https://via.placeholder.com/150?text=Empty';
            saveToLocalStorage();
            renderClassroom();
            closeModal();
        }

        function saveChanges() {
            const student = studentsData.find(s => s.id === currentEditingId);
            const newName = document.getElementById('modalNameInput').value.trim();
            const newAvatar = document.getElementById('modalAvatarPreview').src;
            const targetSwapId = parseInt(document.getElementById('modalSwapSelect').value);

            student.name = newName;
            student.avatar = newAvatar;

            if (targetSwapId) {
                const targetStudent = studentsData.find(s => s.id === targetSwapId);
                const tempName = student.name;
                const tempAvatar = student.avatar;

                student.name = targetStudent.name;
                student.avatar = targetStudent.avatar;

                targetStudent.name = tempName;
                targetStudent.avatar = tempAvatar;
            }

            saveToLocalStorage();
            renderClassroom();
            closeModal();
        }

        // Lightbox Functions
        function openLightbox(imgSrc, captionText) {
            document.getElementById('lightboxImg').src = imgSrc;
            document.getElementById('lightboxCaption').textContent = captionText;
            document.getElementById('lightbox').style.display = 'flex';
        }

        function openLightboxFromModal() {
            const currentAvatar = document.getElementById('modalAvatarPreview').src;
            const currentName = document.getElementById('modalNameInput').value || 'Học sinh';
            openLightbox(currentAvatar, `${currentName} - Ghế ${currentEditingId}`);
        }

        function closeLightbox() {
            document.getElementById('lightbox').style.display = 'none';
        }

        // Khởi chạy khi tải trang
        renderClassroom();
    </script>
</body>
</html>
