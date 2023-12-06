# Run Only Rover in SITL

## The Exercise 
In this exercise your object is to run only the Rover vehicle (and not any other vehicle) using sitl sim_vehicle. 

Do not change the API of using sim_vehicle.py !

DO NOT invent the wheel! use the open-source code and see where it is the easiest to change it to achieve this goal. 

## Home Solution: 

`git status` output : 

```
on branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Tools/autotest/sim_vehicle.py

no changes added to commit (use "git add" and/or "git commit -a")
```

`git diff Tools/autotest/sim_vehicle.py` output : 

```
diff --git a/Tools/autotest/sim_vehicle.py b/Tools/autotest/sim_vehicle.py
index 065b5265c1..3882981a10 100755
--- a/Tools/autotest/sim_vehicle.py
+++ b/Tools/autotest/sim_vehicle.py
@@ -1456,7 +1456,9 @@ if cmd_opts.vehicle in vehicle_map:
 elif cmd_opts.vehicle.lower() in vehicle_map:
     cmd_opts.vehicle = vehicle_map[cmd_opts.vehicle.lower()]
 
-# try to validate vehicle
+cmd_opts.vehicle = "Rover"
+
+## try to validate vehicle
 if cmd_opts.vehicle not in vinfo.options:
     progress('''
 ** Is (%s) really your vehicle type?
```



