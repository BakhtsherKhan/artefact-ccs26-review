# Packet Trace Manifest

This folder contains representative packet traces collected during controlled WeChat experiments. The traces are included to support the paper's empirical claims about recurrent `/mmtls/<id>` traffic, sender/receiver asymmetry, repeated-send behavior, and recovery-sensitive transport activity.

## Files

- `launch_baseline.pcapng`  
  Launch-only baseline trace.

- `send_short_text.pcapng`  
  Sender-side trace during controlled short-text transmission.

- `receive_short_text.pcapng`  
  Receiver-side trace during controlled message reception.

- `receive_while_sender_idle.pcapng`  
  Receiver-side trace while the sender remains idle.

- `repeat_same_text.pcapng`  
  Repeated same-text send experiment.

- `delayed_resend_same_text.pcapng`  
  Delayed resend experiment using the same text.

- `reconnect_then_receive.pcapng`  
  Recovery/reconnect trace followed by receive activity.

## Notes

The traces were collected in a controlled laboratory setting using author-controlled devices and accounts. They are provided only as representative evidence for transport-level observations. The traces should be inspected for `/mmtls/`-associated requests, timing patterns, sender/receiver asymmetry, and recovery-related transport activity.

The traces are not intended to expose private communication contents or third-party user data.