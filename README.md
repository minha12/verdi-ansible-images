## **Running Remote Desktop with XFCE and TightVPN**
- Run `sudo chown -R ubuntu:ubuntu ~/.vnc`
- If vpn at server side haven't started: `vncserver :1`
- Install `RealVNC` at client side
- Run ssh port forwarding at client side: `ssh -L 5901:localhost:5901 <vm_user>@<vm_IP>` (if there is a jumpy host: `ssh -L 5901:localhost:5901 -o 'ProxyJump sshuser@130.236.99.215' ubuntu@<vm_ip>`)
- Enter `localhost:5901` on Real VNC

## **Running Jupter Lab**
- ssh to the VM, run `conda activate`
- Run: `nohup jupyter lab --ip=0.0.0.0 --port=8888 --no-browser &`
- `cat nohup.out `: looking for token
- At client side: `ssh -NfL localhost:8888:localhost:8888 <vm_user>@vm_IP` (if there is a jump host: `ssh -NfL localhost:8888:localhost:8888 -o 'ProxyJump sshuser@130.236.99.215' ubuntu@vm_ip`)
