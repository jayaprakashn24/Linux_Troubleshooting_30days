### Day 4: Server Rebooted Unexpectedly—Where to Check First? 🖥️💥

If your server reboots unexpectedly, troubleshooting quickly is key. Here are some places you should check to pinpoint the cause:

1. **`/etc/fstab`**  
   Check if there are any mount issues, such as filesystem mounting problems, that could have triggered the reboot.

2. **`/var/log/messages`**  
   This log often contains system messages, including error logs, that might explain why the reboot happened.

3. **`dmesg` History in `journalctl`**  
   `dmesg` logs hardware and kernel-related messages. Check `journalctl` for any warnings or errors around the reboot time.

4. **`~/.bashrc`**  
   Unusual modifications to your shell configuration can sometimes cause problems, including system instability.

📌 These logs and configurations are your first line of defense in diagnosing unexpected reboots. Always stay ahead with routine monitoring! 

