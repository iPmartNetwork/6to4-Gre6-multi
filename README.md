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

## کد اول 6to4 tunnel

```bash
ip tunnel add 6to4tun_IR mode sit remote IP.KHARJ local ip.IRAN
ip -6 addr add 2001:470:1f10:e1f::1/64 dev 6to4tun_IR
ip link set 6to4tun_IR mtu 1480
ip link set 6to4tun_IR up
```

## Iran

## کد دوم 6to4 tunnel

```bash
ip tunnel add 6to4tun_IR2 mode sit remote IP.KHARJ2 local ip.IRAN
ip -6 addr add 2001:470:1f10:e1f::3/64 dev 6to4tun_IR2
ip link set 6to4tun_IR2 mtu 1480
ip link set 6to4tun_IR2 up
```



<p align="center">===========================================================================


بتدا در سرور ایران باید این دستورات رو وارد کنیم تا تانل Gre6 در سرور ایران ، برقرار شود .


## Iran

## کد اول GRE tunnel

```bash
ip -6 tunnel add GRE6Tun_IR mode ip6gre remote 2001:470:1f10:e1f::2 local 2001:470:1f10:e1f::1
ip addr add 172.16.1.1/30 dev GRE6Tun_IR
ip link set GRE6Tun_IR mtu 1436
ip link set GRE6Tun_IR up
```

## Iran


## کد دوم GRE tunnel

```bash
ip -6 tunnel add GRE6Tun_IR2 mode ip6gre remote 2001:470:1f10:e1f::4 local 2001:470:1f10:e1f::3
ip addr add 172.16.2.1/30 dev GRE6Tun_IR2
ip link set GRE6Tun_IR2 mtu 1436
ip link set GRE6Tun_IR2 up
```



<p align="center">===========================================================================


## Iran


## فقط در سرور ایران وارد میکنیم 

```bash
iptables -F
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT
iptables -I INPUT -p tcp --dport 22 -j ACCEPT
iptables -t nat -A PREROUTING -p tcp ! --dport 22 -j DNAT --to-destination 172.16.1.2
```


<p align="center">===========================================================================



# کد های مربوط به سرورهای خارج 1 و 2


بجای IP.iran و IP.kharej ای پی های سرور خودتون رو وارد کنید






## Karej1

## کد اول 6to4 tunnel



```bash
ip tunnel add 6to4tun_KH mode sit remote IP.Iran local ip.Kharej
ip -6 addr add 2001:470:1f10:e1f::2/64 dev 6to4tun_KH
ip link set 6to4tun_KH mtu 1480
ip link set 6to4tun_KH up
```

## Kharej1

## کد دوم Gre6 tunnel

```bash
ip -6 tunnel add GRE6Tun_KH mode ip6gre remote 2001:470:1f10:e1f::1 local 2001:470:1f10:e1f::2
ip addr add 172.16.1.2/30 dev GRE6Tun_KH
ip link set GRE6Tun_KH mtu 1436
ip link set GRE6Tun_KH up
```



<p align="center">===========================================================================




## Karej2

## کد اول 6to4 tunnel



```bash
ip tunnel add 6to4tun_KH mode sit remote IP.Iran local ip.Kharej
ip -6 addr add 2001:470:1f10:e1f::4 dev 6to4tun_KH
ip link set 6to4tun_KH mtu 1480
ip link set 6to4tun_KH up
```

## Kharej2

## کد دوم Gre6 tunnel

```bash
ip -6 tunnel add GRE6Tun_KH mode ip6gre remote 2001:470:1f10:e1f::3 local 2001:470:1f10:e1f::4
ip addr add 172.16.2.2/30 dev GRE6Tun_KH
ip link set GRE6Tun_KH mtu 1436
ip link set GRE6Tun_KH up
```





# تلگرام

[@ipmart_network](https://t.me/ipmart_network)

[@iPmart Group](https://t.me/ipmartnetwork_gp)




 # حمایت از ما :hearts:
حمایت های شما برای ما دلگرمی بزرگی است<br> 
<p align="left">
<a href="https://plisio.net/donate/kB7QU7f7" target="_blank"><img src="https://plisio.net/img/donate/donate_light_icons_mono.png" alt="Donate Crypto on Plisio" width="240" height="80" /></a><br>
	
|                    TRX                   |                       BNB                         |                    Litecoin                       |
| ---------------------------------------- |:-------------------------------------------------:| -------------------------------------------------:|
| ```TJbTYV1fFo2485sYMyajxGPLFzxmNmPrNA``` |  ```0x4af3de9b303a8d43105e284823d95b4c600961a3``` | ```MPrkzFiNtw4Rg67bbZB6gCxa9LV87orABM``` |	

</p>	




<p align="center">
<picture>
<img width="160" height="160"  alt="XPanel" src="https://github.com/iPmartNetwork/iPmart-SSH/blob/main/images/logo.png">
</picture>
  </p> 




