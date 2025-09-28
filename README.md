# School Bus Attendance Web App

This project is a simple web application for managing school bus attendance using QR codes. It allows drivers to check in students by scanning QR codes and records attendance online.

## Features
- **Student QR Generator:** Generates unique QR codes for each student.
- **QR Scanner:** Scans student QR codes using a mobile device or webcam.
- **Attendance Tracking:** (Supabase integration ready) Records check-ins for each student.
- **Cloud Database:** Uses Supabase for online student and attendance data.
- **Mobile Friendly:** Works on phones and tablets.

## How It Works
1. **Generate QR Codes:**
   - Use `qr-generator.html` to create QR codes for each student.
   - Print or distribute QR codes to students.
2. **Scan QR Codes:**
   - Open `qr-scanner.html` on a mobile device or laptop.
   - Scan student QR codes as they board the bus.
   - Attendance is tracked and can be integrated with Supabase.

## Getting Started
1. **Clone or Download the Project**
2. **Install Dependencies**
   - Download `html5-qrcode.min.js` from [unpkg](https://unpkg.com/html5-qrcode@2.3.8/html5-qrcode.min.js) and place it in the project folder.
3. **Run Locally**
   - Start a local server (e.g., `python -m http.server 8000`).
   - Open `http://localhost:8000/qr-generator.html` and `http://localhost:8000/qr-scanner.html` in your browser.
4. **Deploy Online**
   - Upload all files to GitHub and enable GitHub Pages in repository settings.
   - Access your app via the provided HTTPS link.

## Folder Structure
```
TRANSPORT/
├── index.html            # Main dashboard
├── qr-generator.html     # QR code generator
├── qr-scanner.html       # QR code scanner
├── html5-qrcode.min.js   # QR code library (downloaded)
├── Transport App - Students.csv # Example student list
├── README.md             # Project documentation
```

## Requirements
- Modern browser (Chrome, Edge, Firefox, Safari)
- Camera access for QR scanning
- Supabase account (for online attendance tracking)

## License
MIT

## Credits
- [html5-qrcode](https://github.com/mebjas/html5-qrcode) for QR code scanning
- [Supabase](https://supabase.com/) for cloud database

        alert(`Attendance checked in for student ID: ${studentId}`);
        // TODO: Add fetch to Supabase attendance table here
      }

      if (window.Html5Qrcode) {
        const qrReader = new Html5Qrcode("qr-reader");
        qrReader.start(
          { facingMode: "environment" },
          {
            fps: 10,
            qrbox: 250
          },
          onScanSuccess,
          errorMessage => {
            document.getElementById('result').innerHTML = `<span style='color:red'>Camera error: ${errorMessage}</span>`;
          }
        ).catch(err => {
          document.getElementById('result').innerHTML = `<span style='color:red'>Camera error: ${err}</span>`;
        });
      } else {
        document.getElementById('result').innerHTML = `<span style='color:red'>QR code library failed to load.</span>`;
      }
    });
  </script>
</body>
</html>
