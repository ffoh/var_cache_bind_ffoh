#var_cache_bind_ffoh
#===================
#
cat >>/etc/bind/named.conf.local <<EONAMED

zone "ffoh" IN {
        type master;
        file "ffoh/ffoh.zone";
        allow-transfer { any; };
        allow-query { ::1/64; 2a01:4f8:161:6487::2/64; 2a01:4f8:161:6487::2; fd73:111:e824::1/48; 2a00:12c0:1015:166::1/48; fe80::f8a8:f6ff:feed:ee2b/64; 192.168.178.0/24; 10.135.0.0/16; 127.0.0.1/32; 141.101.36.19/32; 141.101.36.67/32; 10.207.0.135/16; 109.75.184.140/32; 109.75.177.24/32; 178.162.221.153/32; 5.9.63.137/32; };
};
zone "135.10.in-addr.arpa" IN {
        type master;
        file "ffoh/10.135.zone";
        allow-transfer { any; };
        allow-query { 192.168.178.0/24; 10.135.0.0/16; 127.0.0.1/32; 141.101.36.19/32; 141.101.36.67/32; 10.207.0.135/16; 109.75.184.140; 109.75.177.24/32; 178.162.221.153/32; 5.9.63.137/32; };
};
zone "4.2.8.e.1.1.1.0.3.7.d.f.ip6.arpa" IN {
        type master;
        file "ffoh/fd73:111:e824.zone";
        allow-transfer { any; };
        allow-query { ::1/64; 2a01:4f8:161:6487::2; fd73:111:e824::1/48; 2a00:12c0:1015:166::1/48; fe80::f8a8:f6ff:feed:ee2b/64; 2a01:4f8:161:6487::6; };
};


EONAMED
