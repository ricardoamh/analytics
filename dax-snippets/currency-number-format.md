
#Currency Format

VAR __totalAmount = SUM('tApprovalData'[Amount])
VAR __baseFormat = "$ #,0"
VAR __baseDecimal = "00"
RETURN
SWITCH(
    TRUE(),
    __totalAmount < 100000, __baseFormat & "." & "",
    __totalAmount < 1000000, __baseFormat & ",." & __baseDecimal & " K",
    __totalAmount < 1000000000, __baseFormat & ",,." & __baseDecimal & "M",
    __baseFormat & ",,,." & __baseDecimal & " B"
    )
