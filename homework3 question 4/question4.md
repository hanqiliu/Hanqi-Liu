Question 4
================

Firstly, we should scale and center the data, and also extract the
centers and the scales from the data. By generally checking the data
from social\_marketing dataset, we plan to not take the spam and adult
part into consideration when we think about the marketing segment this
time.

Then we plan to find the number of clusters by finding k\_mean.

We plan to try to find the optimal K\_mean based on the elbow plot for
clustering,and in order to make sure that the SSE within the cluster is
relatively low.

From the following elbow plot, we can see the SSE within the cluster
vesus K. And this is going to go down with K and we’re going to
basically find where it stops going down all that fast.

So in this elbow plot, we know that when K-mean=10, the SSE=18000. And
when k=20, the SSE is around at 16000, so I plan to choose k\_mean as 12
and use it to cluster.

    Warning: did not converge in 10 iterations
    
    Warning: did not converge in 10 iterations
    
    Warning: did not converge in 10 iterations

![](question4-2011_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

Then, we can try k\_means clustering with considering the PCA scores.

In ordet to make it clear, we generally show how the PCA1 and PCA2 look
like.

    Importance of components:
                             PC1    PC2    PC3    PC4     PC5     PC6     PC7
    Standard deviation     5.195 4.0282 3.8075 3.7078 3.21592 2.63072 2.13444
    Proportion of Variance 0.216 0.1298 0.1160 0.1100 0.08274 0.05537 0.03645
    Cumulative Proportion  0.216 0.3458 0.4617 0.5717 0.65448 0.70985 0.74630
                               PC8     PC9    PC10    PC11   PC12    PC13
    Standard deviation     2.02608 1.82266 1.44695 1.36768 1.2893 1.26840
    Proportion of Variance 0.03284 0.02658 0.01675 0.01497 0.0133 0.01287
    Cumulative Proportion  0.77914 0.80572 0.82247 0.83744 0.8507 0.86361
                              PC14    PC15    PC16    PC17    PC18    PC19
    Standard deviation     1.23037 1.21514 1.12994 1.08680 1.07053 0.98946
    Proportion of Variance 0.01211 0.01181 0.01021 0.00945 0.00917 0.00783
    Cumulative Proportion  0.87572 0.88753 0.89775 0.90720 0.91637 0.92420
                              PC20    PC21    PC22    PC23    PC24    PC25
    Standard deviation     0.96864 0.94501 0.92286 0.90292 0.87677 0.87362
    Proportion of Variance 0.00751 0.00714 0.00681 0.00652 0.00615 0.00611
    Cumulative Proportion  0.93170 0.93885 0.94566 0.95219 0.95834 0.96444
                              PC26    PC27    PC28    PC29    PC30    PC31
    Standard deviation     0.85706 0.84120 0.80194 0.74352 0.72553 0.71163
    Proportion of Variance 0.00588 0.00566 0.00515 0.00442 0.00421 0.00405
    Cumulative Proportion  0.97032 0.97598 0.98113 0.98555 0.98976 0.99381
                              PC32    PC33
    Standard deviation     0.65588 0.58595
    Proportion of Variance 0.00344 0.00275
    Cumulative Proportion  0.99725 1.00000

``` 
                         PC1         PC2
current_events   0.013586204  0.04168688
travel           0.005446709  0.19518833
photo_sharing    0.106607662  0.35086526
uncategorized    0.024221313  0.03378822
tv_film          0.005013021  0.06093009
sports_fandom    0.020222401  0.11619035
politics         0.002972377  0.28880326
food             0.095742095  0.06000650
family           0.018343417  0.05971055
home_and_garden  0.014467364  0.02234408
music            0.023045084  0.05678880
news             0.017175898  0.13604921
online_gaming    0.013950537  0.29506263
shopping         0.036364035  0.11448894
health_nutrition 0.818370614 -0.27916539
college_uni      0.002075209  0.35470212
sports_playing   0.018086196  0.08817966
cooking          0.336817136  0.48797048
eco              0.037660102  0.01686240
computers        0.013989361  0.09426921
business         0.011348399  0.03437327
outdoors         0.146248382 -0.02429196
crafts           0.019991048  0.03265181
automotive       0.003060715  0.07930400
art              0.019037628  0.05540921
religion         0.027814610  0.09577868
beauty           0.057672785  0.17553168
parenting        0.028410162  0.07655781
dating           0.035554319  0.04104439
school           0.019387158  0.06551356
personal_fitness 0.390875042 -0.11169165
fashion          0.092609705  0.26357926
small_business   0.004284617  0.03080005
```

By classifying the PCA of the social marketing data, we can see the
different clusters have different features for the PCA.

Cluster 6：In this cluster, there are users/accounts with high PCA1 score
and low PCA2 score.

Cluster 3 ：This cluster comprises of customers with low PCA1 score and
high PCA2 score.

Cluster 8 and 9： These two cluster both have medium PCA1 and PCA2 score.
![](question4-2011_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

We can also produce analysis by taking more PCA characteristics into
consideration. For example, analyze the relationship between clusters
and PCAs.

The following graph shows some obvious features.

Cluster 3 and Cluster 9: These two cluster has high PCA3 scores and PCA4
scores.

Cluster 6: This cluster comprises of users with medium PCA3 and PCA4
scores.

![](question4-2011_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

In this way, the companies could push the different products to
different users/consumers considering their different PCA features.

Then we can try to run kmeans with 12 clusters and starts 50

After clustering, we can figure out which users belong to use clusters.
Considering there are thousands of consumers here, we just show the
situation in cluster 1 and cluster 2.

But that already could show the companies could sell the products to
different clusters, and they can find the specific consumers by knowing
which users belong to which
    cluster.

    Warning: Quick-TRANSfer stage steps exceeded maximum (= 394100)

    jcsovtak3 tmf4x9sbh ki8bl7zpw gqp5jbd6c d8rl7myjh hj1fg7825 7o5etmfc9 
            3        28        85       119       143       172       219 
    gortd4syb 98g7an2rd zu38ts1kx efu5sw32m lkdwf2ebz 3iwvo8qad qwahy715l 
          257       268       301       345       411       430       461 
    iwdfzc5kq 7dakzt4qv 4bdheyqs7 52pw9stie lfi84y5zs 7vdkp8lfm 47kqhuf3g 
          495       508       509       522       531       642       646 
    nqmi8tk4c de9ly4mru gdu69of7x vjnh5sk8r rouxlc86a b2f3jhqnz w8zljehrb 
          728       753       766       772       826       859       900 
    ar95hctjz vita1x3n7 2q4rhmfcj tzkcngx7v 9sjxt7pei wkz6j7xvg 3wk8xgtl5 
          910       941       961      1017      1091      1157      1159 
    a2cjlwxmn iahldj9xz 2x6sdcgb9 jo3kzgb78 m6lzdrfpn rgpbcyj1a yj6cuzixs 
         1162      1201      1243      1251      1299      1340      1347 
    mhkdow2li 9h7q5jdew r6538oznv zqlt32a46 q86fgr2en fevk1auqt 2p6uxsdri 
         1365      1367      1454      1474      1479      1515      1556 
    k462qrt1d lygi1253t gzwrbpdfx 2wgjhykqt c4wl1m7ea p9gvb5z7l ixa4srg6d 
         1649      1651      1663      1674      1724      1756      1780 
    6mcjy4had q6wlkujz5 sl78xkm9r ov56hjlnm otxf6bsnh lc1zq2m3t n3e64rz9p 
         1805      1831      1858      1931      2000      2065      2119 
    8vb5xhqzs yxflewro4 tflh3i612 l3rt8hfd1 soj1iaqly 5s2fv9eq4 vmc5hi4dx 
         2315      2365      2367      2372      2415      2418      2423 
    zsodvw823 rw85vfbz4 jq5c9o2vs 4p6snufmo nj7ufxqcv 5ftqpjswa i3ykjmdo2 
         2431      2466      2543      2592      2643      2644      2754 
    5khdpx4ol u4s6fy9a7 hza8b4fsk l3p98maq7 4m5tuzyrl s7qzym8dx gmyaecnt3 
         2759      2802      2807      2810      2860      2864      2874 
    xjvt7ko3h xmnrqgc27 g28lra9bu rz8beao3i r53smozcl x9iwtrdef 721pnqv3z 
         2886      2908      2918      2924      2926      2928      3003 
    zn1ryclie 2tajdrpf3 jdtrfmzia ouspx8r69 l9pao48ti vk8xb2sin baw2c64d5 
         3010      3016      3024      3034      3064      3075      3134 
    jn41dqltg scr8lgiho 3gwedqusm 5wlfhd913 h6kcjn7xv q1ju8vsf9 mkd5pn8ji 
         3178      3200      3215      3226      3240      3290      3295 
    prmjzwxg2 8chmrbsa1 v8mbdxg9a 7anl2mdpj njz7xr1mu lm8qdyx6i jegzpb85c 
         3303      3313      3403      3421      3441      3462      3499 
    opy6zic9t pi4samlc6 1eroncxda qp18isyau m67ghad53 13cikre8g amvfy7zqj 
         3503      3573      3578      3614      3623      3675      3681 
    x5m4pbtgc ghr9iolm8 1lgiwu56p 81du296qo r14tslivy 9q2itp36x ktb9w4qgd 
         3685      3690      3704      3706      3729      3751      3769 
    9uc4nfxbw dh9p7q1ai wolhxkqna d69weuqyk p9wcfgai2 yk6uqtg47 7qmjs49cb 
         3780      3786      3792      3795      3811      3882      3886 
    6qa35uhfm 9q1r6pa2e 2sh3v1fbz mkwznad4r xmzdwj5sr ojlyzv8kw 5iuqjyntv 
         3907      3924      4026      4073      4082      4124      4128 
    zunr4qady sageowm71 ingdku289 8jrt2yce4 vz3qiy1s9 2nuixzd7j 9d6klwrp5 
         4152      4166      4174      4221      4241      4260      4337 
    vi7w5ued2 ghxvekycw 3uh6d9xba h82spwl67 6tpix78m4 d7hz1fxpg tu9ce64oh 
         4348      4350      4395      4403      4443      4570      4685 
    9yke3bthz 5bgzd4fca c5b7rud4z sq3ozux5d 3bvo2xphf 613uwno52 e4pv9osi8 
         4713      4724      4799      4827      4841      4912      4942 
    n9pzhl41x 5x1bh6rua d8tg9bqkf 7gl3ymxkd 4y7vjcqsi 3sh87cz5v enf4dijr9 
         5014      5056      5135      5136      5212      5214      5216 
    2rjgfvqtp 5vqxs8173 quz17o6vx 5bh6yzp8u daxkbgmpy o2ibnydc3 qdpe4gwri 
         5263      5274      5275      5279      5303      5310      5318 
    pgbm96xuh qtnkzm4ar iqlft9zdy rd5woasxi g3hd8olnp gsrv31naz 9kih1vbsf 
         5337      5355      5366      5443      5444      5482      5509 
    zvthek9bm 9veksz1qy dnb53c29j lwnzumgct t59vhlk2p vsfx4lcaz vmhp9r4t1 
         5604      5605      5647      5665      5674      5699      5711 
    uvl75pi61 5ct12vyro 4x85w6ymq npo1t5gke jfywl5nev kv1nhi8x3 fcuwvesbh 
         5716      5720      5803      5807      5815      5842      5870 
    na3mq4jct rbju3p2fq hjr86wduc 8k7zn3spm f819zlysa lvhbnzyo2 zrxuhlg6a 
         5905      5919      5931      5979      5994      6028      6034 
    kuq28gx3r nhgkp9boe bxiktoncj hwj14iq3z imdk4vtlp 7ei1ghu26 zol64mrxk 
         6073      6142      6227      6294      6334      6364      6390 
    6lwbdxuo5 d5zus7xnb 7p5rscbh3 fz8w6il31 vwrmqs5tg 8rvh7e5ct y7amf3bpd 
         6402      6418      6454      6476      6483      6492      6574 
    wx7ny8qha qluv8exhr ak1moufzc qyu9rve8t tsfokry48 qtg8yrjvo udf9halbm 
         6605      6622      6701      6707      6759      6761      6765 
    dipoqa5j9 7wk2tnpjg nf3meka5b bw6oeymd8 1to4xd5uv rovbilj4d 9kuavnp1o 
         6769      6773      6786      6818      6824      6832      6842 
    62i4kxqfd 5eugx3m4b rahqjuvxt mj5t9g4kw i8u21rgzt 35o6e429n oth87kf2r 
         6869      6872      6983      7010      7092      7096      7097 
    4v8na39gd 92vl3yp16 c9yudvbm1 lx1es35ho z9kvtonem u573rqb1v g5wh7ej48 
         7098      7109      7157      7241      7265      7359      7373 
    zlrwfm9hs zq5lji23g 4qrlgito9 r6xj5et2y uqmsbwace m7wjkvql4 yrflutpds 
         7457      7458      7459      7502      7543      7615      7618 
    kp6dgs8bc 4dyzw69ne jb5wugdy8 156g3au4h gqf14e8kw ejhw263x1 
         7671      7684      7734      7788      7873      7882 

    clk1m5w8s q9d8z4fyt rk1fcwuay yrxhg97pq xfpi6v3cz y2ej1v9ap bmphf36rx 
            2        11        26        29        34        60        62 
    39ngbfx71 auw63d1mi chytokxf3 253mq6j4b lwk5cndmx tmo5pwiqg 4kidun9fr 
           72        77        94       126       146       152       155 
    qgbeln71p ht9rwxbj2 7o8m1gja2 pxldrwo3k esy96m2hd 652ef4i7s azf3b7emn 
          156       179       191       193       204       208       232 
    b3o19kf7s cwjo8htd9 9g4imoe5t zv2i13t4x esrt2lac5 t3mwyx5zu 68nir4sx3 
          235       238       242       247       294       326       349 
    5akh83bix rhlcubv3q oqf4mjskh eutriydfs qph9tx6c4 24hk71xfz wfhuvekix 
          351       352       390       415       426       459       464 
    jl3z85ndw i82vaxo3m o98mpwy45 goc1ph6l2 aewd3mq74 wpunvekzy u6zhw2o1t 
          465       469       470       477       489       500       510 
    4mq68bg3h huefp4mjo 9hcpb3oi2 umj3xsnc2 exq59zypv 29f86dyu4 vc9s3po2d 
          545       547       548       564       565       567       611 
    45rihnlf6 62t583a9s vw6o14ihe qv7lsjhx4 dn5ogilh2 4dro51v3p eb6nftj2i 
          613       615       616       618       622       632       633 
    4blkdznwo s2367gz4o kobm1ca9d enty1rp7o 4z52rnm3f wu1ob42py 9as8u6pil 
          647       652       666       669       696       699       720 
    d5s6rjx4y buatxn87m jbdqw129t wgid7hf2v wsiqt1xpu 9rdyohlg8 s2g345atd 
          738       739       742       759       771       775       785 
    2rhznfowj r3pufmsbz 1m5hb48co j83q5c9g1 4pjr6asbh cm4x2ekzy chlwq42du 
          819       861       863       904       907       921       924 
    l2mfvr6hs 2wykqezgv cgdquv2ra b4f2r1tqw tnyxsjhcz paywr2q4l odst3kaix 
          940       945       953       974       995       996      1001 
    zr631tvip xpbq5wuih u2shcbx39 2vwjpkz5a h42ck189z ophdc7bnl rfehxy7pn 
         1011      1012      1048      1068      1072      1083      1088 
    f164me58v vz5gm8lca oxgk1mvre 5fe6mcsnj 8qwagxjpn ilrbzjwpv domnhty4z 
         1089      1112      1121      1122      1130      1138      1140 
    qhxzc96vw x14ablmsk d53cazvqi gyvzp3t4a anqkjh73w edvtwzsbx frib68mnx 
         1141      1142      1148      1166      1168      1169      1219 
    k76i49zob uhbmoakd4 fwkhaxrql bjg84dy7w 6nbrdq3lg netbw8xr9 5m146g37u 
         1230      1252      1285      1326      1328      1343      1351 
    6br754yjh av2fko75z lnjqpr47s fw17qyrsp 6vupjh54y we43ta2c5 jxomg9lq6 
         1352      1369      1375      1389      1395      1399      1401 
    aliyvo7jt 813xbgzrv y75etlwmh a4f9lz7ge 89sn57fhy elasnpguj 1gkf6j4mi 
         1407      1423      1437      1444      1481      1504      1523 
    akhomrdb4 juzroyb7g h4scpfoxi r2odlkgxu zw72pkmve ef5bys8d3 r3sydglbf 
         1526      1554      1574      1590      1609      1623      1642 
    agbxmr8y7 shbx5en12 ivwuat6eo 3fgtu85w2 d3aevwtbz z42lq7b6e cyvu6j7rq 
         1654      1666      1669      1684      1695      1721      1723 
    um98cj4vk ikdu3q1sr yehrw9v5g ia4mcnrpl h3imlrgvs cl1pwv54n dz3i6rqen 
         1732      1735      1745      1746      1757      1779      1781 
    1b84t3gdj n38h97pfx 5witf46am x6u8esit7 wbvx4368s fmzwtx786 fq27g6w5n 
         1794      1811      1812      1829      1836      1862      1867 
    9kxqm4y3s se8f4mjah ki5enbar3 j7y4h6q2r t4marlq2j 7dc2asmhi npuaoqrz6 
         1868      1874      1884      1885      1900      1912      1952 
    wv46cj73g rcukhms2e n3bi8vkor x6ut9bqr4 puaqyzsol qkjic8zw7 3ikmp5wno 
         1955      1956      1975      1999      2030      2032      2036 
    tpde8r29q 12grikctu mxn37u82c v62rog43a dk1pfzngt admgu7op5 b4nskhlyc 
         2037      2045      2059      2063      2083      2085      2089 
    3tnxqadvc 9ruv6z3bc 12yam59l3 7bnpkge5t ko3nsb7rg bdnrhpszm 2klieydmz 
         2094      2098      2108      2109      2120      2136      2145 
    tdgex9urf f4v1auhpk 4tbcghp2m 74zajyve6 7a6ex93j1 mykcov896 23pxf65cz 
         2171      2175      2177      2185      2192      2196      2277 
    mftq862n5 z95woi8ea pbfvwa2iy wr4dbty1c 768karw5y 4gp8hqyvw odfpu43yc 
         2307      2322      2325      2344      2345      2352      2353 
    cwpsvb4uo cxi379uhe dnsx2crbl qzgkupfya ucqxeln5s zcd9ruv48 ryseix36n 
         2368      2371      2376      2406      2410      2449      2468 
    wstvxu5nz elvhxyum5 ucb59ylzg 3e68jysku 8yhxudzkj leoiqtjgk 8dtbnu51a 
         2469      2477      2489      2491      2494      2498      2525 
    wi8vauo7c 37qau5wlv 2bd9r73fp zitnu2w8f 46tnkrpmb s5wcx6t71 9mqiexghl 
         2526      2530      2539      2540      2557      2560      2599 
    v8zixpmnf t3g2bepjy fkr6i2pn8 8uhr9okyl v7eihtog1 ye9hwbv3a gozjkwmpb 
         2677      2687      2692      2699      2709      2717      2726 
    bp5cadu8j lzco5e4sk axz5epi3g 5eiwmtqor egoj26zqh 9ansbwzj1 jo9r421q7 
         2727      2731      2734      2749      2758      2816      2824 
    dhi32syg8 7uylcadzo c8iyf6se1 icg2k1vm7 6myln15wa jnqgkla96 nhc4z62eg 
         2826      2832      2845      2853      2865      2875      2903 
    alz86xnjf glmjyb258 wmqk9yhas us4h1pqvy rw7vmf9ae 5tk4q1pvb 9k3g8cytb 
         2917      2933      2934      2971      2977      2981      2987 
    yuwbn5ztv jin1549qu niorpwu93 j9hqgie8s h8gdtc9rw kfi81mpet 3mbzri7cv 
         2989      3019      3025      3052      3062      3066      3077 
    jkomcrz23 xw8cyktbf ajn26txip 76awrcl2s 7w5rl4vb9 nwy45t7dq haum2ztkb 
         3086      3100      3104      3129      3133      3149      3158 
    vgy52za6n lb254c93w rio23yw4g tizu63dbr 7rpda4gvi qoskgnlvc 3orabtiqg 
         3168      3184      3207      3228      3229      3261      3274 
    3c67jptq4 7xe1auimr lsf4wuq1p 98h46snij 2pbzyaesr blfjwmhd6 quorajbmh 
         3306      3320      3324      3353      3380      3394      3399 
    h16xul38g tuxmqk37l e8tdw7lo4 lvk2aoqds 9divn6rz1 jg3kyp94i zyi2gtp71 
         3405      3415      3417      3424      3434      3440      3448 
    k1scyvlmh zw1tuyk6q i6w5o4cpl jpder15wx de5t2zx1s z5y89hmjx lk5aqg28e 
         3459      3476      3481      3489      3490      3511      3518 
    rwqtp8vj6 7vx41nb96 qfn9cpko8 4xmw6j2ho 9usq8ila1 ahfuqc278 b6ehiq3xo 
         3520      3524      3536      3543      3547      3568      3569 
    2qcwzbm14 3ytsxr46h ekqjwligp 9fzxyvje2 qa6b2gejn 3n514y2xh 68fpteo4k 
         3579      3596      3618      3625      3632      3637      3641 
    wgczjq7e6 m534alngj sa5wh3f2c e4b9xoyg3 j8532rtc4 8i3tobgez 5kr2tmweg 
         3642      3649      3659      3661      3665      3674      3678 
    yov4ax8g9 vbaoexwcl w7or5cqpt 251kbuca7 h2xe9nydz wrzu7snxp qtvnj75w4 
         3684      3710      3712      3713      3743      3746      3759 
    yxkdeu9ig vxyr6kh4l hm967qaxe ko4di8vau 1tr4k8yeb l83h5pzjy wbr1xmpk2 
         3767      3774      3801      3823      3824      3838      3849 
    a59uphdwc cnpudevz8 na58pulf4 uzkd3f2bh mkptxr9h5 97ycdfniz 7ygxao5b2 
         3858      3887      3888      3914      3916      3917      3933 
    75qlk69rd 5v6de3xw1 uxikaf3rb xp3g21qrt cpthsd9n8 t54e1odql qmbjacuod 
         3944      3953      3956      3986      3995      4012      4015 
    wzoam43fs iu2xkg349 sgdlifmey d36c1senr 5m91c6wyv krdopwysc 1coe82dkm 
         4018      4019      4029      4031      4034      4054      4058 
    mxk4qfe7j 9blc8ktdg o8s21jtvf oiphld1mn 4lgikx36y 6wrj7kvfg cvd1a3smk 
         4065      4070      4101      4104      4115      4125      4127 
    4mkos6vzg x5zeb6kin 21j8p5vxc cnrzhtmqb oyawg75lc dms8n3zuk dvahpbg5c 
         4130      4150      4151      4167      4185      4187      4189 
    89qma65jk b7dvoqf46 6mcf7kqi4 y3m7z268o ebw94ihg7 ywuofcaqk myq62kagn 
         4198      4204      4252      4301      4304      4313      4317 
    6fap7s5h1 oa2kh9cq1 nev69b8yj zd8vw7a2y uezhcofw7 apgsjlt81 7nv9xg6aq 
         4318      4327      4364      4371      4373      4388      4399 
    l972zuj1k vna9h2wbi 3onue9izh mr7s63q95 ayl965i2d ontei7bx4 8hytwk3vo 
         4416      4425      4427      4437      4448      4451      4454 
    f698k4bhr zomgd7nv5 953lx1vbu wdku8cyx6 b7yw1ev5s j6mgv4fye ze14vut3p 
         4472      4475      4529      4567      4598      4604      4630 
    yc1gpaem6 bpmt8rv4x ftxldy8zq i4ousw3k7 luqnkevoc fzxjqk4c7 gl81s7rwh 
         4650      4653      4660      4669      4674      4684      4688 
    ibvqp43ge fwcyzd94p x8wyi5boz gqjalp9br nhsqgia76 3rj49lqmi suedkwtga 
         4701      4702      4709      4716      4717      4739      4749 
    aklnsf864 9rm7hbg3c xtch6jf17 v32mpszc8 tuqiz79fv rmotz2w4q 2zfanj1ir 
         4756      4779      4785      4828      4830      4836      4871 
    nupcjiavk 3wh7s29dp 314bfaurp kcb897i6h g82vlutp7 a6sgbq7yl dn9538xyb 
         4875      4878      4885      4897      4901      4903      4923 
    kahvbgdpw 18yrso2z6 6mdi8wjlx zucboyk8m rmfb3d6p8 98hiz4jdl iulbg2a96 
         4924      4932      4941      4947      4960      4964      4978 
    6datz1j8x vs4iqbwyr mvioe2nbl am9ty4bgz ql5b9xg7p pdszt1ocf yj6r8pbfi 
         5000      5001      5022      5039      5050      5054      5061 
    3g74ktp62 ti1wr2zs7 8tcp3f9l1 6baufk5dy 91chuq6fo ge21lqf7m fy39rew7k 
         5065      5076      5077      5087      5096      5106      5107 
    2rzp6gey9 e8zu1rdmf g39puwz2k uvlk1ch42 8op9ear52 lmq3hwt4f 8ikqjb9az 
         5149      5153      5156      5162      5171      5180      5184 
    c38sxudz7 t9x8b23lc 1snw4fu56 yvl1z7wag 34uysik9c 1tfulp7qa x8saty3jz 
         5188      5191      5201      5208      5217      5232      5298 
    4ul1vhoy9 xdzkabnm8 7215qbf4u lv8r3hkpd v6fbdgu58 5a64tqpiv awvo3fblg 
         5304      5325      5329      5338      5341      5343      5377 
    l54sv3z7a kanepjw7v 1u8nd6ljf m3f4n7qeh dfptq1x9s dvm7r1stu 9etwul1po 
         5390      5397      5402      5405      5415      5422      5433 
    bwrofmt7c 7z8th1qnc 8lzut1vpw 5va9tkrfu w67hsqki3 mqny8fcr5 v7l4jxhzy 
         5436      5459      5468      5474      5477      5481      5485 
    omul5yp8v yf4jpwnds nc8m7uhsy dywh38zxt gewm45lo6 ch5gejs1p t9cmevj2l 
         5498      5516      5533      5557      5578      5579      5595 
    e36afhi7y k4jf3d8z9 vfal7qmdc dpxnvwz6s mcjogi768 j2nshmpbw eds9qfrlg 
         5617      5628      5635      5653      5661      5664      5670 
    ygukjbmsc qu2znirh1 kewhxzrcj h1mv5736e zkthxm2u4 2ajifr95y bzax92ty8 
         5671      5680      5682      5694      5697      5708      5715 
    dla71njt8 atnyh9mvu aqz47rful rv1cjqlih jdyk41e7f d27xi5swk ojpqaz4yr 
         5734      5736      5759      5774      5791      5800      5804 
    xdmnw2tsg ev7sl84gn f4bjrsqe2 w78znuk92 xzp9ftlc3 hyidfnpwc tujkzmwgf 
         5823      5835      5851      5856      5900      5925      5930 
    5oq68ahtl 83s2zm9jy q2c4erndz i5edgc94b mj1vf8ael iln79vowa mis5h8qtn 
         5935      5953      5961      5984      5993      5995      6023 
    evznmk53b 1onxqbj3a ljetbvu1g x2vq61cao zw5xvpu8h 5f7xrcvge ix9qc35su 
         6027      6038      6049      6097      6114      6126      6130 
    xsqta6l87 onidm5qaf 51fyxlmtu q2sxdozp7 7ferx23lb va7fhys3x i4ubpt9go 
         6151      6174      6196      6212      6213      6226      6266 
    2vw9e3n1j dvtr49p7c gc7trspiy anywgx3ju pgncm1jwy syp6hdf8e x14dmighk 
         6286      6290      6296      6297      6332      6353      6357 
    lrxymjg84 dtpzw5yng gtoywb3pe ze9s1u7fb wosi2b4lz xnmzelhrq dc5uo7r6x 
         6359      6362      6366      6369      6375      6414      6415 
    jlsrmwken 8rc9f3j56 i89k5ydex pnrq5c7ud 2crlsaxg3 bjt725y3w nfkqezvtj 
         6425      6429      6442      6461      6462      6470      6477 
    657mgpa98 nhrbgfjkp f8a7e356u qirj42clg iunwqs1hj l2v37a6dm tu17jzdw4 
         6496      6502      6525      6551      6569      6582      6604 
    lzxckur9n izunfw3kv grvc1lkab s1ezpy9vb 82qwtvgca l812bzgnf rofvna6d9 
         6612      6625      6639      6652      6670      6672      6675 
    de348t79x wr9j537ge kulsth8n5 xnghqt29o 3dkbglyas f26k1xwjq p79rkgwue 
         6683      6685      6699      6712      6724      6731      6739 
    hcvgi3aq2 a1v9eq2mf cpywz8vq7 lw6i17xs8 aei6b9uqn ctv1irkym og3wrxhp4 
         6747      6792      6801      6809      6825      6865      6882 
    j4fpvdn7m il2ejsu9f olk596rfc uvzjimf8r 5mgv6aqs7 3iublsac6 exalhsrc4 
         6898      6903      6911      6970      6971      6972      6975 
    m5gn6fr73 3z1uwk7cd 62t1g9kx8 fejt1cwox zrhxtbea8 f4x18lubm y3vl6hnmj 
         6991      7016      7037      7048      7052      7070      7077 
    5fjeyvmb9 oqhia5yxm 7z1frbyev kh5frald7 r4hdkcy1f szbmp21gk h936wierl 
         7111      7130      7133      7192      7194      7195      7198 
    z9sa4i7uh sfvlbj48o 9prny1q5l v6mqsy1w5 osjpvdlm8 3stlrfg8m playekct6 
         7218      7227      7242      7243      7256      7268      7269 
    gc1f58h4y jck487pz1 vd92uqaw1 bgp76dj3l y9ci865kw nl2q13xid cx5296tym 
         7339      7346      7347      7360      7362      7377      7380 
    hojsmn43w wgm25podk tlj6d4uhv 7ratmjzil dlb79r1et 3juoyk2hi al5t9b2i3 
         7397      7418      7429      7448      7461      7463      7469 
    ybm6xa1n9 9lw5q2i3d epbjzyt4o v41r6k3w8 lzvx9o2f3 n7iwpf3o1 7dmv8nzou 
         7479      7483      7512      7517      7531      7533      7535 
    inzyxcmb7 v8fd39bxj qmz8n1527 vftknmzgh 7run4gihj t461qgrsp owys6z7bf 
         7539      7569      7589      7595      7606      7619      7624 
    dhptx41jl d6uc2yzx5 re4plxsdb 74d9svxc8 mwdhfpbxi 9cs2probd nquhc1r3l 
         7646      7648      7655      7661      7675      7683      7694 
    hd8z5cnfi 1rekzqocv wvjms3625 em28zfwpc odme8l6h5 bph8o74d3 amvtfj4yk 
         7701      7705      7731      7743      7746      7760      7763 
    ae1brngk5 z591ojcl7 2s9id4h7c itzv75we8 pg5e6uq4n dtycifnzl 7e14g8pvl 
         7772      7774      7778      7784      7790      7794      7798 
    9x8m1ds4p dsj4b5epm 5zk4n89ap ik3hrcpa8 kgh84r6xf 3kij46emb 
         7799      7821      7824      7840      7842      7863 

By considering the characteristics of differnet variables, we can draw
the graphs to see that the different features of different clusters to
figure out their relatively obvious features.

For example, we can take the features
\[travel,photo\_sharing\],\[tv\_film,sports\_fandom\],\[family,home\_and\_garden\],\[beauty,personal\_fittness\]
together.

From the chart below, we can generally see that the cluster 12 has
relatively more common features in travel and photo\_sharing.

![](question4-2011_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

And it is clear to find that cluster 10 has more common fatures in
sports\_fandom and tv\_films.

![](question4-2011_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

Futhermore, it is easy to see that cluster 5 has more interests in
home\_and\_graden and family topics.

![](question4-2011_files/figure-gfm/unnamed-chunk-10-1.png)<!-- -->

Then, considering the personal\_fitness and the beauty content, we can
see that accounts in cluster 10 mention much more times than other
cluster in their Twitter.

![](question4-2011_files/figure-gfm/unnamed-chunk-11-1.png)<!-- -->

So after seeing the result from that and consider the aim of marketing
segment, we can try to put more sports ads for people in the cluster 10
before they watch television and films.

And for people like travel and photo sharing, like the people in the
cluster 12, the marketing department can push more advertisements of the
famous travelling locations in their Twitter or Instagram and other
social media that has photo sharing functions.

And for accounts in cluster 5, who may be parents have concerns about
the home construction and family themes, marketing can provide more
information about garden, family careness and some similar content on
their pages to attract their attention.

We know that marketing segment is one of the most important part in the
business to help companies to push their advertisements and attract
potential consumers to buy their products, and also a good way for the
social media like Twitter to push advertisements to their users more
efficiently, more attracitvely to enhance the probability of business
success.

Then we take the second run by using kmeans++ initialization and compare
the general result with the first run. We can also see which consumers
in which cluster
    now.

    3oeb4hiln fd75x1vgk zm8kt97ic 4odi1h6wq 6vyz8cwje 3pifxrgs1 g9xyksvu2 
            4         5        14        15        16        19        23 
    znu9lvmbw 64qgjkp2c 9ibsc4f56 9nsby7rfw mieb19fnc s7rpq6c9g lv7s9u8xp 
           24        25        27        31        35        36        40 
    wo3bsa5vx j9sgq3bz2 jfykhpt1c su164zqjk o7jeqmb29 gyi2s5v4x tlk3f7eox 
           41        44        47        49        51        52        58 
    cytl5gjko l1tu6q4hr 8zsk4r31o hnzmja58y u1vfzh7k5 jqs4feybt 3axo81iy2 
           59        61        65        69        71        75        76 
    9pybftuj1 n9xrm6dla on85s31gy xj94kucwq ind4h1by7 qm2lwcd9o cbryu4spk 
           78        79        80        83        89        90        99 
    28f5tnpmb egm37jnxs qr78hfcsl 3kqawlutd bmhqoy1p8 1bjd3vw5h cbyh9d2q7 
          102       103       107       109       110       112       114 
    wnihdpl1c hj1unf8kp k6boil97m za7up8ig2 qju5hrxns 9nfm6trcl 5iy3kup6l 
          117       118       120       127       130       131       133 
    cl1378b6r ky8ahre5i a3m6rhcbs xn5pa3sro uw9s8ygn4 sfmu2nztr rdc64jxkn 
          139       141       142       150       153       159       160 
    8xuhcbmi9 bntfsmlge od6ye9swv w9ztn3u2g qk2syhoga x4y3k7zme yildv9n7f 
          162       165       168       170       171       177       180 
    vonr6izeb lv37cabyt 4iadgb5v9 m7vjxi3cn qndlba62g xwtkn1u8j qciyntfbm 
          181       182       184       187       189       190       195 
    oshgfi1jn 8rt3eacy1 saobv27dm q6g4ueb1w bk3tfi2pe w3g6armlo 7a63dwo12 
          197       198       200       201       205       207       210 
    p1qe6ozg5 xy8k45bv7 gnxfbq5kc uljartgwf g279n4z3v by83ps7r2 w6e5ud731 
          211       212       213       216       218       221       223 
    rdmpvh5e7 h1k86clbi odwslianp 57b3rt6yf 76xnevlgt oldwipvkf 2agilv9w4 
          225       231       236       237       239       240       243 
    1652zjwrc gw4r8qjf3 ei4vh8m6d 9qify3cw2 n1qui8tjy wilfhaso7 qs93kur64 
          246       258       259       260       261       262       267 
    4ycbmh5wp sbio5wlpq iroexhjny 1vbx9eu34 3wy2rbdsq ubdiyq3e4 zolwex2h5 
          269       270       271       276       278       283       284 
    klvea21xg h5gcqxu7z uhydetn94 5j32l9nqp rzo3718sw 6aymn9fb4 l7h5esqvb 
          285       288       290       291       300       302       304 
    zfotdvqnh rt4i37dpv 7y6qstpfx lscx34yij 4htnlxmwo 6lkr1sc7o 9fqbj17kt 
          310       314       317       319       320       321       324 
    mq2akyxhi nekuq9wox tkx7irh6u 9q6xhmvay kn4d1s6lg ahkp78dq4 zgkvib957 
          327       328       331       334       335       337       338 
    6kz3u52jc xdby4tkvc cr6lfhpbd zr6kwip85 kx5agipzm 815d9ztu6 9ohj4q3si 
          343       346       347       350       353       355       360 
    duaiq5l4t ymdzrboxi codpgtmq5 m89vybarz 68hulmdi1 v2wy8gxda 9fx3akzep 
          361       369       371       373       375       377       380 
    1m4k6zv8e p7xld6q42 3gu9niylk bq6ekv4yi zr5d7b8sv npsatvm79 4n9ofdhvy 
          383       386       394       395       399       400       401 
    x84lm2uhs v39rn6y48 i56aftuo3 ugzc92rt1 9d2szcgkx aqmtph3zs c1sijry42 
          402       404       405       407       408       410       417 
    fteu5xwqs 1l87vrbj4 b3wz2v8gq i79gpvmas 1bjyw3i6k q4gfoiek1 8blmv3dyp 
          418       419       422       424       425       427       428 
    awlvyt6kg xz1w7ian8 52g6k43uc kv4y17qxz rwq2f6hbs mk3ojs7it uk2yjcthm 
          429       431       437       440       443       447       455 
    yn8qcdrtf wdfe8ipr1 gk8625ybn 2auvbzik1 5ab8oislz bp653dt1f ny9f1ul72 
          456       457       460       462       466       473       474 
    gsr62hltv nh7aoszj4 cvnb1qdux um1r27e5q x29hwlomn yi78jrmq3 zhav1c3qe 
          475       478       479       485       486       490       494 
    7kqrt49lf rfw6ey2i7 brka9h8qt yuaoevrks 7md8y1ohq hafkg45cz 32o7m5hpa 
          498       503       505       507       511       517       518 
    vcmns17y6 unf8ws9az njt7q59k2 85opax6qt yxks9p4w3 nmixj1zwh idrta2xsg 
          520       521       524       527       529       534       536 
    g6zlsijyh qc9zrkhbi qvu7pkde4 vgofzw8r3 k2395atuv b8vmq7wjc fc3nqdzl1 
          537       538       542       543       546       554       555 
    l8svmcx42 g5yh9brap nabqt7owu vt6hogsqx lsfd19gpr 4cev8mu2k rpk9q2oz6 
          556       558       559       562       568       569       570 
    agi83m72s cg8bkvms5 t6a7pify5 idyq63ws9 jxug1wzl6 gvqtezuxb jtyxmcbaw 
          573       575       576       577       579       584       585 
    13mjqlzyo le5mx4q7u ipwtvl6rb 4ljmpzsor owgqkx2al 4yjlcpdwv rtpq6vkuy 
          586       589       590       593       594       595       599 
    348lbhy9g kt3cupe16 fu6wx5ijp 7xmqglfbz ld6a23i1v r8io9bjul adxk8fy17 
          602       603       605       606       607       608       610 
    oc5adhx4n ow3y4knv8 8h5agpw3r jqy5lxra8 dt3ulbrso lc983uygz q1jyp94dk 
          612       614       619       621       623       627       628 
    tlrq4gaw8 vk5168zcp zictv8h7m rnp6f5k42 elt6zw8r4 d8h569oap 8ctz2ipvm 
          630       634       636       639       640       648       657 
    xpvu2nqy6 la6g2z5kh kobm1ca9d q5f8dph4r sna8fm46b gvp45ucld 72sbkoyw9 
          664       665       666       667       670       675       679 
    txymvh6d3 wy6h9t2um jmhqdcw8g vceuqgni5 84216tzug l764vnhoi ha8dkzesu 
          680       681       682       685       687       700       707 
    jw4ton8r3 qh7zgjc9k bz7gu6mow 2opt6598f c3spxuf6h buepvatjl 6y8pamtrn 
          709       712       713       715       718       722       723 
    ij7cb489f 7i8dm1wpr oi9ql1rpt g5cu3dlzf 9zgw1ntc2 o8ile5kp4 meihoy4aq 
          724       726       730       732       735       737       740 
    5o4dik3um 264qfiyt1 cu9kxt3sr yal3467st 3krx527le arvqchbw8 ile6m5bj3 
          744       745       747       752       755       757       765 
    zw826apkc onfmk7jiz ox6in3cqp ysientx49 2de9f7mov 3e12qynod vs6rbxdyi 
          768       769       770       773       774       778       779 
    m39xvupbz 5tz1aijqm qc8fsnbto ds2xe354k r1a9knt5f 3abitsuq9 6btlzd8oh 
          784       786       789       791       794       796       799 
    xqrvmc8zn wejaxfpcv sjb7fv9t4 wny4zjaqf k7aqzprjg 6h41umsol ptvlh8x59 
          801       802       803       804       809       814       821 
    w2j4oze17 jomz31pkw yklc8u12a ilga29sz3 5ibl4c9gm 32t6rad7l onw6ptf3l 
          825       827       828       831       832       839       841 
    3f179wngu 7tsa3edyx wudatnpre dms1heauv qx1yisrbc v6f1xgk48 ht81ckpd6 
          849       850       852       855       856       857       862 
    zkg4nih17 426zuasxv w5xejcs6l kcxz4na5q 7rhi8syp4 p21w57nkb 2udqj1lvg 
          864       866       867       868       870       871       873 
    w6y4mjezr 1pg2cs3vn gizj4tnbp 4nbc8pf16 xzon93wft cwatdkq39 84rsc9gvo 
          875       877       879       882       884       885       887 
    qa42uetln pyn29urak 49tsv12k8 fyevgo7th ljpk9vghi nyfb2mo7e gvzacklu8 
          889       891       893       895       897       899       903 
    h95kljapy fdvncz2ja q7l8e1jct 3g4q9zjau 6k3tvfj9s kr4mg5sfo mjo37csp4 
          908       909       911       913       917       918       923 
    65cg8jshv 5tuvjxcmh jh97u54cz ex4kbi3qr 24xusrg1k bqzgrldem siktab7ve 
          926       927       928       932       935       936       938 
    59814oszd qhyelna1k x9u2hrksw u5imencvp s9lqvxckt 2qapum8tc pg6lsqxc1 
          939       942       946       947       948       949       951 
    xnb4mz3w7 uignljmeo ozqv1welb 98qoi4ztk 86jmhb21d 2a85prx3n 9pfuscv8z 
          952       954       957       959       960       964       966 
    5vfrciays ah8zd1nql ijtkead3s qe1xf4avu r38nx49jp 5r3w182bv j3pivxmke 
          969       970       973       976       979       981       983 
    n8w1j924x q9cktb3nl ducl5nv39 q3lax5i2c lice17hxq a3om4fejp igx8ofcj5 
          985       987       989       990       992       994      1000 
    o6hcku1gz gzvymixhw jt2e8d1n4 fbwmkd29y q2tbjya7o u5k7lxady epjvd7c9s 
         1004      1007      1008      1013      1015      1018      1023 
    mxkglhsfr dkow1zxls orahc4uek xeflui9jp ezuqlfca9 3gxl7to9p 17ub9exsa 
         1025      1031      1032      1034      1037      1044      1046 
    xhcbm63f1 6g2bskrac 3qbhsuco8 ykzo1gx5w orui4jken phn4v51s9 xqk9opc3s 
         1047      1052      1054      1057      1058      1059      1062 
    hmieq1b8v 8k5rotg9x c12umohpx rnax6534c cn4fqthpv dx7o2j8iv 7y4uqzbfk 
         1063      1069      1071      1073      1074      1078      1079 
    smtkz326a dk6a9y31q etjdqyul4 mecvkd578 l8zykpxs4 sgy7nwilc 6bd5wq43e 
         1081      1092      1096      1098      1100      1104      1108 
    kf8x6m2er qjeil8svc 2qer8uxsn p21xav9q3 a9ty2slqe 2lj5easb1 9qojwmht6 
         1109      1110      1111      1115      1116      1118      1120 
    tl1rmoywc 67xhe2pny uem6tap5b v8cuwnl57 rdpf4auwx n1gz6te2v vxmeh3iab 
         1128      1129      1133      1134      1135      1136      1143 
    5mktfr3a4 ctg78pl1e 3murzk7nf il94hwp72 lbiayj2ou ws5vufi37 u3j54hz8v 
         1144      1150      1152      1154      1158      1164      1165 
    uvkq4aybw 47or3vdag rlfnmik2e 971ly6prk otxqshadl u7inwogbh 56apxrqfj 
         1167      1170      1171      1172      1173      1178      1185 
    jaztp31d4 scke93qif xefwjyv31 mrb8dx9u6 y8wxgl59o c571plfu8 gtqzawyh8 
         1186      1188      1191      1192      1193      1195      1197 
    o534ycrsa 9imudz8wj p4kz368rd oyziw9npv 7cizlxhow klew7qsgc e39zbpvng 
         1199      1203      1205      1208      1209      1211      1212 
    r7nqegv8c 5n4zvtguq pur3kmdqw ywfom3urn gmyn8o5pa qsyiwb4av dty47anzs 
         1214      1216      1224      1225      1226      1227      1228 
    1hem3qco7 exvhtnf7i uen8fq2lp az3ufdvwb qmxhs53n4 132y8f6aj 9gw5h28y6 
         1232      1233      1234      1235      1236      1237      1238 
    rs9lztv82 oz1w68b4k 92wiz1mkb wue87dr2v oy1jgcbkm rohyaux9q se6lwaq2b 
         1240      1241      1244      1247      1253      1254      1257 
    9c2k35elv 2ayjgih7p 8lrmwu4q9 skzw3uybc p1azxlgus y6i4p8b91 79v5lcmba 
         1262      1267      1268      1271      1276      1279      1281 
    jnz3maxuk d4wtkpzy2 tbgm9ufq5 ujr2deti1 kcv6anq8f w1vjq3dgk 6eag7jhrt 
         1284      1290      1296      1298      1303      1304      1305 
    axc87lm2z 756e4rp3c bf4rcp1kt ymu28o746 83yxq64sv 1f2mjulxb 19p3joq7f 
         1310      1314      1317      1321      1324      1330      1332 
    57sgeqahd stbp6a8eg afblqsewg lg652c7qe yac4k63gn t7kx89sby d1jxvymot 
         1335      1337      1338      1341      1348      1353      1355 
    pjkqd96fi lixcr6gnw oql9nzbhr za23rib85 e98sfncgz e2kmgd7rb 4t12eyic7 
         1356      1357      1359      1366      1370      1372      1373 
    5exuq8bsl j79z2qrun omh4jfe2i i1xfqe2j7 pwnhe257t q2mltxoej yeni132xj 
         1374      1376      1377      1378      1379      1383      1385 
    1ac4nftdq 8aq76b52j yuzwc7jg8 zk8tveg5q 1aoc2dnir qz1vjobx5 weotr19dl 
         1386      1387      1390      1393      1394      1396      1397 
    tcdzoxhim rnwolpy7u 3avip7o5e 7nu6g53yj 4pgtqmai3 ux8lb4aio hfny4izjl 
         1402      1409      1411      1413      1414      1415      1418 
    gzt7mjvq2 hrxcuenzj zlq3c6ut7 eq96tu4l8 aywf42jq5 zvyteqcfu 7dspv3xan 
         1419      1424      1426      1428      1429      1432      1433 
    iduxhj63b mpi31vha5 te4i8axq2 b5j3u9ayx otg3z1enj 2x74fyp3a 4fb6gejt5 
         1440      1441      1443      1446      1447      1449      1451 
    vf3tsy1cx y5isndzf8 5oblx31hr kt1a3c2n7 bq694mfx3 nsjq3wzbo a9zjtch1n 
         1452      1453      1457      1458      1465      1466      1471 
    12klxic7j 94e3dotmn fe3x6r9ud 3ap1v6bxf 4abovzli1 kr6sqhtay zb8v75ufr 
         1472      1473      1475      1476      1478      1480      1482 
    r5znc1dmf qmykxrs9b nvyfig13p 47xv1i9tl d63vmqipu va6gp4oci cvlu6trig 
         1483      1485      1491      1493      1494      1496      1500 
    m4solh5nf mai8ksopf cm17nr6ds vi9fygwor 1x9pyfrd7 r6nd71tsg c5bld1fah 
         1501      1503      1506      1510      1511      1519      1520 
    9geafy6r8 fy1mpxq4u f2pe87srm yxr1fp5ua gerto1l8n d4boxrqeg 3hrj5kvn7 
         1527      1528      1530      1531      1532      1535      1536 
    jkyezomn6 85qnig1xh znvhds5i3 5nswucd3v iw8ztg73l 5br8tpiy2 th5n7bmra 
         1537      1543      1546      1549      1550      1551      1553 
    jcyp5gqrx 1qjlc2sxi mzp3y1ucn voei4s7k3 fdv5uktrj zlb2erpwx 2m1o4yqr8 
         1557      1562      1563      1566      1568      1569      1570 
    m6nyruafo yc2gvz3t1 71ehpfgqc t4nujzq9v o4t39bec1 hxcj39d81 q2twz6ane 
         1573      1576      1577      1583      1585      1587      1588 
    tf62zq1hr fl2rpdt9g mzp8ralix vahqgrj17 k74lx3rgz ekvi1hyjl r7ei8loqc 
         1589      1592      1596      1598      1599      1603      1606 
    58dculze4 s37t6a528 bangiocep oq7ldu9cb wa7epnmo6 8jel4yunb 6wxrh9tsz 
         1607      1611      1614      1616      1617      1618      1621 
    ih63ywepn kjux93sot bp5wakinz sykqm362e hs79lcoj2 u1p4kv9qw x8u5bqn9a 
         1625      1626      1627      1629      1634      1638      1639 
    4qfnzscxa dq6cwm9ig hiz27e4g1 lspyzmo6q a3hz2w1jx t3un1haxy 2w3f7gvbi 
         1640      1644      1646      1648      1657      1659      1661 
    3g26otl5r 9ktmpcsf4 fqadpyjli x89am63nj 4zaqewg1j uj5pmegio r47gvkdjn 
         1673      1676      1679      1681      1688      1689      1691 
    gi5pb1kux jnuxydwgt xr6gl8d5o op9vlxsgn jau2b4i1e iakoemwg6 bjf2t9syz 
         1696      1701      1705      1708      1709      1710      1711 
    neuirbopw 47iqdvlwn 5q48r6iks phdzfslnm yzrn9qa1v o9di2zf8t us5cgqjrt 
         1714      1719      1720      1722      1726      1728      1730 
    ti8lvusn2 gizxk1qm8 zl8atvk51 31ajdz8pt 93twqpan6 vnrc8o6xf fadvi4okz 
         1736      1737      1740      1741      1743      1744      1747 
    i2npzfxqw t5gw3iz1p 28jnxweil 16nbsl7cq gluszjqf7 h6prnvbic yovdp54l9 
         1748      1749      1752      1754      1755      1759      1761 
    mbuq5pd69 13wi7a4xu 1tb25v37c dwty4zme5 x3fjwurdz y79pbrxts 1yj83k74x 
         1762      1763      1764      1767      1770      1775      1777 
    p7sc4jwzy saerhlxm6 198vnt5mf em12h5boq guzv8lk6h om4nywauv xqmgrnv47 
         1784      1785      1789      1790      1791      1792      1796 
    874do1nwg g4wu6len3 8caykm7xe 2hqia7c3z 2lnfu1ks7 ack7umv3o jrifwbgc6 
         1801      1808      1813      1817      1818      1820      1821 
    lgeqfj8ic vncodqlas 1uh8o9ba7 ig1lr235y ol6gxw4jp yrdgo4tpe aribj7489 
         1823      1825      1828      1832      1834      1839      1841 
    9el5chdnv bao6xk9rg d7fk1t36v cyi6ub9ml acqb9t47r i4anxeml8 9tbec8lo4 
         1844      1845      1847      1854      1856      1859      1863 
    5wub37dpo aski4yr5n b2usofm1r jnlf8rwt3 zecdy2bsp teckvasrf ozv6x3awr 
         1864      1866      1871      1877      1878      1880      1883 
    k6ib5xcsy rmoeu6a85 ylvrtoxgi jk48sz2nq j4khfqxir vfl7aicdn hflwecqn7 
         1888      1890      1896      1897      1899      1907      1910 
    l962qxuvc rsjtgihom 7hqp3bgl2 dman5ye1j fwasxolzm jidntxk4v zqn3te8gc 
         1911      1913      1917      1919      1920      1921      1923 
    ahjiveb9y 2xeoh8mkt suec2zmbo hfkuclgpy jif4e3kw2 fu2o6tyr9 caihp78tw 
         1927      1929      1930      1932      1933      1936      1937 
    qyzx7eldt xsdjm15o8 tvyfo7dhu 8i7bztuyf 3p8detb4h 9gyr3i4q6 26x3lv17m 
         1938      1943      1944      1948      1949      1950      1957 
    9wc1mvbux kna3w9zg6 nv4cmr8pu xf3dwatql qlxu27pvd da5w6o1th can8ov4xq 
         1959      1960      1966      1979      1980      1984      1986 
    gqnd5pvim heyn6wus3 ipsvnglae qbop7kgth 1k8mb9dx3 nrlm7vcao jrbh38dnq 
         1996      1997      2002      2006      2009      2010      2013 
    c7adoqk8t 5izusac2t 83c21zhei xo1pcf5le h7a2exygq 14vx7edqo drygo89bk 
         2016      2018      2019      2021      2024      2028      2038 
    fyvrm47ob a1qrx4z9o t5a41u3eb tpu9efoyr re6vc1li2 b36u8ceza j98zruaci 
         2039      2041      2042      2044      2048      2049      2050 
    indebqacx bray6lgwp lbhwide7o rz2guamtd yjnaceh25 icype18on 7wqatn14i 
         2053      2054      2055      2056      2060      2061      2064 
    ivt6sycrp 4hdxty2cw g1t6a9dr3 lv5g2durs 48hcunawk ecuj43lxy hm6kld7vj 
         2067      2070      2071      2073      2075      2076      2082 
    ayn4lejqt edm97tw8y o97xatniv 6uat4xlrw s4y87qzdj qza8rn42s f6759zkq3 
         2087      2093      2100      2102      2103      2104      2107 
    ezp2fyt5h kb6mcqotv rb4ywpeg7 lfwupncsj y3c9pmklz g65b7q9du 29u6xvsqb 
         2112      2113      2114      2116      2122      2123      2124 
    1ufc5nrvd 2y9rjae6l 26iuwsyh4 dmuyk6o9b 5ikol6a9m erknumt6i 4sajmohyp 
         2125      2129      2132      2135      2137      2138      2139 
    dph6omgtq wpqx9v5rs lha37erm4 ldg2f9bsk yhv4x2k6c 98i41kmzd ib623kxhe 
         2141      2143      2144      2146      2147      2148      2150 
    bmgpcqild uzgkos7h5 wc3f2g7sn e3r6ipmnh 2gadpjoez pvmz6b5jq 2ktnrx6c3 
         2152      2153      2156      2158      2159      2161      2163 
    5jlkyn21b 7cohp5823 eh3afcq1b iqv2783ok amuj3opwg 5ijtsa2mr v2dmoqayi 
         2168      2169      2170      2172      2174      2176      2179 
    up5cfwagm lba764z28 znijrd53a s2m7iyd1c zva7c93r1 ridnlxcz3 e2m8bk65j 
         2180      2184      2186      2188      2191      2193      2194 
    xj7169i3t m5x71na8p 576xcwk1v q8hu4isna j2klagfiy wnuvlh6qo m4ta9bcny 
         2195      2199      2201      2202      2203      2204      2208 
    bpwr6sdlt wgtq357ml 3sp4ybzxo w3sd4l1jb 6ch42q3b5 te1swlgb3 e46j2ds59 
         2212      2215      2220      2222      2223      2224      2231 
    3uhc5na7i 8sg21mjen nywpbd8t4 frsd1i5q6 1qwizusnd tb4priy8g i6qjlmvaw 
         2233      2234      2236      2238      2241      2243      2246 
    6z4uait1r 14bapqk8x dayl3rk8q bpwv8g7jr kn3y8uid4 wqsn14cla 9xs1vbyr8 
         2249      2251      2253      2254      2257      2262      2265 
    izsrlxonf vgx6frout eim3rwjxk 1n9izx5ud 8iw9av5fq ydax6vstn vcb67fglp 
         2266      2269      2271      2275      2276      2278      2282 
    dnbpjigxc 4blhtgqvj krb3cwjeo oanypvut3 m6t9uzep3 unxpsmlvc iqhz4dv35 
         2286      2290      2294      2297      2301      2302      2304 
    muf16be3i d2kbur1l4 cbu297dgk rw32qli4s tbipuho4k ujeh4s3k6 k2so9mlap 
         2308      2309      2311      2313      2317      2318      2319 
    2p4icjs19 2rea7igp1 vbuk6a247 on2rpcaue 7hp4wa9rq 5wyix2cus koua9czt5 
         2321      2326      2328      2331      2332      2333      2336 
    wcz3r2lmg zwpd9317c co8x17lgk nqv21jr9h odfpu43yc q49eabulj 3vfzs1qpn 
         2342      2346      2347      2349      2353      2354      2356 
    prl1ba35c lgr1ntfyz 31lvrjez4 elnyq94mr flmgir6au c23kszqob hklibf3ym 
         2357      2359      2361      2363      2370      2373      2378 
    5pn8cu73i 6txdjnghu zyp4c68qs 9nau7ymg8 uce3w8vfx gnsxjuqdl a3h8quk7p 
         2379      2380      2382      2386      2396      2397      2400 
    5rk9z37cd ic43nf8xk 56segtcx1 198jznbum 2lw7ahvdz tdpfgcai3 9zkl1dgx6 
         2401      2402      2403      2408      2411      2412      2413 
    tyzwd3p74 qu957psd2 vbgy3aji1 7bzkud1qg 825mycdhx v74wntkel qjy2mdkev 
         2416      2417      2420      2421      2424      2426      2434 
    uz4yx1otw 9hfz3n7qw 54apyilwz aen57km9d 6xnpb1o5u lagow42sf k65x4g21j 
         2438      2443      2444      2445      2446      2448      2451 
    jiwhxgvy2 8eglh14c3 4g5mqoku8 zat36uc8n kultpyzqe t1jqnb9sz vufxrnd1w 
         2453      2454      2462      2463      2470      2474      2480 
    obwkfm5he ia4nqgjow i7gdsa95x mcstu9lop x7f56nhsb 1oswhtiuc rgfsym295 
         2482      2486      2488      2497      2503      2504      2508 
    9il3unczx k2pyzxag7 aveihg6ru 9nxvk34rw 6jl8cufkq xfvhlegz3 ktcs2l8xa 
         2510      2512      2513      2514      2515      2519      2522 
    s3ogfiyrm fm6ucazk9 d3e51o8uq qmn95uyl6 m5n2d7yxh xiyv3logp tilk9rand 
         2529      2533      2534      2537      2538      2542      2545 
    1q3ipxf49 86x3i2qwv 8o6qlgbau lr129mbyo jrkn1fq47 2b14rhvs6 ep16c2kaz 
         2550      2552      2553      2561      2562      2563      2564 
    hlbm3k4ij vbhxlewyz gs9eqrwca dxc6uihk8 c89k41zyn 1bdc3vipa ifcg5al7q 
         2565      2568      2571      2575      2581      2582      2583 
    8uelj9f1w r82wndmye 5d94n3cto hdpwly5vx 9mqiexghl k7ueismvp uognaj1ip 
         2586      2587      2594      2597      2599      2600      2604 
    ogs3j1ia5 l6o78ftgn d1w7fhymi lnuvmojd8 8nf7edcwz zt8bcxdmq 9vlgbycaz 
         2606      2612      2613      2614      2616      2617      2624 
    y4tkg8d67 bems8364n 7z2bnqlaf ch4lymjks lm4r89hzb wvrnslqbj lcundw5o7 
         2627      2635      2638      2639      2645      2647      2649 
    xkfbwpey6 6wjeyz19i wo2uvgq85 iart5xcmw bgqhijsyf e5brkyqcz 7zpnclb6y 
         2650      2651      2653      2657      2658      2664      2668 
    ypng7bwvm ojhdklpc5 az7p9m2xg erm1g67l2 b5cyjv8za 8u1yp4lc7 8y1jetdsg 
         2670      2672      2673      2674      2675      2678      2679 
    t7bqfl2kp h9wi34y7m gen17oflk qfpmku9be quzc76r3n ajptr48bq 5k8elu64g 
         2680      2681      2682      2684      2685      2690      2693 
    vm9lh7tui om1rf7vyz te9xikgop ydrvjbiu4 8vlfdrsih yzs3ohx12 dajw94yxn 
         2694      2697      2698      2701      2702      2705      2708 
    opzs31xbv j34psoyw6 wf6jla24x w2ni148l6 k7ds4nv12 6skxnpfhl dfgr42etw 
         2710      2711      2712      2715      2718      2720      2722 
    rk4m1q7bu f61zq7mix 7dgys8le5 51ile34rt xd63zyfuw 3t5opsyvn b7aq59k8i 
         2723      2725      2730      2733      2735      2744      2745 
    w2nlx9e6a 5p2mucr13 ij8rtqv5z nc2fy47we smxqh3wd4 tfx9ihwa6 2qw7nc43t 
         2746      2747      2750      2752      2760      2761      2763 
    if4zpctlu cybelm1ni fmgrenicj 7m5a3rtlu u2r1nzgv5 qnxvw4kyt 7m5siqxzw 
         2767      2768      2769      2771      2775      2779      2781 
    lkdu69s2r 6il2agzop bqckpai7e xbykdti7w 1m4iyl9f3 pczt4dqm7 xvtcp7lu6 
         2785      2786      2788      2789      2791      2793      2794 
    qpw6fix8r 3iab8rspg at36prjc2 8uro5721b l9xg8icpa atobqjnfp hv4pme28d 
         2795      2798      2801      2803      2804      2806      2812 
    u5v9phcbr fl5c61uns 8ewgdujfv rtgucyin1 1kxp5g8vz r31odpe4v ku2qg9pni 
         2814      2815      2818      2820      2821      2822      2825 
    li4jp962a pgd39khj5 25o8caviy u7grxjhyv pa7ksyqwo m7ak9rnfp 6tyang1wb 
         2830      2831      2837      2840      2843      2846      2848 
    9s6pvbfca hf7pdvzwu agx89cjoe 1slq6zba7 ljayqs18o sarkfy4b9 26htk1u73 
         2851      2854      2855      2857      2861      2863      2867 
    jepx35k8w 67a4lqmgz f9dcpuyab wdh1n8cvg h5xd9b2lu t6kcpg5n3 ezh5ljn7i 
         2868      2871      2872      2878      2879      2881      2884 
    x2d8163qy xtgakvd6n qr1tu4csm j38r4zxte pd3az7xco ew126bsan ab1lh25x3 
         2887      2888      2889      2898      2909      2913      2914 
    ciz2m349e 38ibyd7zr wvbdcyat3 fxglyhv2i 57mbcirtw dgmsr3ceh lstqb6gyw 
         2920      2922      2923      2925      2927      2929      2936 
    vprnw3ti1 vb4igzxem hkt85gqdl z2kb3ex9p d6t5o37zk j5n4uqxg8 avt3f24zi 
         2937      2938      2939      2941      2943      2946      2948 
    js51qm7pd cibwn5ar1 bts7l3ofd sz97brkcw 823m5sbrk oc9jhs5wg swvdxmn6f 
         2951      2952      2953      2957      2958      2959      2960 
    f2jqxkdvz qrd5aekyz cpgkdwzfb n47mizk5e qlru4v3je lrnoicjxt gkudzj24v 
         2963      2966      2967      2969      2970      2972      2973 
    caqwgohtl 3fx2ghoj4 dq39z4ioa achu3nsz8 tou2aqlsv 93vgm6l1z dwrtbp1v3 
         2976      2978      2980      2986      2990      2991      2992 
    3kcz65umr jzvptmkba 8rhvpt7f3 xtreudq3h heylz6isd hvj3pie2o s6fupjdka 
         2995      2999      3002      3004      3005      3008      3012 
    y1qfvekwt 4r2dkn9gz genr6q1v9 x3m95b2pd aros3ketx ti4ned3w8 shiwy623f 
         3015      3020      3021      3023      3026      3027      3031 
    ly5ev1huo e8q5c2hyr jfbd8tmv2 v1og6bc7l yufxtcb7i gs4kyf59t tl671mowe 
         3035      3037      3038      3039      3041      3046      3048 
    3n4kdhue2 wjudgp1me vkuzi15gr lkngoey9b 8a1wo5npx e1dwz9jy4 aq9r67sz4 
         3054      3055      3058      3060      3061      3067      3069 
    ki8ah6w7m ywpu3sb7d xtbhdygj8 un31e4x7c ry7q26z5v 2g4duzi57 dgn3hju54 
         3076      3078      3079      3080      3081      3082      3083 
    v3wyedblx y7ovxdun3 g46bwp9mn djhkcvxaz 5xiv6mgkh ajn26txip jbplfgeyw 
         3085      3088      3095      3096      3097      3104      3105 
    eyo4lhbp3 l37per4q5 igft21ohs wserljbmy roaflyu5d pe52rmq18 9o2msin7z 
         3106      3107      3109      3110      3111      3113      3114 
    p6k92hotw j8nferkv2 ogr9c6jm4 jf2av5sdo df2m6qjsi okzjfeydp lvega86rx 
         3118      3119      3122      3124      3130      3131      3135 
    ltenhvr29 1b9fa34s5 qsfeiwryu yx9gkjrmo y95nxcgh1 ef7ap4itr mbs147rek 
         3137      3140      3141      3144      3146      3147      3154 
    ogsneu9vx uekfnvhsa nzlkt8r2f dpwjzuqsb e6sdgmvhi mh5nq236i eanvw7i2l 
         3156      3157      3167      3170      3171      3172      3180 
    5iclveu6q 95rw4ylnt 9ifer1xbp 1p9c8e3jz yfr1bnv8u cf9gw6pka ymn9v1ehp 
         3182      3183      3186      3189      3190      3191      3194 
    u4ypwlj13 wgpf36aoj 4voi5eqbc 94mecfgl5 3gvstpr5k 3a46i9qtb tl2nx5a4o 
         3196      3201      3202      3203      3205      3214      3216 
    adiktepz1 mu75a68xi nxy4vs5cg 4f3hkqz16 vdznpl7jr 6luxb2qpa s29mgihvr 
         3217      3221      3222      3224      3231      3233      3237 
    qgdkia9tj 5cfikr1n6 yaxn9r41q nj7oezpd5 mhktij4lq 5wq8pm7lo ae57kbcj1 
         3243      3249      3251      3252      3253      3258      3259 
    1bwox52ca lu78pecfr d9k7hew5q 5lt1ruf3x dj26i1vbf l684v5rze csjfdyrlu 
         3263      3264      3266      3268      3270      3271      3273 
    j4gib1nt3 4h15ci2o8 o6ruyzaw2 f3ouzcm5j qgxrcfk6w ey5twgo7u 1lnvpkjf3 
         3279      3280      3281      3286      3291      3292      3298 
    plsrivqjf ywaz12k8j hoyc8ut6x xgam4wbrp 7gb9iw84y m31sgqiyz 7p9mol3ya 
         3299      3301      3307      3310      3311      3312      3316 
    ykqa32jb9 phnbu94de xq27tnzue yk8dur3lm ux2j1n6cr ajotb964x kqw3fa9l8 
         3317      3321      3322      3326      3327      3329      3330 
    9asdpbyx3 5k3tducjw x9d2egqba bswozp8gd ca9htvzbe krxh3jwo6 u4glzam8w 
         3331      3333      3335      3336      3338      3341      3342 
    pdns536iy tr9i2czux zcg6aui41 6sklz4tnb yg5b8d419 tlu4ybogv ws8pjov1m 
         3344      3352      3357      3359      3360      3361      3365 
    4hxzfwdv7 pxtqz254g mkvxwncz8 tjbno5uih 7bapc9xfd lt4f21oj6 ngwv81qka 
         3371      3373      3374      3377      3384      3386      3395 
    frqb51ex9 r84y3fpsh fq6i4g258 84xcgwa9r h51yomp6f 8rs16ycnx tsbd5i2hl 
         3397      3398      3401      3410      3411      3412      3414 
    clawvj6sx n1d9x7hsr qea2lpuof 1lbx2gmtr g2x4iwmtv 7kroldg9f 54kctslv3 
         3422      3423      3426      3427      3429      3430      3433 
    d7liau6no itxkcdrb3 y9w6z87vn sz74ago8m 1ad7gsw2c yw5p1q4gm hdwgmxkb9 
         3436      3437      3442      3445      3447      3449      3451 
    9md43bfxs l4vgb5ue7 3dy785sai gaiuxy7hd pzit3ko21 dbyz6utgp eyqpn5zu8 
         3455      3456      3458      3461      3463      3466      3467 
    aefchtg71 sbf75pkqn yrwvecuil igaswe28m 89qytzmfo oi28967dp t4oferlp5 
         3470      3472      3473      3474      3479      3480      3483 
    yk1946otz 2vb5imhyn 87o6mbnls q7b8xfmky v8r2ajezt gyrvxjf1n ei167yubh 
         3484      3487      3491      3492      3493      3495      3496 
    c784mxfz9 yz8mkwacp ws8hnabtg fl3gkbn9t nfd9prw1e lp9v8fdi6 gnwaqleu2 
         3498      3500      3501      3504      3506      3507      3509 
    ezpf6nwsd vutp4qhji pkanm7sh5 829am1zck frcsmvjzb lki9dzjf6 so8yemr7c 
         3510      3512      3514      3517      3525      3528      3531 
    cmz6hfngl koe9zh6tx 2zfdneug4 79npovhd6 f6ocz3eux khpftej6y ecraqpvtb 
         3540      3541      3544      3548      3549      3550      3551 
    a5zetqug2 4zgao9mph s4gb26xkt l6amwx8y9 gybne7o59 ri2tluzv4 ocb15u9z8 
         3552      3554      3555      3556      3557      3558      3559 
    4xm7zgqk6 lz9g6ih4b yu5n14fkm 45w18uyzq xln1ht3wv 69nufs1ca 28svpm6yh 
         3560      3565      3567      3577      3580      3581      3582 
    68nd9xmak esx52b8g6 pqxj3yhr2 bwt927xrj 7nm6h31wl cv9yabuf2 2bztnaomp 
         3583      3587      3588      3589      3590      3593      3594 
    xwci3691v ydu5i1pce d124iu6bh bv6iyfu9x a6sqmn1oc 4qx63dazt sv59fn84p 
         3597      3601      3602      3603      3605      3607      3611 
    i7hj3od2x wqlvaemnb bitksozcr o2tqszwug z4pujhtwg qhmub8a3k 5v1jwpl3g 
         3612      3613      3615      3616      3619      3620      3624 
    m1zwp5fia 1go23d9me vgwhp3tj9 ew62jn7gd 2a4sbmzev rwyb9dc1n 4ndr56whv 
         3626      3627      3628      3631      3640      3644      3647 
    4litsqxpf qah9s8f14 5c6vpgfzy b6fc8htav lmsr439ja rvea7j35k kqhydgtl9 
         3650      3653      3656      3658      3662      3663      3668 
    5132ktao4 iknflj2q6 38y4fksdt drgqpksze qx94ksmu8 ebxruh9vz lm26fipob 
         3671      3672      3676      3677      3680      3686      3687 
    w6mh7qgu8 c9sxoub4z wrnjq6fxb mya2rzu31 dxo4hysqu tq4ygv2u1 3olvndga7 
         3688      3689      3692      3700      3701      3702      3705 
    eyztnp1d7 gi6w12zvh t5jxruysz u3cigkr8b 9rvuhnlcz cdgqb796h n45k92rac 
         3708      3711      3716      3718      3719      3722      3723 
    9aguzqpf7 zps7e8jdw md4y8c6ej fwau98g3r cphq9j487 shlvfux2e j7l23muty 
         3724      3726      3727      3730      3732      3734      3736 
    tav2uikdy gymor4e1q bt3j1xwya yxk4gihzc ml3v9eqri 18phx9yef k3gmwqvtp 
         3740      3741      3744      3748      3750      3755      3756 
    ozb9h582k cxh592vdz phs9lt1q8 pmyajwk4c gti3arqyz 41g3vhji7 27o4kjr5s 
         3757      3758      3760      3761      3764      3770      3771 
    zbct4ae1o qstnzri6f 4nswbh8me hviqc5su7 ozp7t8x2c dzauyx8qb ru3knbsd9 
         3772      3773      3775      3777      3778      3779      3782 
    gpnas1eh6 1ujblt6g5 wdg3xuomc e8wnmgq5z ykd6n7fwv vwoegk8zd eb6pd9rci 
         3783      3788      3793      3797      3798      3800      3803 
    d1vjg5ysl 83h7flm1t z4hwetlqx suamv7nph whmy94axi q4dfkn6h7 8xkbsevu2 
         3806      3810      3813      3815      3817      3818      3820 
    vsf48jcqg 2teo4xi58 qz6a8f7xe w9yo1f2tv tzy1esghj fh2tlyace ws3pgmnih 
         3821      3827      3828      3832      3833      3839      3840 
    hsqaxvfgc 9wr5aybo2 yiz2jrkw5 1rkvmenyo o54x6i2gn y17fw8sov f1yctm5h9 
         3841      3845      3846      3847      3848      3853      3854 
    qo628l1fk 75jaspgw9 sh5nbilxk hpu9zr5m2 tm1qc8zo9 i931qhetu 1o2p35h96 
         3860      3861      3863      3864      3866      3868      3870 
    cnazjr782 nwrd4jk6x nh4lp8b91 3c2d7hrvp m45qcoy9g fqjhipdec ih786drxe 
         3872      3874      3879      3881      3884      3890      3891 
    dvup6f158 aypm5w1tn v1g32jwr6 fnsidmywl zqeb7sg2p 9pw3txe6s wt8jy59xn 
         3895      3896      3897      3898      3900      3901      3902 
    v5r4smi3b gho2yrpx7 uift7zw6s gx2do9lcv 7kr4pvawx 2us6d48gv 8p731ijro 
         3904      3908      3910      3911      3915      3919      3920 
    qhsbcnidf m9tzi4rbp lr1ca2x34 ernqvk2c6 xahnc32bu r1mw4n6pk qvcdozhgw 
         3926      3929      3931      3932      3934      3935      3938 
    4cwti9xqz 4edsi2j1u sjy3o1q96 i38kvayom lypr7oh6n 1xwayn9qe n6y3481pz 
         3939      3940      3942      3946      3947      3948      3950 
    ydxjlonam e6sx8diuz botz9h542 5kwitgh9o 6dphls2wg sl8mygje4 zlqion9rj 
         3952      3959      3962      3964      3967      3969      3970 
    2qwya3r8u e3iam9zy4 7hreotnsl my13pw2o4 13xi4oek6 5tpbkfn86 stl5de3gk 
         3974      3979      3980      3982      3984      3985      3988 
    lf8sdjyae 4focuzitd 7mukjqw36 bimvq6rc9 wazge89lk 7xslhe2yi e3klxygbv 
         3993      3994      3999      4000      4002      4004      4008 
    h62prmc3j 89mqk6p2x pvq135cet ta6mdzr9s ex183qpv7 pv5liok8z qjfgowl2a 
         4013      4016      4020      4021      4023      4028      4033 
    htju48v6r ty5rlvp2m 1ps83i9rf 2j5gx41pw mrg1lz7x8 89mjaqp1c zyk9hw2fn 
         4040      4046      4047      4048      4050      4052      4056 
    58aiv4mol ruef7amoc wiq3ukvyc nh1bpiqwc 3v91z5jy2 es7cgt6xb oqbveg1zu 
         4057      4059      4060      4063      4066      4069      4071 
    s9vpr2iu1 ohrc2lsaf alb2ihotr mznq2r6jx dlaumnpvw ntme8bloh n9f1gpl8r 
         4072      4075      4077      4078      4080      4081      4088 
    2svep34un s7panhoi2 irxd7t4zp wurf5npj4 5mydqpclz vnoxykqmi zba2mieyt 
         4089      4090      4092      4094      4095      4096      4097 
    pdtm5zj87 763k1vtn4 zca91yidq fnd2p1xje a6uo3rd7g pckd79j5v umqthyvsd 
         4098      4102      4103      4105      4108      4109      4111 
    8ozjkrh12 clwk13hjy 34fretvj9 lman7qp41 1f4te8b2n 1izepu5q3 9lut43ki2 
         4112      4114      4116      4117      4119      4122      4123 
    lk8uqozye cf37lm1jd 3ydkorzbc ah9fqxklr jp9ul7g42 zrqh54xnt rick4pw6u 
         4132      4133      4134      4135      4136      4138      4140 
    5fjt2ocra vrg8n19oe 58zor7469 ba9fte4uv 3l4dupa8w vg9oqx4fw 135k7cozy 
         4144      4155      4159      4161      4163      4164      4168 
    21e86uf45 1lep9i6co v629gnfbs e9frhia57 kisbrd61x aqvditn6g b27vxzdsc 
         4169      4172      4176      4177      4178      4179      4181 
    benha7q6i w2mc5x7jg m2hdg83ca f4blw9r21 x4pjzbh37 qaikcmrvy 5obrfygwc 
         4182      4183      4190      4191      4194      4196      4197 
    jdnawo7t9 lf8w5vc1n z54aprbsq g3bjircqh b1m9f4puw bfti185qp 6av94igd3 
         4200      4201      4207      4208      4210      4213      4217 
    56felk1gx 21atp5sje dhs2u57pi 1iw9nokmq 3frjc7tqk rjs629yfq htqwgizem 
         4219      4224      4227      4233      4236      4238      4239 
    cg1p2av7f fo1dzqykj 7nqv6jch8 8mtyufinl 6q1h4ksgu aueqf2wp5 b1vijedu7 
         4240      4242      4243      4246      4247      4253      4254 
    w1o5ablvz 7eyczu9jp uosvdmxcn wbrismot8 f2nwr41i5 aj7i9xdb4 lbekh1xgr 
         4256      4259      4266      4269      4271      4275      4278 
    v9o8cphmd n51zsetrm jmcrh2xzp jy1b9qnva j75hqgok6 fysj57btq 5gpkfilt3 
         4280      4285      4289      4292      4293      4295      4300 
    3v6sqf4gz nkle2gqm1 293kif1x5 zmahx42wp itv96ao8k nz4eoaquv i5hbpfz7c 
         4303      4311      4314      4321      4322      4325      4328 
    r6fibz5ot 9epqr6idx cg9a34wy2 hw28pt59r exhgdnlib vhpfkulgq ry8q36ekx 
         4331      4334      4335      4342      4343      4344      4349 
    pnzco8kgh fbcrt64jp tuo93m5cf vqtz76msc leb1kfg9d 8uzoqx6jb 4xwnyhz65 
         4351      4352      4353      4356      4360      4374      4378 
    zgyh483b9 8vkb261hj f69ib1way 54pmo9qwi tm9ba1yr5 u2s5yxijl cizel9r4w 
         4380      4382      4384      4386      4389      4391      4392 
    zw4y7hxb1 blo8pd4wh qe4oz5f61 ec263pgjm gq6dmnvlb tlukbyv25 eciky6b1t 
         4396      4397      4398      4400      4401      4402      4404 
    6wxmjy8ef r4xoyalqk wgd1fpuc9 2y8l9dgoc f1832wuam xjqsm53pr x9s4ayu3k 
         4405      4408      4411      4413      4414      4417      4418 
    ve62z8xw1 6qxbjumcg ohz1nx78w idzs9ec8r wj71cekqi 63bsan7i8 1lpfjn876 
         4428      4429      4430      4433      4434      4435      4441 
    dfzh765qc e2l7rdbxf kqav5dc6t zipvsanqg nyqafzdk3 3ghyikazn n7pxhscfv 
         4444      4446      4450      4452      4453      4455      4456 
    v5jpo3nwf 9pmjbhlfs ibufnmxwh 6x85capkb zw2rjkvuf v1hkufmoa k7vl9wo5j 
         4466      4471      4478      4479      4481      4482      4488 
    rgvixcmzs hxemvo5b3 3t12zurw4 qf94vgcia mrlapbeih 35p4h7sin u6tjdf1la 
         4492      4494      4495      4496      4497      4501      4503 
    8cl6wzqxo fpe9yao8w hm9bt7do4 gk53vntl4 kpm4aru9q svuczrg8w km2leypba 
         4506      4507      4508      4509      4510      4514      4517 
    bihfsc7rg bylvs9p6q aibc8n5jp sfk6ejnhl 6idawoys2 hpw73lxik mdeolu6rf 
         4518      4520      4522      4526      4527      4528      4532 
    gcq6ftbhm 6tis5jxfw t376gym9l 2xjf85qus 9zu3iolgp e7swuh4by u3yqslimg 
         4534      4539      4543      4548      4550      4551      4553 
    maqjrkuih jhtirl2np gifzd3xow cqkfzbsr1 a19fn7lcr zn8ocqjar r9aj4zo1q 
         4554      4555      4559      4560      4565      4573      4578 
    fpny4zeij bmfkjo8gz 781gxzd4o 1f3l6mstj swocj4x5a lmu5syv3e xje4knz5w 
         4580      4583      4584      4587      4589      4590      4591 
    ofwgpkbit tmxewr65a a41efghdo m71i98keo 3d5fiv6g9 dbfzly7aq 9ox1u78bs 
         4593      4594      4595      4596      4597      4599      4605 
    v3dxjksfl lgtwkb75q 743fs6xur nzwshk953 g1un349hm 67k2pbmcn yfagqhvtc 
         4606      4609      4610      4614      4615      4616      4618 
    h2yz4fd5k u7kd51cho vszm563bw 7nwmeyk1v 71ibrx8f4 6zcnwv3p9 wyq6gucsf 
         4620      4622      4624      4625      4626      4627      4628 
    fornq5wps pcfkwzymq s1vqwtip2 fc8xl96it 6cfgbqkvp e8isdayot tvsblkpmi 
         4631      4632      4633      4634      4638      4644      4649 
    14kp6vrm3 qxdc23jl6 ihcny36j1 3tg5rb8yk y5lprhuwf r3fcd2gy5 n83bzj1fd 
         4652      4657      4658      4662      4663      4664      4668 
    deilrntcf 9lysj4gi2 6tjxlnmce fy6zlsth1 khvq1zl9f 8hrg2wmlt q9cfzbuj4 
         4671      4673      4677      4678      4679      4680      4681 
    6s9trza3q k84atnuoy 1ntg6mu54 6nksuwpby 5eqdb3k4a zu1xv9nmd sofhjabtk 
         4683      4686      4687      4690      4691      4692      4693 
    4bpemdcny uz36f278q ehqbuct65 zcj4rdq7a kreqapzmx xtsirp9lc rcs19qy6u 
         4696      4699      4704      4706      4710      4711      4715 
    xg93tphq7 3cpuklyeq a7jqymzbx 9q5di2zyv i61h7lbkq 3ozfurklg lnvrso3t7 
         4718      4719      4720      4732      4736      4741      4742 
    dz6feuby5 532lgtj8z co4fvr5zd jrg6a4wve 2rj8517bp 3jpamzg28 ib5lqovm1 
         4744      4758      4762      4765      4767      4768      4770 
    rnw2u7oa3 qrntobegs fxnuzcrg1 tvej7942c 2bm9wjl65 r2iqwgjz3 mjytd3rec 
         4771      4772      4774      4780      4782      4783      4786 
    2ok17spjw pvuktli58 9seczynkd vgpoecr3b iexwkplog g73uc2yv6 2c3xeyqop 
         4788      4789      4790      4793      4794      4795      4797 
    kw3ieo7nd 8g6qf3dib if4r9thm5 nw4lx5syv dc4ligmxv rtbwa69fo 2wxsp15gt 
         4798      4800      4806      4807      4808      4810      4811 
    r3fpqco4l 1ko6m92ta ta6zuifcs m57kgof61 se18nqfy6 dksbn9ghp pxgoyqacr 
         4814      4819      4820      4823      4824      4825      4826 
    q3x78ys6h g6c7vbfyk w4t2yxpog 7vosqu4jm czx82g1k3 tef5z2i3j zr8eklgox 
         4829      4831      4837      4838      4839      4840      4844 
    cpny6uxm4 8gmbua2cn 51f2escjp tjrdg7qec w3jt5iznh 58h132cpm o2juld1ag 
         4845      4846      4849      4850      4853      4854      4856 
    tqn34dfpk diye6bfsl 5smxadlyi ceuk4lyoa zr6fy79vd nfe7lvcuq 1sofgirpv 
         4857      4861      4864      4869      4872      4874      4877 
    tjz1f9rms czu1wsv52 gu293jmlb 5v8m1cnlg 8hw9r2fp1 cv3yp4d18 s1qkbzdyf 
         4879      4880      4883      4884      4888      4889      4890 
    x38mfytvd wnesu81yk x84n5fr1g pxw8d6has 4c5g2xqvh 9y4xlwcqn cxfsr9ju3 
         4892      4893      4898      4899      4900      4904      4906 
    gqpvl841t m1eansgpl 8ajo3ew57 m195zuk3s o1ul273sp s7t4q86wm 3wx475t8p 
         4907      4908      4914      4915      4918      4926      4930 
    nc4a793v6 yfs2g8m35 zop74ife9 s2nmrhguv w593yt8qj ba49vyrin t4zlku76p 
         4931      4933      4935      4937      4940      4945      4946 
    5od3r6knf e8b5fctwy t8lvrimsz i15mobjun 7cixksu2n 7okyr4lad 791peolj2 
         4949      4950      4955      4958      4961      4963      4966 
    713v8jrms ycipr6bnx r46ymgubo dw9xom5u2 etvo9djw5 zqgt7l5dh 9jyx52lco 
         4974      4976      4977      4979      4980      4982      4983 
    h73ct6zu5 9kaeg27oi kw92ejd85 u69x3pbgi aijhmt6fr g9ks2r7al s83exwjgq 
         4987      4990      4991      4993      4994      4996      5007 
    zfb9l5nyc bndvtxsip k31fy8e5g b4uw7f2pz lukpz1nec 6hnem912k szfid32um 
         5008      5011      5013      5015      5017      5019      5024 
    a7f6qzs8c fa8pj1gs6 lymrf914z nwd3r9toa 23thasvf8 1zrtknbw7 nvl8ydq1o 
         5025      5026      5028      5030      5032      5035      5038 
    zmdc6p4jx u1vm64etz zvh8dcu1f 9baz3nhqj 9ky3mwtvo m8vqogfex 78r9dj3iw 
         5041      5047      5049      5051      5055      5057      5058 
    w3nvpq8tl gyt2e85xi nhzol3vm9 5cs3bvqf2 2h34od18v x5bzcts4j yvb6kw7id 
         5060      5062      5063      5067      5079      5081      5083 
    14sdhpvf8 wkuh24p79 9qxkehyw1 pose8mk2g hyx637wzk 9qnbu62w5 vtmx7ou53 
         5085      5086      5090      5093      5094      5095      5100 
    xovm4prby 5aeqlmg1o xq68dcntr t4vdocuni gmkuoey58 e9f3hduwv bj8l7pxyu 
         5101      5103      5104      5105      5111      5114      5116 
    km7y9xpv1 8g5lc9yhw gld4w1x7q 7tn8o3p9y yq9punmgf dmiwhay9k c3pd25xnk 
         5117      5121      5124      5125      5127      5131      5134 
    hojpcmiwn dwqu6mbf4 fwl68tvnc vnf74j862 6wv829mp3 1b2nhtvqe ywnpiorhz 
         5139      5142      5144      5145      5150      5152      5154 
    1z8bkirqf 2jr3t5lh9 urxza24i9 2nd3b6q7l 5dm4o2nsu ykinxsa2o oeawvtkzl 
         5155      5157      5163      5164      5168      5173      5177 
    br4z8emkj j6z3iyn87 5g3fw6mnu hit14v6np oap28xbm7 9pxa6yerw 6zt4nfak3 
         5181      5186      5187      5189      5190      5195      5196 
    tuw9afix1 o3w7g482q ka5m4cr1y gulirfs7h hj3r9pgl2 cd2ozphs3 aiqx8cm3e 
         5202      5203      5204      5218      5221      5222      5223 
    vcet2ordx tlvfh24gd qidzfsbvn qkslymtbj tm3ld49os 3zubefmtc 2ted9nvux 
         5225      5234      5235      5236      5237      5238      5239 
    za7crp9js zhmlqofk6 swc4y6mn7 on7m83lhy udb7z2wnq fims5v8r9 13p6uhmba 
         5240      5244      5245      5246      5247      5250      5251 
    qkm4t1rhd pntk84f2e 5tquyps1i fewobgtq6 fdzsevb9n uctzy3gnw lvnxca9q5 
         5257      5259      5260      5265      5268      5273      5277 
    l7bip2geh hnrbdp5j7 zn3ci9pwy ol987ruy1 hf8bnw71v lj4dmhu5f bfw1ryi9u 
         5282      5283      5285      5287      5288      5289      5290 
    tn7d5kecr be1zwnilk uzpobgmvl utmsrf2p8 k3n25tep8 anvletz15 cmyv1ehks 
         5294      5299      5302      5305      5306      5307      5308 
    wpuysfb5v 1r974lyko kl3w52igy g12l3mp6e msxvj7r8k puliwgz7n xgtj9rf17 
         5312      5313      5315      5320      5322      5324      5327 
    mz3byslrh ciz4elxvd 9i4nmu6sa sfhb27wtl 1mir8kcfq r9ub5fy8s 6v8ejh3rf 
         5328      5330      5331      5333      5334      5335      5336 
    wbj47tsod ja7pfhzoc 3ecdi9ba1 81osp4e6j e8tungqi6 rjth6a53i br2k63fvj 
         5340      5342      5345      5346      5349      5351      5352 
    9zl51vy7t nqcjv9ra5 q3r7gmhe2 5gibzrfx8 tzc5j3rwx dzjvw2eb4 ymj2d4pz6 
         5358      5360      5368      5369      5370      5371      5374 
    h8jrtczk2 f2njlkwg3 nb2k7jumv 3lb47nwd6 em18dksbo j9woqsp47 uzm9htdg6 
         5379      5380      5381      5382      5383      5384      5387 
    sx7d1imny v18n76kyp iqjfepknl hzsxbdcft i3j9nctzl t8w543pq2 tgioa5s94 
         5389      5391      5393      5395      5400      5401      5403 
    5cwodj9k8 deu3hj1mt 74sz56391 yekwas987 y73f86xdb yzkxuaf68 9kmpnft4y 
         5409      5411      5413      5420      5421      5424      5425 
    nup9zbde6 oczwv2x6d 6onxhzfay byz1wil7c op2i9nvwh x1z7q6bgd 4e76ulhsb 
         5426      5428      5429      5431      5435      5440      5445 
    pmc8zvb6j 39hzue5xy ioahfebrn raw6hj3oc 7z8th1qnc kpczvaxq9 85rfok2pm 
         5446      5447      5449      5453      5459      5461      5463 
    1vi43qaul fj3qun2ko eqpgidj3l jf5bp6qz8 71dkoyu8n wguqt86ma ijrk8zedt 
         5465      5469      5470      5478      5480      5486      5491 
    6w79oijtb 4rpm1oau6 crwsyxjpq tembsa2q1 v53nrzghw ik5lhn97s 2k14gy9xn 
         5492      5493      5497      5499      5502      5503      5507 
    uytkgnx7b wx8rk4g57 yu1xsia3t lx7qb3tg1 uasql5f1r nrv4u1tqe wn263sqr4 
         5508      5510      5511      5512      5513      5514      5515 
    u8qora1dl jqovet37z dc8ypzvf4 2z6gjcutl cw67kp24f fzpjbnm7r 2acru8vs7 
         5518      5519      5523      5524      5525      5526      5527 
    vhm3yfsl8 kvliwg7ns gats7214c hafz1x63g xk5uanb72 mu1k93rif vu7f3i48k 
         5528      5529      5530      5534      5536      5538      5540 
    ztd9ar58x 69pnzcmqg clygusatf u8n3eyxdo tqyp417zo rcna26tov c13eohlgk 
         5541      5542      5544      5546      5548      5549      5554 
    gmz79bqu6 vykpaui1b xefr782zk 81n4twr5o zmtoay9p7 wv26c5blq mwb8j5vnq 
         5561      5563      5564      5566      5568      5569      5573 
    9cy1enm8x 52mfpo3cg l1ehn29pr nbk3dy1lp cs36mwdbx jtpe4xisn 2wzlvr7ib 
         5575      5580      5584      5586      5588      5589      5590 
    2bxse6j7h e2pkl8vjn 4nmp982ea 7fk46invz atnc7ui69 yfvgqod21 xjvesdm9u 
         5593      5597      5598      5607      5608      5609      5611 
    rjmw8ok6z 8a7yc9nd3 xwsak6oqv oqivs2dhb fzlws7q3p s58jwkrpu szaktopy6 
         5612      5619      5620      5622      5629      5632      5640 
    z2egvy86k 2tg4arljh 3aypz8xsw rdgxuwy4i cylhu5g97 6rt5e7fam 3czqln6ks 
         5641      5643      5644      5646      5648      5656      5659 
    6u1rzyakv 2qac6pwmy hdz2oc7li zmw5uxikj rho8fe746 srjle3gwk fxteolwjn 
         5666      5668      5669      5673      5675      5677      5687 
    hx2wqlk9a yqvjoflie zo7apnw3m lus4wi8ne 7juimfnst 6lvknrxib ry8d3es5o 
         5688      5689      5690      5691      5703      5717      5718 
    1tgkucinb pjhq9nc6a 1mk2jicvd rspnexati q7dx9br4t 5mw6a197i s94xrei73 
         5719      5721      5729      5730      5731      5732      5742 
    amxs7pv5d wkiz6ltdb s9rfc6tyj 6apv94nbe 9dcrahg6o tbixcmeqr yrlhg6zjo 
         5743      5746      5747      5751      5758      5760      5763 
    koz7wr9i2 rwkys8pct awimxg24q p1ne64u28 xw8h3duc1 dmp4zrbw2 le14yaig8 
         5764      5768      5771      5775      5776      5780      5784 
    lga1cs7kt 6z93y8lc5 yzunepm4a dux3o98b5 new9xpy6d ih2fp4tly kic5ldx4h 
         5787      5788      5795      5796      5801      5802      5805 
    lzn6qb9hv lgsoxupjh nlso52y1q eigwm4h7q g6wqlmpnb ydeq3vtm5 cb9dafth4 
         5809      5811      5813      5816      5817      5819      5822 
    bzsxt2p6u v4b7m2uf3 bv6hjdmoi yl486xg9h 7r4y3zbd9 84ecn723f j61o5csd7 
         5825      5829      5830      5834      5836      5837      5841 
    xldzvutkn eucva2wst vju391lkb fmlwozk89 1zomqnyp8 oprfmuske vk4in2fs3 
         5843      5846      5847      5848      5849      5850      5852 
    8or6ycixj zpbvlo51y lnwh3fki5 yzskxhij9 daypui24o umd5i82ln pkfv73axn 
         5853      5855      5857      5861      5862      5863      5867 
    jknaogu41 4h5ql9xjr skq4ni3bm dp4ual8hk 2ldhbj5x6 omlz34rpa tbv5619nq 
         5868      5869      5871      5872      5874      5875      5876 
    5sbtwgqcn mpbyloi97 me45bodp6 xjsv19tfl 93ohlpwsn ouernqt6f ijnsdxk3t 
         5877      5879      5881      5883      5885      5886      5892 
    av3tnzcds pa1z5isok gbju4wecy fcjm1q6p3 zlrjy41wu hzmeusgoy tulb38cpa 
         5893      5894      5896      5897      5902      5909      5911 
    pqxeow1ru 146cowikt pqmcufh5s pl5ihdvx3 rbx2vcmgf 1k47lpx5i tcmuk6rps 
         5914      5916      5918      5922      5924      5926      5928 
    7v8r6ubi9 sjl5rahmy re3xdw51n 68czamnqy a5397cwjk 3wgpoe84y i3l6czgx1 
         5934      5940      5947      5949      5954      5956      5958 
    gql8ibvk7 6oh1pd3k2 lqznpsh5f avbeg7kni 7wq1lm8tj a645fzqc2 1t6un2gm8 
         5960      5962      5964      5969      5972      5976      5982 
    q9gjyf4h2 j4th2gfko 3cmhj8wv7 d967eaiot 2pxdrkit1 ja43c2uwp l98ty463i 
         5983      5987      5988      5989      5998      6000      6001 
    4f3eul8x7 l7xiz25qo byozi9fjv nkgr6p9m2 9az48c3po zgh4nkaoc kun8ivgje 
         6002      6003      6004      6006      6007      6009      6011 
    l79gsrzia h75efymv1 h654bstnu gijqao7r6 r1b3leg7c lxabnsre1 1ayx5jhed 
         6015      6018      6019      6020      6021      6022      6024 
    uhv9t4q5x lzgvt3i2h p1lun9fqy 5rdgb69lf 2mr7ndyve ytbjpm7w5 zgv85dbri 
         6025      6031      6032      6036      6039      6043      6046 
    5gen1ylv7 jh4a9pivf oa6qiyhj5 wh4u7oad2 dwb21c7yx qu3458zbm uo5rhv3i6 
         6052      6053      6055      6057      6058      6059      6060 
    38gw4asm5 uvz4koapi ja47plisw dngrq3s2i rbq14lfzt fhxo7931q opym9z541 
         6067      6070      6075      6076      6079      6080      6081 
    h7tsgbpzd plf5ymkns 4dsixk5fh bhtoq89ip j24obvh7m bfs1la7t3 8xv9ilruk 
         6083      6084      6085      6089      6092      6093      6098 
    n5t6bidlc cpyg25zrd ewk9lgdra eaftpq6zx swfrdvogy 4ckgsjyfd kcnwy63ho 
         6102      6104      6105      6108      6109      6110      6112 
    8f2s6ch14 n5ebdpmr7 4g5qkzpic z3h7sdqcv s1yucgapt vln6sfkti 5nhow1rl9 
         6113      6116      6117      6119      6121      6123      6128 
    48fa2hxmv kfx47pqs5 cf86a1wve 62zhpd3kv dorpjcftl s3he91jpk ox2d3t517 
         6136      6137      6138      6139      6140      6141      6143 
    w1qcvi8fo wrpxthf3e hn7k1yve5 cqj4gepdm yulbm5phv 4eujbnhy3 1hoq34tub 
         6144      6150      6152      6153      6157      6158      6159 
    yu8ckh4v5 3ca8lrxtv ry8uxv6m1 gh5wmozvb 42iowda9n galovpwur wh3qfdrag 
         6162      6164      6166      6168      6170      6172      6175 
    letjkvzo5 2m73wrosp bxahgd5tv moc6apvxu fe4xat1dm rcn84wzu7 4g9zhjsl8 
         6176      6177      6180      6181      6183      6186      6188 
    7hspwjrtc xes7waky4 a85rzxvm2 j79goy6kc fxi6b2ykw gn7edprcq ds4px2w7j 
         6189      6190      6191      6192      6193      6197      6199 
    5fg6qksv1 e7l86stub nhv5i9a3e 9eg61oajr 74cmuprk6 w4jnpi56a s5ikur4j2 
         6200      6201      6202      6203      6207      6208      6209 
    mb6xl5pn7 aly8vru1i x5swf3p9d 9c1xz4n8u tda9qvxnl 46yxubpwa m16y9fdvq 
         6210      6215      6216      6217      6219      6222      6223 
    pqo9nz7xg gyo83a91b je51u9dfp kcv8fxgmr ob2d3rihg cp3k7hfzm xl1tk9gcj 
         6225      6235      6237      6238      6239      6240      6242 
    oyc5p2enk otlwn1jxp c1oimxgl6 hrtqu8ob2 dvp2x6u14 hiugrcsjp voenbgxzm 
         6243      6247      6248      6249      6250      6251      6256 
    o46fxvinc o3sylbrdg qkaigc3w4 d8c9xls1o mruas4tpf qzw3ghcx8 l4awoevxu 
         6257      6258      6259      6260      6265      6268      6270 
    vi26cwqas afyj5xdbe zitumxbcg xry7ts9od ofpumbg47 d6ive2c75 kc726y8ra 
         6271      6273      6274      6275      6278      6279      6280 
    5xubk3ysl af5tegzuh 9sypkrwca pizk3tmy7 psyagibn6 fyxo2qlic dfc7mt8yn 
         6281      6283      6288      6289      6291      6293      6295 
    etyx42kfv 2f83rjt51 tnk6le5xg 546gvzewf anu9qsdhp g1cv4q3pr ykojudt7h 
         6299      6303      6305      6306      6308      6310      6312 
    1v8bkzdmf n2g7jw4ou 3kmy2foqw arhjmcn7q iwh7ujzm9 cbxtalh5z 3fwzbh4od 
         6313      6317      6318      6321      6323      6325      6328 
    i2sru3n61 ojb52ln4w t5uyq27jg dh9o75qva mdshy1cx6 m2crxq1nb lxwsgumji 
         6329      6333      6335      6337      6338      6339      6340 
    qhtyna5o4 2ihj63vre vowsxtz6k jekazg4xp fhim2dtbs ncs93exyd f4hlcanyt 
         6342      6347      6349      6352      6358      6363      6367 
    3bo2kz5xv ctf213eyb v8uxfyla6 i6lcoafp4 6z8n9sw2b ul1vmdsar h5pzft12i 
         6368      6372      6374      6376      6378      6379      6380 
    28pyoil9z uzna1md72 fuhr8cqps a4wxzvq81 weilg9r4y os7pk9n65 ra124edwh 
         6384      6386      6389      6392      6393      6394      6396 
    liuwrazvb z3l28eh9p zvchy6fng hobla75ge gzbc4fa7q g8nmpfaoh bv9qlipuc 
         6399      6407      6411      6412      6417      6420      6421 
    y4fl3m5kp 14dc7iuso vcwy49n7l t4q13ijo5 2ei35819v f56schdax 9rdjwxt4l 
         6428      6430      6431      6432      6433      6434      6435 
    c5ysvh7l2 dbvo2l79m zfocabkd3 clpt3sovm hisdxe85g f67ezijbx pohqse12l 
         6436      6437      6438      6439      6443      6444      6447 
    61n5lc7t8 zv4k6x93g 1fec6jkrw tvys1jdz6 6aljz239r cwfza8iuh dgpvy5oe7 
         6450      6451      6456      6463      6464      6466      6467 
    sthml9yp2 eqaxcot18 8glmuqd53 qhkay6nd2 i2qjmtdkb qu3veg157 2s8ofe3pm 
         6468      6469      6471      6474      6475      6479      6480 
    qxwasc6up 2tkdlx3oa gfdzsqj5k 4z2g9xk71 dq3upc4tj xt8cuzonp xc2mubej6 
         6482      6485      6486      6487      6488      6495      6498 
    ja95e1idq gny7dtqok vzwno8yma jo8utwr9n zef9kydxn oslwxp7ce 6eda4hkqi 
         6500      6501      6503      6504      6506      6510      6513 
    erdpoqj76 cos9napv6 ih8bkcnv9 bpr5ezqlw u74lo1c2m k521eurda 5m3fkvpe1 
         6514      6516      6518      6519      6520      6524      6528 
    dehb4n6au 79rsoekdv uq4bvt7od scwfhju8b xwzir526u 7ftqsnczx wbne6tuh3 
         6532      6533      6535      6539      6544      6546      6549 
    bemc1zu25 rhdv5moge caker3i5x ldt3siw7k zron45wa6 qgdyitz57 2s71k8omb 
         6553      6555      6558      6562      6563      6564      6566 
    5fnwvjo76 aordxmc1z phg972uvs hv3ylkxar p245ncx3v ruxhwyfoz 43bwhupli 
         6568      6570      6572      6573      6576      6577      6578 
    zfi7nupw6 l74jrnouh k3zdr68n9 3x8zc4gtq bnf2oi1rt 9gkqdsij8 evgirk4u3 
         6579      6580      6581      6587      6589      6594      6596 
    im8t32ouq hwaorktpe o9rm2dx68 7hrwcbtl8 tsgmvkn87 3ogb5tiys mx3cdpyvk 
         6598      6600      6606      6607      6610      6611      6614 
    tse4hzdmu 4dieza3v7 bn6f8hzow jch41xfu7 c3eb1gws7 n5ryhe1u2 rjiq5aphs 
         6618      6626      6627      6629      6633      6640      6641 
    tm6f8xzgk q56lrcymx xurgwdb26 pdeq941uj 65hgvtan7 bodp29tsa nq85u6dxm 
         6642      6643      6644      6649      6650      6653      6655 
    uqzcn8b39 f4ys3uezk jf2kb49wd n8l6qzx92 q9raj31fe xz7jmau8b mdh4u91gc 
         6656      6658      6659      6660      6661      6662      6663 
    zfo1jhegd 84fj3qzhw s8olun5v9 xfiwl4gqa g83vkentb czivw6s7x jr21emzpc 
         6664      6669      6674      6677      6678      6682      6684 
    o3sptu8ji 4rlv3p8yt fb1q5k4wc 41e63lgkq waq4u27pg 4n51ts6hi b1cqzw57m 
         6686      6692      6693      6694      6695      6697      6700 
    oyksx1qeh qjkl564xs d3vgyr1mo 1ji6wx7bg z3ed7x2kp ej8hikldo umo8krexd 
         6702      6705      6708      6709      6710      6713      6714 
    un3mh2lji d5intchpx gokqi6vmr ruovspkdz 5elknv4a1 ytlhvo5jd decs1z4bw 
         6716      6718      6727      6728      6738      6743      6746 
    b1epdlcr5 t89ibazm1 69kfbcpze 84dg1oz93 y9jt23emc bwml157e6 jqsfc9b5a 
         6750      6752      6754      6757      6758      6762      6763 
    q8hfubv4j izh2d1sno 3wu8kasnm 27nvljmyo j8y2klzx5 vdgtn6m7x f91xvnbr5 
         6764      6767      6768      6772      6776      6777      6781 
    fa7g29vzb wqyz6mhv7 d9fk7nmi6 gvzskybhc hksoqzg57 f2kqc9hta ypn8zbuwd 
         6783      6784      6785      6788      6789      6791      6793 
    1jflwv5tu p429cbdgx ujr7tlwb3 2wdkezm5n pihkvlxj3 tvg8hfi1d 914ivukoq 
         6796      6799      6800      6803      6804      6806      6810 
    a689istnx uyb7zmosj ku4ojc7wh hnerz952v fmak6ocyl 9j46ye38r jt37sif4o 
         6811      6816      6817      6823      6830      6833      6835 
    r4kxzavwp svuihfo1n nu19h7ij5 plxmactjz 8t7dj2zwb lo9ahjbxn k4evi85p6 
         6836      6843      6844      6845      6848      6851      6854 
    cbdfrh8kn y5z39oicm t38yvj427 eypunzm2o 41uszfjl7 tmkopi1ga 438tqwb1l 
         6857      6861      6862      6867      6870      6873      6874 
    jbsp26n48 k5rcu6p8o 92cw7onqk xr56ews3t o9we31fzr ru16mo4bt psgnwm1oy 
         6876      6878      6879      6880      6886      6888      6890 
    dej8iq1ho 1o9r3hsbj 6a1ht5lrm ga1bmo72r u5mg2vq4w w8cx415fv kwht31ald 
         6893      6896      6899      6900      6906      6910      6914 
    xu14ksr8t 4wbt9usp1 sojbu1i8f fxo6hqsja vqoag7fhx 5ubef8yx3 i97c4xt5h 
         6915      6917      6918      6923      6924      6925      6931 
    t2pxcjg97 kduo24iep 2i1l5sjkd 9om6a82ki 29lyu1res wb3f5gjmt obdecfpyw 
         6933      6934      6937      6938      6939      6942      6943 
    t3mp9korx b8lyq356c 7c86dqmhy v2pawiryk nwdf6xj4l gye3ub97s n7z5s39d4 
         6949      6951      6955      6959      6960      6962      6963 
    dp3nk9lqb 4cuzbomdh lgdjx5f96 7eo3vu91m bomgn164h f73sv8nhg ak4ox7yhv 
         6964      6966      6967      6968      6973      6974      6978 
    nyk4iq753 2n3ocipuf at3pflrcg x495vgosp m9qz164id r4giyha8o lkmt8yrfu 
         6979      6981      6984      6987      6988      6989      6992 
    imd2suztk lxbeqpwou zqnop2fh9 6lg1y58jo vrj856igs 4zn6muxdp 7hoxvszwa 
         6993      6995      6996      6998      7000      7003      7004 
    es2agjrcn ufpnt2yij 37crkilj4 3maprgvdf 5g2p17i9r 1jlykx6o8 ny73e6of9 
         7008      7011      7013      7017      7018      7019      7020 
    sfrxoezpq 728wgvk3i f6s5cm9nv 5kid2a1bu j6v8onfg3 yuq7w4jil d7yobanu3 
         7022      7023      7024      7025      7026      7027      7028 
    5amvw4x82 wtcey67ql cptrhieol clyitu64k wsbtm9uha vxtn2p7q6 g49nd2qea 
         7029      7030      7032      7033      7035      7036      7040 
    8dzqehu1w 8w7dxurvt zg5ec4yao b2x8i3qwc d1pasowmt zqjvdgcun kgvlz64ni 
         7043      7044      7049      7050      7051      7053      7056 
    xlk8tvnuw anzo21kv3 3uiro5f6n e3sj7wdfg 2prlta31j 983xlu7qy ph91axwzy 
         7058      7060      7061      7069      7073      7075      7076 
    9kgcjxb1l 3g47ch2ua 3cdzgvmpo 6hc4ev5y9 rhcjzkxym 16at5bnpj slnu24ho5 
         7082      7083      7084      7086      7088      7089      7091 
    u96yldjqn zepnaxhqv zirh45adv v7ksx3blw ki17nvmf2 1anjo4s9y et53b4dyj 
         7093      7094      7095      7099      7100      7108      7110 
    68mly94ne 5hnudic9y tu6m4fidb u9k135xql roeli4mux kroh6by3x fq8gv1oa2 
         7112      7115      7116      7117      7120      7122      7124 
    m9hzqovt7 kni98q5yt 7gu6qaph5 uaqcoyvwn djpu49c7b 5h7vrj8pf hakr1fdu7 
         7126      7128      7129      7131      7139      7142      7143 
    c738flgri eqocxnimv plmxcrugo zciqfah5m ck1dzi4so tcgzm57jd kdqaz31rs 
         7144      7145      7147      7148      7151      7158      7159 
    m86saxkuo clyja2shm krmtf3npa u5ojx672q nkg6ueh4v uq5t3fglw otdzg8yv5 
         7160      7161      7162      7163      7165      7167      7168 
    h9oqw6usj dqvrmislw y2i81lx7o 3ij952zy8 1whk5vspe d2ysng3w1 gt5aocmuh 
         7171      7173      7174      7178      7179      7181      7182 
    b1kpuj6vt nbwq4idj1 1fc4s9wbg a2gmbd165 twnz9hqmb ijthn6vqx 79bpeozur 
         7184      7185      7188      7189      7191      7200      7202 
    k3alwoebx 6cw4qmdnl ycprba4fo zil9ths16 sgvcen9ub t94ys5f6l 4fatygon9 
         7204      7206      7207      7211      7212      7222      7229 
    zl4gkut6a phls2iog1 fq9g5cmyi 42mawuy3h 1tf5okahb 39v8nk6by av36rspku 
         7230      7231      7235      7236      7237      7239      7251 
    dv5gw1b3t b5ugsxqmz 9ib8hvx7y 5fzmyxd6r qmiet3l51 ux5ngjtzk vh23gw8sn 
         7252      7258      7259      7261      7276      7278      7279 
    np9rkli18 84dsazgfj gbe21lnc4 ct4m9nrgp vs26d1fle rcdustx69 bp95ozsem 
         7283      7285      7287      7289      7291      7293      7294 
    ixgoylpcm wktlnz7v2 olp4r17xs 6r39bngy2 4bxcmk6p7 6p7cqg8jt 6mh2nxybd 
         7295      7298      7304      7305      7307      7312      7314 
    helpgyoui nh3tv5sqi xydr85u91 bje926owg 96jupig1k anfk816ut b8ckivy3l 
         7315      7317      7318      7321      7323      7325      7329 
    s69bnp8li dvuxtzmq7 1tedafwhv lciwhvp4x p9r1joga4 wl5y2x7km kqj8z6fd7 
         7330      7331      7333      7334      7337      7340      7341 
    lkpgf3cez ojgveqsw1 csqj3vbpo 5ih3d79at xy2p4fgnm j39la1vp2 9hlfouj5w 
         7342      7349      7352      7353      7355      7357      7358 
    467tn9kw3 io9wx13ye karo59jd6 bqwnplh8y b2wpsz571 62etz8fga csdu38yqw 
         7363      7365      7366      7367      7370      7371      7374 
    uh3glca6t wsetco6zy kwsvypzfg zcd83txbi tc295dlnh yf78i9153 yh3akx5g2 
         7385      7396      7399      7400      7401      7402      7403 
    8465obam7 vi8hj6c35 6gsibw97o dbns2te7y a8uwrz7i4 mrluh5i87 b6yx5paej 
         7404      7405      7406      7410      7412      7413      7414 
    ueb7gjiq6 93tig61qm 9vhrge7id k2yvg3a5q dv6le1atn 9oaqmx1pu m5tra4hud 
         7416      7419      7422      7425      7428      7432      7433 
    6ij3grqlf k2t163sen iq2p7fa1w egm7pw8f4 1izs2xjy5 klo4utfia xzyq8w5os 
         7439      7440      7442      7443      7444      7445      7449 
    c7dboeslu 1xygq7r5e vxsyejl9n p61v5ru93 1v64djhg9 m6bs8472c h7693gbkm 
         7455      7460      7466      7468      7470      7473      7474 
    43wchmz6s cu4tjmwlk v7ujwkrit 91yjlf2nz rfg2atis5 awky2xbph t1hwlsb8f 
         7477      7480      7481      7487      7489      7494      7495 
    n51cqelk8 b5xupw1d2 gn4k53dol 9ngwk1po6 cd3821uzx oqltfkudv 84tgbhilk 
         7498      7500      7501      7514      7516      7519      7520 
    ydutkgms7 xefvh4yzt gqf5txj1p q8rzpmivx updgh5jbf q2diswk3m lakm48pdc 
         7522      7524      7526      7529      7536      7540      7542 
    ey3s5dm72 91vgfzjh7 ck9e716hx 53tupwknq mcsf54gzi u1aiq8r4p g81rfkubt 
         7549      7554      7555      7556      7571      7572      7574 
    avl5pmqnj gfz2wbyd4 vgft1ajdk 2rt1gkxe6 41vp32kjf a13p7d2yb pz5a96iws 
         7575      7582      7583      7584      7590      7592      7593 
    zwadihnop s29an6h78 q9idjk2vg v7ck3ledi 3yx7tnkzv ou57zvt69 rm9qsdx5n 
         7594      7597      7601      7608      7613      7616      7626 
    prc86oey4 4dmqx1psl jltv9dx1e 6tcpl9bij vdaclus35 f8bqhpkm2 lpaugwv9j 
         7628      7630      7632      7633      7642      7647      7650 
    xdo629z3q c1nk4mzia dp68ejihn 29vbecutf bmw843yui rcpaf4bz7 chnof4lv5 
         7651      7656      7657      7662      7664      7668      7673 
    v2n7f85sh jlxqwpa4t 461i8ga3b jnfm3ekqt 2ne3fjsut omx6h3l1v avscbiy23 
         7674      7676      7677      7679      7690      7697      7699 
    524vfxk9w 6i1cw9hkt wuxcjqo42 7jtxrh1s2 jleg89p2a u5d9rt4lm b6qc598ry 
         7702      7706      7707      7710      7714      7716      7719 
    twaecshir u7jeb1daz nirjy26dv 3ibnq5yjm v6xdrmchb lcmzxuwie mro32ci1s 
         7720      7722      7723      7726      7727      7733      7735 
    vkhlrdupf wle8mir59 kswjcbf8i o6yrg5l1e f7njw28si jh3rm95qw tk1ajlv9g 
         7737      7738      7740      7741      7742      7745      7747 
    p2m36yz71 he8uabikn jlu63ze75 8sfjb3ekl fb2vnhdzk ygszqv1ic qs9kb5i14 
         7749      7753      7757      7761      7768      7769      7770 
    smh7zdve3 m8aohd47l zr8lo1k9x j6kwdpi4o clehiav1f uf8des63i anlp86hmk 
         7773      7779      7782      7786      7791      7792      7793 
    b3uzk6tgq pigo1c7jy 5n3alqsbr 1ogs3cfy5 ekzm6fjox h8z629uyc 9vzimkw7j 
         7795      7796      7797      7801      7804      7805      7806 
    i5nc3gr8b 5az8l2ptg jxual58f9 7ijkc4roq pwrqducmt 15r9lq4ok j5vs4crg1 
         7808      7811      7812      7815      7816      7817      7818 
    w7fqox9hr yuspv8bwq npw714c6r d9pglv8nu 1ho6gr8qx isb5mgf1c pvq7ot13e 
         7822      7827      7839      7843      7846      7849      7850 
    fw6orh9j5 r1luaxsev ergzfmlph 1564b7xks 7msy38fra w9fexc2sa q43gt5yhw 
         7852      7853      7855      7857      7859      7861      7864 
    c7xjsurwi a9i7gp5tr ez9hn4c6g la5w7c6t8 y3ijoqfgd gevsyip7o 
         7867      7868      7869      7871      7878      7881 

    2n471r3hv 76gtqzenu uxe5jvsmd ucs7ae1h9 yeomc1xqw fnzsq2c6k gyjsu6th2 
           21        63        64        81        97       128       174 
    rbjy1fouq wksx3edoy 5jxqygf93 d1c7o4u5j jg6rki2bd god48l2ay xiwnot5zc 
          196       202       220       241       244       255       282 
    91mur5fg2 ljuskcmd7 fy1imkled k1426ltys 3i2vbwk8q xungwzm27 vw6fxe2kh 
          297       322       341       354       376       387       412 
    72yacvjz1 tfgqb6e43 euh8b5pf9 8bi1kwxj4 unykrp5cl 9po7fdt4c vq3osbh5i 
          413       432       438       444       467       519       528 
    7hscoz93l 153n6ojcw 1d56gocm3 9vakyjhgx yz1jaemv7 lgp4wsyn7 3leymg7xv 
          553       601       656       659       661       668       683 
    b4udjpw5t qagx5fwsy 1muo8vw47 ja1y36nrw 68lutjk59 jhw2s63z1 qmi87lvgf 
          690       704       717       719       746       763       777 
    9lmfdaxgb 5yu86ogq1 lvezpx185 1npst5x7d z3n8obvre m3g6w1dj8 tq1aryolc 
          817       858       874       892       901       916       922 
    va8b1u3w4 j19pq86ur r3tlypb7f u6xea5o9k njxw5d98l 52ydgpczu z1gx4humf 
          931       975       984      1021      1038      1039      1041 
    2n6ap5yjv r53auenc9 elhra2p59 vwitn68pb 2snyurt4w 4tze9wx5j cowbn198e 
         1101      1131      1163      1183      1260      1288      1295 
    wyfojpg78 la8cugts6 2pm7z4srx vj2wq5xks fdy7relx6 9l8p1h6jg onft1hq7e 
         1322      1329      1349      1358      1368      1391      1404 
    fxngy8kqi gkc8ytvle 1bidoqwvy gv7ejo4yh 513yg47sk x4521dgwc 2qpkgbult 
         1417      1439      1534      1565      1581      1586      1605 
    kosm82j7n gkaus7vtm 6k29co1a3 5k2u6eo1p k4q5xiyem 4ekuhld6t uyt2srman 
         1631      1652      1685      1799      1809      1953      1962 
    r7lq32hui y1jores4n ry8v7epms si8ypnuof 4yr89jpex ujgk1bprt zem48vxln 
         1994      2069      2142      2190      2213      2219      2263 
    xdiyuspjb y96tu2bwf jhdg28bfm coyh1x3qv kpbx2y95a uoptvai72 nqcly7xjs 
         2339      2355      2381      2433      2483      2631      2646 
    s6j8iyo5m 5izwsrcx2 49w5oxkf8 n2jbrskto 5fqn4y6ix 9fxcspzg1 knfv1z7ht 
         2648      2669      2724      2729      2739      2755      2764 
    9h83oremv lh6wtpkzx ubtrxfk4e v9iab6kq2 xcqr45bun 4jkfo39iz d64w5vlg8 
         2765      2813      2885      2891      2893      2901      2911 
    yupjo63n8 g86xznf95 bw47y2fom 1fs72qy3u a8fuygw7r qukwlce6m bkipjxr6z 
         2919      2974      2993      3001      3093      3098      3102 
    epc74aiju f3mj6o1hk fkqdj2ebm ybm1pkagt mzp3jnf9k x7z2l8f46 tk47chfr5 
         3212      3223      3272      3276      3288      3289      3304 
    lyktv3f9m abm5rpxk9 y9qhwn3vk l8kaebfij vg5idpt8m 3ionq4jv7 urv4ajn23 
         3309      3323      3328      3355      3370      3372      3378 
    1o3ncqi6u 7dbt4o81p h3zd8k21t 8wd1voycp gj6kdw957 zxkr7mlay jxn3yt7gi 
         3407      3413      3452      3488      3508      3617      3646 
    eid4tl86c 48ahmuldq 1o9e5hpgj 4w6a8mlue y95lgr7ad xqk2rblmw kq36ltidj 
         3648      3667      3731      3738      3787      3816      3871 
    hlb7e5otz b4jtli35k vrfo4s7dc q8c3hxnje 3bycv1tjk pxrtukd2w q57odkn6f 
         3878      3893      3909      3961      3987      4005      4100 
    njz5839dk j5yvl1w4c 9axwibdch dw1mzoy36 xkr4edsph tobw97nj6 arnfcjsy1 
         4107      4110      4148      4188      4218      4226      4270 
    oi4e7s6jx ctdzr1hwe h3rbvmdqy 981xs2clz vj9gihpn5 fxs5upa7z yxurk2izt 
         4281      4305      4460      4493      4500      4505      4545 
    kh4t3xy8d xltnv2ozc oec8hj3lz m4ec6jgwi u72rymxb1 wigndc5my hx5tvlknd 
         4656      4695      4725      4733      4752      4761      4847 
    8m3coaygw eswkhj7bt 93lx1hr7q xy784kzq6 1k6tqf2ly 9t26caoqx l6pugn9sf 
         4862      4927      4953      4970      5036      5043      5123 
    sdhuqzjpc lhjiwd87a z41dh28ra jt1sr8bvz em9a1gdq4 al6grd7wj fq1wnizdc 
         5132      5143      5161      5192      5215      5228      5229 
    o81chqmra tzn2mpjqe qzujf82b7 gthmp7ckj cwtvemqux j7i3c4bt6 phb3y9cg7 
         5261      5281      5292      5326      5394      5471      5475 
    ni6od1hqv qvu1cxory t1sn7cbuj 9umby3zvt eo1tzd49f x5mvypth4 fnoe8sxt7 
         5487      5495      5560      5626      5733      5781      5799 
    mupa9b5cg lwcbiqh9m kqwhza3gm s5nh21moy 6g2a1u7t8 f7rshpvo8 rp7mhzj3y 
         5814      5828      5832      5860      5864      5899      5903 
    c21pu7jkh o537urjv2 apck3ujrn ks2n36amq ozxcpts3r j12k463if rfu164hnc 
         5907      5921      5932      5965      5968      5971      5981 
    r9ba8yjfn 1xvmyf9go x8vc6n14r 7f81omlqp xzkpretai 7eu3bqhnt 87alz9uyv 
         6030      6087      6146      6194      6220      6253      6267 
    kgq9rpji3 p7fvnwt8g dx4kmoe3f 9hk8vfipl p1u3sje9g xh523rzct cu2wx9z5s 
         6304      6309      6322      6330      6344      6360      6361 
    fuizkyg8x qh75kvd1y sbqw4yo28 a28p71eg5 j3e4mgtzx fkivatwsp 94exc5ytv 
         6365      6385      6409      6481      6540      6543      6550 
    grj78vans kfrns8aog h8ipobncj wv89n2rmo z51jl6gm8 7h8y9cnx3 2rwvmto8i 
         6597      6666      6721      6723      6741      6795      6822 
    bxr3ftsl2 yfsv9z7kg hdazxeiu7 if5h7osga xi4sknwlc w6u7p1cv3 stg79ncm6 
         6826      6827      6828      6831      6853      6858      6941 
    eofnvj3py drp73njk4 pk9uqavh4 icu2ox7fw q1c8mbek5 q9sv3zi81 nsmlhqfz1 
         6994      7005      7015      7045      7074      7136      7137 
    s7exvm1qk v2f1rm7h8 3rj49k5ih sgrb16y4n q9v2w8fbx entr6pgjq 9zmi72kox 
         7150      7164      7175      7225      7282      7292      7326 
    i5av82u64 w7ar63kqh gbvqup6x9 aot85sgl6 dwcigr35e rcoslh1u9 5sw92vej1 
         7356      7364      7368      7390      7435      7465      7478 
    qs3jtpcvr ejnzds4x5 ca6xeh5uv r36d8ns9g chlrofwsz 2wm87sxek u6lx3mhj9 
         7506      7552      7573      7609      7643      7691      7708 
    nctq6jlkp w4hl1c2yg b6a82ucf7 12t4msroj 
         7721      7838      7874      7877 

    hmjoe4g3k y2g68vhkf qg1jsawuy af7eqjw8r p94myqeo6 pr8qd7xjv wxjofvkt4 
            1         9        39        82        86        91       104 
    k3ury7nvg 1vx3tznus 47nchz8gb v3tlkwj51 j32dbqg49 58ndl2rhy 5nqkugldx 
          105       108       121       157       158       166       167 
    7kbre6zo3 fjtr145ey mfc6vuq1d ylskpeqjr ynrheu46x 4uq7yx863 ceokhdut7 
          173       176       186       192       206       224       227 
    r8l4x279z zedtqi9y8 8qomjvade slwhu9n3z onchsr94l he7mrykia dpe1m5j7f 
          228       233       249       250       251       265       277 
    lq5aencvm p46cnsq28 8vajf5i34 sd356hmj7 bn5j2u98x cljxprwsk awnxmr8d4 
          295       296       307       308       318       329       339 
    n9ucjpwie efw5hc81s k5c78oth9 lhu5eipgc z2nscaui6 svhw7pyad ql81c7h53 
          344       363       381       389       409       416       433 
    uwf5yo6z2 lfzcosb95 ofvqpah89 zyoanvwhi vdmfn4tyc 2hbzal3po wcx61t2rn 
          434       449       472       481       487       514       516 
    xm8d5bwqo yl6xrqcof g98v1yms7 8mxl9jfh5 w9e5aisrh 4pimrcwy3 os5u4amyv 
          525       526       532       535       550       551       557 
    mrjvidun5 x3gvcklbd 9yprxtacw 5bg7sdc16 tj53xzn8r bvq6dxtkp xyg7hubz1 
          574       582       609       629       649       674       676 
    as5thbzgi y71dx9zet lqct5bum6 rw2mj3chz b937ti6yq yh4icu5ns x7tevn5ym 
          677       678       701       702       710       714       716 
    jvwumfx4n t3ibm9fj1 sgt6hy87o x1m7wfp24 l9jiz3r5w r6xlb3pvq hsul8baz2 
          729       733       748       749       754       767       818 
    ifb2ku5d9 vopldhf12 14h59xfcl 9coklh5bw ek751rsyp odsuzxhq5 g13ixyedb 
          833       880       881       920       929       930       962 
    eut4nvcmh wqsdk13x6 grip57n6l rkelthwvn 2dkhgbafc z5shjna2f qz6ocpihu 
          977       978      1005      1006      1022      1027      1035 
    27pdhew3c 1irmzaocy 4po7gn91l 8qkhxs9et yewl37sua oenvhs172 ahqkwn9xj 
         1049      1053      1064      1067      1077      1080      1082 
    9bag4lj68 vmb1okz27 7gijla8x2 8ko54nl3q cwpfi2rme v3n5ywxp2 unflz26qx 
         1085      1097      1099      1119      1126      1132      1147 
    wfb5ji3tu z6gd2plmi rlp86s3vu 1xyg27cwh c5wmukf1j cnpaybleq u9ik3wzs5 
         1151      1153      1174      1187      1189      1194      1206 
    yb26cdp3z oprvg2bzw hbvtx83l9 zcyhp7g2f txey9oldg 79sgy5mr2 k65dbxj3s 
         1213      1217      1229      1242      1258      1270      1272 
    46mhd9vkt cgxti72df ehn5fa2c7 4rohs5v3d n4cjfoqa2 ru1bfxqpi gmrit84af 
         1287      1292      1294      1309      1312      1316      1319 
    tir1nazm3 qbt7cylgm zg3cupkrb sce5wijbd f4pyjd56x d2ukegmpn 3tz7erxbv 
         1323      1333      1339      1382      1410      1420      1430 
    xhnvgeot4 2jdn6mav9 8uykfsdqz i5fvpw7dx klagj7dew tvise4w65 4wg29eyip 
         1431      1434      1436      1455      1459      1464      1468 
    gjbo2e9ry 8qj2gn4hy evihau3xm jqgfcovmw 8nikwqcbd bhw8r7a9p l3otmq7uh 
         1469      1470      1487      1508      1512      1513      1518 
    kjelno3xw d3p8jt1wu i7fcoa38b oley1m3fs nctgaj635 xjsfm12tq on5cipaex 
         1522      1529      1533      1540      1542      1544      1545 
    fi13qrmtk fob6d2nhg kheawltq8 pyzisq6nf 9ynud5vpx b89kahwrs umb1fg5vc 
         1547      1584      1591      1608      1610      1620      1624 
    rdwiu2lte qv4fi3ypx mzh62dgno bqeuymzw2 tgh2ck9ie gsxp42enk zcprwia6l 
         1630      1643      1645      1653      1655      1656      1677 
    9gynxcpvu od1luaten g8coa1lq6 pgkt7xenf c3t1qr6sa 65o48cp9f 2fc5ieqtj 
         1678      1680      1703      1707      1727      1751      1772 
    l7d16n2t8 fko1gcr97 esygx3rn7 7tvl324na 98hdr4lsy soamw849y zwhlcndm4 
         1807      1815      1850      1852      1872      1873      1881 
    dkaxst7fw d9jthzv2l hdbg8iewu ymn58etf7 2ozbiemlw rjv4tpmaw dlev61xku 
         1925      1942      1947      1963      1968      1969      1995 
    trq65zjau ycxi2dwev zdq1cijhe djrlfswgb ot4ng6q3i zfwgkmvay 7ish39yt8 
         1998      2001      2014      2052      2078      2086      2095 
    ytfrjbuzd 2c6jiy74d jyrlxw8zf 9ro3d6utz 3j8u1pw6e i1brplhsu 7h6k84elr 
         2096      2105      2115      2127      2131      2140      2154 
    yolqx7ndi h1ztcnm27 2t94vuz8f tkhocw95s 186vafwxd wl781x3ku 769lwntqr 
         2157      2162      2182      2197      2200      2216      2237 
    tngap4i5d p5rxvjtiu ri8wmxsal 3w1lgix8t uldt9ebcn ckl29gyx4 o3ysam621 
         2250      2259      2264      2268      2274      2280      2291 
    p9y8uvq4a 4lin61jyr bnr9xygze l71mxhdy6 gez3n96yv m52e916oz rhpuzg8b6 
         2293      2295      2298      2303      2310      2314      2327 
    7qouegkb3 1w4eirynj 63ltj8ga2 zjcyvwrd4 87a2onwqp ew4au6vkg uta16bwmr 
         2360      2404      2407      2414      2425      2428      2429 
    1bdlxjen7 hktq4xrpm 7ux2vam5p 1hji78o9t ebf4oixvd l12rcpyab 3af54vnjy 
         2464      2465      2473      2485      2493      2524      2532 
    27sawbmt8 ebgt7p698 c2up9ty7d uj7rqham4 mjqsgca27 pl915ymgc rkxzj3qms 
         2535      2536      2546      2559      2572      2577      2578 
    fk3xl4ne9 ltf2jzhgw tgsxhj5cr 56ltikomd 6dcpbux27 p739uxa6s vj8fp1q2g 
         2588      2589      2593      2601      2610      2611      2619 
    325vbwp7s y8sivo1nu hwmze9ag2 49d2bc7mn ivonug3e1 qazjxpwmy e3q5pok2n 
         2621      2622      2640      2656      2659      2663      2665 
    9tsk1hcq5 6fq74n3wj vhujxd8wm o1khawpqu o32v965za o89pkrcid y68wfe9oc 
         2667      2691      2696      2714      2721      2728      2742 
    2wf7juldg ejwt319al plynihxu3 qx1bcwguf 8hg1sv7ac afk1cqlyg nldiz93uc 
         2766      2772      2784      2787      2799      2841      2866 
    ixltw7r5h k89w3gn7y a25gbjeon kdbxczi63 dnzteivp8 e1ylm8ijt 6zrxaiugo 
         2869      2897      2912      2916      2940      2956      2979 
    kleqphu7w bhcnwg376 8cx6zd725 mowixc5hk 5avlhxc8p imy26vzqt fdjebnvpt 
         2996      3006      3007      3009      3013      3028      3030 
    52y9hdp3i 7jp8qr4s3 pfb3dyx9h 6ucrgzwd7 8ktyfd4ra 7kzti1gq4 iz3qmv6w9 
         3042      3047      3049      3056      3063      3084      3092 
    v8obwj2u9 dxlki3wqo 4xhcsfk5t 9a21fe8it fxthw8rga kzg4plvs8 6q14brjzh 
         3115      3116      3127      3138      3148      3151      3187 
    chguonmx9 6v9q47nko bfj4q1dln 9jznbuhpv fk9s6vpzt 2urn6mtpe jynvtpaxu 
         3204      3209      3225      3232      3242      3244      3246 
    e8xavrhym qvbxey3zh 7gqtxdhme zmior6yq7 34xhcbp15 dymlvjf6e 6sl19njrd 
         3250      3255      3262      3265      3267      3277      3278 
    7m81ge6cd pnhgakc3w 7wrkxj698 tjr9ixg1n 4vshclbmi zi36k5sy1 o1l2f6ckn 
         3287      3302      3346      3350      3351      3364      3369 
    no3eaidy9 fzruptekn 6r8at5wym api9o5bsl fzm6snlgv wc8vy9ler 8dj5kc9l6 
         3382      3383      3385      3388      3416      3418      3419 
    532bhdkj9 vp74nkszx kcpxwt2eo dezjyncu5 sn8mbfreh 4r7nigdaf nwryhmtuj 
         3477      3515      3521      3527      3530      3532      3570 
    9yzchr6m4 d6zpfsmve 1hgd9r3on w7adynbzr wh5a3o4cl khmywtd2g 54gfphqbt 
         3575      3576      3584      3595      3600      3606      3636 
    jqp95l37z 1qjo4ks9h yc7avpmg6 5uqrpjswt v9c1olyfa 7ilmze639 1lz62hksn 
         3643      3645      3655      3670      3679      3683      3697 
    h71gotviz mos325u74 89qiyfdhw yre3pvibz kr5fydnwi ht85mjobe y7n34eogi 
         3699      3707      3715      3717      3728      3735      3742 
    n6fh13qrs yg46wlup2 bqdsx1luo dafkl6cx5 ozt9wnbi1 pboc7f3tr r73pwo4i2 
         3747      3768      3785      3791      3794      3799      3830 
    trqvnlbo3 e6j24b1wi yslitrjdg yxwo754zp z7s3ng9d4 l6fsjd2ez 5obfzl7pm 
         3831      3837      3852      3857      3873      3875      3922 
    f397oqhs1 l6t9u3zn4 xeqylpz24 6uwxfp5os klh7sgfx1 yofueixpj isb5dm3zy 
         3930      3949      3951      3960      3966      3976      3990 
    oryw6sdu7 mzcpswk7t jdoyzimuh thda8cpv3 62xml1gnt u35dgj1cw hln4zbf3u 
         3992      3996      4007      4011      4014      4027      4036 
    yrumaq1dg 6du9op8xr r31qs2glp b4uatwz69 81m4qos7c asudpiz85 t8hcbfsrv 
         4042      4044      4053      4061      4067      4084      4085 
    uvyjw2b5o q94wkve52 mqxr5327h x68o3naci smdtan8gu nhucfdijk q2e6g9wya 
         4093      4121      4137      4157      4170      4173      4195 
    9qagns35d oiqj31dt7 y79twkv82 rkswpcaz7 vqu4ozni1 895pziqx2 gwokh2f9z 
         4203      4209      4229      4235      4237      4262      4272 
    684zn3jmw wu8zq7xyg 6ud4zxwj1 sdz67xqcv tkd5xuh8y t3jcxqrbl fe523ny1h 
         4302      4316      4319      4324      4330      4333      4354 
    zs91gahbe h8v6ke5pi zbsa7mphc 2feyhmsrt nt1kpre3c s76if8hnu m72zgy8i1 
         4358      4359      4367      4369      4375      4377      4393 
    c9n8dhvuy ts91aljui zp2y6ieou ayg61v2zi di8wrqvgf v2ruim8k3 2th9187i5 
         4407      4431      4458      4461      4477      4502      4530 
    vpx1f3ygn ztshyvb2c lf2jmbyqr zl13b2d4k ytmj1eiqz 942srcx3d p379gyle8 
         4533      4557      4563      4569      4572      4592      4623 
    ais86klmh ksof45bjw 5b32f74ew wvy9i8o4p qwp9n34gt t9vj2nsmy 14wuvr5ph 
         4640      4655      4670      4672      4675      4689      4694 
    1zufl4bcp dt86q954w axtbl64q8 eldp93bmy qd8ix35fm tlsbcxgjf ftjaszr6m 
         4698      4707      4721      4727      4746      4748      4753 
    w5vqp3d9f d4zjqs3kp fsnu7xwql 9l8egunyk 68y2r7t3k 56fgjk8zv qkhy9u6ap 
         4754      4773      4784      4796      4802      4817      4835 
    ikowm7spx xl3vjfirc h7ut8oepx dp6wrbf3u 9crnght2a 3srcp19e8 gc53uo9s6 
         4852      4859      4876      4896      4928      4934      4939 
    4feyxoq68 j7rqow6mh 8nplbzkws ywg2rldbe nstyz13u2 6stv4yokx uwsy8x91t 
         4951      4954      4962      4972      4975      4981      4989 
    veumr6c82 869frijhw 8xulnshem u8flzbv3o 7kgrm36ln 6xop2ubfd ldz59peax 
         4998      5012      5016      5031      5037      5052      5053 
    ml7u2hbj8 fmj4qlbdx j6lfg23ct wcftirn4l zmjrkc31a zupcrif7n tgsviq4z8 
         5071      5078      5080      5082      5097      5102      5113 
    15gsko9xj 17myz4gsw osljnumby s6kzn17qi fescu6yzi 7621thrbx p961kl8vq 
         5118      5128      5129      5130      5140      5146      5147 
    8l2bvx64j sph5voix9 a3bp1nqvt vn3dh2ag5 rgz8typfm o4t97jeki o4ksz8wi5 
         5185      5193      5197      5199      5206      5220      5224 
    n5xhruwg7 xlz6yq5h4 url3ygs8n oxa26f8um 1wh9b6xmd 7vj2b9ogq nxovmh4a5 
         5230      5242      5243      5249      5256      5270      5280 
    5go2ek4bq zxtk1iysj aigzf2rb3 q5opgk32a 1qx9nsbc2 d8z14mfly twca4bdg1 
         5291      5297      5301      5316      5317      5347      5348 
    kpr3b1axf 5sdq913rl pxqlg4sd9 2lrxtkq8v r5l1hiy3f d5xq9s8cn dy12q5rtj 
         5350      5353      5354      5356      5363      5376      5388 
    r2xuv8hnd n6vq4rh1w xm8kblhqs eswtx3bgk wvtf7y5jq 83syv5wjz 39qvm8ylj 
         5396      5416      5417      5419      5427      5441      5455 
    zv6yclgxd 18lamgd56 bu2zf8odm nhs78x9a5 fwud3jknh zh3kosqt5 n6ci4usg7 
         5456      5467      5473      5479      5488      5489      5504 
    gt1klvf32 hgozlbt8u m2yob3jcq qcuwbgzjd o13earcq4 n8vblm9tg 3rlakgjnv 
         5506      5517      5520      5537      5551      5556      5571 
    p1jz6g2dc gcwup2tko j5orpadby 359id2t4k lx3knz9av 78ac4nq6e isodblw9j 
         5606      5610      5624      5660      5663      5709      5713 
    po8x79erb qus2acxdf 1z76gfju5 5qzkg6ib4 dlfzukcs2 q7hfrlktj lhixoq27s 
         5714      5723      5725      5735      5740      5745      5749 
    lre3go6sw dp18bsmjt bsaytxm8e tydqmg26k rl8btinw6 ltcrsd82v 5frn2v1s3 
         5750      5753      5761      5777      5779      5789      5792 
    eiclgu3s7 fc2irapvk 54nubf36o z9bjqgket rkh3udals afquj4vs6 p9qg7uevt 
         5794      5797      5810      5824      5838      5865      5873 
    4irhg2s1q wmtvjucqz lz2vfjxwo 6w3lohqdm 49pq2x8ng 7u2nqi945 ykm96oheg 
         5882      5891      5904      5912      5920      5927      5941 
    t13vjxpbl bwsza3t26 l9uq72v1r ea5fmnksb sbo8lrgy2 r639v8lio muv61af47 
         5955      5963      5973      6014      6041      6054      6056 
    kyjvg6so2 jgbh39w71 2jga1ihs4 fcdesuqwk svjgpr4n9 po59hs1m3 jmh569bz7 
         6063      6065      6066      6071      6072      6074      6077 
    satd4ceq6 u3no9sjhf w9vjhsklq hgwblyq4o obqzy8vnd 6ldwcr8qs qwo973ku1 
         6094      6096      6107      6118      6132      6147      6149 
    w4jnqexuk z3gfiw2m4 vhigerbqx 9n6rhojwe 6a8k49nqd v2mbzf5gn g6ml9pjyf 
         6160      6163      6198      6224      6228      6236      6245 
    nui74sfl2 jd2615af9 yxb1rkvht w81sj29u7 wjrydh6x2 feuipoktn xtsnlifrq 
         6302      6314      6324      6326      6331      6341      6354 
    z2lapydi9 oud8wgxs9 fng9tj15a h6xmio3de urof3zd8w xpszc681b fixpe4u5a 
         6370      6387      6391      6395      6400      6405      6416 
    v1o65a3yl 29kacb31z pny3akwh5 puse1yh4t z8lspnm6b 6qrpsy2ta iorany5x7 
         6427      6449      6465      6472      6491      6526      6527 
    tdrz38y7i l3naimovh c5digxqp7 qxr1eifpj 2uji4s9dv fun6pc1vz t8sfdcu6v 
         6529      6530      6531      6542      6547      6548      6552 
    li6v573ns 65h1mso4e h6vm7fqze 1i8pfcwqe 5raxqgwts mjnk4q2fa wosay7mpr 
         6591      6595      6615      6630      6631      6638      6647 
    z8i24twbg ytej3uvpx hz27kecf5 ji9oqtlf2 shjfvxnkw 3fjei5ux4 6zup3i87t 
         6648      6679      6681      6690      6691      6717      6725 
    dmu8w4jtb 67jor9kz4 tua1zei4o tk7n5s9hc n9evjiho4 p69lgwt5o 7bhinysr6 
         6740      6770      6774      6779      6782      6805      6813 
    qj3vc5oik nta3c47gm 29qmsaxo5 fqgdm6x9y sru5wkive la6wrhbgt zpan3rm2t 
         6815      6820      6840      6841      6860      6871      6875 
    v192hgi6s uhk6nlb17 ecn53h6m4 1xqthn9df 8mltfiuar oe6nkjz8t j3qwfzasr 
         6881      6891      6901      6928      6945      6969      6982 
    jya9tg2o6 phrdob4ly uelnstymx 2fv6ck9bm nvgkiq3tz fzycvih8e b8p674u15 
         6999      7042      7047      7062      7079      7101      7105 
    cybfvmqr8 l6xtj81mg tnov74ic3 v71yat4bf 9jelhxwz7 f1sejydlq 6nbm982tw 
         7106      7107      7118      7125      7152      7153      7156 
    dlnukwfzo o4983bf5d sqrgtvub2 xs5ulvge7 h7mo2v3ar bzpl8aow1 ev4kclbf9 
         7190      7210      7217      7228      7240      7244      7264 
    gksy5z4lv vcd4zgwri 1ybrpskhc sh9m7bz1g 2evasxdm8 8d3xzpl26 yvw2f9q4z 
         7266      7296      7297      7299      7301      7308      7313 
    ygt83ehn1 fn3ztad5p zn1lob8ax pnj791evx w2lt7nzqi muqv1dw46 fw69g7ukq 
         7322      7328      7343      7345      7350      7351      7381 
    vwl269fxo t1eb3c2hz rmec2fx1a akrmxgnq5 xvgpczoul arzejquxi cbwe4m1lt 
         7382      7386      7387      7388      7392      7395      7409 
    epwou2a8l jpcr21dy7 fy5nk9ez6 xt7aq9kjp vytsjizap ha1z9i4cb ug5cjo64i 
         7411      7417      7430      7452      7453      7454      7476 
    9zf1raesi g8pxy6n5z ydvgpwakt qcdx2oksp jzmpf8lqs g1miqv7kp ost1cmv74 
         7485      7488      7492      7497      7521      7527      7541 
    4nep6v5bi l6mey31u8 r95xow3dc uwalfi5jb dp9e43q6w s3b7ejrvd bay897li2 
         7560      7563      7566      7570      7581      7585      7586 
    1j62f7s34 9wecygroz drfje1xpk drujonq46 93bwa4zjl 95mcsx2e8 l78x2abq4 
         7588      7612      7652      7660      7681      7687      7688 
    vq52x3df8 cd4ejaiq8 aqgxscu9p 8s3mxrgya 2onjcek6v ok23nabzu gy7wvljpa 
         7709      7713      7725      7729      7752      7755      7756 
    j4i5uwa2m xymlqhr6v wslc5vz21 u6m2g4clt vm7xp8zqt 5pviyg6l4 ibfpj83ya 
         7766      7767      7775      7787      7802      7807      7814 
    4189nk2b5 asbw5p8k9 hsw2efyid f71rt6cyg 
         7820      7866      7875      7880 

Compare versus within-cluster average distances from the first run

We can see they are the same within each other. The first two rows show
the value considering withinss, the third and fourth row show the value
considering tot.withiness, and the last two rows show the values
concerned with
betweeness.

``` 
 [1]  8432.770 12748.494 15099.322  7828.209  6011.610 15442.886  9414.178
 [8]  9848.981 32123.832 18339.905 11238.117 13507.144
```

``` 
 [1] 32125.392  7828.209 18265.796 12783.141 13220.504  9930.936 11238.117
 [8] 15597.650  6011.610 15068.545  8551.394  9414.178
```

    [1] 160035.4

    [1] 160035.5

    [1] 160035.4

    [1] 160035.5

    [1] 100037.6

    [1] 100037.5

Generally speaking,not only we can use the graphs of clustering
considering the combination of different content informatiom shown on
their Twiiter. (i.e family/sports/tv/edcation), we can also consider the
clusters with different PCA characteristics.

After that and from the visualization of the data, we can help the
marketing segment to help precise marketing more efficiently.

To be specific, the companies can release products, servieces and
advertisements that target users and consumers based on several
parameters like the content they are interested in.
