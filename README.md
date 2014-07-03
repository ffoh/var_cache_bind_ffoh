var_cache_bind_ffoh
===================

cat >>/etc/bind/named.conf.local <<EONAMED

zone "ffoh" IN {
        type master;
        file "ffoh/ffoh.zone";
        allow-transfer { any; };
        allow-query { 10.135.0.0/18; 127.0.0.1/32; 141.101.36.19/32; 10.207.0.135/16; 109.75.177.24/32; };
};
zone "135.10.in-addr.arpa" IN {
        type master;
        file "ffoh/10.135.zone";
        allow-transfer { any; };
        allow-query { 10.135.0.0/18; 127.0.0.1/32; 141.101.36.19/32; 10.207.0.135/16; 109.75.177.24/32; };
};
zone "4.2.8.e.1.1.1.0.3.7.d.f.ip6.arpa" IN {
        type master;
        file "ffoh/fd73:111:e824.zone";
        allow-transfer { any; };
        allow-query { fd73:111:e824::/48; 2a00:12c0:1015:166::1:1/48; fe80::f8a8:f6ff:feed:ee2b/64; };
};

EONAMED
