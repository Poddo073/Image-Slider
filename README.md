# Video-Slider*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

section{
    position: relative;
    width: 800px;
    height: 500px;
    margin: auto;
    margin-top: 50px;
}

section video{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.navigation{
    height: 500px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    opacity: 0;
    transition: opacity 0.5s ease;
    -webkit-transition: opacity 0.5s ease;
    -moz-transition: opacity 0.5s ease;
    -ms-transition: opacity 0.5s ease;
    -o-transition: opacity 0.5s ease;
}

section:hover .navigation{
    opacity: 1;
}

.prev-btn, .next-btn{
    z-index: 999;
    font-size: 2em;
    color: #222;
    background: rgba(255, 255, 255, 0.8);
    padding: 10px;
    cursor: pointer;
}

.prev-btn{
    border-top-right-radius: 3px;
    border-bottom-right-radius: 3px;
}

.next-btn{
    border-top-left-radius: 3px;
    border-bottom-left-radius: 3px;
}











.navigation-manual{
    position:absolute;
    width: 100%;
    margin-top: 450px;
    display:flex;
    justify-content: center;
}

.manual-btn{
    border: 3px solid #40D3DC;
    padding: 10px;
    border-radius: 10px;
    -webkit-border-radius: 20px;
    -moz-border-radius: 10px;
    -ms-border-radius: 10px;
    -o-border-radius: 10px;
    cursor: pointer;
    transition: 1s;
    -webkit-transition: 1s;
    -moz-transition: 1s;
    -ms-transition: 1s;
    -o-transition: 1s;
}

.manual-btn:not(:last-child){
    margin-right: 20px;
}

.manual-btn:hover{
    background: #40D3DC;
}

body {
    background: #40d3dc;
}









<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Video Slider</title>
    <script src="https://kit.fontawesome.com/bc9453ed53.js" crossorigin="anonymous"></script>

    <link rel="stylesheet" href="style.css" type="text/css">
</head>
<body>
    <section>
        <video id="slider" class="slider-video" autoplay muted loop>
            <source src="video/video1.mp4" type="video/mp4">
        </video>
        <div class="navigation-manual">
            <label for="radio1" class="manual-btn" onclick="videoUrl('video/video1.mp4')"></label>
            <label for="radio2" class="manual-btn" onclick="videoUrl('video/video2.mp4')"></label>
            <label for="radio3" class="manual-btn" onclick="videoUrl('video/video3.mp4')"></label>
            <label for="radio4" class="manual-btn" onclick="videoUrl('video/video4.mp4')"></label>
        </div>
        <div class="navigation">
            <i class="fas fa-chevron-left prev-btn" onclick="prev()"></i>
            <i class="fas fa-chevron-right next-btn" onclick="next()"></i>
        </div>
    </section>
    <script type="text/javascript">
        function videoUrl(hmmmm){
            document.getElementById("slider").src = hmmmm;
        }
        
        let slider_video = document.querySelector('.slider-video');
        let videos = ['video1.mp4', 'video2.mp4', 'video3.mp4', 'video4.mp4'];
        let i = 0; //Current Video index

        function prev(){
            if(i <= 0) i = videos.length;
            i--;
            return setVideo();
        }

        function next(){
            if(i >= videos.length - 1) i = -1;
            i++;
            return setVideo();
        }
        function setVideo(){
            return slider_video.setAttribute('src', 'video/' + videos[i]);
        }
        
    </script>
</body>
</html>
