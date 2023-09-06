<!DOCTYPE html>
<html>
<head>
   <style>
      #image-container {
         text-align: center;
      }
      h3 {
         text-align: center; /* Center-align the heading text */
      }
   </style>
</head>
<body>
   <h3>ZoomIN and ZoomOUT of the images using range slider</h3>
   <div id="image-container">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTlBIKkgScruMchCgsEeCzkxPmG9p6YBT_sNw&usqp=CAU" height="500px" width="500px" alt="sample image" id="image">
      <br><br>
      <input type="range" id="zoomRange" min="50" max="200" step="1" value="100" oninput="Zoom()">
      
   </div>
   <script>
      let image = document.getElementById('image');
      let zoomRange = document.getElementById('zoomRange');

      function Zoom() {
         let zoomValue = zoomRange.value;
         image.style.width = zoomValue + "%";
         image.style.height = zoomValue + "%";
      }

      function ZoomIn() {
         let zoomValue = parseInt(zoomRange.value);
         if (zoomValue < 150) {
            zoomRange.value = zoomValue + 10;
            Zoom();
         }
      }

      function ZoomOut() {
         let zoomValue = parseInt(zoomRange.value);
         if (zoomValue > 70) {
            zoomRange.value = zoomValue - 10;
            Zoom();
         }
      }
   </script>
</body>
</html>
