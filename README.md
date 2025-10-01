# Guttedpossum Staking Solutions (GPSS) Website

## Overview

This repository contains the source code for the Guttedpossum Staking Solutions (GPSS) website, hosted at [rubioberry.com](http://rubioberry.com). GPSS provides a simple platform for staking Ethereum with a 3.1% APY, including features for wallet integration, real-time Ethereum block data, and a contact form. The site features dynamic, AI-generated background videos (created with MidJourney) that loop at 30% opacity, blended with royal blue or cyan backgrounds for an immersive user experience.

The website consists of three main pages:
- **index.html**: Home page with staking overview and latest Ethereum block info.
- **staking.html**: Staking interface for selecting terms and amounts, with MetaMask wallet integration.
- **contact.html**: Contact form for user inquiries.

## Features

- **Staking Functionality**: Users can connect their MetaMask wallet and stake Ethereum for 3, 6, or 12 months at 3.1% APY. Rewards are paid in ETH, with compensation in $RBR coin (RubioBerry) for any downtime.
- **Real-Time Data**: Fetches the latest Ethereum block data from the Beaconcha API on the home page.
- **Contact Form**: Uses Formspree for email submissions.
- **Background Videos**: Each page has a looping MP4 video at 30% opacity:
  - `BACKGROUND.mp4` on home (royal blue background, #4169E1).
  - `STAKING.mp4` on staking (royal blue background, #4169E1).
  - `CONTACT.mp4` on contact (cyan blue background, #00CED1).
  Videos are AI-generated (e.g., coin gaming machine themes) and optimized for web (H.264 codec, 1-3MB size, 5-10 seconds duration).
- **Responsive Design**: Uses flexbox and tables for centering content, with semi-transparent overlays for readability.
- **iOS Compatibility**: Includes `playsinline` attribute and JavaScript fallback for video autoplay on iPhones.
- **Disclaimer**: Highlights risks associated with crypto staking.

## Technologies Used

- **HTML5 & CSS3**: For structure and styling.
- **JavaScript**: For API fetches, wallet integration (via MetaMask), and video playback handling.
- **External APIs**:
  - Beaconcha API for Ethereum block data.
  - Formspree for contact form submissions.
- **Video Optimization**: MP4 files compressed with tools like HandBrake or FFmpeg for fast loading.
- **No Frameworks**: Pure vanilla code for simplicity and performance.

## Installation & Setup

1. **Clone the Repository**:
   ```
   git clone https://github.com/your-username/gpss-website.git
   ```

2. **File Structure**:
   ```
   gpss-website/
   ├── index.html          # Home page
   ├── staking.html        # Staking page
   ├── contact.html        # Contact page
   ├── styles.css          # Shared stylesheet
   ├── BACKGROUND.mp4      # Background video for index.html
   ├── STAKING.mp4         # Background video for staking.html
   ├── CONTACT.mp4         # Background video for contact.html
   └── README.md           # This file
   ```

3. **Place Videos**: Ensure the MP4 files are in the root directory. Compress them to under 5MB if needed (see Optimization section).

4. **Host the Site**:
   - Use a web server like GitHub Pages, Vercel, or a local server (e.g., `python -m http.server`).
   - Update absolute paths if hosting in a subfolder.

5. **Dependencies**:
   - No external libraries required (vanilla JS/CSS).
   - Requires a modern browser with MetaMask extension for staking.

## Usage

1. **Home Page (index.html)**:
   - View staking info, disclaimer, and latest Ethereum block (fetched via JS).
   - Buttons: Navigate to Staking or Contact.

2. **Staking Page (staking.html)**:
   - Select staking term (3/6/12 months) and ETH amount.
   - Click "Connect Wallet" to link MetaMask.
   - Click "Stake Ethereum" to send transaction (to address: 0x57CBA93A8f0abC01695917BD1c3cF569217Ab203).

3. **Contact Page (contact.html)**:
   - Fill in email and message.
   - Submit via Formspree (endpoint: https://formspree.io/f/myzgnyzp).

**Note**: Staking involves risks; always review the disclaimer.

## Optimization & Troubleshooting

- **Video Compression**: Use HandBrake or FFmpeg:
  ```
  ffmpeg -i INPUT.mp4 -vcodec h264 -crf 28 -an OUTPUT.mp4
  ```
  Aim for 720p resolution, no audio.

- **iPhone Playback Issues**:
  - Ensure `<video>` includes `playsinline`.
  - Add JS fallback:
    ```js
    const video = document.getElementById('background-video');
    video.play().catch(() => {
        document.addEventListener('click', () => video.play(), { once: true });
    });
    ```
  - Test with Low Power Mode off.

- **Fallbacks**: Use `poster` attribute for static images if videos fail to load.

## Contributing

Contributions are welcome! Fork the repo, make changes, and submit a pull request. Focus on:
- Bug fixes (e.g., cross-browser compatibility).
- Enhancements (e.g., additional staking options).
- Video updates (ensure AI-generated with MidJourney or similar).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Contact

For questions, use the site's contact form or reach out via [GitHub Issues](https://github.com/your-username/gpss-website/issues).

*Last Updated: October 01, 2025*