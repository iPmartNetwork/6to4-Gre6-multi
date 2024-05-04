<p align="center">
<picture>
<img width="160" height="160"  alt="XPanel" src="https://github.com/iPmartNetwork/iPmart-SSH/blob/main/images/logo.png">
</picture>
  </p> 
<p align="center">
<h1 align="center"/>6to4-Gre6-multi</h1>
<h6 align="center">
تانل برای یک سرور ایران و چند سرور خارج و برعکس 
<h6>
</p>


<p align="center">===========================================================================


تمامی مراحل رو خط به خط برید جلو بجای IP.iran و IP.kharej ای پی های سرور خودتون رو وارد کنید

ابتدا در سرور ایران باید این دستورات رو وارد کنیم تا تانل 6to4 در سرور ایران ، برقرار شود .



## Iran



'''bash
ip tunnel add 6to4tun_IR mode sit remote IP.KHARJ local ip.IRAN
ip -6 addr add 2001:470:1f10:e1f::1/64 dev 6to4tun_IR
ip link set 6to4tun_IR mtu 1480
ip link set 6to4tun_IR up
'''


