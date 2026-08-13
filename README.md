# 🎮 Virtual Steering Wheel

Control PC car games using your **hands as a virtual steering wheel** — no physical steering wheel required.

This project uses your webcam, **MediaPipe**, **OpenCV**, and **Python** to detect your hand gestures and convert them into keyboard controls.

## 🚗 How It Works

Hold both hands in front of your webcam as if you're holding a steering wheel.

The program detects:

* 👊 Both fists → Accelerate
* 👊 Both fists + tilt left → Accelerate + Steer Left
* 👊 Both fists + tilt right → Accelerate + Steer Right
* 🖐 Both hands open → Brake
* 🖐 Both hands open + tilt left → Brake + Steer Left
* 🖐 Both hands open + tilt right → Brake + Steer Right
* 👊🖐 One fist + one open hand → Neutral
* No hands → Release all keys

## 🎮 Controls

| Hand Gesture       | Keyboard Action |
| ------------------ | --------------- |
| 👊 👊              | ↑ Accelerate    |
| 👊 👊 + Tilt Left  | ↑ + ←           |
| 👊 👊 + Tilt Right | ↑ + →           |
| 🖐 🖐              | ↓ Brake         |
| 🖐 🖐 + Tilt Left  | ↓ + ←           |
| 🖐 🖐 + Tilt Right | ↓ + →           |
| 👊 🖐              | Neutral         |
| No Hands           | Release Keys    |

## 🛠️ Technologies

* Python 3.11
* MediaPipe
* OpenCV
* NumPy
* Pynput
* Webcam / Camera

## 📋 Requirements

* Python 3.11 recommended
* Webcam
* macOS or Windows
* A game that accepts keyboard controls

## 📦 Installation

Clone the repository:

bash
git clone https://github.com/YOUR-USERNAME/virtual-steering-wheel.git
cd virtual-steering-wheel

Create a virtual environment:

bash
python3.11 -m venv .venv


Activate it on macOS/Linux:

bash
source .venv/bin/activate

Install the dependencies:

bash
python -m pip install mediapipe==0.10.21 opencv-python==4.10.0.84 pynput numpy==1.26.4

## ▶️ Run

Start the program with:

bash
python steering.py


A camera window will open.

Press **Q** to quit.

## ⚙️ Configuration

You can change these settings at the top of `steering.py`:

python
CAMERA_INDEX = 0
DEAD_ZONE_DEG = 12
FLIP_CAMERA = True
GRACE_FRAMES = 8
OPEN_FINGER_THRESH = 3
SMOOTHING = 0.25
MAX_STEERING_DEG = 45


### Camera Index

python
CAMERA_INDEX = 0

`0` is normally the built-in webcam.

Try `1` or `2` if you're using another camera.

### Steering Dead Zone

python
DEAD_ZONE_DEG = 12

Increase this value if the steering moves when your hands are almost level.

### Camera Flip

python
FLIP_CAMERA = True

Set it to False if your steering direction is reversed.

### Steering Smoothness

python
SMOOTHING = 0.25

Lower values provide smoother movement.

Higher values provide faster response.

## 🍎 macOS Permissions

macOS may require permissions for the camera and keyboard control.

Go to:

**System Settings → Privacy & Security → Camera**

Enable access for the application running Python, such as Terminal or VS Code.

For keyboard control, check:

**System Settings → Privacy & Security → Accessibility**

and allow the application running the Python program.

## 🎮 Compatible Games

The project is designed for games that accept keyboard input.

Examples include:

* Browser racing games
* Google Chrome Dino
* Trackmania
* TORCS
* Other PC racing games with keyboard controls

Compatibility can vary depending on the game's control system.

## 🐛 Troubleshooting

### Camera doesn't open

Try changing:

python
CAMERA_INDEX = 0

to:

python
CAMERA_INDEX = 1

or:

python
CAMERA_INDEX = 2

### Steering is reversed

Try:

python
FLIP_CAMERA = False


### Steering is too sensitive

Increase:

python
DEAD_ZONE_DEG = 18

### Steering is too slow

Increase:

python
SMOOTHING = 0.35

### Keys don't control the game

Make sure your operating system has granted keyboard/accessibility permissions to the application running Python.

Also verify that the game actually supports the keyboard keys being sent.

## 📁 Project Structure

text
virtual-steering-wheel/
│
├── steering.py
├── README.md
└── requirements.txt

## 🚀 Future Improvements

Possible future features:

* 🎮 Nitro gesture
* 🏎️ Drift gesture
* 🎚️ Adjustable steering sensitivity
* 📊 Better steering calibration
* 🤚 More gesture controls
* 🎥 Improved hand tracking
* 🎮 Game-specific control profiles
* 🔊 Sound effects
* 📱 Mobile/webcam support

## ⭐ Contributing

Pull requests and improvements are welcome.

If you have an idea for a new gesture or feature, feel free to contribute.

## 📄 License

This project is open-source and available under the MIT License.

---

**Made with Python, MediaPipe, OpenCV and a webcam. 🏎️💨**
