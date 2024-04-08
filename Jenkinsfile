pipeline {
    agent {
        // ใช้ Docker executor ระบุเวอร์ชั่นเพื่อความเสถียร
        docker {
            image 'mcr.microsoft.com/playwright' // เลือกเวอร์ชั่นที่รองรับ
        }
    }
    stages {
        stage('ติดตั้ง Playwright') {
            steps {
                script {
                    """
                    npm install -D playwright/test
                    npx playwright install
                    """
                }
            }
        }
        stage('แสดงวิธีใช้ Playwright Test') {
            steps {
                script {
                    // คำสั่งสั้น ๆ อยู่ในบรรทัดเดียว
                    sh 'npx playwright test --help'
                }
            }
        }
        stage('รัน Playwright Tests') {
            steps {
                script {
                    """
                    # แสดงรายการเทสต์ที่มี
                    npx playwright test --list

                    # รันเทสต์ทั้งหมด
                    npx playwright test
                    """
                }
            }
        }
    }
}
