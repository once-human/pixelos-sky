# unlock the bootloader

you need an unlocked bootloader for any custom rom. xiaomi controls this part, so the rules (waiting time, account requirements) depend on your region and change now and then. follow what your phone and xiaomi's tool tell you.

**unlocking wipes your phone.** back up first.

## steps

1. **on the phone**
   1. sign in with your xiaomi account (settings > xiaomi account)
   2. settings > about phone > tap **os version** 7 times to enable developer options
   3. settings > additional settings > developer options > **mi unlock status** > add your account
   4. if it asks you to wait or to apply through the xiaomi community app, do that. the timer starts here
2. **on the pc** (windows)
   1. download xiaomi's official **mi unlock** tool
   2. sign in with the same xiaomi account
3. **unlock**
   1. phone off, hold **power + volume down** for fastboot mode, plug it in
   2. hit unlock in mi unlock and follow it
   3. if it shows a waiting time, wait it out and try again after

## check it worked

in fastboot mode:

```bash
fastboot getvar unlocked
```

`unlocked: yes` means you're good. next: [firmware](firmware.md).
