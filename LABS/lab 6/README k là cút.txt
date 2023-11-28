		1.SET PASSWORD FOR MODES

	access using putty,..
-conf t
-line console 0-4
-password "letmein"
-login

	privileges mode
-conf t
-enable password "letmein"
-end

	motd (router)
-conf t
-banner motd "Warning ! Authorized access only"

			
		3.OSPF configuration (router)
-enable
-conf t
-router ospf 'process-id'
-network 'ip-of-network-directly-connected-to-router' 'wildcard-mask' area 'area-id'
-default-information originate(for router have way to internet )
-passive-interface [interface] 
-end



		4.DHCP configuration
ROUTER AS DHCP SERVER
Router(config)#ip dhcp excluded-address 'ip-address or ip range'
Router(config)#ip dhcp pool [tên của pool]
				net
Router(config)#network [ip of network] [subnet mask]
Router(config)#default-router [default-gateway của mạng cần cấp ip]			xx
Router(config)#dns-server [ip of dns server]				xx
NHỚ THÊM CÁI IP


Relay agent (CẤU HÌNH TRÊN SWL3 ĐỂ CHUYỂN TIẾP CÁC GÓI TIN YÊU CẦU CẤP IP MÀ BÌNH THƯỜNG ROUTER CHẶN LẠI)
- ip helper-address [ip-address-of-the-dhcp-server] (cấu hình trên router gần vs mạng cần đc cấp nhất)


		5.STATIC ROUTE (router)
-ip route [destination-network] [subnet mask] [ip of interface of router which is directly connected ]
-ip route 0.0.0.0 0.0.0.0 [ip of interface of router which directly connected to through cloud]





WEB CÓ MẤY CÁI ACL

https://thietbimangcisco.vn/huong-dan-cau-hinh-access-list-acls-tren-thiet-bi-cisco-v-322-327-5251.html





