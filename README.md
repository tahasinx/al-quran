# Al-Quran Random Ayah Generator

A simple web application that displays random verses (ayahs) from the Holy Quran. The app fetches verses from the Al-Quran Cloud API and presents them in a clean, elegant interface.

## 🌟 Features

- **Random Ayah Display**: Shows a random verse from any of the 114 surahs of the Quran
- **Clean UI**: Minimalist design with elegant typography using Mate SC font
- **Responsive Design**: Works on desktop and mobile devices
- **Real-time API Integration**: Fetches verses from the Al-Quran Cloud API
- **Source Attribution**: Displays the surah name and verse number for each ayah

## 🚀 Getting Started

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (required for API calls)

### Installation

1. Clone or download this repository
2. Open `index.html` in your web browser
3. The app will automatically load and display a random ayah

### Usage

- The application automatically displays a random ayah when the page loads
- Refresh the page to get a new random verse
- Each ayah is displayed with its source (Surah name and verse number)

## 🛠️ Technical Details

### Technologies Used

- **HTML5**: Structure and markup
- **CSS3**: Styling and responsive design
- **JavaScript**: Dynamic functionality and API integration
- **Al-Quran Cloud API**: External API for Quran data

### API Integration

The app uses the [Al-Quran Cloud API](https://alquran.cloud/api) to fetch verses:

- **Endpoint**: `https://api.alquran.cloud/v1/ayah/{surah}:{ayah}/en.asad`
- **Translation**: English translation by Muhammad Asad
- **Alternative**: For Bengali translation, use `bn.bengali` instead of `en.asad`

### Code Structure

- **Surah Data**: Complete array of all 114 surahs with their ayah counts
- **Random Selection**: Algorithm to randomly select surah and ayah numbers
- **API Fetching**: Asynchronous data retrieval with error handling
- **DOM Manipulation**: Dynamic content updates

## 📱 Features in Detail

### Random Ayah Generation
```javascript
function getRandomAyah() {
    const randomSurahIndex = Math.floor(Math.random() * surahs.length);
    const randomSurah = surahs[randomSurahIndex];
    const randomAyahIndex = Math.floor(Math.random() * randomSurah.ayah_count) + 1;
    // ... API call and display logic
}
```

### Responsive Design
- Flexbox layout for centering content
- Mobile-friendly viewport settings
- Elegant typography with Mate SC font
- Clean fieldset design for content presentation

## 🎨 UI Components

- **Main Container**: Fieldset with legend "Al-Quran"
- **Ayah Text**: Centered display of the verse
- **Source Information**: Right-aligned attribution showing surah name and verse number
- **Typography**: Mate SC font for elegant Arabic-style text rendering

## 🔧 Customization

### Changing Translation
To use a different translation, modify the API endpoint:

```javascript
// For Bengali translation
fetch(`https://api.alquran.cloud/v1/ayah/${randomSurahIndex + 1}:${randomAyahIndex}/bn.bengali`)

// For other translations, replace 'en.asad' with the desired translation code
```

### Styling Modifications
- Modify the CSS in the `<style>` section to change colors, fonts, or layout
- Adjust the fieldset width, padding, or positioning
- Customize the typography by changing font-family properties

## 📊 API Response Structure

The Al-Quran Cloud API returns data in this format:
```json
{
  "code": 200,
  "status": "OK",
  "data": {
    "number": 1,
    "text": "In the name of Allah, the Entirely Merciful, the Especially Merciful.",
    "surah": {
      "number": 1,
      "name": "Al-Fatihah",
      "englishName": "The Opening",
      "englishNameTranslation": "The Opening"
    },
    "numberInSurah": 1
  }
}
```

## 🤝 Contributing

Feel free to contribute to this project by:
- Adding new features
- Improving the UI/UX
- Adding more translation options
- Optimizing the code
- Reporting bugs or issues

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- [Al-Quran Cloud API](https://alquran.cloud/api) for providing the Quran data
- Muhammad Asad for the English translation
- Google Fonts for the Mate SC font

## 📞 Support

If you encounter any issues or have questions:
1. Check the browser console for error messages
2. Ensure you have an active internet connection
3. Verify that the Al-Quran Cloud API is accessible

---

**Note**: This application is designed for educational and spiritual purposes. Please respect the sacred nature of the Quran content displayed. 