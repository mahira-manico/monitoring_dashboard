# 📊 System Monitoring Dashboard

A real-time web-based system monitoring dashboard that displays comprehensive system metrics including CPU usage, memory, network information, running processes, and file statistics. Built with Python, HTML, CSS, and JavaScript.

*Live dashboard displaying real-time system metrics*

## ✨ Features

### 🖥️ System Information
- Machine hostname and operating system details
- System uptime tracking
- Connected users list
- Version information display

### ⚡ CPU Monitoring
- Real-time CPU usage percentage
- Interactive animated gauge visualization
- CPU core count
- Current CPU frequency (Hz)

### 💾 Memory Tracking
- RAM usage (used vs. total)
- Visual progress bar with percentage
- Real-time memory statistics
- Memory usage by active processes


### 🌐 Network Information
- Primary IP address display
- Network interface details

### 📈 Process Management
- **Top 3 processes by CPU usage** with percentage
- **Top 3 processes by RAM usage** with percentage
- Real-time process monitoring
- Process name and resource consumption display


### 📁 File Statistics
- File type analysis in project directory
- File count by extension
- Percentage distribution visualization
- Total file count

### 🔄 Auto-Refresh
- Dashboard auto-refreshes every 30 seconds
- Timestamp of last generation
- Live data updates

## 🛠️ Tech Stack

- **Python 3** - Backend data collection with `psutil`
- **HTML5** - Dashboard structure
- **CSS3** - Responsive styling
- **JavaScript** - Interactive gauge and animations
- **Bash** - Automation script
- **GaugeJS** - CPU usage visualization
- **W3.CSS** - Progress bar styling

## 📋 Prerequisites

- Linux-based operating system (Ubuntu/Debian recommended)
- Python 3.x
- pip (Python package manager)
- Web browser (Firefox, Chrome, etc.)
- sudo privileges (for installation script)

## 🚀 Installation

1. **Clone the repository**
```bash
git clone https://github.com/mahira-manico/monitoring_dashboard.git
cd monitoring_dashboard
```

2. **Make the installation script executable**
```bash
chmod +x Dashboard.sh
```

3. **Run the installation script**
```bash
./Dashboard.sh
```

The script will automatically:
- Update system packages
- Install Python 3 and pip
- Install required Python dependencies (`psutil`)
- Open the dashboard in your default browser
- Start the monitoring loop

## 📖 Usage

### Starting the Dashboard

**Automated Start:**
```bash
./Dashboard.sh
```

**Manual Start:**
```bash
# Start the monitoring script
python3 monitor.py

# Open index.html in your browser
firefox index.html  # or your preferred browser
```

### Dashboard Navigation

The navigation bar provides quick access to different sections:
- **Système** - System information
- **CPU** - Processor metrics
- **Mémoire** - Memory statistics
- **Réseau** - Network details
- **Processus** - Running processes
- **Fichier** - File statistics

### Customization

**Change Refresh Interval:**

Edit `index.html` and modify the meta refresh tag:
```html
  
```

**Modify Monitored Directory:**

Edit `monitor.py` and update the directory path in the `file_analysis()` function:
```python
directory = Path("/your/custom/path")
```

**Adjust CPU Gauge Colors:**

Edit `java.js` to customize the gauge color thresholds:
```javascript
percentColors: [
  [0.0, "#a9d70b"],   // Green for 0-50%
  [0.50, "#f9c802"],  // Yellow for 50-100%
  [1.0, "#ff0000"]    // Red at 100%
]
```

## 📂 Project Structure

```
monitoring_dashboard/
│
├── Dashboard.sh          # Installation and startup script
├── monitor.py           # Python backend - data collection
├── template.html        # HTML template with placeholders
├── index.html          # Generated dashboard (auto-updated)
├── template.css        # Stylesheet
├── java.js            # JavaScript for gauge visualization
├── settings.json      # IDE settings
└── gitignore.txt      # Git ignore patterns
```

## 🔧 How It Works

1. **Data Collection** (`monitor.py`):
   - Uses `psutil` library to gather system metrics
   - Collects CPU, memory, network, process, and file data
   - Runs in continuous loop with 1-second intervals

2. **Template Processing**:
   - Reads `template.html` with `{{ placeholder }}` variables
   - Replaces placeholders with real-time data
   - Writes updated content to `index.html`

3. **Dashboard Display**:
   - Browser loads `index.html`
   - JavaScript initializes the CPU gauge
   - Page auto-refreshes every 30 seconds
   - CSS provides responsive styling

4. **Automation** (`Dashboard.sh`):
   - Handles dependencies installation
   - Opens browser automatically
   - Maintains continuous monitoring loop

![Workflow Diagram](docs/workflow.gif)

## 🎨 Customization Examples

### Change Color Scheme

Edit `template.css`:
```css
header {
  background: #your-color;  /* Header background */
}

nav ul li a {
  background: #your-color;  /* Navigation buttons */
}
```

### Add New Metrics

1. Add data collection function in `monitor.py`
2. Add placeholder in `template.html`
3. Update the replacement logic in `monitor.py`

## 🐛 Troubleshooting

**Dashboard not updating:**
- Check if `monitor.py` is running: `ps aux | grep monitor.py`
- Verify file permissions: `ls -la index.html`
- Check console for JavaScript errors

**Import errors:**
```bash
pip3 install psutil --break-system-packages
```

**Permission denied:**
```bash
chmod +x Dashboard.sh
sudo chmod 666 index.html
```

**Browser not opening automatically:**
```bash
# Manually open the dashboard
xdg-open index.html  # Linux
open index.html      # macOS
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 👥 Authors

- **[mahira-manico](https://github.com/mahira-manico)** - *Lead Developer* - Python backend development, data collection, and core monitoring logic
- **[nicolas-lambert-1](https://github.com/nicolas-lambert-1)** - *Frontend Developer* - JavaScript gauge implementation, HTML structure, CSS styling, Apache2 configuration, and Bash automation
- **[marion-ory](https://github.com/marion-ory)** - *UI/UX Designer* - HTML layout design and CSS styling

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- [psutil](https://github.com/giampaolo/psutil) - Cross-platform library for system monitoring
- [GaugeJS](https://github.com/bernii/gauge.js) - Animated gauge visualization library
- [W3.CSS](https://www.w3schools.com/w3css/) - Modern CSS framework for progress bars

## 📧 Contact

For questions or feedback, please open an issue on the [GitHub repository](https://github.com/mahira-manico/monitoring_dashboard/issues).

---

**Repository:** https://github.com/mahira-manico/monitoring_dashboard.git

Made with ❤️ by the Triple A Team
