# Kwikflix UDP send
## kwik-udp-send

### Features

* Sending ts file(s) as a ts udp stream

* If there is no files to send, it sends null packets

* Works with real-time process/threads priorities to provide stability of the stream

* Works with FIFO files

### Tested environments

* Debian Jessy

* Ubuntu 14.04 LTS

### Build

Just run make in the project directory

### Command-line options

* -i &lt;address&gt; - ip address to send packets

* -p &lt;port&gt; - port to send packets

* -b &lt;bitrate&gt; - bitrate of stream

* -d &lt;path to directory&gt; - send all files from a directory, sorted my modified time, the directory is scanned in real-time, you can add files on fly

* -f &lt;path to file&gt; - send one file, you have to select either a file or a directory

* --ts_in_cache &lt;number&gt;, -s &lt;number&gt; - commons cache size

* --accumul_ts &lt;number&gt;, -a &lt;number&gt; - size of filled cache part

* --ttl &lt;number&gt;, -t &lt;number&gt; - set ttl

* --pri &lt;number&gt;, -P &lt;number&gt; - set the process/thread priority

* --ts_in_udp &lt;number&gt;, -u &lt;number&gt; - the number of ts packets in one udp packet

* -c - don't stop file reading if it read zero bytes, use it for FIFO files

* -m - print debugging messages on the screen

* -l &lt;file name&gt; - save debugging messages to a file 

###Examples

####Reading directory
sudo ./kwik_udp_send -d /ts -i 239.0.0.10 -p 1234 -l ./log --ts_in_cache 40000 --accumul_ts 20000 -b 2000320

####Reading FIFO file, generated by ffmpeg
sudo ./kwik_udp_send -f /ts/tst.ts -i 239.0.0.10 -p 1234 -l ./log --ts_in_cache 40000 --accumul_ts 20000 -b 2000320 -c

### Feedbacks and tickets

We will appreciate you feedbacks or any contribution to our app. So, create tickets and let's discuss.


