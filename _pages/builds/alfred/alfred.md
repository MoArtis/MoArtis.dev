---
layout: page
title: 
permalink: /builds/alfred
ext-css: ./assets/builds/template/style.css
---

<div id="unity-container" class="unity-desktop embed-responsive embed-responsive-16by9">
  <canvas id="unity-canvas" class="embed-responsive-item" tabindex="-1"></canvas>
  <div id="unity-loading-bar">
    <div id="unity-logo"></div>
    <div id="unity-progress-bar-empty">
      <div id="unity-progress-bar-full"></div>
    </div>
  </div>
  <div id="unity-warning"> </div>
</div>

<div id="unity-footer">
  <div id="unity-fullscreen-button"></div>
  <div id="unity-build-title">Fullscreen</div>
</div>

<script>
  var container = document.querySelector("#unity-container");
  var canvas = document.querySelector("#unity-canvas");
  var loadingBar = document.querySelector("#unity-loading-bar");
  var progressBarFull = document.querySelector("#unity-progress-bar-full");
  var fullscreenButton = document.querySelector("#unity-fullscreen-button");
  var warningBanner = document.querySelector("#unity-warning");

  // Shows a temporary message banner/ribbon for a few seconds, or
  // a permanent error message on top of the canvas if type=='error'.
  // If type=='warning', a yellow highlight color is used.
  // Modify or remove this function to customize the visually presented
  // way that non-critical warnings and error messages are presented to the
  // user.
  function unityShowBanner(msg, type) {
    function updateBannerVisibility() {
      warningBanner.style.display = warningBanner.children.length ? 'block' : 'none';
    }
    var div = document.createElement('div');
    div.innerHTML = msg;
    warningBanner.appendChild(div);
    if (type == 'error') div.style = 'background: red; padding: 10px;';
    else {
      if (type == 'warning') div.style = 'background: yellow; padding: 10px;';
      setTimeout(function() {
        warningBanner.removeChild(div);
        updateBannerVisibility();
      }, 5000);
    }
    updateBannerVisibility();
  }

  var buildFileName = "webgl";
  var buildName = "alfred";
  var buildUrl = "/assets/builds/" + buildName + "/";
  var buildFileUrl = buildUrl + buildFileName;
  var loaderUrl = buildFileUrl + ".loader.js";
  var config = {
    dataUrl: buildFileUrl + ".data.br",
    frameworkUrl: buildFileUrl + ".framework.js.br",
    codeUrl: buildFileUrl + ".wasm.br",
    streamingAssetsUrl: "StreamingAssets",
    companyName: "SparklingVinegar",
    productName: "FlexMotion",
    productVersion: "1.0.0",
    showBanner: unityShowBanner,
  };

  loadingBar.style.display = "block";

  var script = document.createElement("script");
  script.src = loaderUrl;
  script.onload = () => {
    createUnityInstance(canvas, config, (progress) => {
      progressBarFull.style.width = 100 * progress + "%";
          }).then((unityInstance) => {
            loadingBar.style.display = "none";
            fullscreenButton.onclick = () => {
              unityInstance.SetFullscreen(1);
            };
          }).catch((message) => {
            alert(message);
          });
        };

  document.body.appendChild(script);

</script>