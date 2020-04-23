Troubleshooting Error:
```
Exception in thread "main" java.net.UnknownHostException: google.com: System error
	at com.oracle.svm.jni.JNIJavaCallWrappers.jniInvoke_VA_LIST:Ljava_net_UnknownHostException_2_0002e_0003cinit_0003e_00028Ljava_lang_String_2_00029V(JNIJavaCallWrappers.java:0)
	at java.net.Inet4AddressImpl.lookupAllHostAddr(Inet4AddressImpl.java)
	at java.net.InetAddress$PlatformNameService.lookupAllHostAddr(InetAddress.java:929)
	at java.net.InetAddress.getAddressesFromNameService(InetAddress.java:1515)
	at java.net.InetAddress$NameServiceAddresses.get(InetAddress.java:848)
	at java.net.InetAddress.getAllByName0(InetAddress.java:1505)
	at java.net.InetAddress.getAllByName(InetAddress.java:1364)
	at java.net.InetAddress.getAllByName(InetAddress.java:1298)
	at java.net.InetAddress.getByName(InetAddress.java:1248)
	at Main.main(Main.java:7)
```

```
docker build -f Dockerfile.scratch -t graalvm-dns-issue-scratch .
docker run --rm graalvm-dns-issue-scratch

docker build -f Dockerfile.distroless-static -t graalvm-dns-issue-distroless-static .
docker run --rm graalvm-dns-issue-distroless-static

docker build -f Dockerfile.ubuntu -t graalvm-dns-issue-ubuntu .
docker run --rm graalvm-dns-issue-ubuntu
```
