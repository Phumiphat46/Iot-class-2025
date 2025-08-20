# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
[17:01:08] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [17:01:08] DEBUG | Received CONNACK (0, 0)
It is hard 
Enter QoS level (0, 1, 2): 2
[17:01:16] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6410301032/'', ... (10 bytes)
[17:01:16] PUBLISH REQUESTED | QoS=2 | Message='It is hard' | msgid=1
Enter message to publish: [17:01:16] DEBUG | Received PUBREC (Mid: 1)
[17:01:16] DEBUG | Sending PUBREL (Mid: 1)
[17:01:16] DEBUG | Received PUBCOMP (Mid: 1)
[17:01:16] PUBLISHED | msgid=1
[17:02:08] DEBUG | Sending PINGREQ
[17:02:08] DEBUG | Received PINGRESP
[17:03:08] DEBUG | Sending PINGREQ
[17:03:08] DEBUG | Received PINGRESP
[17:04:09] DEBUG | Sending PINGREQ
[17:04:09] DEBUG | Received PINGRESP
```

## Subscriber_qos.py Output

```
[17:01:02] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
[17:01:02] DEBUG | Received CONNACK (0, 0)
[17:01:02] Connected with result code 0
[17:01:02] DEBUG | Sending SUBSCRIBE (d0, m1) [(b'test/qos/6410301032/', 2)]
[17:01:02] DEBUG | Received SUBACK
[17:01:16] DEBUG | Received PUBLISH (d0, q2, r0, m1), 'test/qos/6410301032/', ...  (10 bytes)
[17:01:16] DEBUG | Sending PUBREC (Mid: 1)
[17:01:16] DEBUG | Received PUBREL (Mid: 1)
[17:01:16] RECEIVED | QoS=2 | Topic=test/qos/6410301032/ | Message=It is hard | msgid=1
[17:01:16] DEBUG | Sending PUBCOMP (Mid: 1)
[17:02:03] DEBUG | Sending PINGREQ
[17:02:03] DEBUG | Received PINGRESP
[17:03:03] DEBUG | Sending PINGREQ
[17:03:03] DEBUG | Received PINGRESP
[17:04:04] DEBUG | Sending PINGREQ
[17:04:04] DEBUG | Received PINGRESP
```