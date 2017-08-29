If you want to update firmware in your cheap cnc 2417
you need to apply this patch to cpu_map.h file into arduino grbl library
before start to compile code.

After compile and upload firmware you need to invert Z axis and calibrate all axes steps by mm

Type following code in the chc console

```
$3=4
$100=400
$101=400
$102=400
```

Your CNC in default working condition.

$$ settings will look like this

```
$0=10
$1=25
$2=0
$3=4
$4=0
$5=0
$6=0
$10=1
$11=0.010
$12=0.002
$13=0
$20=0
$21=0
$22=0
$23=0
$24=25.000
$25=500.000
$26=250
$27=1.000
$30=1000
$31=0
$32=0
$100=400.000
$101=400.000
$102=400.000
$110=500.000
$111=500.000
$112=500.000
$120=10.000
$121=10.000
$122=10.000
$130=200.000
$131=200.000
$132=200.000
```

after market cnc have v0.8 grbl and this settings

```
$0=10 (step pulse, usec)
$1=255 (step idle delay, msec)
$2=0 (step port invert mask:00000000)
$3=0 (dir port invert mask:00000100)
$4=0 (step enable invert, bool)
$5=0 (limit pins invert, bool)
$6=0 (probe pin invert, bool)
$10=3 (status report mask:00000011)
$11=0.010 (junction deviation, mm)
$12=0.002 (arc tolerance, mm)
$13=0 (report inches, bool)
$20=0 (soft limits, bool)
$21=0 (hard limits, bool)
$22=0 (homing cycle, bool)
$23=0 (homing dir invert mask:00000000)
$24=25.000 (homing feed, mm/min)
$25=500.000 (homing seek, mm/min)
$26=250 (homing debounce, msec)
$27=1.000 (homing pull-off, mm)
$100=400.000 (x, step/mm)
$101=400.000 (y, step/mm)
$102=400.000 (z, step/mm)
$110=1500.000 (x max rate, mm/min)
$111=1500.000 (y max rate, mm/min)
$112=1500.000 (z max rate, mm/min)
$120=1000.000 (x accel, mm/sec^2)
$121=1000.000 (y accel, mm/sec^2)
$122=1000.000 (z accel, mm/sec^2)
$130=200.000 (x max travel, mm)
$131=200.000 (y max travel, mm)
$132=200.000 (z max travel, mm)
```

Enjoy!
