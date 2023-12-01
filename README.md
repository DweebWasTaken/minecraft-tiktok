# minecraft-tiktok
Java Guide
## **SuperStream: Actions Guide**

Actions are responses set by the plugin to events from TikTok. Here's a comprehensive breakdown of the available actions:

### **1. actionbar:**
Displays a message on the player's action bar.
```yaml
actionbar:
  text: "Thanks for the gift, <user>!"
```

### **2. execute:**
Executes server commands either as the server console or as the player.
```yaml
execute:
  asPlayer: true
  commands:
    - "give <player> diamond 1"
```

### **2.5. random execute:**
Executes a random server command either as the server console or as the player.
```yaml
random-execute:
  asPlayer: true
  commands:
    - "give <player> diamond 1"
    - "say hello"
```

### **3. title:**
Shows a title (and optional subtitle) on the player's screen.
```yaml
title:
  text: "Gift from <user>"
  subtitle: "Thank you!"
  fadeIn: 10
  stay: 70
  fadeOut: 20
```

### **4. spawn:**
Spawns entities on the player with customizable attributes.

**Available Variables:**
- `type`: Type of the entity you want to spawn.
- `amount`: How many entities you want to spawn (default is 1).
- `yOffset`: Vertical distance above the player where the entity should spawn.
- `addSenderName`: Attach the name of the sender to the entity (e.g., "Gift from <user>").
- `senderNameColor`: Color code for the sender's name (default is &f).
- `isMob`: Should be `false` for non-mobs like PRIMED_TNT. Default is `true`.
- `customName`: Specify a custom name for the spawned entity.
- `blastRadius`: For entities like TNT and CREEPERS, defines the explosion's radius.
- `isCharged`: If set to `true`, spawns a charged creeper.
- `isTamed`: If set to `true`, spawns a tamed entity (e.g., tamed wolf).
- `fuseTicks`: Defines the fuse duration for entities like TNT and CREEPERS.

*Charged Creeper with Player's name:*
```yaml
spawn:
  creeper:
    type: CREEPER
    addSenderName: true
    senderNameColor: "&e"
    isMob: true
    isCharged: true
```

*Pig with Custom colored name:*
```yaml
spawn:
  pigWithName:
    type: PIG
    customName: "&eBilly"
    customName: "<player>'s Buddy"
```

**Tips:**
- Remember to refer to the available variables list when customizing the `spawn` action.
- Always test in a controlled environment before using in a live stream.

### **5. sound:**
Plays a sound at the player's location.
```yaml
sound:
  name: BLOCK_NOTE_BLOCK_PLING
  volume: 1.0
  pitch: 1.0
```

### **6. effect:**
Applies a potion effect to the player.
```yaml
effect:
  name: SPEED
  duration: 200
  amplifier: 1
```

### **7. message:**
Sends a series of chat messages to the player.
```yaml
message:
  messages:
    - "Thanks for the <gift>, <user>!"
    - "You're awesome!"
```

## **Tips:**
- Carefully review each action's syntax before applying.
- Test each action in a controlled environment to ensure desired effects.
