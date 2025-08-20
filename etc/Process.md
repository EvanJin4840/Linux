## what is the demon process? 

* 정의: 사용자의 터미널(화면)과 붙어있지 않은 백그라운드 서비스 프로세스. 시스템이 켜져 있는 동안 지속적으로 대기하며 요청을 처리하거나 주기적으로 일을 함. (예시 : sshd, cron, nginx)
* 참고: crontab은 사용자의 예약 작업 목록이고, 이를 읽어 **cron 데몬(crond)**이 지정한 시각에 명령을 실행함.

#### where entries live?

- User crontab : crontab -e로 편집(사용자별 스풀: 보통 /var/spool/cron 또는 /var/spool/cron/crontabs).
- System crontab: /etc/crontab (여긴 사용자명 필드가 추가됨).
- Drop-in: /etc/cron.d/* (system crontab과 동일 형식, 사용자명 필드 필요).
- Convenience dirs: /etc/cron.hourly, /etc/cron.daily, /etc/cron.weekly… (배포판의 run-parts가 실행).