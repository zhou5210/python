#!/usr/bin/python
#-*-coding:utf-8-*-

import sys
reload(sys)
sys.setdefaultencoding('utf8') 
import smtplib;
from email.MIMEText import MIMEText

def send_email(host,username,passwd,send_to,subject,content):
    msg = MIMEText( content.encode('utf8'), _subtype = 'html', _charset = 'utf8')
    msg['From'] = username
    msg['Subject'] = u'%s' % subject
    msg['To'] = ",".join(send_to)
    
    try:
        s = smtplib.SMTP_SSL(host,465)        
        s.login(username, passwd )
        s.sendmail(username, send_to,msg.as_string())
        s.close()
    except Exception as e:
        print 'Exception: send email failed', e
 
if __name__ == '__main__':
    host = 'smtp.163.com'
    username = '123@163.com'
    passwd = '123'
    to_list = ['123@163.com']
    subject = "邮件主题"
    content = '使用Python发送邮件'
    send_email(host,username,passwd,to_list,subject,content)
