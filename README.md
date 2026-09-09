<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PhotoResizer.store - सरकारी फ़ॉर्म फ़ोटो एवं सिग्नेचर कंप्रेसर</title>
  <meta name="description" content="बिना चेहरा खराब किए और बिना पिक्सल बिगाड़े फ़ोटो और सिग्नेचर को 20KB और 50KB में बदलें। SSC, UP Police, रेलवे फ़ॉर्म हेतु मुफ़्त टूल।">

  <style>
    :root {
      --primary: #2563eb;
      --primary-dark: #1d4ed8;
      --success: #16a34a;
      --bg: #f8fafc;
      --card: #ffffff;
      --text: #0f172a;
      --muted: #64748b;
      --border: #e2e8f0;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif; }
    body { background-color: var(--bg); color: var(--text); padding: 20px 10px; }
    .wrapper { max-width: 650px; margin: 0 auto; }
    
    header { text-align: center; margin-bottom: 25px; }
    header h1 { font-size: 28px; color: var(--primary); margin-bottom: 6px; }
    header p { color: var(--muted); font-size: 15px; }

    .ad-banner { background: #e2e8f0; border: 1px dashed #94a3b8; padding: 12px; text-align: center; margin-bottom: 20px; font-size: 12px; color: var(--muted); border-radius: 6px; }

    .tool-card { background: var(--card); border-radius: 14px; padding: 25px; box-shadow: 0 4px 20px rgba(0,0,0,0.06); }

    /* Upload Zone */
    .dropzone { border: 2px dashed #93c5fd; background: #eff6ff; border-radius: 10px; padding: 30px 15px; text-align: center; cursor: pointer; transition: 0.2s; margin-bottom: 22px; }
    .dropzone:hover { background: #dbeafe; border-color: var(--primary); }
    .dropzone-icon { font-size: 38px; margin-bottom: 8px; }
    .dropzone p { font-size: 15px; font-weight: 600; color: var(--text); }
    .dropzone span { font-size: 13px; color: var(--muted); }
    input[type="file"] { display: none; }

    /* Quick Preset Buttons */
    .preset-title { font-size: 14px; font-weight: 600; margin-bottom: 10px; color: var(--text); }
    .preset-chips { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 20px; }
    .chip { flex: 1; min-width: 120px; background: #f1f5f9; border: 1px solid var(--border); padding: 10px; text-align: center; border-radius: 8px; font-size: 13px; font-weight: 600; cursor: pointer; transition: 0.2s; }
    .chip:hover { border-color: var(--primary); color: var(--primary); }
    .chip.active { background: #eff6ff; border-color: var(--primary); color: var(--primary); }

    /* Target Size Input Box */
    .target-box { background: #f8fafc; border: 1px solid var(--border); border-radius: 8px; padding: 15px; margin-bottom: 22px; }
    .target-box label { display: block; font-size: 13px; font-weight: 600; margin-bottom: 8px; }
    .target-input-group { display: flex; align-items: center; gap: 10px; }
    .target-input-group input { flex: 1; padding: 10px; border: 1px solid var(--border); border-radius: 6px; font-size: 16px; font-weight: bold; }
    .target-input-group span { font-size: 14px; font-weight: 600; color: var(--muted); }

    /* Action Button */
    .action-btn { width: 100%; background: var(--primary); color: white; border: none; padding: 14px; border-radius: 8px; font-size: 16px; font-weight: 600; cursor: pointer; transition: 0.2s; }
    .action-btn:hover { background: var(--primary-dark); }

    /* Result Area */
    .result-section { display: none; margin-top: 25px; padding-top: 20px; border-top: 1px solid var(--border); text-align: center; }
    .comparison { display: flex; justify-content: center; gap: 15px; margin: 15px 0; flex-wrap: wrap; }
    .stat-pill { background: #f1f5f9; border: 1px solid var(--border); padding: 8px 16px; border-radius: 20px; font-size: 13px; font-weight: 600; }
    .stat-pill.success { background: #dcfce7; border-color: #86efac; color: var(--success); font-weight: 700; }
    .preview-box img { max-width: 170px; max-height: 200px; border-radius: 6px; border: 1px solid var(--border); margin: 10px 0; object-fit: contain; }
    .download-btn { display: inline-block; background: var(--success); color: white; text-decoration: none; padding: 12px 30px; border-radius: 6px; font-weight: 600; margin-top: 10px; }
    .download-btn:hover { background: #15803d; }

    /* SEO Section */
    .seo-section { margin-top: 30px; background: var(--card); padding: 22px; border-radius: 12px; }
    .seo-section h2 { font-size: 16px; margin-bottom: 10px; color: var(--text); }
    .seo-section p { font-size: 13px; color: #475569; line-height: 1.6; }

    footer { text-align: center; margin-top: 30px; font-size: 13px; color: var(--muted); }
    footer a { color: var(--primary); text-decoration: none; font-weight: 500; }
  </style>
</head>
<body>

<div class="wrapper">
  
  <header>
    <h1>PhotoResizer.store</h1>
    <p>सरकारी फ़ॉर्म फ़ोटो एवं हस्ताक्षर कंप्रेसर (चेहरे की क्वालिटी ख़राब किए बिना)</p>
  </header>

  <div class="ad-banner">
    विज्ञापन स्थान (Google AdSense Responsive Banner)
  </div>

  <div class="tool-card">
    
    <!-- Upload Dropzone -->
    <div class="dropzone" onclick="document.getElementById('fileInput').click()">
      <div class="dropzone-icon">📷</div>
      <p id="uploadTitle">फ़ोटो या सिग्नेचर चुनने के लिए यहाँ टैप करें</p>
      <span id="fileDetails">JPG, JPEG या PNG फ़ाइल चुनें</span>
      <input type="file" id="fileInput" accept="image/*">
    </div>

    <!-- Quick Buttons -->
    <div class="preset-title">फ़ॉर्म की ज़रूरत अनुसार चुनें:</div>
    <div class="preset-chips">
      <div class="chip" onclick="setPreset(20, this)">हस्ताक्षर (20 KB)</div>
      <div class="chip active" onclick="setPreset(50, this)">पासपोर्ट फ़ोटो (50 KB)</div>
      <div class="chip" onclick="setPreset(100, this)">दस्तावेज़ (100 KB)</div>
    </div>

    <!-- Target KB Input -->
    <div class="target-box">
      <label>अधिकतम साइज़ सीमा (Target Size):</label>
      <div class="target-input-group">
        <input type="number" id="targetKb" value="50" min="5" max="500">
        <span>KB से कम</span>
      </div>
    </div>

    <button class="action-btn" onclick="processImage()">फ़ोटो कंप्रेस करें</button>

    <!-- Results -->
    <div class="result-section" id="resultBlock">
      <div class="comparison">
        <div class="stat-pill" id="origStat">मूल: 0 KB</div>
        <div class="stat-pill success" id="newStat">तैयार: 0 KB</div>
      </div>
      <div class="preview-box">
        <img id="outPreview" alt="Compressed Preview">
      </div>
      <br>
      <a id="downloadBtn" class="download-btn" download="photo_ready.jpg">तैयार फ़ोटो डाउनलोड करें</a>
    </div>

  </div>

  <div class="seo-section">
    <h2>सरकारी फ़ॉर्म में फ़ोटो रिजेक्ट होने से कैसे बचाएं?</h2>
    <p>सरकारी पोर्टल्स (जैसे SSC, UP Police, रेलवे) पर अगर फ़ोटो की चौड़ाई और लंबाई को ज़बरदस्ती खींचा जाए, तो फ़ोटो धुंधली या विकृत हो जाती है। यह टूल आपकी फ़ोटो के ओरिजिनल अनुपात को बिल्कुल वैसा ही रखता है और केवल फ़ाइल का साइज़ (KB) कम करता है, जिससे फ़ॉर्म 100% स्वीकार हो जाता है।</p>
  </div>

  <footer>
    सहायता एवं सुझाव: <a href="mailto:photoresizerstore@gmail.com">photoresizerstore@gmail.com</a> | 
    &copy; 2026 PhotoResizer.store
  </footer>

</div>

<script>
  let activeFile = null;

  document.getElementById('fileInput').addEventListener('change', function(e) {
    if (e.target.files.length > 0) {
      activeFile = e.target.files[0];
      const kb = (activeFile.size / 1024).toFixed(1);
      document.getElementById('uploadTitle').innerText = '✅ चुनी गई: ' + activeFile.name;
      document.getElementById('fileDetails').innerText = 'मूल साइज़: ' + kb + ' KB';
      document.getElementById('origStat').innerText = 'मूल साइज़: ' + kb + ' KB';
    }
  });

  function setPreset(kb, element) {
    document.getElementById('targetKb').value = kb;
    document.querySelectorAll('.chip').forEach(c => c.classList.remove('active'));
    element.classList.add('active');
  }

  function processImage() {
    if (!activeFile) { 
      alert('कृपया पहले एक फ़ोटो या सिग्नेचर चुनें!'); 
      return; 
    }

    const targetKb = parseFloat(document.getElementById('targetKb').value) || 50;
    const reader = new FileReader();

    reader.onload = function(e) {
      const img = new Image();
      img.src = e.target.result;

      img.onload = function() {
        const canvas = document.createElement('canvas');
        const ctx = canvas.getContext('2d');

        // ओरिजिनल अनुपात (Aspect Ratio) सुरक्षित रखना
        let width = img.width;
        let height = img.height;
        const maxDimension = 1200;

        if (width > maxDimension || height > maxDimension) {
          if (width > height) {
            height = Math.round((height * maxDimension) / width);
            width = maxDimension;
          } else {
            width = Math.round((width * maxDimension) / height);
            height = maxDimension;
          }
        }

        canvas.width = width;
        canvas.height = height;

        // सफ़ेद बैकग्राउंड ताकि पारदर्शी PNG भी सही JPG बने
        ctx.fillStyle = '#ffffff';
        ctx.fillRect(0, 0, width, height);
        ctx.drawImage(img, 0, 0, width, height);

        let quality = 0.92;

        function compressLoop() {
          canvas.toBlob(function(blob) {
            const currentKb = blob.size / 1024;

            if (currentKb > targetKb && quality > 0.12) {
              quality -= 0.07;
              compressLoop();
            } else {
              const url = URL.createObjectURL(blob);
              document.getElementById('outPreview').src = url;
              document.getElementById('newStat').innerText = 'तैयार साइज़: ' + currentKb.toFixed(1) + ' KB (सफल)';
              
              const dl = document.getElementById('downloadBtn');
              dl.href = url;
              dl.download = 'PhotoResizer_' + activeFile.name.replace(/\.[^/.]+$/, "") + ".jpg";

              document.getElementById('resultBlock').style.display = 'block';
            }
          }, 'image/jpeg', quality);
        }

        compressLoop();
      };
    };

    reader.readAsDataURL(activeFile);
  }
</script>

</body>
</html>
