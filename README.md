<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>XENOPATH</title>
  <!-- Google Fonts - Poppins and Luckiest Guy -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Luckiest+Guy&display=swap" rel="stylesheet">
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    /* Base styles */
    :root {
      --titanium-color: #8A9199; /* Base titanium color */
      --titanium-light: #9DA2AA; /* Lighter titanium for hover states */
      --titanium-dark: #757980; /* Darker titanium for shadows and gradients */
      --titanium-gradient: linear-gradient(to right, #8A9199, #757980); /* Titanium gradient */
      
      --primary-color: #ffffff; /* White instead of Gold */
      --secondary-color: var(--titanium-color); /* Titanium instead of Blue */
      --bg-color: #000000; /* Black background */
      --light-gray: #cccccc; /* Light gray */
      --text-color: #ffffff; /* White text */
      --contrast-color: #ffffff; /* White for contrast */
      --deep-gray: var(--titanium-dark); /* Dark titanium */
      --medium-gray: var(--titanium-color); /* Medium titanium */
      --light-gray-gradient: var(--titanium-gradient); /* Titanium gradient */
      --button-color: var(--titanium-color); /* Titanium for buttons */
      --button-hover-color: var(--titanium-light); /* Slightly lighter titanium for hover states */
    }
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }
    
    body {
      background-color: var(--bg-color);
      color: var(--text-color);
      line-height: 1.6;
      padding: 5px;
      text-align: center;
    }
    
    .container {
      max-width: 100%;
      margin: 0 auto;
      padding: 5px;
      position: relative;
      z-index: 1;
    }
    
    /* Header styles with title moved to top left - now with embossed effect */
    .header {
      text-align: left;
      margin-bottom: 10px;
      position: relative;
      padding: 15px;
      background: var(--titanium-color);
      border-radius: 12px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.2);
    }
    
    .title {
      font-family: 'Luckiest Guy', cursive;
      font-size: 1.2rem;
      color: #ffffff;
      margin-bottom: 5px;
      position: relative;
      letter-spacing: 1px;
      text-shadow: 0 2px 2px rgba(0, 0, 0, 0.7);
    }
    
    .subtitle {
      color: var(--light-gray);
      font-size: 0.7rem;
      margin-bottom: 10px;
      text-shadow: 0 1px 1px rgba(0, 0, 0, 0.5);
    }
    
    /* Bing-like prompt container - with rounded corners */
    .prompt-container {
      background-color: rgba(138, 145, 153, 0.8);
      border-radius: 16px;
      padding: 12px 8px;
      margin-bottom: 15px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(8px);
      position: relative;
      overflow: hidden;
      max-width: 1200px;
      margin-left: auto;
      margin-right: auto;
    }
    
    .prompt-input {
      width: 100%;
      min-height: 70px;
      padding: 10px;
      border-radius: 12px;
      border: 1px solid #333333;
      background-color: rgba(20, 20, 20, 0.5);
      color: white;
      font-size: 0.9rem;
      resize: none;
      transition: all 0.3s ease;
      box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
      margin-bottom: 10px;
      overflow: hidden;
    }
    
    .prompt-input:focus {
      outline: none;
      border-color: #666666;
      box-shadow: 0 0 5px rgba(255, 255, 255, 0.2);
    }
    
    /* Settings buttons row - now with embossed effect */
    .settings-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      justify-content: center;
      margin-bottom: 12px;
    }
    
    .settings-btn {
      background: var(--titanium-color);
      color: var(--text-color);
      padding: 6px 12px;
      border-radius: 12px;
      border: 1px solid var(--titanium-dark);
      font-size: 0.65rem;
      cursor: pointer;
      transition: all 0.3s ease;
      display: flex;
      align-items: center;
      gap: 6px;
      box-shadow: 0 2px 3px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.2);
      text-shadow: 0 1px 1px rgba(0, 0, 0, 0.5);
      flex: 1;
      min-width: 110px;
      max-width: 160px;
      position: relative;
      overflow: hidden;
    }
    
    .settings-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 3px 5px rgba(0, 0, 0, 0.5), inset 0 1px 1px rgba(255, 255, 255, 0.2);
      background: var(--titanium-light);
    }
    
    .settings-btn i {
      font-size: 0.75rem;
      color: #cccccc;
    }
    
    /* Compact parameter settings - with rounded corners */
    .parameters-container {
      display: flex;
      flex-wrap: wrap;
      gap: 5px;
      justify-content: center;
      margin-bottom: 10px;
    }
    
    .parameter-group {
      background-color: var(--titanium-color);
      border-radius: 12px;
      padding: 6px 8px;
      flex: 1;
      min-width: 120px;
      max-width: 180px;
      position: relative;
      overflow: hidden;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
    }
    
    .parameter-label {
      display: block;
      font-size: 0.7rem;
      color: var(--light-gray);
      margin-bottom: 3px;
      font-weight: 500;
      text-align: left;
    }
    
    .parameter-input {
      width: 100%;
      padding: 4px 6px;
      border-radius: 8px;
      border: 1px solid #333333;
      background-color: rgba(20, 20, 20, 0.5);
      color: white;
      font-size: 0.75rem;
    }
    
    .parameter-input:focus {
      outline: none;
      border-color: #666666;
      box-shadow: 0 0 5px rgba(255, 255, 255, 0.1);
    }
    
    .range-container {
      display: flex;
      align-items: center;
      gap: 5px;
    }
    
    .range-value {
      width: 30px;
      text-align: center;
      background: var(--titanium-color);
      padding: 2px;
      border-radius: 6px;
      font-weight: 600;
      color: var(--text-color);
      font-size: 0.7rem;
      position: relative;
      overflow: hidden;
      box-shadow: 0 1px 2px rgba(0, 0, 0, 0.3), inset 0 1px 1px rgba(255, 255, 255, 0.1);
    }
    
    .form-group {
      margin-bottom: 8px;
      text-align: left;
      padding-left: 5px;
      border-radius: 8px;
    }
    
    label {
      display: block;
      margin-bottom: 3px;
      color: var(--light-gray);
      font-weight: 500;
    }
    
    input[type="text"],
    input[type="number"],
    select,
    textarea {
      width: 100%;
      padding: 6px 8px;
      border-radius: 10px;
      border: 1px solid #333333;
      background-color: rgba(20, 20, 20, 0.5);
      color: white;
      font-size: 0.85rem;
      transition: all 0.3s ease;
      box-shadow: 0 0 3px rgba(0, 0, 0, 0.3);
    }
    
    input[type="text"]:focus,
    input[type="number"]:focus,
    select:focus,
    textarea:focus {
      outline: none;
      border-color: #666666;
      box-shadow: 0 0 5px rgba(255, 255, 255, 0.1);
    }
    
    textarea {
      resize: vertical;
      min-height: 60px;
    }
    
    .btn-container {
      display: flex;
      justify-content: center;
      gap: 8px;
      margin-top: 10px;
    }
    
    .btn {
      padding: 6px 12px;
      border-radius: 12px;
      border: 1px solid var(--titanium-dark);
      font-size: 0.75rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      position: relative;
      overflow: hidden;
      text-shadow: 0 1px 1px rgba(0, 0, 0, 0.5);
      background: var(--titanium-color);
      color: white;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.2), 0 3px 0 rgba(0, 0, 0, 0.3);
    }
    
    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.2), 0 5px 0 rgba(0, 0, 0, 0.3);
      background: var(--titanium-light);
    }
    
    .btn:active {
      transform: translateY(1px);
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.3), inset 0 1px 1px rgba(255, 255, 255, 0.1), 0 2px 0 rgba(0, 0, 0, 0.3);
      background: var(--titanium-dark);
    }
    
    .btn-primary, .btn-secondary {
      background: var(--titanium-color);
    }
    
    /* Images gallery - with rounded corners */
    .images-container {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
      gap: 6px;
      margin-top: 15px;
    }
    
    .image-card {
      background-color: var(--titanium-color);
      border-radius: 16px;
      overflow: hidden;
      transition: all 0.3s ease;
      position: relative;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.05);
    }
    
    .image-card:hover {
      transform: translateY(-2px) scale(1.02);
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5), inset 0 1px 1px rgba(255, 255, 255, 0.05);
    }
    
    .image-card img {
      width: 100%;
      height: auto;
      display: block;
      transition: transform 0.5s ease;
      cursor: pointer; /* Add cursor pointer to indicate it's clickable */
      border-radius: 14px 14px 0 0;
    }
    
    .image-card:hover img {
      transform: scale(1.05);
    }
    
    .image-card .actions {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      padding: 5px;
      background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
      display: flex;
      justify-content: space-between;
      opacity: 1;
      transition: opacity 0.3s ease;
      border-radius: 0 0 16px 16px;
    }
    
    .image-action {
      color: white;
      background: none;
      border: none;
      cursor: pointer;
      font-size: 0.9rem;
      padding: 3px;
      transition: all 0.3s ease;
      border-radius: 8px;
    }
    
    .image-action:hover {
      color: #cccccc;
      transform: scale(1.1);
      background: rgba(255, 255, 255, 0.1);
      box-shadow: 0 1px 2px rgba(0, 0, 0, 0.3), inset 0 1px 1px rgba(255, 255, 255, 0.1);
    }
    
    /* Loading animation */
    .loading {
      display: none;
      margin: 15px auto;
      text-align: center;
    }
    
    .spinner {
      display: inline-block;
      width: 30px;
      height: 30px;
      border: 3px solid rgba(150, 150, 150, 0.3);
      border-radius: 50%;
      border-top-color: white;
      border-bottom-color: #cccccc;
      animation: spin 1s linear infinite;
    }
    
    @keyframes spin {
      to {
        transform: rotate(360deg);
      }
    }
    
    .error-message {
      color: #ff6b6b;
      background-color: rgba(255, 107, 107, 0.1);
      padding: 8px;
      border-radius: 12px;
      margin-top: 10px;
      display: none;
      box-shadow: 0 2px 5px rgba(255, 107, 107, 0.2);
      font-size: 0.8rem;
    }
    
    /* Responsiveness */
    @media (max-width: 768px) {
      .title {
        font-size: 1.1rem;
      }
      
      .subtitle {
        font-size: 0.7rem;
      }
      
      .btn-container {
        flex-direction: row;
        width: 100%;
      }
      
      .btn {
        flex: 1;
      }
      
      .form-row {
        flex-direction: column;
      }
      
      .form-group.half {
        width: 100%;
      }
      
      .parameters-container {
        flex-direction: row;
      }
      
      .parameter-group {
        max-width: none;
        width: 100%;
      }
      
      .prompt-input {
        min-height: 70px;
        font-size: 0.9rem;
        padding: 8px;
      }
      
      .images-container {
        grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
        gap: 6px;
      }
      
      .image-card .actions {
        opacity: 1;
        padding: 5px;
      }
      
      .modal-content {
        padding: 12px;
        max-width: 95%;
      }
      
      .image-container {
        min-width: 100%;
        margin-bottom: 8px;
      }
      
      .image-comparison {
        flex-direction: column;
      }
      
      .settings-buttons {
        flex-direction: row;
        flex-wrap: wrap;
      }
      
      .settings-btn {
        flex: 1;
        min-width: 100px;
        max-width: 130px;
        font-size: 0.65rem;
      }
    }
    
    @media (max-width: 480px) {
      .container {
        padding: 3px;
      }
      
      .prompt-container {
        padding: 10px 8px;
      }
      
      .title {
        font-size: 1rem;
      }
      
      .subtitle {
        font-size: 0.7rem;
      }
      
      .parameter-label {
        font-size: 0.7rem;
      }
      
      .parameter-input {
        font-size: 0.75rem;
        padding: 4px;
      }
      
      .images-container {
        grid-template-columns: repeat(auto-fill, minmax(130px, 1fr));
        gap: 5px;
      }
      
      .range-value {
        width: 28px;
        font-size: 0.7rem;
      }
      
      .image-card .actions {
        padding: 3px;
      }
      
      .image-action {
        font-size: 0.8rem;
        padding: 2px;
      }
      
      .settings-btn {
        padding: 4px 8px;
        font-size: 0.6rem;
        min-width: 90px;
      }
    }
    
    /* Custom range input styling */
    input[type="range"] {
      -webkit-appearance: none;
      width: 100%;
      height: 5px;
      background: var(--titanium-dark);
      border-radius: 4px;
      outline: none;
    }
    
    input[type="range"]::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: linear-gradient(to bottom, #ffffff, #dddddd);
      cursor: pointer;
      box-shadow: 0 0 3px rgba(0, 0, 0, 0.7);
    }
    
    input[type="range"]::-moz-range-thumb {
      width: 16px;
      height: 16px;
      border-radius: 50%;
      background: linear-gradient(to bottom, #ffffff, #dddddd);
      cursor: pointer;
      box-shadow: 0 0 3px rgba(0, 0, 0, 0.7);
    }
    
    .form-row {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      margin-bottom: 8px;
    }
    
    .form-group.half {
      flex: 1;
      min-width: 130px;
    }
    
    /* Modal for upscaling - with rounded corners and embossed elements */
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.8);
      backdrop-filter: blur(5px);
      z-index: 1000;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      overflow-y: auto;
    }
    
    .modal-content {
      background-color: var(--titanium-color);
      border-radius: 16px;
      padding: 15px;
      max-width: 90%;
      max-height: 90%;
      overflow: auto;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5), inset 0 1px 1px rgba(255, 255, 255, 0.05);
      position: relative;
      animation: modalAppear 0.3s ease-out;
      margin: 15px 0;
    }
    
    @keyframes modalAppear {
      from { transform: scale(0.9); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }
    
    .close-modal {
      position: absolute;
      top: 5px;
      right: 10px;
      font-size: 1.3rem;
      color: white;
      background: none;
      border: none;
      cursor: pointer;
      transition: all 0.3s ease;
      z-index: 2;
      border-radius: 50%;
      width: 25px;
      height: 25px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .close-modal:hover {
      color: #cccccc;
      transform: scale(1.1);
      background: rgba(255, 255, 255, 0.1);
      box-shadow: 0 1px 2px rgba(0, 0, 0, 0.3), inset 0 1px 1px rgba(255, 255, 255, 0.1);
    }
    
    .image-comparison {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      margin: 15px 0;
    }
    
    .image-container {
      flex: 1;
      min-width: 280px;
      max-width: 500px;
      border-radius: 14px;
      padding: 5px;
      background-color: var(--titanium-color);
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.5), inset 0 1px 1px rgba(255, 255, 255, 0.05);
      position: relative;
      overflow: hidden;
    }
    
    .image-container img {
      width: 100%;
      height: auto;
      border-radius: 10px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.4);
    }
    
    .image-label {
      font-size: 0.8rem;
      color: #cccccc;
      margin-bottom: 3px;
      text-shadow: 0 1px 1px rgba(0, 0, 0, 0.5);
    }
    
    .upscale-options {
      margin: 10px 0;
      text-align: left;
      padding-left: 8px;
      border-radius: 12px;
    }
    
    .model-badge {
      display: inline-block;
      padding: 2px 6px;
      border-radius: 10px;
      font-size: 0.65rem;
      margin-left: 4px;
      vertical-align: middle;
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.1);
      background: var(--titanium-color);
    }
    
    .model-badge.pollinations {
      background: var(--titanium-color);
      color: white;
    }
    
    .upscale-progress {
      margin: 12px 0;
      padding: 8px;
      background-color: var(--titanium-color);
      border-radius: 12px;
      text-align: center;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3), inset 0 1px 1px rgba(255, 255, 255, 0.05);
      position: relative;
      overflow: hidden;
    }
    
    .progress-bar {
      height: 5px;
      background-color: var(--titanium-dark);
      border-radius: 3px;
      margin-top: 4px;
      overflow: hidden;
      box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.5);
    }
    
    .progress-bar-fill {
      height: 100%;
      background: linear-gradient(to right, var(--titanium-color), var(--titanium-light));
      width: 0%;
      transition: width 0.3s ease;
    }
    
    .topaz-badge {
      background: var(--titanium-color);
      color: white;
      font-size: 0.65rem;
      padding: 2px 8px;
      border-radius: 10px;
      display: inline-block;
      margin-left: 5px;
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.1);
    }
    
    .topaz-options-container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 10px;
      margin: 10px 0;
    }
    
    .checkbox-container {
      display: flex;
      align-items: center;
      gap: 5px;
      margin: 5px 0;
    }
    
    .checkbox-container input[type="checkbox"] {
      accent-color: var(--titanium-color);
      width: 14px;
      height: 14px;
    }
    
    /* Settings modal - with rounded corners */
    .settings-modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.8);
      backdrop-filter: blur(5px);
      z-index: 1000;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      overflow-y: auto;
    }
    
    .settings-modal-content {
      background-color: var(--titanium-color);
      border-radius: 16px;
      padding: 15px;
      width: 90%;
      max-width: 500px;
      max-height: 90%;
      overflow: auto;
      box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5), inset 0 1px 1px rgba(255, 255, 255, 0.05);
      position: relative;
      animation: modalAppear 0.3s ease-out;
    }
    
    .settings-modal-title {
      color: white;
      font-size: 1.1rem;
      margin-bottom: 10px;
      text-align: center;
      position: relative;
      padding-bottom: 5px;
      text-shadow: 0 1px 2px rgba(0, 0, 0, 0.7);
    }
    
    .settings-modal-title::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 50%;
      height: 2px;
      background: linear-gradient(to right, var(--titanium-dark), var(--titanium-light), var(--titanium-dark));
      border-radius: 5px;
    }
    
    /* Fullscreen mode styles */
    .fullscreen-image {
      width: 100vw;
      height: 100vh;
      object-fit: contain;
      background-color: rgba(0, 0, 0, 0.9);
      cursor: pointer;
    }
    
    /* Prompt History Column styles */
    .prompt-history-container {
      background-color: rgba(138, 145, 153, 0.8);
      border-radius: 16px;
      padding: 12px;
      margin-bottom: 15px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(8px);
      position: relative;
      overflow: hidden;
      max-width: 1200px;
      margin-left: auto;
      margin-right: auto;
    }
    
    .prompt-history-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-bottom: 8px;
      margin-bottom: 12px;
      border-bottom: 1px solid var(--titanium-dark);
    }
    
    .prompt-history-header h3 {
      font-size: 0.9rem;
      color: white;
      margin: 0;
      display: flex;
      align-items: center;
      gap: 6px;
      text-shadow: 0 1px 1px rgba(0, 0, 0, 0.5);
    }
    
    .history-btn {
      background: var(--titanium-color);
      color: var(--text-color);
      padding: 4px 8px;
      border-radius: 8px;
      border: 1px solid var(--titanium-dark);
      font-size: 0.65rem;
      cursor: pointer;
      transition: all 0.3s ease;
      display: flex;
      align-items: center;
      gap: 4px;
      box-shadow: 0 2px 3px rgba(0, 0, 0, 0.4), inset 0 1px 1px rgba(255, 255, 255, 0.2);
    }
    
    .history-btn:hover {
      transform: translateY(-1px);
      background: var(--titanium-light);
    }
    
    .prompt-history-list {
      display: flex;
      flex-direction: column;
      gap: 10px;
      max-height: 400px;
      overflow-y: auto;
      padding-right: 5px;
    }
    
    .prompt-history-item {
      background-color: rgba(20, 20, 20, 0.5);
      border-radius: 10px;
      padding: 10px;
      position: relative;
      border: 1px solid #333333;
      transition: all 0.3s ease;
      cursor: pointer;
    }
    
    .prompt-history-item:hover {
      background-color: rgba(30, 30, 30, 0.7);
      transform: translateY(-2px);
      box-shadow: 0 3px 7px rgba(0, 0, 0, 0.3);
    }
    
    .prompt-history-text {
      color: white;
      font-size: 0.85rem;
      margin-bottom: 5px;
      white-space: pre-wrap;
      word-break: break-word;
      text-align: left;
    }
    
    .prompt-history-date {
      color: #999;
      font-size: 0.65rem;
      text-align: right;
    }
    
    .prompt-history-actions {
      display: flex;
      gap: 5px;
      margin-top: 8px;
      justify-content: flex-end;
    }
    
    .prompt-action-btn {
      background: var(--titanium-color);
      color: white;
      border: none;
      padding: 3px 8px;
      border-radius: 6px;
      font-size: 0.7rem;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 4px;
      transition: all 0.3s ease;
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.3);
    }
    
    .prompt-action-btn:hover {
      background: var(--titanium-light);
      transform: translateY(-1px);
    }
    
    .prompt-history-edit-area {
      width: 100%;
      min-height: 60px;
      padding: 8px;
      border-radius: 8px;
      border: 1px solid #666;
      background-color: rgba(10, 10, 10, 0.8);
      color: white;
      font-size: 0.8rem;
      resize: none;
      margin-bottom: 5px;
    }
    
    .prompt-history-edit-area:focus {
      outline: none;
      border-color: #888;
      box-shadow: 0 0 5px rgba(255, 255, 255, 0.1);
    }
    
    .prompt-history-empty {
      color: #999;
      text-align: center;
      padding: 20px;
      font-style: italic;
      font-size: 0.85rem;
    }
    
    .editing-actions {
      display: flex;
      justify-content: flex-end;
      gap: 5px;
      margin-top: 8px;
    }
    
    .editing-btn {
      padding: 3px 8px;
      border-radius: 6px;
      font-size: 0.7rem;
      cursor: pointer;
      transition: all 0.3s ease;
      background: var(--titanium-color);
      color: white;
      border: 1px solid var(--titanium-dark);
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.3);
    }
    
    .editing-btn:hover {
      background: var(--titanium-light);
      transform: translateY(-1px);
    }
    
    /* Download overlay and animation */
    .download-overlay {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.7);
      z-index: 2000;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      backdrop-filter: blur(3px);
    }
    
    .download-animation {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      background: var(--titanium-color);
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
      position: relative;
      animation: pulse 1.5s infinite;
    }
    
    @keyframes pulse {
      0% { transform: scale(1); opacity: 1; }
      50% { transform: scale(1.1); opacity: 0.8; }
      100% { transform: scale(1); opacity: 1; }
    }
    
    .download-animation i {
      font-size: 36px;
      color: white;
      animation: downloadMove 1.5s infinite;
    }
    
    @keyframes downloadMove {
      0% { transform: translateY(-10px); opacity: 0.5; }
      50% { transform: translateY(5px); opacity: 1; }
      100% { transform: translateY(-10px); opacity: 0.5; }
    }
    
    .download-message {
      margin-top: 20px;
      color: white;
      font-size: 1rem;
      text-shadow: 0 1px 3px rgba(0, 0, 0, 0.8);
    }
    
    /* Additional responsive styles for prompt history */
    @media (max-width: 768px) {
      .prompt-history-list {
        max-height: 300px;
      }
      
      .prompt-history-actions {
        flex-wrap: wrap;
      }
      
      .prompt-action-btn {
        flex: 1;
        justify-content: center;
        min-width: 70px;
      }
    }
    
    @media (max-width: 480px) {
      .prompt-history-container {
        padding: 10px 8px;
      }
      
      .prompt-history-header h3 {
        font-size: 0.8rem;
      }
      
      .prompt-history-item {
        padding: 8px;
      }
      
      .prompt-history-text {
        font-size: 0.75rem;
      }
      
      .prompt-action-btn {
        padding: 2px 6px;
        font-size: 0.65rem;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Header -->
    <header class="header">
      <h1 class="title">XENOPATH</h1>
      <p class="subtitle">AI Image Generation Studio</p>
    </header>
    
    <!-- Bing-like Prompt Container -->
    <div class="prompt-container">
      <textarea id="promptInput" class="prompt-input" placeholder="Describe what you want to see... (e.g., 'A cyberpunk city at sunset with neon lights')"></textarea>
      
      <!-- Settings Buttons Row (replacing the parameter sections) -->
      <div class="settings-buttons">
        <button id="negativePromptBtn" class="settings-btn">
          <i class="fas fa-ban"></i> Negative Prompt
        </button>
        <button id="styleBtn" class="settings-btn">
          <i class="fas fa-paint-brush"></i> Style
        </button>
        <button id="dimensionsBtn" class="settings-btn">
          <i class="fas fa-crop-alt"></i> Dimensions
        </button>
        <button id="modelBtn" class="settings-btn">
          <i class="fas fa-robot"></i> AI Model
        </button>
        <button id="countScaleBtn" class="settings-btn">
          <i class="fas fa-images"></i> Count & Scale
        </button>
        <button id="advancedBtn" class="settings-btn">
          <i class="fas fa-sliders-h"></i> Advanced
        </button>
      </div>
      
      <div class="btn-container">
        <button id="generateBtn" class="btn btn-primary">
          <i class="fas fa-bolt"></i> Generate
        </button>
        <button id="randomPromptBtn" class="btn btn-secondary">
          <i class="fas fa-random"></i> Random Prompt
        </button>
        <button id="resetBtn" class="btn btn-secondary">
          <i class="fas fa-redo"></i> Reset
        </button>
      </div>
    </div>
    
    <!-- Prompt History Container -->
    <div class="prompt-history-container">
      <div class="prompt-history-header">
        <h3><i class="fas fa-history"></i> Prompt History</h3>
        <div>
          <button id="recallLastPromptBtn" class="history-btn">
            <i class="fas fa-redo"></i> Recall Last
          </button>
          <button id="clearHistoryBtn" class="history-btn">
            <i class="fas fa-trash"></i> Clear All
          </button>
        </div>
      </div>
      <div id="promptHistoryList" class="prompt-history-list">
        <!-- Prompt history items will be added here dynamically -->
      </div>
    </div>
    
    <!-- Loading indicator -->
    <div id="loadingIndicator" class="loading">
      <div class="spinner"></div>
      <p>Generating your images...</p>
    </div>
    
    <!-- Error message -->
    <div id="errorMessage" class="error-message">
      <i class="fas fa-exclamation-circle"></i> <span id="errorText"></span>
    </div>
    
    <!-- Image gallery -->
    <div id="imagesContainer" class="images-container"></div>
    
    <!-- Negative Prompt Modal -->
    <div id="negativePromptModal" class="settings-modal">
      <div class="settings-modal-content">
        <button class="close-modal" id="closeNegativePromptModal"><i class="fas fa-times"></i></button>
        <h3 class="settings-modal-title"><i class="fas fa-ban"></i> Negative Prompt</h3>
        <p style="font-size: 0.8rem; margin-bottom: 10px; color: #ccc;">Specify what elements you want to avoid in your image</p>
        <div class="form-group">
          <input type="text" id="negativePromptInput" class="parameter-input" placeholder="E.g. blurry, distorted, low quality, bad anatomy">
        </div>
        <div class="btn-container">
          <button id="applyNegativePromptBtn" class="btn btn-primary">
            <i class="fas fa-check"></i> Apply
          </button>
        </div>
      </div>
    </div>
    
    <!-- Style Modal -->
    <div id="styleModal" class="settings-modal">
      <div class="settings-modal-content">
        <button class="close-modal" id="closeStyleModal"><i class="fas fa-times"></i></button>
        <h3 class="settings-modal-title"><i class="fas fa-paint-brush"></i> Style Settings</h3>
        <p style="font-size: 0.8rem; margin-bottom: 10px; color: #ccc;">Choose an artistic style for your generated images</p>
        <div class="form-group">
          <select id="styleSelect" class="parameter-input">
            <option value="none">No specific style</option>
            <option value="abstract">Abstract</option>
            <option value="abstract-expressionism">Abstract Expressionism</option>
            <option value="analog-film">Analog Film</option>
            <option value="anime">Anime</option>
            <option value="art-deco">Art Deco</option>
            <option value="art-nouveau">Art Nouveau</option>
            <option value="baroque">Baroque</option>
            <option value="bauhaus">Bauhaus</option>
            <option value="carbon-pencil">Carbon Pencil</option>
            <option value="charcoal-drawing">Charcoal Drawing</option>
            <option value="children-book-illustration">Children's Book Illustration</option>
            <option value="cinematic">Cinematic</option>
            <option value="clean">Clean</option>
            <option value="colorful">Colorful</option>
            <option value="comic-book">Comic Book</option>
            <option value="conceptual">Conceptual</option>
            <option value="constructivism">Constructivism</option>
            <option value="cubism">Cubism</option>
            <option value="cyberpunk">Cyberpunk</option>
            <option value="dadaism">Dadaism</option>
            <option value="dark-fantasy">Dark Fantasy</option>
            <option value="dark-moody">Dark & Moody</option>
            <option value="digital-art">Digital Art</option>
            <option value="dmt-art">DMT Art</option>
            <option value="documentary">Documentary</option>
            <option value="doodle">Doodle</option>
            <option value="dots">Dots</option>
            <option value="dreamscape">Dreamscape</option>
            <option value="expressionism">Expressionism</option>
            <option value="fantasy-art">Fantasy Art</option>
            <option value="fauvism">Fauvism</option>
            <option value="film-noir">Film Noir</option>
            <option value="flat-2d">Flat 2D</option>
            <option value="flat-illustration">Flat Illustration</option>
            <option value="folk-art">Folk Art</option>
            <option value="futurism">Futurism</option>
            <option value="glitch-art">Glitch Art</option>
            <option value="glow-in-the-dark">Glow in the Dark</option>
            <option value="gothic">Gothic</option>
            <option value="graffiti">Graffiti</option>
            <option value="gouache">Gouache</option>
            <option value="horror">Horror</option>
            <option value="hyperrealism">Hyperrealism</option>
            <option value="impressionism">Impressionism</option>
            <option value="ink-drawing">Ink Drawing</option>
            <option value="isometric">Isometric</option>
            <option value="japanese-art">Japanese Art</option>
            <option value="knolling">Knolling</option>
            <option value="line-art">Line Art</option>
            <option value="logo-design">Logo Design</option>
            <option value="low-poly">Low Poly</option>
            <option value="macro-photography">Macro Photography</option>
            <option value="magical-realism">Magical Realism</option>
            <option value="manga">Manga</option>
            <option value="marker-drawing">Marker Drawing</option>
            <option value="medieval">Medieval</option>
            <option value="minimalism">Minimalism</option>
            <option value="modernism">Modernism</option>
            <option value="nature">Nature</option>
            <option value="neo-baroque">Neo-Baroque</option>
            <option value="neon-punk">Neon Punk</option>
            <option value="neo-expressionism">Neo-Expressionism</option>
            <option value="neo-futurism">Neo-Futurism</option>
            <option value="neo-impressionism">Neo-Impressionism</option>
            <option value="neo-rococo">Neo-Rococo</option>
            <option value="oil-painting">Oil Painting</option>
            <option value="origami">Origami</option>
            <option value="paper-marbling">Paper Marbling</option>
            <option value="paper-mache">Paper Mache</option>
            <option value="pastels">Pastels</option>
            <option value="pattern">Pattern</option>
            <option value="pencil-drawing">Pencil Drawing</option>
            <option value="photographic">Photographic</option>
            <option value="photorealism">Photorealism</option>
            <option value="pixel-art">Pixel Art</option>
            <option value="pointillism">Pointillism</option>
            <option value="pop-art">Pop Art</option>
            <option value="post-apocalyptic">Post-Apocalyptic</option>
            <option value="post-impressionism">Post-Impressionism</option>
            <option value="poster-art">Poster Art</option>
            <option value="primitive">Primitive</option>
            <option value="printmaking">Printmaking</option>
            <option value="psychedelic">Psychedelic</option>
            <option value="realism">Realism</option>
            <option value="renaissance">Renaissance</option>
            <option value="retro">Retro</option>
            <option value="rococo">Rococo</option>
            <option value="sci-fi">Sci-Fi</option>
            <option value="silhouette">Silhouette</option>
            <option value="splash-art">Splash Art</option>
            <option value="stained-glass">Stained Glass</option>
            <option value="steampunk">Steampunk</option>
            <option value="sticker-design">Sticker Design</option>
            <option value="still-life">Still Life</option>
            <option value="street-art">Street Art</option>
            <option value="surrealism">Surrealism</option>
            <option value="symbolic">Symbolic</option>
            <option value="synthwave">Synthwave</option>
            <option value="technical-drawing">Technical Drawing</option>
            <option value="terragen">Terragen</option>
            <option value="tilt-shift">Tilt-Shift</option>
            <option value="typography">Typography</option>
            <option value="ukiyo-e">Ukiyo-e</option>
            <option value="vaporwave">Vaporwave</option>
            <option value="vector-art">Vector Art</option>
            <option value="vintage">Vintage</option>
            <option value="watercolor">Watercolor</option>
            <option value="zentangle">Zentangle</option>
            <option value="3d-model">3D Model</option>
            <option value="3d-render">3D Render</option>
            <option value="8-bit">8-bit</option>
            <option value="16-bit">16-bit</option>
            <option value="concept-art">Concept Art</option>
          </select>
        </div>
        <div class="btn-container">
          <button id="applyStyleBtn" class="btn btn-primary">
            <i class="fas fa-check"></i> Apply
          </button>
        </div>
      </div>
    </div>
    
    <!-- Dimensions Modal -->
    <div id="dimensionsModal" class="settings-modal">
      <div class="settings-modal-content">
        <button class="close-modal" id="closeDimensionsModal"><i class="fas fa-times"></i></button>
        <h3 class="settings-modal-title"><i class="fas fa-crop-alt"></i> Image Dimensions</h3>
        <p style="font-size: 0.8rem; margin-bottom: 10px; color: #ccc;">Select the aspect ratio for your generated images</p>
        <div class="form-group">
          <select id="aspectRatioSelect" class="parameter-input">
            <option value="1:1">Square (1:1)</option>
            <option value="3:2">Standard Photo (3:2)</option>
            <option value="4:3">Standard (4:3)</option>
            <option value="16:9">Widescreen (16:9)</option>
            <option value="9:16" selected>Portrait (9:16)</option>
            <option value="21:9">Ultrawide (21:9)</option>
          </select>
        </div>
        <div class="btn-container">
          <button id="applyDimensionsBtn" class="btn btn-primary">
            <i class="fas fa-check"></i> Apply
          </button>
        </div>
      </div>
    </div>
    
    <!-- AI Model Modal -->
    <div id="modelModal" class="settings-modal">
      <div class="settings-modal-content">
        <button class="close-modal" id="closeModelModal"><i class="fas fa-times"></i></button>
        <h3 class="settings-modal-title"><i class="fas fa-robot"></i> AI Model</h3>
        <p style="font-size: a0.8rem; margin-bottom: 10px; color: #ccc;">Select the AI model to use for image generation</p>
        <div class="form-group">
          <select id="modelSelect" class="parameter-input">
            <option value="pollinations">Pollinations.AI</option>
          </select>
        </div>
        <div class="btn-container">
          <button id="applyModelBtn" class="btn btn-primary">
            <i class="fas fa-check"></i> Apply
          </button>
        </div>
      </div>
    </div>
    
    <!-- Count & Scale Modal -->
    <div id="countScaleModal" class="settings-modal">
      <div class="settings-modal-content">
        <button class="close-modal" id="closeCountScaleModal"><i class="fas fa-times"></i></button>
        <h3 class="settings-modal-title"><i class="fas fa-images"></i> Count & Scale</h3>
        <p style="font-size: 0.8rem; margin-bottom: 10px; color: #ccc;">Adjust how many images to generate and their scaling</p>
        
        <div class="form-group">
          <label class="parameter-label" for="imageCountInput"><i class="fas fa-images"></i> Number of Images</label>
          <div class="range-container">
            <input type="range" id="imageCountInput" min="1" max="9" value="4" step="1" class="parameter-input">
            <span id="imageCountValue" class="range-value">4</span>
          </div>
        </div>
        
        <div class="form-group">
          <label class="parameter-label" for="scaleInput"><i class="fas fa-expand-arrows-alt"></i> Image Scale</label>
          <div class="range-container">
            <input type="range" id="scaleInput" min="1" max="4" value="3" step="0.5" class="parameter-input">
            <span id="scaleValue" class="range-value">3.0</span>
          </div>
        </div>
        
        <div class="btn-container">
          <button id="applyCountScaleBtn" class="btn btn-primary">
            <i class="fas fa-check"></i> Apply
          </button>
        </div>
      </div>
    </div>
    
    <!-- Advanced Settings Modal -->
    <div id="advancedModal" class="settings-modal">
      <div class="settings-modal-content">
        <button class="close-modal" id="closeAdvancedModal"><i class="fas fa-times"></i></button>
        <h3 class="settings-modal-title"><i class="fas fa-sliders-h"></i> Advanced Settings</h3>
        <p style="font-size: 0.8rem; margin-bottom: 10px; color: #ccc;">Fine-tune advanced parameters for image generation</p>
        
        <div class="form-group">
          <label class="parameter-label" for="seedInput"><i class="fas fa-random"></i> Seed</label>
          <input type="number" id="seedInput" class="parameter-input" placeholder="Random" min="0">
        </div>
        
        <div class="form-group">
          <label class="parameter-label" for="qualitySelect"><i class="fas fa-star"></i> Quality</label>
          <select id="qualitySelect" class="parameter-input">
            <option value="standard">Standard</option>
            <option value="high" selected>High</option>
            <option value="premium">Premium</option>
          </select>
        </div>
        
        <div class="btn-container">
          <button id="applyAdvancedBtn" class="btn btn-primary">
            <i class="fas fa-check"></i> Apply
          </button>
        </div>
      </div>
    </div>
    
    <!-- Topaz Gigapixel AI Modal -->
    <div id="upscaleModal" class="modal">
      <div class="modal-content">
        <button class="close-modal" id="closeModalBtn"><i class="fas fa-times"></i></button>
        
        <!-- Topaz Gigapixel AI Logo and Header -->
        <div style="text-align: center; margin-bottom: 12px;">
          <svg class="topaz-logo" viewBox="0 0 380 70" xmlns="http://www.w3.org/2000/svg" style="height: 40px; margin-bottom: 5px;">
            <path d="M30 15h320c8.284 0 15 6.716 15 15v10c0 8.284-6.716 15-15 15H30c-8.284 0-15-6.716-15-15V30c0-8.284 6.716-15 15-15z" fill="#8A9199"/>
            <text x="190" y="40" font-family="Arial, sans-serif" font-size="22" font-weight="bold" fill="white" text-anchor="middle">TOPAZ GIGAPIXEL AI</text>
          </svg>
          <h2 style="margin-bottom: 5px; color: white; font-size: 1.1rem;">
            <i class="fas fa-expand"></i> Professional AI Upscaling
          </h2>
          <p style="font-size: 0.75rem; color: #ccc; margin-bottom: 8px;">Enhance image resolution and details with professional-grade AI technology</p>
        </div>
        
        <div class="topaz-options-container">
          <div class="form-group">
            <label for="upscaleFactorSelect"><i class="fas fa-search-plus"></i> Scale</label>
            <select id="upscaleFactorSelect">
              <option value="0.5">0.5x - Downscale</option>
              <option value="2">2x - Moderate Enhancement</option>
              <option value="4" selected>4x - HD Upscaling</option>
              <option value="6">6x - Ultra HD Upscaling</option>
            </select>
          </div>
          
          <div class="form-group">
            <label for="upscaleModelSelect"><i class="fas fa-microchip"></i> AI Model</label>
            <select id="upscaleModelSelect">
              <option value="standard" selected>Standard - Balanced processing</option>
              <option value="highFidelity">High Fidelity - Maximum detail</option>
              <option value="archival">Archival - For old photos</option>
              <option value="natural">Natural - Photorealistic results</option>
            </select>
          </div>
        </div>
        
        <div class="form-row">
          <div class="form-group half">
            <label><i class="fas fa-sliders-h"></i> Enhancement Options</label>
            <div class="checkbox-container">
              <input type="checkbox" id="removeNoiseCheck" checked>
              <label for="removeNoiseCheck" style="display: inline; margin: 0;">Remove Noise</label>
            </div>
            <div class="checkbox-container">
              <input type="checkbox" id="removeBlurCheck" checked>
              <label for="removeBlurCheck" style="display: inline; margin: 0;">Remove Blur</label>
            </div>
          </div>
          
          <div class="form-group half">
            <label><i class="fas fa-cog"></i> Advanced Options</label>
            <div class="checkbox-container">
              <input type="checkbox" id="faceRefineCheck" checked>
              <label for="faceRefineCheck" style="display: inline; margin: 0;">Face Refinement</label>
            </div>
            <div class="checkbox-container">
              <input type="checkbox" id="colorStabilityCheck">
              <label for="colorStabilityCheck" style="display: inline; margin: 0;">Color Stability</label>
            </div>
          </div>
        </div>
        
        <div id="upscaleProgress" class="upscale-progress" style="display: none;">
          <p><i class="fas fa-cog fa-spin"></i> Processing with Topaz Gigapixel AI...</p>
          <div class="progress-bar">
            <div id="progressBarFill" class="progress-bar-fill"></div>
          </div>
          <p id="progressPercentage">0%</p>
          <p id="processingStage" style="font-size: 0.75rem; color: #bbb; margin-top: 5px;">Analyzing image details...</p>
        </div>
        
        <div id="imageComparison" class="image-comparison">
          <div class="image-container">
            <div class="image-label">Original Image</div>
            <img id="originalImage" src="" alt="Original image">
          </div>
          <div class="image-container">
            <div class="image-label">Upscaled with <span class="topaz-badge">Topaz Gigapixel AI</span></div>
            <img id="upscaledImage" src="" alt="Upscaled image">
          </div>
        </div>
        
        <div class="btn-container">
          <button id="startUpscaleBtn" class="btn btn-primary">
            <i class="fas fa-magic"></i> Start Upscaling
          </button>
          <button id="downloadUpscaledBtn" class="btn btn-secondary" style="display: none;">
            <i class="fas fa-download"></i> Download Image
          </button>
        </div>
      </div>
    </div>
    
    <!-- Fullscreen Image Container -->
    <div id="fullscreenContainer" class="modal" style="background-color: rgba(0, 0, 0, 0.9); z-index: 1100;">
      <img id="fullscreenImage" class="fullscreen-image">
    </div>
    
    <!-- Download Animation Overlay -->
    <div id="downloadOverlay" class="download-overlay">
      <div class="download-animation">
        <i class="fas fa-download"></i>
      </div>
      <p class="download-message">Downloading your image...</p>
    </div>
  </div>
  
  <script>
    // DOM Elements
    const promptInput = document.getElementById('promptInput');
    const negativePromptInput = document.getElementById('negativePromptInput');
    const styleSelect = document.getElementById('styleSelect');
    const modelSelect = document.getElementById('modelSelect');
    const imageCountInput = document.getElementById('imageCountInput');
    const imageCountValue = document.getElementById('imageCountValue');
    const scaleInput = document.getElementById('scaleInput');
    const scaleValue = document.getElementById('scaleValue');
    const aspectRatioSelect = document.getElementById('aspectRatioSelect');
    const seedInput = document.getElementById('seedInput');
    const qualitySelect = document.getElementById('qualitySelect');
    const generateBtn = document.getElementById('generateBtn');
    const randomPromptBtn = document.getElementById('randomPromptBtn');
    const resetBtn = document.getElementById('resetBtn');
    const loadingIndicator = document.getElementById('loadingIndicator');
    const errorMessage = document.getElementById('errorMessage');
    const errorText = document.getElementById('errorText');
    const imagesContainer = document.getElementById('imagesContainer');
    const promptHistoryList = document.getElementById('promptHistoryList');
    const clearHistoryBtn = document.getElementById('clearHistoryBtn');
    const recallLastPromptBtn = document.getElementById('recallLastPromptBtn');
    const downloadOverlay = document.getElementById('downloadOverlay');
    
    // Settings Buttons
    const negativePromptBtn = document.getElementById('negativePromptBtn');
    const styleBtn = document.getElementById('styleBtn');
    const dimensionsBtn = document.getElementById('dimensionsBtn');
    const modelBtn = document.getElementById('modelBtn');
    const countScaleBtn = document.getElementById('countScaleBtn');
    const advancedBtn = document.getElementById('advancedBtn');
    
    // Modals
    const negativePromptModal = document.getElementById('negativePromptModal');
    const styleModal = document.getElementById('styleModal');
    const dimensionsModal = document.getElementById('dimensionsModal');
    const modelModal = document.getElementById('modelModal');
    const countScaleModal = document.getElementById('countScaleModal');
    const advancedModal = document.getElementById('advancedModal');
    const upscaleModal = document.getElementById('upscaleModal');
    
    // Close Buttons
    const closeNegativePromptModal = document.getElementById('closeNegativePromptModal');
    const closeStyleModal = document.getElementById('closeStyleModal');
    const closeDimensionsModal = document.getElementById('closeDimensionsModal');
    const closeModelModal = document.getElementById('closeModelModal');
    const closeCountScaleModal = document.getElementById('closeCountScaleModal');
    const closeAdvancedModal = document.getElementById('closeAdvancedModal');
    
    // Apply Buttons
    const applyNegativePromptBtn = document.getElementById('applyNegativePromptBtn');
    const applyStyleBtn = document.getElementById('applyStyleBtn');
    const applyDimensionsBtn = document.getElementById('applyDimensionsBtn');
    const applyModelBtn = document.getElementById('applyModelBtn');
    const applyCountScaleBtn = document.getElementById('applyCountScaleBtn');
    const applyAdvancedBtn = document.getElementById('applyAdvancedBtn');
    
    // Upscale Modal Elements
    const closeModalBtn = document.getElementById('closeModalBtn');
    const upscaleFactorSelect = document.getElementById('upscaleFactorSelect');
    const upscaleModelSelect = document.getElementById('upscaleModelSelect');
    const removeNoiseCheck = document.getElementById('removeNoiseCheck');
    const removeBlurCheck = document.getElementById('removeBlurCheck');
    const faceRefineCheck = document.getElementById('faceRefineCheck');
    const colorStabilityCheck = document.getElementById('colorStabilityCheck');
    const originalImage = document.getElementById('originalImage');
    const upscaledImage = document.getElementById('upscaledImage');
    const startUpscaleBtn = document.getElementById('startUpscaleBtn');
    const downloadUpscaledBtn = document.getElementById('downloadUpscaledBtn');
    const upscaleProgress = document.getElementById('upscaleProgress');
    const progressBarFill = document.getElementById('progressBarFill');
    const progressPercentage = document.getElementById('progressPercentage');
    const processingStage = document.getElementById('processingStage');
    
    // Fullscreen Elements
    const fullscreenContainer = document.getElementById('fullscreenContainer');
    const fullscreenImage = document.getElementById('fullscreenImage');
    
    // Variables to store current image for upscaling
    let currentUpscaleImage = null;
    
    // Prompt History Array
    let promptHistory = [];
    
    // pollinationsAIImageGen
    let styles = [
      "renaissance", "baroque", "cyberpunk", "anime", "studio ghibli", "pixel art", 
      "oil painting", "watercolor", "impasto", "3D render", "glitch art", "vaporwave", 
      "ukiyo-e", "chinese brush painting", "surrealism", "dystopian", "fashion editorial"
    ];

    let subjects = [
      "woman in red dress", "white horse", "ancient warrior", "city at night", 
      "mystical forest", "cyborg girl", "k-pop singer", "royal cat", "desert traveler"
    ];

    let lighting = [
      "cinematic light", "soft lighting", "backlight", "glow", "low light", "foggy"
    ];

    // Function to randomly select an item from an array
    function random(array) {
      return array[Math.floor(Math.random() * array.length)];
    }

    // Function to generate a random prompt
    function generateRandomPrompt() {
      // Construct the prompt
      let style = random(styles);
      let subject = random(subjects);
      let light = random(lighting);

      return `${subject}, in style of ${style}, ${light}`;
    }

    // Event listener for random prompt button
    randomPromptBtn.addEventListener('click', () => {
      promptInput.value = generateRandomPrompt();
      autoResizeTextarea(promptInput);
    });
    
    // Open/Close Modal Functions
    function openModal(modal) {
      modal.style.display = 'flex';
    }
    
    function closeModal(modal) {
      modal.style.display = 'none';
    }
    
    // Settings Button Event Listeners
    negativePromptBtn.addEventListener('click', () => openModal(negativePromptModal));
    styleBtn.addEventListener('click', () => openModal(styleModal));
    dimensionsBtn.addEventListener('click', () => openModal(dimensionsModal));
    modelBtn.addEventListener('click', () => openModal(modelModal));
    countScaleBtn.addEventListener('click', () => openModal(countScaleModal));
    advancedBtn.addEventListener('click', () => openModal(advancedModal));
    
    // Close Button Event Listeners
    closeNegativePromptModal.addEventListener('click', () => closeModal(negativePromptModal));
    closeStyleModal.addEventListener('click', () => closeModal(styleModal));
    closeDimensionsModal.addEventListener('click', () => closeModal(dimensionsModal));
    closeModelModal.addEventListener('click', () => closeModal(modelModal));
    closeCountScaleModal.addEventListener('click', () => closeModal(countScaleModal));
    closeAdvancedModal.addEventListener('click', () => closeModal(advancedModal));
    
    // Apply Button Event Listeners
    applyNegativePromptBtn.addEventListener('click', () => closeModal(negativePromptModal));
    applyStyleBtn.addEventListener('click', () => closeModal(styleModal));
    applyDimensionsBtn.addEventListener('click', () => closeModal(dimensionsModal));
    applyModelBtn.addEventListener('click', () => closeModal(modelModal));
    applyCountScaleBtn.addEventListener('click', () => closeModal(countScaleModal));
    applyAdvancedBtn.addEventListener('click', () => closeModal(advancedModal));
    
    // Close modals when clicking outside
    window.addEventListener('click', (event) => {
      if (event.target === negativePromptModal) closeModal(negativePromptModal);
      if (event.target === styleModal) closeModal(styleModal);
      if (event.target === dimensionsModal) closeModal(dimensionsModal);
      if (event.target === modelModal) closeModal(modelModal);
      if (event.target === countScaleModal) closeModal(countScaleModal);
      if (event.target === advancedModal) closeModal(advancedModal);
      if (event.target === fullscreenContainer) closeModal(fullscreenContainer);
    });
    
    // Function to auto-resize textarea
    function autoResizeTextarea(textarea) {
      textarea.style.height = 'auto'; // Reset height to recalculate
      textarea.style.height = textarea.scrollHeight + 'px'; // Set to scroll height
    }
    
    // Add event listener to prompt input for auto-resize
    promptInput.addEventListener('input', function() {
      autoResizeTextarea(this);
    });
    
    // Update range input values
    imageCountInput.addEventListener('input', () => {
      imageCountValue.textContent = imageCountInput.value;
    });
    
    scaleInput.addEventListener('input', () => {
      scaleValue.textContent = scaleInput.value;
    });
    
    // Reset form
    resetBtn.addEventListener('click', () => {
      promptInput.value = '';
      negativePromptInput.value = '';
      styleSelect.value = 'none';
      modelSelect.value = 'pollinations';
      imageCountInput.value = 4;
      imageCountValue.textContent = '4';
      scaleInput.value = 3;
      scaleValue.textContent = '3.0';
      aspectRatioSelect.value = '9:16';
      seedInput.value = '';
      qualitySelect.value = 'high';
      errorMessage.style.display = 'none';
      
      // Reset textarea height
      promptInput.style.height = '70px';
    });
    
    // Generate images
    generateBtn.addEventListener('click', async () => {
      // Validate input
      if (!promptInput.value.trim()) {
        showError('Please enter a prompt to generate images.');
        return;
      }
      
      // Add to prompt history
      addPromptToHistory(
        promptInput.value.trim(),
        negativePromptInput.value.trim(),
        styleSelect.value
      );
      
      // Show loading indicator
      loadingIndicator.style.display = 'block';
      imagesContainer.innerHTML = '';
      errorMessage.style.display = 'none';
      generateBtn.disabled = true;
      
      try {
        // Get form values
        const prompt = promptInput.value.trim();
        const negativePrompt = negativePromptInput.value.trim();
        const stylePreset = styleSelect.value;
        const model = modelSelect.value;
        const imageCount = parseInt(imageCountInput.value);
        const scale = parseFloat(scaleInput.value);
        const aspectRatio = aspectRatioSelect.value;
        const quality = qualitySelect.value;
        const seed = seedInput.value ? parseInt(seedInput.value) : Math.floor(Math.random() * 1000000);
        
        // Get dimensions based on aspect ratio
        const dimensions = getImageDimensions(aspectRatio);
        
        // Generate images
        const images = await generateImages(prompt, negativePrompt, stylePreset, model, imageCount, dimensions, seed, quality);
        
        // Display generated images
        displayImages(images, prompt, scale, model);
      } catch (error) {
        showError('Error generating images. Please try again later.');
        console.error('Error:', error);
      } finally {
        // Hide loading indicator
        loadingIndicator.style.display = 'none';
        generateBtn.disabled = false;
      }
    });
    
    // Get image dimensions based on aspect ratio
    function getImageDimensions(aspectRatio) {
      const [width, height] = aspectRatio.split(':').map(Number);
      const ratio = width / height;
      
      // Base size around 1024 pixels for standard quality
      if (ratio > 1) {
        // Landscape
        return { width: Math.round(1024), height: Math.round(1024 / ratio) };
      } else {
        // Portrait or square
        return { width: Math.round(1024 * ratio), height: Math.round(1024) };
      }
    }
    
    // Show error message
    function showError(message) {
      errorText.textContent = message;
      errorMessage.style.display = 'block';
    }
    
    // Generate images using selected AI Model
    async function generateImages(prompt, negativePrompt, style, model, count, dimensions, seed, quality) {
      // Simulate API delay
      await new Promise(resolve => setTimeout(resolve, 1500));
      
      // Create an array of image results
      const images = [];
      
      for (let i = 0; i < count; i++) {
        const currentSeed = seed + i;
        let imageUrl;
        
        // Construct the full prompt with style if specified
        let fullPrompt = prompt;
        if (style && style !== 'none') {
          // Fix: Convert dash-case to normal text for style description
          const styleText = style.replace(/-/g, ' ');
          fullPrompt += `, ${styleText} style`;
        }
        
        // Build URL parameters
        let urlParams = `width=${dimensions.width}&height=${dimensions.height}&seed=${currentSeed}&nologo=true`;
        
        // Add negative prompt if specified
        if (negativePrompt) {
          urlParams += `&negative=${encodeURIComponent(negativePrompt)}`;
        }
        
        // Add quality parameter if specified
        if (quality && quality !== 'standard') {
          urlParams += `&quality=${quality}`;
        }
        
        // Use Pollinations.AI with HTTPS and include all parameters
        imageUrl = `https://image.pollinations.ai/prompt/${encodeURIComponent(fullPrompt)}?${urlParams}`;
        
        images.push({
          url: imageUrl,
          prompt: fullPrompt,
          seed: currentSeed,
          dimensions,
          model
        });
      }
      
      return images;
    }
    
    // Display generated images
    function displayImages(images, prompt, scale, model) {
      imagesContainer.innerHTML = '';
      
      images.forEach((image, index) => {
        const imageCard = document.createElement('div');
        imageCard.className = 'image-card';
        
        const img = document.createElement('img');
        img.src = image.url;
        img.alt = `Generated image ${index + 1}: ${prompt}`;
        img.loading = 'lazy';
        
        // Add click event to open fullscreen view
        img.addEventListener('click', function() {
          openFullscreen(this.src);
        });
        
        const actions = document.createElement('div');
        actions.className = 'actions';
        
        // Model badge
        const modelBadge = document.createElement('span');
        modelBadge.className = `model-badge ${image.model}`;
        modelBadge.textContent = getModelDisplayName(image.model);
        
        // Download button
        const downloadBtn = document.createElement('button');
        downloadBtn.className = 'image-action';
        downloadBtn.innerHTML = '<i class="fas fa-download"></i>';
        downloadBtn.title = 'Download image';
        downloadBtn.onclick = (e) => {
          e.stopPropagation(); // Prevent triggering the parent's click event
          downloadImage(image.url, `rai-ig-${image.model}-${image.seed}.jpg`);
        };
        
        // Upscale button
        const upscaleBtn = document.createElement('button');
        upscaleBtn.className = 'image-action';
        upscaleBtn.innerHTML = '<i class="fas fa-expand"></i>';
        upscaleBtn.title = 'Upscale with Topaz Gigapixel AI';
        upscaleBtn.onclick = (e) => {
          e.stopPropagation(); // Prevent triggering the parent's click event
          openUpscaleModal(image, scale);
        };
        
        // Add buttons to actions
        actions.appendChild(modelBadge);
        const actionButtons = document.createElement('div');
        actionButtons.style.display = 'flex';
        actionButtons.appendChild(downloadBtn);
        actionButtons.appendChild(upscaleBtn);
        actions.appendChild(actionButtons);
        
        // Add everything to the card
        imageCard.appendChild(img);
        imageCard.appendChild(actions);
        
        // Add card to container
        imagesContainer.appendChild(imageCard);
      });
      
      // Scroll to images
      imagesContainer.scrollIntoView({ behavior: 'smooth' });
    }
    
    // Open fullscreen image view
    function openFullscreen(imageSrc) {
      fullscreenImage.src = imageSrc;
      fullscreenContainer.style.display = 'flex';
      
      // Add event listener to exit fullscreen when the image is clicked
      fullscreenImage.addEventListener('click', exitFullscreenOnClick);
      
      // Add event listener to exit fullscreen when ESC key is pressed
      document.addEventListener('keydown', exitFullscreenOnEsc);
    }
    
    // Exit fullscreen when image is clicked
    function exitFullscreenOnClick(event) {
      // Stop event propagation to prevent the container's click handler from triggering
      event.stopPropagation();
      
      // Close the fullscreen view
      closeModal(fullscreenContainer);
      
      // Remove event listeners
      document.removeEventListener('keydown', exitFullscreenOnEsc);
      fullscreenImage.removeEventListener('click', exitFullscreenOnClick);
    }
    
    // Exit fullscreen when ESC key is pressed
    function exitFullscreenOnEsc(event) {
      if (event.key === 'Escape') {
        closeModal(fullscreenContainer);
        
        // Remove event listeners
        document.removeEventListener('keydown', exitFullscreenOnEsc);
        fullscreenImage.removeEventListener('click', exitFullscreenOnClick);
      }
    }
    
    // Get display name for model
    function getModelDisplayName(model) {
      return 'Pollinations.AI';
    }
    
    // Download image with animation
    async function downloadImage(url, filename) {
      try {
        // Show download animation
        downloadOverlay.style.display = 'flex';
        
        // Create a link element
        const a = document.createElement('a');
        a.href = url;
        a.download = filename;
        a.target = '_blank';
        document.body.appendChild(a);
        a.click();
        document.body.removeChild(a);
        
        // Wait for a short delay to show the animation
        await new Promise(resolve => setTimeout(resolve, 800));
        
        // Hide download animation
        downloadOverlay.style.display = 'none';
        
        // Close any open modals
        closeModal(upscaleModal);
      } catch (error) {
        // Hide download animation in case of error
        downloadOverlay.style.display = 'none';
        showError('Error downloading image. Please try again.');
        console.error('Download error:', error);
      }
    }
    
    // Open Topaz Gigapixel AI upscale modal
    function openUpscaleModal(image, scale) {
      // Store the current image for upscaling
      currentUpscaleImage = image;
      
      // Set the original image in the modal
      originalImage.src = image.url;
      upscaledImage.src = '';
      
      // Reset modal state
      upscaleProgress.style.display = 'none';
      startUpscaleBtn.style.display = 'block';
      downloadUpscaledBtn.style.display = 'none';
      
      // Reset checkboxes to default state
      removeNoiseCheck.checked = true;
      removeBlurCheck.checked = true;
      faceRefineCheck.checked = true;
      colorStabilityCheck.checked = false;
      
      // Show the modal
      upscaleModal.style.display = 'flex';
      
      // Set the default upscale factor based on the image scale
      upscaleFactorSelect.value = Math.min(6, Math.max(2, Math.round(scale * 2)));
    }
    
    // Close AI modal
    closeModalBtn.addEventListener('click', () => {
      upscaleModal.style.display = 'none';
    });
    
    // Window click to close modal
    window.addEventListener('click', (event) => {
      if (event.target === upscaleModal) {
        upscaleModal.style.display = 'none';
      }
    });
    
    // Start upscaling process with Topaz Gigapixel AI
    startUpscaleBtn.addEventListener('click', async () => {
      if (!currentUpscaleImage) {
        return;
      }
      
      // Get Topaz upscale settings
      const factor = parseFloat(upscaleFactorSelect.value);
      const model = upscaleModelSelect.value;
      const removeNoise = removeNoiseCheck.checked;
      const removeBlur = removeBlurCheck.checked;
      const faceRefine = faceRefineCheck.checked;
      const colorStability = colorStabilityCheck.checked;
      
      // Start upscaling process with Topaz Gigapixel AI
      await upscaleImageWithTopazGigapixelAI(currentUpscaleImage, factor, model, removeNoise, removeBlur, faceRefine, colorStability);
    });
    
    // Download upscaled image
    downloadUpscaledBtn.addEventListener('click', () => {
      if (upscaledImage.src) {
        downloadImage(upscaledImage.src, `topaz-upscaled-${currentUpscaleImage.seed}.jpg`);
      }
    });
    
    // Upscale image with Topaz Gigapixel AI (simulated)
    async function upscaleImageWithTopazGigapixelAI(image, factor, model, removeNoise, removeBlur, faceRefine, colorStability) {
      try {
        // Show progress and hide start button
        upscaleProgress.style.display = 'block';
        startUpscaleBtn.style.display = 'none';
        
        // Simulate Topaz Gigapixel AI processing with detailed stages
        const stages = [
          { percent: 10, message: "Analyzing image details..." },
          { percent: 20, message: "Calculating optimal parameters..." },
          { percent: 30, message: "Enhancing details..." },
          { percent: 50, message: "Applying neural processing..." },
          { percent: 60, message: "Reconstructing high-resolution data..." },
          { percent: 70, message: "Refining edges and textures..." },
          { percent: 80, message: removeNoise ? "Reducing noise artifacts..." : "Processing final details..." },
          { percent: 90, message: faceRefine ? "Enhancing facial features..." : "Finalizing image..." },
          { percent: 100, message: "Completing upscale process..." }
        ];
        
        // Process each stage with realistic timing
        for (let stage of stages) {
          // Update progress bar
          progressBarFill.style.width = `${stage.percent}%`;
          progressPercentage.textContent = `${stage.percent}%`;
          processingStage.textContent = stage.message;
          
          // Add delay to simulate processing time - varies based on complexity
          const delay = Math.random() * 300 + 200; // 200-500ms per stage
          await new Promise(resolve => setTimeout(resolve, delay));
        }
        
        // FIX: Instead of modifying the original URL which would change the image completely,
        // we'll use the exact same image URL for the upscaled version in this demo
        // This ensures the image doesn't change during upscaling
        upscaledImage.src = image.url;
        
        // Show download button
        downloadUpscaledBtn.style.display = 'block';
        
        // Hide progress after a short delay
        setTimeout(() => {
          upscaleProgress.style.display = 'none';
          processingStage.textContent = "Processing complete!";
        }, 500);
        
      } catch (error) {
        showError('Error during Topaz Gigapixel AI upscaling. Please try again.');
        console.error('Topaz upscale error:', error);
        upscaleProgress.style.display = 'none';
        startUpscaleBtn.style.display = 'block';
      }
    }
    
    // Prompt History Functions
    
    // Load prompt history from localStorage
    function loadPromptHistory() {
      const savedHistory = localStorage.getItem('xenopath_prompt_history');
      if (savedHistory) {
        try {
          promptHistory = JSON.parse(savedHistory);
          renderPromptHistory();
        } catch (error) {
          console.error('Error loading prompt history:', error);
          promptHistory = [];
        }
      }
    }
    
    // Save prompt history to localStorage
    function savePromptHistory() {
      try {
        localStorage.setItem('xenopath_prompt_history', JSON.stringify(promptHistory));
      } catch (error) {
        console.error('Error saving prompt history:', error);
        showError('Failed to save prompt history. Local storage might be full.');
      }
    }
    
    // Add prompt to history
    function addPromptToHistory(prompt, negativePrompt = '', style = 'none') {
      // Don't add empty prompts
      if (!prompt.trim()) return;
      
      // Create a history item with all relevant details
      const historyItem = {
        id: Date.now(), // Use timestamp as unique ID
        prompt,
        negativePrompt,
        style,
        timestamp: new Date().toISOString()
      };
      
      // Add to beginning of array (newest first)
      promptHistory.unshift(historyItem);
      
      // Limit history to 50 items
      if (promptHistory.length > 50) {
        promptHistory.pop();
      }
      
      // Save to localStorage and update UI
      savePromptHistory();
      renderPromptHistory();
      
      // Save last prompt to localStorage for quick recall
      localStorage.setItem('xenopath_last_prompt', JSON.stringify(historyItem));
    }
    
    // Render prompt history in the UI
    function renderPromptHistory() {
      promptHistoryList.innerHTML = '';
      
      if (promptHistory.length === 0) {
        promptHistoryList.innerHTML = '<div class="prompt-history-empty">No prompt history yet. Generate some images!</div>';
        return;
      }
      
      promptHistory.forEach(item => {
        const historyItem = document.createElement('div');
        historyItem.className = 'prompt-history-item';
        historyItem.dataset.id = item.id;
        
        const date = new Date(item.timestamp);
        const formattedDate = date.toLocaleDateString() + ' ' + date.toLocaleTimeString();
        
        historyItem.innerHTML = `
          <div class="prompt-history-text">${item.prompt}</div>
          ${item.negativePrompt ? `<div class="prompt-history-negative" style="color:#999;font-size:0.7rem;margin-top:2px;text-align:left;">Negative: ${item.negativePrompt}</div>` : ''}
          ${item.style !== 'none' ? `<div class="prompt-history-style" style="color:#999;font-size:0.7rem;margin-top:2px;text-align:left;">Style: ${item.style}</div>` : ''}
          <div class="prompt-history-date">${formattedDate}</div>
          <div class="prompt-history-actions">
            <button class="prompt-action-btn use-prompt-btn">
              <i class="fas fa-play"></i> Use
            </button>
            <button class="prompt-action-btn edit-prompt-btn">
              <i class="fas fa-edit"></i> Edit
            </button>
            <button class="prompt-action-btn copy-prompt-btn">
              <i class="fas fa-copy"></i> Copy
            </button>
            <button class="prompt-action-btn delete-prompt-btn">
              <i class="fas fa-trash-alt"></i> Delete
            </button>
          </div>
        `;
        
        // Add event listeners for buttons
        const usePromptBtn = historyItem.querySelector('.use-prompt-btn');
        const editPromptBtn = historyItem.querySelector('.edit-prompt-btn');
        const copyPromptBtn = historyItem.querySelector('.copy-prompt-btn');
        const deletePromptBtn = historyItem.querySelector('.delete-prompt-btn');
        
        usePromptBtn.addEventListener('click', () => usePromptFromHistory(item));
        editPromptBtn.addEventListener('click', () => switchToEditMode(historyItem, item));
        copyPromptBtn.addEventListener('click', () => copyPromptToClipboard(item));
        deletePromptBtn.addEventListener('click', () => deletePromptFromHistory(item.id));
        
        // Add click event on the prompt history item itself for quick recall
        historyItem.addEventListener('click', (e) => {
          // Only trigger if clicking on the item itself, not on buttons
          if (!e.target.closest('.prompt-history-actions')) {
            usePromptFromHistory(item);
          }
        });
        
        promptHistoryList.appendChild(historyItem);
      });
    }
    
    // Use a prompt from history
    function usePromptFromHistory(item) {
      promptInput.value = item.prompt;
      negativePromptInput.value = item.negativePrompt || '';
      styleSelect.value = item.style || 'none';
      
      // Auto-resize the prompt input
      autoResizeTextarea(promptInput);
      
      // Scroll to the prompt input
      promptInput.scrollIntoView({ behavior: 'smooth' });
      
      // Focus on the prompt input
      promptInput.focus();
    }
    
    // Switch to edit mode for a history item
    function switchToEditMode(historyItemElement, item) {
      // Create edit form
      const originalContent = historyItemElement.innerHTML;
      
      historyItemElement.innerHTML = `
        <textarea class="prompt-history-edit-area" placeholder="Enter prompt...">${item.prompt}</textarea>
        <input type="text" class="prompt-history-edit-negative" placeholder="Negative prompt (optional)" 
               value="${item.negativePrompt || ''}" style="width:100%;padding:6px;margin-top:5px;border-radius:8px;background:rgba(10,10,10,0.8);border:1px solid #666;color:white;font-size:0.75rem;">
        <select class="prompt-history-edit-style" style="width:100%;padding:6px;margin-top:5px;border-radius:8px;background:rgba(10,10,10,0.8);border:1px solid #666;color:white;font-size:0.75rem;">
          ${styleSelect.innerHTML}
        </select>
        <div class="editing-actions">
          <button class="editing-btn cancel-edit-btn">
            <i class="fas fa-times"></i> Cancel
          </button>
          <button class="editing-btn save-edit-btn">
            <i class="fas fa-check"></i> Save
          </button>
        </div>
      `;
      
      // Set the style select value
      const styleSelectEl = historyItemElement.querySelector('.prompt-history-edit-style');
      styleSelectEl.value = item.style || 'none';
      
      // Auto-resize the textarea
      const textarea = historyItemElement.querySelector('.prompt-history-edit-area');
      autoResizeTextarea(textarea);
      
      // Focus on the textarea
      textarea.focus();
      
      // Add event listeners for editing
      const cancelBtn = historyItemElement.querySelector('.cancel-edit-btn');
      const saveBtn = historyItemElement.querySelector('.save-edit-btn');
      
      cancelBtn.addEventListener('click', () => {
        historyItemElement.innerHTML = originalContent;
        
        // Re-add event listeners
        const usePromptBtn = historyItemElement.querySelector('.use-prompt-btn');
        const editPromptBtn = historyItemElement.querySelector('.edit-prompt-btn');
        const copyPromptBtn = historyItemElement.querySelector('.copy-prompt-btn');
        const deletePromptBtn = historyItemElement.querySelector('.delete-prompt-btn');
        
        usePromptBtn.addEventListener('click', () => usePromptFromHistory(item));
        editPromptBtn.addEventListener('click', () => switchToEditMode(historyItemElement, item));
        copyPromptBtn.addEventListener('click', () => copyPromptToClipboard(item));
        deletePromptBtn.addEventListener('click', () => deletePromptFromHistory(item.id));
        
        // Re-add click event on the prompt history item itself
        historyItemElement.addEventListener('click', (e) => {
          if (!e.target.closest('.prompt-history-actions')) {
            usePromptFromHistory(item);
          }
        });
      });
      
      saveBtn.addEventListener('click', () => {
        const newPrompt = textarea.value.trim();
        const newNegativePrompt = historyItemElement.querySelector('.prompt-history-edit-negative').value.trim();
        const newStyle = historyItemElement.querySelector('.prompt-history-edit-style').value;
        
        if (newPrompt) {
          // Update the history item
          const index = promptHistory.findIndex(it => it.id === item.id);
          if (index !== -1) {
            promptHistory[index].prompt = newPrompt;
            promptHistory[index].negativePrompt = newNegativePrompt;
            promptHistory[index].style = newStyle;
            
            // Save to localStorage and re-render
            savePromptHistory();
            renderPromptHistory();
            
            // If this was the last used prompt, update that in localStorage too
            const lastPrompt = JSON.parse(localStorage.getItem('xenopath_last_prompt') || '{}');
            if (lastPrompt.id === item.id) {
              localStorage.setItem('xenopath_last_prompt', JSON.stringify(promptHistory[index]));
            }
          }
        }
      });
    }
    
    // Copy a prompt to clipboard
    function copyPromptToClipboard(item) {
      // Create a text representation of the prompt
      let textToCopy = item.prompt;
      
      if (item.negativePrompt) {
        textToCopy += '\n\nNegative prompt: ' + item.negativePrompt;
      }
      
      if (item.style && item.style !== 'none') {
        textToCopy += '\n\nStyle: ' + item.style;
      }
      
      // Use the Clipboard API if available
      if (navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(textToCopy)
          .then(() => {
            showCopiedMessage();
          })
          .catch(err => {
            console.error('Failed to copy prompt: ', err);
            showError('Failed to copy to clipboard. Your browser may not support this feature.');
          });
      } else {
        // Fallback method
        const textarea = document.createElement('textarea');
        textarea.value = textToCopy;
        textarea.style.position = 'fixed';
        document.body.appendChild(textarea);
        textarea.focus();
        textarea.select();
        
        try {
          const successful = document.execCommand('copy');
          if (successful) {
            showCopiedMessage();
          } else {
            showError('Failed to copy to clipboard. Your browser may not support this feature.');
          }
        } catch (err) {
          console.error('Failed to copy prompt: ', err);
          showError('Failed to copy to clipboard. Your browser may not support this feature.');
        }
        
        document.body.removeChild(textarea);
      }
    }
    
    // Show a copied success message
    function showCopiedMessage() {
      // Create or get the message element
      let messageEl = document.getElementById('copiedMessage');
      
      if (!messageEl) {
        messageEl = document.createElement('div');
        messageEl.id = 'copiedMessage';
        messageEl.style.cssText = 'position:fixed;bottom:20px;right:20px;background:rgba(0,150,0,0.8);color:white;padding:10px;border-radius:8px;font-size:0.8rem;z-index:1000;transition:all 0.3s ease;opacity:0;';
        messageEl.innerHTML = '<i class="fas fa-check-circle"></i> Copied to clipboard!';
        document.body.appendChild(messageEl);
      }
      
      // Show and then hide the message
      messageEl.style.opacity = '1';
      setTimeout(() => {
        messageEl.style.opacity = '0';
      }, 2000);
    }
    
    // Delete a prompt from history
    function deletePromptFromHistory(id) {
      // If this is the last prompt, remove it from localStorage
      const lastPrompt = JSON.parse(localStorage.getItem('xenopath_last_prompt') || '{}');
      if (lastPrompt.id === id) {
        localStorage.removeItem('xenopath_last_prompt');
      }
      
      promptHistory = promptHistory.filter(item => item.id !== id);
      savePromptHistory();
      renderPromptHistory();
    }
    
    // Clear all prompt history
    function clearPromptHistory() {
      if (confirm('Are you sure you want to clear all prompt history?')) {
        promptHistory = [];
        localStorage.removeItem('xenopath_last_prompt');
        savePromptHistory();
        renderPromptHistory();
      }
    }
    
    // Event listener for clearing all history
    clearHistoryBtn.addEventListener('click', clearPromptHistory);
    
    // Event listener for recalling last prompt
    recallLastPromptBtn.addEventListener('click', () => {
      const lastPrompt = localStorage.getItem('xenopath_last_prompt');
      if (lastPrompt) {
        try {
          const lastPromptObj = JSON.parse(lastPrompt);
          promptInput.value = lastPromptObj.prompt || '';
          negativePromptInput.value = lastPromptObj.negativePrompt || '';
          styleSelect.value = lastPromptObj.style || 'none';
          autoResizeTextarea(promptInput);
          
          // Scroll to the prompt input
          promptInput.scrollIntoView({ behavior: 'smooth' });
          
          // Focus on the prompt input
          promptInput.focus();
        } catch (error) {
          console.error('Error loading last prompt:', error);
          showError('Failed to recall last prompt. It may be corrupted.');
        }
      } else {
        showError('No previous prompt to recall.');
      }
    });
    
    // Initialize
    window.addEventListener('DOMContentLoaded', () => {
      // Set default values
      scaleValue.textContent = scaleInput.value;
      // Initialize textarea auto-resize
      autoResizeTextarea(promptInput);
      // Load prompt history
      loadPromptHistory();
      
      // Try to load last prompt from localStorage
      const lastPrompt = localStorage.getItem('xenopath_last_prompt');
      if (lastPrompt) {
        try {
          const lastPromptObj = JSON.parse(lastPrompt);
          promptInput.value = lastPromptObj.prompt || '';
          negativePromptInput.value = lastPromptObj.negativePrompt || '';
          styleSelect.value = lastPromptObj.style || 'none';
          autoResizeTextarea(promptInput);
        } catch (error) {
          console.error('Error loading last prompt:', error);
        }
      }
    });
  </script>
</body>
</html># xeno-path1
