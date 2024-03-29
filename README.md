# LottieFiles
Demo: [lottiefiles.vercel.app](https://lottiefiles.vercel.app/)

Document: [Lottie Docs](https://airbnb.io/lottie/?utm_source=cdnjs&utm_medium=cdnjs_link&utm_campaign=cdnjs_library#/)

## Example usage
**HTML**
```
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>LottieFiles</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>

<body class="bg-gray-100 w-screen h-screen overflow-x-hidden overflow-y-auto">
  <div class="container px-4 mx-auto h-full flex justify-center items-center">
    <div class="bg-white p-4 rounded-xl max-w-[400px] relative">
      <div id="svgContainer" class="w-full absolute bottom-0 left-1/2 -translate-x-1/2 pointer-events-none hidden"></div>
      <h1 class="font-bold text-2xl">Lottie</h1>
      <p class="text-gray-600">Lottie is a library for Android, iOS, Web, and Windows that parses Adobe After Effects animations exported as JSON with Bodymovin and renders them natively on mobile and on the web!<br>
      <a class="text-blue-500 underline" href="https://airbnb.io/lottie/?utm_source=cdnjs&utm_medium=cdnjs_link&utm_campaign=cdnjs_library#/web" target="_blank" rel="noopener noreferrer">view document</a></p>
      <div class="text-right">
        <button id="btn" class="bg-blue-500 text-white px-4 py-2 rounded transition mt-4 hover:bg-blue-600">Click to Play!</button>
      </div>
    </div>
  </div>
</body>

</html>
```
**Import lottie.min.js**
```
<!-- CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/bodymovin/5.12.2/lottie.min.js" integrity="sha512-jEnuDt6jfecCjthQAJ+ed0MTVA++5ZKmlUcmDGBv2vUI/REn6FuIdixLNnQT+vKusE2hhTk2is3cFvv5wA+Sgg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
```
**Add script**
```
const btn = document.getElementById("btn");
const svgContainer = document.getElementById("svgContainer");

const animation = bodymovin.loadAnimation({
  container: svgContainer, // Required
  renderer: 'svg', // Required
  loop: false, // Optional
  autoplay: false, // Optional
  path: 'https://lottie.host/02977bca-34d8-4e9e-841a-661a4625841e/Fs4O0hzSpS.json', // Required
});

btn.addEventListener('click', () => {
  svgContainer.classList.remove('hidden');
  animation.goToAndPlay(0, true);
});

animation.addEventListener('complete', () => {
  svgContainer.classList.add('hidden');
})
```
