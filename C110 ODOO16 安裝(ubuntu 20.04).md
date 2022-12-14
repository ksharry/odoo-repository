## odoo16 安裝-[影片](https://www.youtube.com/watch?v=Uskr6rm0P9Y&t=2s)
#### STEP0：ubuntu環境架設(20.04)，安裝SSH並設定連線。
#### STEP1：Odoo16環境架設(使用Yenthe666的Script簡化安裝)
1. sudo wget https://raw.githubusercontent.com/Yenthe666/InstallScript/16.0/odoo_install.sh
2. sudo chmod +x odoo_install.sh
3. 調整使用nginx與註冊憑證。
   + 設定ngin
   + 手動使用網址註冊
4. sudo ./odoo_install.sh

#### STEP2: 測試環境
1. http://192.168.xxx.xxx:8069
2. 設定MasterPassword:sudo vi /etc/odoo-server.conf
3. 重新啟動:sudo service odoo-service stop/start
5. 註冊網址:sudo certbot --nginx -d xienci.com -d www.xienci.com --noninteractive --agree-tos --email harry.chang@dahsheng.com --redirect

#### STEP3: 完成後建議
1. 建議使用ubuntu進行正式機的設置
2. 學習腳本內容

#### 錯誤排除訊息
1. 資料庫沒正確安裝
   + sudo apt-get install postgresql postgresql-server-dev-all -y
   + systemctl status postgresql.service
   + sudo su - postgres -c "createuser -s  odoo" 2> /dev/null || true
   + sudo -u postgres psql
   + SELECT rolname FROM pg_roles;
2. wkhtmltopdf沒正確安裝
3. 沒正常重新啟動
   + 檢查是否未正常關閉:ps aux  | grep 'odoo'
   + sudo kill -9 PID

#### 安裝ODOO的影片
1. [透過 docker 快速建立 odoo 環境 - 從無到有-沈弘哲](https://www.youtube.com/watch?v=uqxzq4Td6aU)
2. [手把手教學!如何於GCP上完整安裝odoo-台灣ODOO/ODOO研究所](https://www.youtube.com/watch?v=tlbZjfmbTEE)
