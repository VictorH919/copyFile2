# copyFile2
自动拷贝文件以时间命名2
import os
import time

#需要备份的目录
source = ['D:\\FRM']

#备份存储位置
target_dir = 'D:\\copy'

#打包成zip文件
target = target_dir + os.sep + time.strftime('%Y%m%d%H%M%S') + '.zip'

#如不存在目录则创建备份位置
if not os.path.exists(target_dir):
    os.mkdir(target_dir)

#打包成zip文件命令
zip_command = '7z a {0} {1}'.format(target,''.join(source))

#开始备份
print('Zip command is:')
print(zip_command)
print('Running:')
if os.system(zip_command) == 0:
    print('Successful backup to',target)
else:
    print('Backup FAILED')

