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
   <h3>Zoom IN and Zoom OUT of the image using range slider</h3>
   <div id="image-container">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTlBIKkgScruMchCgsEeCzkxPmG9p6YBT_sNw&usqp=CAU" height="500px" width="500px" alt="sample image" id="image">
      <br><br>
      <input type="range" id="zoomRange" min="20" max="100" step="1" value="50" oninput="Zoom()">
   </div>
   <script>
      let image = document.getElementById('image');
      let zoomRange = document.getElementById('zoomRange');

      function Zoom() {
         // Calculate the zoom factor based on the range component's value
         let zoomFactor = (parseInt(zoomRange.value) - 50) / 50;
         // Apply the zoom factor to the image size
         image.style.width = 500 * (1 + zoomFactor) + "px";
         image.style.height = 500 * (1 + zoomFactor) + "px";
      }
   </script>
</body>
</html>
