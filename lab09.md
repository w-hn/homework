## 首先从简着手，建立一个便于理解的简易框架   
选择 洗衣模式 输入 水位、时间
注水至预设水位
浸泡预设时间
漂洗预设时间
每个周期 电机转动左三秒、右三秒
排水至水位为0
脱水
电机快速转动 每周期左100秒右100秒 5个周期
关闭电源

3.2)
READ(water_line,soak_time,rinse_time)

WHILE getwatervolume()<water_line
waterinswitch(open)
ENDWHILE

waterinswitch(close)

SET now=timecounter()
WHILE timecounter()<=now+soak_time
ENDWHILE

SET now=timecounter()
WHLILE timecounter()<=now+rinse_time
SET now1=timecounter()
motorrun(left)
IF timecounter()==now1+3
motorrun(right)
ENDIF
IF timecounter()==now1+6
motorrun(stop)
ENDIF
ENDWHILE

WHILE getwatervolume()>0
wateroutswitch(open)
ENDWHILE

FOR i=1 to 5
now1=timecounter();
motorrun(left)
IF timecounter()==now1+100
motorrun(right)
ENDIF
IF timecounter()==now1+200
motorrun(stop)
ENDIF
ENDFOR
wateroutswitch(close)

halt(success)


