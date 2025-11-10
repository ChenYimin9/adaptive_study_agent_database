# You can change this to a newer version of MySQL available at
# https://hub.docker.com/r/mysql/mysql-server/tags/
FROM mysql/mysql-server:8.0.36  # 最新稳定版，修复安全漏洞，提升性能

RUN mkdir -p /var/lib/mysql/backups

CMD mysqldump -h"$MYSQL_HOST" -u"$MYSQL_USER" -p"$MYSQL_PASSWORD" \
    --single-transaction \  # 标准参数名，替换中文“单次事务”
    --databases adaptive_study_db \  # 仅备份项目核心库（需与项目数据库名一致）
    --result-file=/var/lib/mysql/backups/backup_$(date +%F_%H%M%S).sql  # 时间格式更紧凑
