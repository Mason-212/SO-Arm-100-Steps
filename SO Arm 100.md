## Leader Arm
- Port ID is /dev/tty.usbmodem58FA0930941
ID setting command:
```bash
python -m lerobot.setup_motors \
    --teleop.type=so100_leader \
    --teleop.port=/dev/tty.usbmodem58FA0930941
```

Calibration of motor (Range, Posistion)
```bash
python -m lerobot.calibrate \
    --teleop.type=so100_leader \
    --teleop.port=/dev/tty.usbmodem58FA0930941
    --teleop.id=my_awesome_leader_arm**
```
## Follower Arm
 - Port ID is /dev/tty.usbmodem5A680095431
 ID setting:
 ```Bash
python -m lerobot.setup_motors \
    --robot.type=so100_follower \
    --robot.port=/dev/tty.usbmodem5A680095431
```

Calibration of motor (Range, Posistion):
```bash

python -m lerobot.calibrate \
    --robot.type=so100_follower \
    --robot.port=/dev/tty.usbmodem5A680095431
    --robot.id=my_awesome_follower_arm

```

## Teleoperation
- Makes Follower arm perfectly mimic and mirror the leader arm
Teleoperation without camera Command:
```bash
python -m lerobot.teleoperate \
    --robot.type=so100_follower \
    --robot.port=/dev/tty.usbmodem5A680095431 \
    --robot.id=my_awesome_follower_arm \
    --teleop.type=so100_leader \
    --teleop.port=/dev/tty.usbmodem58FA0930941 \
```
Teleoperation with camera command:
```bash
python -m lerobot.teleoperate \
    --robot.type=so100_follower \
    --robot.port=/dev/tty.usbmodem5A680095431 \
    --robot.id=my_awesome_follower_arm \
    --robot.cameras="{ right: {type: opencv, index_or_path: 0, width: 1280, height: 720, fps: 30}}" \
    --teleop.type=so100_leader \
    --teleop.port=/dev/tty.usbmodem58FA0930941 \
    --teleop.id=my_awesome_leader_arm \
    --display_data=true
```
## Hugging Face
Hugging Face Access Token
	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
Hugging Face log in command:
```bash
huggingface-cli login --token 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 --add-to-git-credential
```
