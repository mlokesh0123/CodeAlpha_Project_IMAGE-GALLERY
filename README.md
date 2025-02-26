<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            margin: 0;
        }
        .gallery-container {
            position: relative;
            width: 600px;
            height: 400px;
            overflow: hidden;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        .gallery img {
    width: 100%;
    height: auto;
    max-height: 100%;
    display: none;
}


        .gallery img.active {
            display: block;
        }
        .nav-button {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(0,0,0,0.5);
            color: white;
            border: none;
            padding: 10px;
            cursor: pointer;
        }
        .prev { left: 10px; }
        .next { right: 10px; }
    </style>
</head>
<body>
    <div class="gallery-container">
        <button class="nav-button prev" onclick="prevImage()">&#10094;</button>
        <div class="gallery">
            <img src="C:\Users\lokhe\OneDrive\Pictures\Screenshots\Screenshot 2025-01-26 114924.png" class="active">
            <img src="C:\Users\lokhe\OneDrive\Pictures\Screenshots\Screenshot 2025-01-31 160511.png">
            <img src="C:\Users\lokhe\OneDrive\Pictures\Screenshots\Screenshot (1).png">
        </div>
        <button class="nav-button next" onclick="nextImage()">&#10095;</button>
    </div>
    <script>
        let currentIndex = 0;
        const images = document.querySelectorAll('.gallery img');
        
        function showImage(index) {
            images.forEach(img => img.classList.remove('active'));
            images[index].classList.add('active');
        }
        
        function prevImage() {
            currentIndex = (currentIndex > 0) ? currentIndex - 1 : images.length - 1;
            showImage(currentIndex);
        }
        
        function nextImage() {
            currentIndex = (currentIndex < images.length - 1) ? currentIndex + 1 : 0;
            showImage(currentIndex);
        }
    </script>
</body>
</html>
