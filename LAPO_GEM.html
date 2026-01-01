<?php
// Mulai session untuk menyimpan data sementara
session_start();

// Inisialisasi data tugas jika belum ada
if (!isset($_SESSION['tasks'])) {
    $_SESSION['tasks'] = [
        'tugas1' => [
            'nama' => 'Tugas 1: Presentasi Digital Marketing',
            'items' => [
                ['nama' => 'Riset kompetitor', 'selesai' => true],
                ['nama' => 'Buat slide presentasi', 'selesai' => true],
                ['nama' => 'Rekam video presentasi', 'selesai' => false],
                ['nama' => 'Upload ke platform', 'selesai' => false]
            ]
        ],
        'tugas2' => [
            'nama' => 'Tugas 2: Laporan Keuangan',
            'items' => [
                ['nama' => 'Kumpulkan data transaksi', 'selesai' => true],
                ['nama' => 'Analisis pengeluaran', 'selesai' => false],
                ['nama' => 'Buat grafik visualisasi', 'selesai' => false],
                ['nama' => 'Presentasi ke manajer', 'selesai' => false]
            ]
        ],
        'tugas3' => [
            'nama' => 'Tugas 3: Website Company Profile',
            'items' => [
                ['nama' => 'Desain UI/UX', 'selesai' => true],
                ['nama' => 'Koding frontend', 'selesai' => true],
                ['nama' => 'Koding backend', 'selesai' => false],
                ['nama' => 'Testing dan deployment', 'selesai' => false]
            ]
        ]
    ];
}

// Proses update checklist jika ada form yang dikirim
if ($_SERVER['REQUEST_METHOD'] === 'POST' && isset($_POST['task_id']) && isset($_POST['item_index'])) {
    $taskId = $_POST['task_id'];
    $itemIndex = $_POST['item_index'];
    
    if (isset($_SESSION['tasks'][$taskId]['items'][$itemIndex])) {
        // Toggle status selesai
        $_SESSION['tasks'][$taskId]['items'][$itemIndex]['selesai'] = 
            !$_SESSION['tasks'][$taskId]['items'][$itemIndex]['selesai'];
    }
    
    // Redirect untuk menghindari resubmit form
    header('Location: ' . $_SERVER['PHP_SELF']);
    exit();
}

// Hitung statistik
$totalTugas = count($_SESSION['tasks']);
$totalItem = 0;
$itemSelesai = 0;

foreach ($_SESSION['tasks'] as $task) {
    foreach ($task['items'] as $item) {
        $totalItem++;
        if ($item['selesai']) {
            $itemSelesai++;
        }
    }
}

$persentase = $totalItem > 0 ? round(($itemSelesai / $totalItem) * 100) : 0;
?>
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pelacak Perkembangan Tugas</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-tasks"></i> Pelacak Perkembangan Tugas</h1>
            <p class="subtitle">Pantau perkembangan tugas kelompok secara real-time</p>
        </header>
        
        <div class="stats-card">
            <div class="stat">
                <h3><?php echo $totalTugas; ?></h3>
                <p>Total Tugas</p>
            </div>
            <div class="stat">
                <h3><?php echo $itemSelesai . '/' . $totalItem; ?></h3>
                <p>Item Selesai</p>
            </div>
            <div class="stat">
                <h3><?php echo $persentase; ?>%</h3>
                <p>Progress Keseluruhan</p>
            </div>
            <div class="progress-bar">
                <div class="progress-fill" style="width: <?php echo $persentase; ?>%"></div>
            </div>
        </div>
        
        <div class="tasks-container">
            <?php foreach ($_SESSION['tasks'] as $taskId => $task): 
                // Hitung progress per tugas
                $totalItems = count($task['items']);
                $completedItems = 0;
                foreach ($task['items'] as $item) {
                    if ($item['selesai']) $completedItems++;
                }
                $taskProgress = $totalItems > 0 ? round(($completedItems / $totalItems) * 100) : 0;
            ?>
            <div class="task-card">
                <div class="task-header">
                    <h2><?php echo htmlspecialchars($task['nama']); ?></h2>
                    <span class="progress-indicator"><?php echo $taskProgress; ?>% selesai</span>
                </div>
                
                <div class="task-progress">
                    <div class="progress-bar small">
                        <div class="progress-fill" style="width: <?php echo $taskProgress; ?>%"></div>
                    </div>
                </div>
                
                <div class="checklist">
                    <?php foreach ($task['items'] as $index => $item): ?>
                    <form method="POST" class="checklist-item">
                        <input type="hidden" name="task_id" value="<?php echo $taskId; ?>">
                        <input type="hidden" name="item_index" value="<?php echo $index; ?>">
                        
                        <button type="submit" class="checkbox <?php echo $item['selesai'] ? 'checked' : ''; ?>">
                            <?php if ($item['selesai']): ?>
                                <i class="fas fa-check"></i>
                            <?php endif; ?>
                        </button>
                        
                        <span class="item-text <?php echo $item['selesai'] ? 'completed' : ''; ?>">
                            <?php echo htmlspecialchars($item['nama']); ?>
                        </span>
                        
                        <span class="status-badge <?php echo $item['selesai'] ? 'selesai' : 'belum'; ?>">
                            <?php echo $item['selesai'] ? 'Selesai' : 'Belum'; ?>
                        </span>
                    </form>
                    <?php endforeach; ?>
                </div>
                
                <div class="task-footer">
                    <div class="status-count">
                        <span><i class="fas fa-check-circle"></i> <?php echo $completedItems; ?> selesai</span>
                        <span><i class="fas fa-clock"></i> <?php echo $totalItems - $completedItems; ?> belum</span>
                    </div>
                    <div class="last-update">
                        Terakhir diperbarui: <?php echo date('H:i'); ?>
                    </div>
                </div>
            </div>
            <?php endforeach; ?>
        </div>
        
        <div class="info-box">
            <h3><i class="fas fa-info-circle"></i> Cara Menggunakan</h3>
            <p>1. Klik checkbox untuk menandai item sebagai selesai/belum</p>
            <p>2. Status otomatis tersimpan dan dapat dilihat oleh semua pengguna</p>
            <p>3. Progress bar menunjukkan perkembangan setiap tugas</p>
            <p>4. Data tetap tersimpan selama sesi browser aktif</p>
        </div>
        
        <footer>
            <p>© 2023 Pelacak Tugas Kelompok | Data tersimpan dalam session browser</p>
            <p class="hint">Catatan: Untuk penyimpanan permanen, perlu integrasi dengan database</p>
        </footer>
    </div>
    
    <script>
        // Animasi saat checklist diklik
        document.addEventListener('DOMContentLoaded', function() {
            const checkboxes = document.querySelectorAll('.checkbox');
            
            checkboxes.forEach(checkbox => {
                checkbox.addEventListener('click', function() {
                    // Tambahkan efek visual
                    this.style.transform = 'scale(0.9)';
                    setTimeout(() => {
                        this.style.transform = 'scale(1)';
                    }, 150);
                });
            });
            
            // Auto refresh progress setiap 30 detik
            setTimeout(function() {
                window.location.reload();
            }, 30000);
        });
    </script>
</body>
</html>
