
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Real Time Object Detection</title>

<!-- TensorFlow.js -->
<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@4.17.0/dist/tf.min.js"></script>

<!-- COCO-SSD Object Detection Model -->
<script src="https://cdn.jsdelivr.net/npm/@tensorflow-models/coco-ssd@2.2.3/dist/coco-ssd.min.js"></script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background: linear-gradient(135deg, #141e30, #243b55);
    color: white;
    text-align: center;
    padding: 20px;
}

h1 {
    margin: 15px;
    color: #00ffcc;
}

.container {
    max-width: 750px;
    margin: auto;
    background: #ffffff15;
    padding: 20px;
    border-radius: 15px;
}

.camera-box {
    position: relative;
    width: 100%;
    margin: 20px auto;
    background: black;
    border-radius: 10px;
    overflow: hidden;
}

video, canvas {
    width: 100%;
    display: block;
}

canvas {
    position: absolute;
    top: 0;
    left: 0;
}

button {
    padding: 13px 25px;
    margin: 10px;
    border: none;
    border-radius: 8px;
    background: #00ffcc;
    color: #111;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
}

button:hover {
    background: #00ccaa;
}

#status {
    margin: 15px;
    color: yellow;
}

#results {
    background: #00000040;
    padding: 15px;
    margin-top: 15px;
    border-radius: 10px;
    text-align: left;
}

.object {
    padding: 10px;
    border-bottom: 1px solid #ffffff30;
    font-size: 17px;
}
</style>
</head>

<body>

<h1>AI Object Detection</h1>
<p>Real-Time Camera Object Detection System</p>

<div class="container">

    <h3>Camera Preview</h3>

    <div class="camera-box">

        <video id="video" autoplay playsinline muted></video>

        <canvas id="canvas"></canvas>

    </div>

    <button onclick="startCamera()">
        Start Camera
    </button>

    <button onclick="stopCamera()">
        Stop Camera
    </button>

    <p id="status">Loading AI Model...</p>

    <div id="results">
        <h3>Detected Objects</h3>
        <p>Waiting for camera...</p>
    </div>

</div>

<script>

const video = document.getElementById("video");
const canvas = document.getElementById("canvas");
const ctx = canvas.getContext("2d");

const statusText = document.getElementById("status");
const results = document.getElementById("results");

let model = null;
let stream = null;
let detecting = false;

// Load AI Model
async function loadModel() {

    try {

        statusText.innerText = "Loading AI Model...";

        model = await cocoSsd.load();

        statusText.innerText = "AI Model Loaded Successfully!";

    } catch(error) {

        statusText.innerText = "Model loading failed. Check internet.";

        console.error(error);

    }

}

// Start Camera
async function startCamera() {

    if (!model) {
        statusText.innerText = "Please wait for AI model to load.";
        return;
    }

    try {

        stream = await navigator.mediaDevices.getUserMedia({

            video: {
                facingMode: "environment"
            },

            audio: false

        });

        video.srcObject = stream;

        await video.play();

        detecting = true;

        statusText.innerText = "Camera Started - Detecting Objects";

        detectObjects();

    } catch(error) {

        statusText.innerText =
        "Camera permission denied or camera unavailable.";

        console.error(error);

    }

}

// Stop Camera
function stopCamera() {

    detecting = false;

    if (stream) {

        stream.getTracks().forEach(track => track.stop());

        stream = null;

    }

    video.srcObject = null;

    ctx.clearRect(0, 0, canvas.width, canvas.height);

    results.innerHTML = "<h3>Detected Objects</h3><p>Camera stopped.</p>";

    statusText.innerText = "Camera Stopped";

}

// Detect Objects
async function detectObjects() {

    if (!detecting || !model) return;

    if (video.readyState >= 2) {

        canvas.width = video.videoWidth;
        canvas.height = video.videoHeight;

        const predictions = await model.detect(video);

        ctx.clearRect(0, 0, canvas.width, canvas.height);

        let html = "<h3>Detected Objects</h3>";

        if (predictions.length === 0) {

            html += "<p>No objects detected.</p>";

        }

        predictions.forEach(prediction => {

            const [x, y, width, height] = prediction.bbox;

            const name = prediction.class;

            const confidence =
            (prediction.score * 100).toFixed(1);

            // Draw Rectangle
            ctx.strokeStyle = "#00ff00";
            ctx.lineWidth = 3;

            ctx.strokeRect(x, y, width, height);

            // Draw Object Name
            ctx.fillStyle = "#00ff00";
            ctx.font = "18px Arial";

            ctx.fillText(
                name + " " + confidence + "%",
                x,
                Math.max(y - 8, 20)
            );

            html += `
                <div class="object">
                    <b>Object:</b> ${name}
                    <br>
                    <b>Confidence:</b> ${confidence}%
                </div>
            `;

        });

        results.innerHTML = html;

    }

    if (detecting) {

        setTimeout(detectObjects, 200);

    }

}

// Load model when page opens
loadModel();

</script>

</body>
</html>
