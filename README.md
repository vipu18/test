# SecureVault - Advanced Encrypted Document Management System

A highly secure, zero-knowledge document storage and sharing platform with advanced privacy features, dead man's switch capabilities, and multi-cloud backup support.

## 🌟 Key Features

### 🔐 Security-First Architecture
- **Zero-Knowledge Encryption**: Full client-side encryption using AES-256-GCM
- **Hardware Key Support**: YubiKey, FIDO2, and WebAuthn integration
- **Biometric Authentication**: Fingerprint and Face unlock on supported devices
- **Passwordless Login**: Modern authentication without traditional passwords
- **File Integrity Verification**: SHA-256 checksums with tamper detection
- **Anti-Screenshot Protection**: Blur sensitive content and detect screen capture attempts
- **Secure File Destruction**: Multi-pass overwrite deletion with "Burn After Reading" mode

### 🚨 Advanced Privacy Features

#### Dead Man's Switch
- Automatic activation after X days of inactivity
- Encrypted emergency package delivery to trusted contacts
- Configurable timeout periods and contact management

#### Emergency Vault
- Hidden panic vault accessible via alternate password
- Decoy Mode: Fake vault for coercion situations
- Geo-Fencing: Restrict document access by country/device

#### Blockchain Audit Proofs
- Immutable audit records stored on blockchain
- Verifiable access history and document integrity

### ☁️ Backup & Sync
- **Multi-Cloud Support**:
  - Google Drive
  - Dropbox
  - Microsoft OneDrive
  - Amazon S3
- **Version History**: Restore previous document versions
- **Offline Vault Mode**: Encrypted offline desktop/mobile synchronization
- **Rclone Integration**: Advanced cloud sync configuration

### 📄 Document Management
- Secure upload and storage (up to 100MB per file)
- Organization with tags, document types, and status tracking
- OCR support with metadata extraction
- File integrity monitoring

### 🔗 Secure Sharing System
- Token-based secure sharing links
- OTP-protected access
- Configurable download restrictions
- Dynamic watermarking
- View limits and expiry-based sharing
- DRM toggle support
- Share revocation capability

### 📊 Access Logs & Audit Trail
Comprehensive tracking of:
- Viewer identity
- Actions performed
- IP address and location
- Device information
- User agent details
- Timestamp (IST timezone formatting)

### 🆔 KYC / Identity Verification
- Profile management system
- Document verification fields
- Risk scoring algorithm
- Consent management

### 🔔 Notification System
- In-app notifications
- Security alerts
- System update announcements

## 🖥️ User Interface

### Dashboard Pages
- **Main Dashboard**: Overview of documents and activity
- **Document Viewer**: Secure encrypted file viewing
- **Notifications Panel**: Real-time security updates
- **Consent Manager**: KYC and permission controls
- **Recipients Manager**: Shared access management
- **Settings Page**: Comprehensive configuration options
- **Access Logs Page**: Detailed audit trail viewer
- **Rclone Settings**: Cloud sync configuration

### User Preferences
- Theme customization (Light/Dark mode)
- Default sharing preferences
- Expiry control defaults
- IST timezone formatting support

## 🛠️ Technical Specifications

### Encryption Standards
- **Algorithm**: AES-256-GCM
- **Key Derivation**: PBKDF2 with unique salt per file
- **Nonce**: Unique nonce for each encryption operation
- **Storage**: Encrypted filenames and paths

### Authentication
- Password hashing with bcrypt/argon2
- Session-based authentication
- Optional 2FA (TOTP, SMS, Email)
- Hardware security key support
- Biometric authentication APIs

### Security Measures
- Secure filename handling
- Server never sees plaintext or keys
- Anti-CSRF and XSS protection
- Rate limiting and brute force prevention
- Secure session management

## 📋 Installation & Setup

### Prerequisites
- Node.js 18+ or Python 3.9+
- Database (PostgreSQL recommended)
- Redis for session management
- Cloud storage credentials (optional)

### Configuration

#### Environment Variables
```bash
# Encryption
ENCRYPTION_KEY=<your-master-key>
PBKDF2_ITERATIONS=100000

# Database
DATABASE_URL=postgresql://user:pass@localhost/securedb

# Session
SESSION_SECRET=<random-secret>
SESSION_TIMEOUT=3600

# Cloud Storage (Optional)
GOOGLE_DRIVE_CLIENT_ID=
DROPBOX_APP_KEY=
ONEDRIVE_CLIENT_ID=
AWS_S3_BUCKET=
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=

# Rclone Configuration
RCONFIG_PATH=/path/to/rclone.conf
AUTO_SYNC_ENABLED=true
SYNC_INTERVAL=3600

# Dead Man's Switch
DMS_INACTIVITY_DAYS=30
DMS_EMERGENCY_CONTACT=email@example.com

# Geo-Fencing
ALLOWED_COUNTRIES=IN,US,GB
ALLOWED_DEVICES=desktop,mobile

# Blockchain Audit
BLOCKCHAIN_RPC_URL=
SMART_CONTRACT_ADDRESS=
```

#### Rclone Settings Page Configuration
The application includes a dedicated settings page for Rclone configuration:
- Add/Edit cloud remotes
- Test connection status
- Configure sync schedules
- Set bandwidth limits
- Enable/disable auto-sync
- View sync logs and history

## 🚀 Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/securevault.git
   cd securevault
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   pip install -r requirements.txt
   ```

3. **Configure environment**
   ```bash
   cp .env.example .env
   # Edit .env with your settings
   ```

4. **Initialize database**
   ```bash
   npm run db:migrate
   # or
   python manage.py migrate
   ```

5. **Start the application**
   ```bash
   npm start
   # or
   python app.py
   ```

6. **Access the dashboard**
   Open `http://localhost:3000` in your browser

## 🔧 Settings Page Features

### General Settings
- Profile management
- Password change
- 2FA enrollment
- Session management

### Security Settings
- Hardware key registration
- Biometric setup
- Anti-screenshot toggle
- Secure deletion preferences

### Cloud Sync Settings (Rclone)
- **Remote Configuration**: Add/edit cloud storage remotes
- **Sync Schedule**: Set automatic sync intervals
- **Bandwidth Control**: Limit upload/download speeds
- **Filter Rules**: Include/exclude specific files or folders
- **Sync Status**: Real-time sync progress and logs
- **Test Connection**: Verify cloud storage connectivity

### Sharing Defaults
- Default link expiry time
- Download restrictions
- Watermark settings
- OTP requirement toggle

### Notification Preferences
- Email alerts
- In-app notifications
- Security alert thresholds

### Privacy Controls
- Dead Man's Switch configuration
- Emergency contact management
- Geo-fencing rules
- Decoy vault setup

## 📱 Supported Platforms
- Web (Modern browsers: Chrome, Firefox, Safari, Edge)
- Desktop (Windows, macOS, Linux via Electron)
- Mobile (iOS, Android via React Native/Flutter)

## 🤝 Contributing
Contributions are welcome! Please read our contributing guidelines before submitting PRs.

## 📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

## ⚠️ Security Notice
- This software handles sensitive data. Always review code before deployment.
- Never store encryption keys on the server.
- Regularly update dependencies and monitor for vulnerabilities.
- Conduct security audits before production use.

## 📞 Support
For issues, questions, or security reports, please open an issue on GitHub or contact security@securevault.example.com

---

**Built with privacy and security as the foundation.**
