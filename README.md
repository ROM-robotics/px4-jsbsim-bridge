<img align="right" height="20" src="https://auterion.com/wp-content/uploads/2020/05/auterion_logo_default_sunrise.svg">

# JSBSim Bridge
[![Build Tests](https://github.com/Auterion/px4-jsbsim-bridge/workflows/Build%20Tests/badge.svg?branch=master)](https://github.com/Auterion/px4-jsbsim-bridge/actions?query=workflow%3A%22Build+Tests%22)

JSBSim bridge သည် [jsbsim](https://github.com/JSBSim-Team/jsbsim) နှင့် ဆက်သွယ်ဆောင်ရွက်ရန် PX4 mavlink HIL interface ကို ပေါင်းစပ်ထားသော (integration) တစ်ခု ဖြစ်သည်။


## ထည့်သွင်းခြင်း (JSBSim)
JSBSim ၏ rolling releases များကို JSBSim ၏ [release page](https://github.com/JSBSim-Team/jsbsim/releases) တွင် ရယူနိုင်သည်။

ရုပ်ပုံပြ (visualization) ကို အသုံးပြုလိုပါက flightgear ကို install လုပ်ပါ။

```
apt install flightgear
```

## bridge ကို run ခြင်း
Firmware ထဲမှ run ချင်ပါက အောက်ပါအတိုင်း ဥပမာတစ်ခု run နိုင်သည်
```
make px4_sitl jsbsim
```

flightgear ရုပ်ပုံပြမပါဘဲ run ချင်ပါက၊
```
HEADLESS=1 make px4_sitl jsbsim
```

## ROS နှင့်အတူ bridge ကို run ခြင်း
`px4-jsbsim-bridge` package ကို သင့် catkin workspace ထဲသို့ clone လုပ်ပါ:
```
cd <path_to_catkin_ws>/src
git clone https://github.com/Auterion/px4-jsbsim-bridge.git
```
`jsbsim_bridge` catkin package ကို build လုပ်ပါ:
```
catkin build jsbsim_bridge
```
:::note
သင့် workspace တွင် MAVROS ကို အရင်ဆုံးထည့်သွင်းပြီးသား ဖြစ်ရပါမည် (မထည့်သွင်းရသေးပါက [MAVROS installation guide](../ros/mavros_installation.md) ရှိ ညွှန်ကြားချက်များအတိုင်း လုပ်ဆောင်ပါ)။
:::
JSBSim ကို ROS မှတစ်ဆင့် launch file ကို အသုံးပြု၍ အောက်ပါအတိုင်း စတင်ပါ:
```
roslaunch jsbsim_bridge px4_jsbsim_bridge.launch
```
