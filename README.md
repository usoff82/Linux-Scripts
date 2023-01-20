# Linux-Scripts

```
select distinct
'METH '||replace(nvl(substr(substr(d.SNAME, 1, instr(d.SNAME, chr(10))), 1, instr(d.SNAME,' ')), substr(d.SNAME, 1, instr(d.SNAME, ' '))), '.', ' ')
--,d.* 
from DIARY_METHODS d
where USER_ID like '%susov%'
and ACTION != 'COMPILE'
union all
select distinct
'CRIT '||replace(nvl(substr(substr(d.SNAME, 1, instr(d.SNAME, chr(10))), 1, instr(d.SNAME,' ')), d.SNAME), '.', ' ')
--,d.*
from DIARY_CRITERIA d
where USER_ID like '%susov%'
and ACTION != 'COMPILE'
;
```
