Töluleg diffrun og heildun
==========================

Inngangur
---------

Töluleg deildun og heildun 
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Deildun og heildun eru meginaðgerðir stærðfræðigreiningarinnar.

Þess vegna er nauðsynlegt að geta nálgað

.. math::

   f'(a),f''(a),f'''(a),\dots \quad 
     \text{ og } \quad
     \int_a^b f(x)\, dx,

þar sem :math:`f` er fall sem skilgreint er á bili :math:`I` sem
inniheldur :math:`a` og :math:`b`.

Meginhugmynd í öllum nálgunaraðferðunum
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Látum :math:`p` vera margliðu sem nálgar :math:`f`, og látum
:math:`r(x)=f(x)-p(x)` tákna skekkjuna í nálgun á :math:`f(x)` með
:math:`p(x)`. Þá er

.. math:: f'(x)=p'(x)+r'(x), \quad f''(x)=p''(x)+r''(x), \dots

og

.. math:: \int_a^b f(x)\, dx=\int_a^b p(x)\, dx+\int_a^b r(x)\, dx.

Nú þurfum við að gera tvennt:

#. Finna heppilegar nálgunarmargliður og reikna út

   .. math:: p'(a), \ p''(a),\dots, \qquad \int_a^b p(x)\, dx

#. Meta skekkjurnar

   .. math:: r'(a), \ r''(a), \dots \int_a^b r(x)\, dx

Byrjum á að leiða út nokkrar nálgunarformúlur með skekkjumati.

Töluleg deildun
---------------

Látum :math:`f : I \to \mathbb R` vera fall á bili
:math:`I \subset \mathbb R` og :math:`a` vera punkt í :math:`I`. Afleiða
:math:`f` í punktinum :math:`a` er skilgreind með

.. math::

   f'(a) = \lim\limits_{h \to 0}
     \frac{f(a+h)-f(a)}{h}

ef markgildið er til. Við skrifum því oft

.. math:: f'(a) \approx \frac{f(a+h)-f(a)}{h}

Þessi nálgun er kölluð *frammismunur* því oftast hugsar maður sér að
:math:`h > 0` og þá er :math:`a+h` lítið skref áfram frá :math:`a`.

Við þurfum skekkjumat fyrir þessa formúlu ef við eigum að geta notað
hana.

Frammismunur
~~~~~~~~~~~~

Við fáum mat á skekkjuna í nálguninni með að skoða Taylor-margliðu
:math:`f` í :math:`a`. Samkvæmt setningu Taylors er til :math:`\xi` á
milli :math:`a` og :math:`a+h` þannig að

.. math:: f(a+h) = f(a) + f'(a)h + \frac{1}{2} f''(\xi)h^2.

Þá fæst að skekkjan í nálgun á :math:`f'(a)` með

.. math:: \frac{f(a+h)-f(a)}{h} = f[a,a+h]

er

.. math:: e = f'(a) - \frac{f(a+h)-f(a)}{h} = -\frac{1}{2} f''(\xi) h

 Með öðrum orðum

.. math::

   \min_{t\in [0,h]} -\frac 12 f''(t)h \leq e \leq 
   \max_{t\in [0,h]} -\frac 12 f''(t)h.

Við sjáum því að :math:`e=O(h)` þegar :math:`h \to 0`.

Bakmismunur
~~~~~~~~~~~

Við getum sett :math:`a-h` í stað :math:`a+h` í skilgreininguna á
afleiðu. Þá fæst svokallaður *bakmismunur*

.. math:: f'(a) \approx \frac{f(a)-f(a-h)}{h}

og ljóst er að sama skekkjumat gengur fyrir þessa nálgun og fyrir nálgun
með frammismun.

Miðsettur mismunakvóti
~~~~~~~~~~~~~~~~~~~~~~

Lítum nú á þriðja stigs Taylor nálgun

.. math::

   \begin{aligned}
     f(a+h)&=f(a)+f'(a)h+\tfrac 12 f''(a)h^2+\tfrac 16 f'''(\alpha)h^3,\\
     f(a-h)&=f(a)-f'(a)h+\tfrac 12 f''(a)h^2-\tfrac 16 f'''(\beta)h^3,\end{aligned}

þar sem :math:`\alpha` er á milli :math:`a` og :math:`a+h` og
:math:`\beta` er á milli :math:`a` og :math:`a-h`.

Tökum nú mismuninn og fáum

.. math:: f(a+h)-f(a-h)=f'(a)\cdot 2h+\tfrac 16\big(f'''(\alpha)+f'''(\beta)\big)h^3

Ef :math:`f'''` er samfellt fall, þá gefur milligildissetningin okkur að
til er :math:`\xi` á milli :math:`\alpha` og :math:`\beta` þannig að
:math:`f'''(\xi)=\tfrac 12 (f'''(\alpha)+f'''(\beta))`

Niðurstaðan verður

.. math:: f'(a)=\dfrac{f(a+h)-f(a-h)}{2h}-\tfrac 16f'''(\xi)h^2.

Þannig að skekkjan er

.. math:: e = -\frac 16 f'''(\xi) h^2,

og jafnframt er :math:`e = O(h^2)` þegar :math:`h\to 0`.

Miðsettur mismunakvóti fyrir aðra afleiðu
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Við getum útfært þessa sömu hugmynd til þess að reikna út aðra afleiðu,
en þá byrjum við með fjórða stigs Taylor-nálgun

.. math::

   \begin{aligned}
     f(a+h)&=f(a)+f'(a)h+\tfrac 12 f''(a)h^2+\tfrac 16 f'''(a)h^3
   +\tfrac 1{24}f^{(4)}(\alpha)h^4,\\
     f(a-h)&=f(a)-f'(a)h+\tfrac 12 f''(a)h^2-\tfrac 16 f'''(a)h^3
   +\tfrac 1{24}f^{(4)}(\beta)h^4,\end{aligned}

þar sem :math:`\alpha` er á milli :math:`a` og :math:`a+h` og
:math:`\beta` er á milli :math:`a` og :math:`a-h`.

Nú leggjum við saman og fáum

.. math::

   f(a+h)+f(a-h)=2f(a) +f''(a)h^2+\tfrac
   1{24}\big(f^{(4)}(\alpha)+f^{(4)}(\beta)\big)h^4.

Nú þurfum við að gefa okkur að :math:`f^{(4)}` sé samfellt fall, þá
gefur milligildissetningin okkur að til er :math:`\xi` á milli
:math:`\alpha` og :math:`\beta` þannig að
:math:`f^{(4)}(\xi)=\tfrac 12 (f^{(4)}(\alpha)+f^{(4)}(\beta))`.

Niðurstaðan verður

.. math:: f''(a)=\dfrac{f(a+h)+f(a-h)-2f(a)}{h^2}-\tfrac 1{12}f^{(4)}(\xi)h^2

Með Taylor-margliðum má leiða út fleiri nálgunarformúlur fyrir afleiður.

Við ætlum ekki að halda lengra í þessa átt heldur snúa okkur að almennu
aðferðinni.

Almenn aðferð til að nálga afleiður
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ef :math:`x_0,\ldots, x_n` eru punktar í :math:`I` (hugsanlega með
endurtekningum) og :math:`p` er margliðan sem brúar :math:`f` í þeim, þá
er

.. math:: f(x) = p(x) + r(x),

þar sem skekkjuliðurinn :math:`r(x)` er gefinn með formúlunni

.. math:: r(x)=f[x_0,\ldots,x_n,x](x-x_0)\cdots(x-x_n)

Ef við tökum :math:`p'(a)` sem nálgun á :math:`f'(a)` er skekkjan

.. math:: r'(a) =  f'(a) - p'(a).

Skekkjumat
~~~~~~~~~~

Munið að formúlan fyrir afleiðu af margfeldi margra þátta er

.. math::

   \begin{gathered}
     (\varphi_1\varphi_2\varphi_3\cdots\varphi_m)'(a)\\
   =\varphi_1'(a)\varphi_2(a)\varphi_3(a)\cdots\varphi_m(a)
   +\varphi_1(a)\varphi_2'(a)\varphi_3(a)\cdots\varphi_m(a)
   +\cdots\\
   \cdots+\varphi_1(a)\varphi_2(a)\cdots \varphi_{m-1}(a)\varphi_m'(a)\\\end{gathered}

Horfum nú á skekkjuliðinn :math:`r(x)`. Hann er svona margfeldi með
:math:`\varphi_1(x)=f[x_0,\dots,x_n,x]`, :math:`\varphi_2(x)=x-x_0`,
:math:`\varphi_3(x)=x-x_1` o.s.frv.

Athugum nú að ef :math:`a` er einn af gefnu punktunum :math:`x_k`, þá er
:math:`\varphi_{k+2}(x)=(x-x_k)` sem gefur :math:`\varphi_{k+2}(x_k)=0`
og :math:`\varphi_{k+2}'(x_k)=1`.

Þetta segir okkur að ef við tökum :math:`a=x_k`, þá eru allir liðirnir í
summunni í hægri hliðinni :math:`0` nema einn, þ.e. við sitjum eftir með
þann sem inniheldur :math:`{\varphi}_{k+2}'`.

Niðurstaðan verður því að skekkjan í nálgun á :math:`f'(a)` með
:math:`p'(a)` er

.. math::

   \begin{aligned}
     f'(a) - p'(a) &= r'(a)
   =f[x_0,\dots,x_n,x_k]
   \prod_{\stackrel{j=0}{j \not= k}} (x_k-x_j)\\
   &=\dfrac{f^{(n+1)}(\xi)}{(n+1)!}
     \prod_{\stackrel{j=0}{j \not= k}} (a-x_j)\end{aligned}

þar sem :math:`a=x_k`.

Hér notuðum við skekkjumatið fyrir Newton aðferðina (glæra 5.56) sem
segir að til er :math:`\xi` á minnsta bilinu sem inniheldur
:math:`x_0,\ldots,x_n,x_k` sem uppfyllir

.. math:: f[x_0,\ldots,x_n,x_k] = \frac{f^{(n+1)}(\xi)}{(n+1)!}.

Frammismunur
~~~~~~~~~~~~

Nálgum :math:`f` með fyrsta stigs brúunarmargliðunni gegnum punktana
:math:`(a,f(a))` og :math:`(a+h,f(a+h))` (þ.e. :math:`x_0 = a` og
:math:`x_1 = a+h`),

.. math:: f(x)=f[a]+f[a,a+h](x-a)+f[a,a+h,x](x-a)(x-a-h)

Af þessu leiðir formúlan sem við vorum áður komin með

.. math::

   f'(a)=f[a,a+h]+f[a,a+h,a](a-a-h)
     =\dfrac{f(a+h)-f(a)}h-\tfrac 12 f''(\xi)h

Þar sem :math:`\xi` er á milli :math:`a` og :math:`a+h` og uppfyllir að
:math:`f[a,a+h,a]=f[a,a,a+h]=\tfrac 12f''(\xi)`. Hér erum við að
notafæra okkur aftur skekkjumatið sem við sönnuðum í kaflanum um
brúunarmargliður.

Miðsettur mismunakvóti
~~~~~~~~~~~~~~~~~~~~~~

Tökum þriggja punkta brúunarformúlu með :math:`a-h`, :math:`a+h` og
:math:`a`. Þá er

.. math::

   \begin{aligned}
     f(x)&=f[a-h]+f[a-h,a+h](x-a+h)\\
     &+f[a-h,a+h,a](x-a+h)(x-a-h)\\
     &+f[a-h,a+h,a,x](x-a+h)(x-a-h)(x-a)\end{aligned}

Athugum að afleiðan af annars stigs þættinum

.. math:: x\mapsto (x-a+h)(x-a-h)=(x-a)^2-h^2

er :math:`0` í punktinum :math:`a` og því er

.. math::

   \begin{aligned}
     f'(a)&=f[a-h,a+h]+f[a-h,a+h,a,a](-h^2)\\
     &=\dfrac{f(a+h)-f(a-h)}{2h}-\tfrac 16 f'''(\xi)h^2 \end{aligned}

Hér nýttum við okkur að til er :math:`\xi` á milli :math:`a-h` og
:math:`a+h` þannig að :math:`f[a-h,a+h,a,a]=\tfrac 16 f'''(\xi)`.

Miðsettur mismunakvóti fyrir aðra afleiðu
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Áfram heldur leikurinn. Nú skulum við leiða aftur út formúluna fyrir
nálgun á :math:`f''(a)` með miðsettum mismunakvóta

Þá tökum við þriggja punkta brúunarformúlu með :math:`a-h`, :math:`a+h`
og :math:`a` með :math:`a` tvöfaldan. Þá er

.. math::

   \begin{aligned}
     f(x)&=f[a-h]+f[a-h,a+h](x-a+h)\\
     &+f[a-h,a+h,a](x-a+h)(x-a-h)\\
     &+f[a-h,a+h,a,a](x-a+h)(x-a-h)(x-a)\\
     &+f[a-h,a+h,a,a,x](x-a+h)(x-a-h)(x-a)^2\end{aligned}

Gætum þess að halda liðnum :math:`(x-a)`. Þá fáum við

.. math::

   \begin{aligned}
     f(x)&=f[a-h]+f[a-h,a+h](x-a+h)\\
     &+f[a-h,a+h,a]\big((x-a)^2-h^2)\big)\\
     &+f[a-h,a+h,a,a]\big((x-a)^3-h^2(x-a))\big)\\
     &+f[a-h,a+h,a,a,x]\big((x-a)^4-h^2(x-a)^2)\big)\end{aligned}

Nú þurfum við að reikna aðra afleiðu í punktinum :math:`a`. Athugum að
önnur afleiða af annars stigs þættinum

.. math:: x\mapsto (x-a+h)(x-a-h)=(x-a)^2-h^2

er fastafallið :math:`2`, önnur afleiða af þriðja stigs liðnum

.. math:: x\mapsto (x-a)^3-h^2(x-a)

er :math:`0` í punktinum :math:`a` og önnur afleiða af fjórða stigs
liðnum

.. math:: x\mapsto (x-a)^4-h^2(x-a)^2

er fastafallið :math:`-2h^2`.

Við höfum því

.. math:: f''(a)=2f[a-h,a+h,a]+f[a-h,a+h,a,a,a](-2h^2)

Nú er til punktur :math:`\xi` á minnsta bili sem inniheldur :math:`a-h`,
:math:`a+h` og :math:`a` þannig að :math:`f[a-h,a+h,a,a,a]=\tfrac
1{24}f^{(4)}(\xi)`.

Við þurfum að reikna út fyrri mismunakvótann

.. math::

   \begin{aligned}
     f[a-h,a+h,a]&=f[a-h,a,a+h]=\dfrac{f[a,a+h]-f[a-h,a]}{2h}\\
     &=\dfrac 1{2h}\bigg(\dfrac{f(a+h)-f(a)}h-\dfrac{f(a)-f(a-h)}h\bigg)\\
     &=\dfrac{f(a+h)+f(a-h)-2f(a)}{2h^2}  \end{aligned}

Við höfum því leitt aftur út formúluna

.. math::

   f''(a)=\dfrac{f(a+h)+f(a-h)-2f(a)}{h^2}-\tfrac
     1{12}f^{(4)}(\xi)h^2

Richardson útgiskun
-------------------

Það ætti að vera ljóst að töluleg deildun er nokkuð óstöðug aðferð því
ef skrefastærðin :math:`h` er lítil eru tölurnar
:math:`f(a+h), f(a), f(a-h)` nálægt hver annarri og við getum lent í
styttingarskekkjum.

Því er ekki hægt að búast við að fá alltaf betri nálgun á :math:`f'(a)`
við að minnka skrefalengdina :math:`h`.

Leiðin er Richardson útgiskun (e. extrapolation), sem er aðferð til að
bæta nálganir.

Til eru mjög almennar útgáfur þessarar aðferðar en við munum aðeins
skoða þau sértilfelli sem nýtast okkur mest.

Útleiðsla á miðsettum mismunakvóta
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Við skulum byrja á að að leiða aftur út formúluna fyrir miðsettann
mismunakvóta til að fá betri upplýsingar um skekkjuliðinn. Fyrir fall
:math:`f` sem er nógu oft deildanlegt má beita Taylor til að skrifa

.. math::

   \begin{aligned}
     f(a+h) &= f(a) + f'(a)h   + \ldots
     + \frac{f^{(2n)}(a)}{(2n!)}h^{2n}
     + \frac{f^{(2n+1)}(a)}{(2n+1)!)}h^{2n+1} + O(h^{2n+2}) \\
     f(a-h) &= f(a) - f'(a)h 
       + \ldots
     + \frac{f^{(2n)}(a)}{(2n!)}h^{2n}
     - \frac{f^{(2n+1)}(a)}{(2n+1)!)}h^{2n+1} + O(h^{2n+2})\end{aligned}

Ef við drögum seinni jöfnuna frá þeirri fyrri fæst

.. math::

   f(a+h)-f(a-h) = 2f'(a)h + 2\frac{f'''(a)}{3!}h^3
     + \ldots + 2\frac{f^{(2n+1)}(a)}{(2n+1)!}h^{2n+1} + O(h^{2n+2})

svo ef við einangrum :math:`f'(a)` sjáum við að

.. math::

   f'(a) = R_1(h) 
     + a_2 h^2 + a_4 h^4 + \ldots + a_{2n} h^{2n} + O(h^{2n+1})

þar sem

.. math::

   R_1(h) = \frac{f(a+h)-f(a-h)}{2h}
     \quad \text{og} \quad
     a_k = -\frac{f^{(k+1)}(a)}{(k+1)!},
     \quad k = 2,4,\ldots,2n.

Helmingun á skrefinu
~~~~~~~~~~~~~~~~~~~~

Hér er minnsta veldi í skekkjuliðnum :math:`h^2`, svo nálgunin
:math:`f'(a)
\approx R_1(h)` er :math:`O(h^2)`, eins og við höfum reyndar séð áður.
Helmingum nú skrefalengdina :math:`h`, þá fæst

.. math::

   f'(a) = R_1(h/2) + a_2 \left(\frac{h}{2}\right)^2
     + a_4 \left(\frac{h}{2}\right)^4 + \ldots
     + a_{2n} \left(\frac{h}{2}\right)^{2n} + O(h^{2n+1}).

Nú berum við saman þessi tvö skref:

.. math::

   \begin{aligned}
     f'(a) &= R_1(h/2) + \tfrac 14 a_2 h^2
     + a_4 \left(\frac{h}{2}\right)^4 + \ldots
     + a_{2n} \left(\frac{h}{2}\right)^{2n} + O(h^{2n+1}),\\
     f'(a) &= R_1(h) 
     + a_2 h^2 + a_4 h^4 + \ldots + a_{2n} h^{2n} + O(h^{2n+1})\\\end{aligned}

Margföldum efri jöfnuna með :math:`4` og drögum þá síðari frá. Þá
stendur eftir

.. math::

   \begin{aligned}
     3f'(a) &= 4 R_1(h/2) - R_1(h) 
     + a_4 \left( \frac{4}{2^4} - 1 \right)h^4 \\
     &+ a_6 \left( \frac{4}{2^6} - 1 \right)h^6
     + \ldots
     + a_{2n} \left( \frac{4}{2^{2n}} - 1 \right)h^{2n}
     + O(h^{2n+1})\end{aligned}

Fjórða stigs nálgun
~~~~~~~~~~~~~~~~~~~

Nú erum við komin með nýja formúlu:

.. math::

   f'(a) = R_2(h) + b_4 h^4 + b_6 h^6 + \ldots + b_{2n} h^{2n}
     + O(h^{2n+1})

þar sem

.. math::

   R_2(h) = \frac{4 R_1(h/2) - R_1(h)}{3}
     \quad \text{og} \quad
     b_k = \frac{a_k}{3} \cdot \left(\frac{4}{2^k}-1\right),
     \  k = 4,6,\ldots,2n.

Ef við berum þetta saman við jöfnuna sem við byrjuðum með

.. math::

   f'(a) = R_1(h) 
     + a_2 h^2 + a_4 h^4 + \ldots + a_{2n} h^{2n} + O(h^{2n+1})

þá sjáum við að minnsta veldi í skekkjuliðnum er :math:`h^4`, svo
nálgunin :math:`f'(a)
\approx R_2(h)` uppfyllir

.. math:: f'(a) - R_2(h) = O(h^4)

 og er því betri nálgun en áður.

Þetta ferli heitir *Richardson útgiskun*.

Hægt er að halda áfram útgiskun
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Næsta takmark er að eyða liðnum :math:`b_4h^4` úr þessari formúlu með
því að líta á

.. math::

   f'(a) = R_2(h/2) + b_4 \left(\frac{h}{2}\right)^4 
     + b_6 \left(\frac{h}{2}\right)^6 + \ldots
     + b_{2n} \left(\frac{h}{2}\right)^{2n} + O(h^{2n+1})

Síðan stillum við þessari jöfnu upp með þeirri síðari

.. math::

   \begin{aligned}
     f'(a) &= R_2(h/2) + \tfrac 1{16}b_4 h^4 
     + \tfrac 1{64}b_6 h^6 + \ldots
     + \tfrac 1{2^{2n}}b_{2n} h^{2n} + O(h^{2n+1})\\
     f'(a) &= R_2(h) + b_4 h^4 + b_6 h^6 + \ldots + b_{2n} h^{2n}
     + O(h^{2n+1})\end{aligned}

Margföldum fyrri jöfnuna með :math:`16` og drögum þá síðari frá

.. math::

   \begin{aligned}
     15f'(a) &= 16 R_2(h/2) - R_2(h) 
     + b_6 \left( \frac{16}{2^6} - 1 \right) h^6 \\
     &+ b_8 \left( \frac{16}{2^8} - 1 \right) h^8
     + \ldots
     + b_{2n} \left( \frac{16}{2^{2n}} - 1 \right) h^{2n}
     + O(h^{2n+1}).\end{aligned}

Sjötta stigs skekkja
~~~~~~~~~~~~~~~~~~~~

.. math::

   \begin{aligned}
     15f'(a) &= 16 R_2(h/2) - R_2(h) 
     + b_6 \left( \frac{16}{2^6} - 1 \right) h^6 \\
     &+ b_8 \left( \frac{16}{2^8} - 1 \right) h^8
     + \ldots
     + b_{2n} \left( \frac{16}{2^{2n}} - 1 \right) h^{2n}
     + O(h^{2n+1}).\end{aligned}

Því er

.. math::

   f'(a) = R_3(h) + c_6 h^6 + c_8 h^8 \ldots + c_{2n} h^{2n}
     + O(h^{2n+1})

þar sem

.. math::

   R_3(h) = \frac{16 R_2(h/2) - R_2(h)}{15},
     \quad \text{og} \quad
     c_k = \frac{b_k}{15} \cdot \left( \frac{16}{2^k} - 1 \right),
     \quad k = 6,8,\ldots,2n.

Nýja nálgunin uppfyllir

.. math:: f'(a) - R_3(h) = O(h^6)

og er því enn betri en áður, en við þurfum líka að reikna út
:math:`R_1(h/4)` til að reikna :math:`R_2(h/2)`.

Almenn rakningarformúla
~~~~~~~~~~~~~~~~~~~~~~~

Richardson-útgiskunin heldur áfram og út kemur

.. math::

   R_{i+1}(h) = \frac{4^i R_i(h/2) - R_i(h)}{4^i-1}
     = R_i(h/2) + \frac{R_i(h/2)-R_i(h)}{4^i-1}

fyrir :math:`(i+1)`-tu Richardson útgiskun og :math:`R_{i+1}(h)`
uppfyllir að

.. math:: f'(a) - R_{i+1}(h) = O(h^{2i+2}),

en á móti kemur að til að reikna út :math:`R_{i+1}(h)` þurfum við að
hafa reiknað út tölurnar

| :math:`R_1(h)`, :math:`R_1(h/2)`, :math:`\ldots`, :math:`R_1(h/2^i)`
  auk
| :math:`R_2(h)`, :math:`R_2(h/2)`, …, :math:`R_2(h/2^{i-1})` og svo
  framvegis að
| :math:`\qquad \vdots`
| :math:`R_i(h)` og :math:`R_i(h/2)`.

Eins og áður sagði fara styttingarskekkjur á endanum að segja til sín í
útreikningum á :math:`R_1(h)`, svo einhver takmörk eru fyrir hversu
margar Richardson útgiskanir er hægt að framkvæma.

Reiknirit
~~~~~~~~~

Útreikningarnir að ofan eru yfirleitt settir fram í töflu

.. math::

   \begin{array}{ccccc}
       D(1,1) &   &   &   &   \\
       D(2,1) & D(2,2) &  &  &  \\
       D(3,1) & D(3,2) & D(3,3) & & \\
       \vdots & \vdots & \vdots & \ddots & \\
       D(n,1) & D(n,2) & D(n,3) & \ldots & D(n,n)
     \end{array}

þar sem :math:`D(i,j) = R_j(h/2^{i-j})` og þar með

.. math::

   D(i,j) = \begin{cases}
       \dfrac{f(a+h/2^{i-1})-f(a-h/2^{i-1})}{2\cdot h/2^{i-1}}, & j = 1 \\
       D(i,j-1) + \dfrac{D(i,j-1)-D(i-1,j-1)}{4^{j-1}-1}, & j > 1
     \end{cases}

 sem gerir auðvelt að forrita Richardson útgiskun.

Skekkjumat
~~~~~~~~~~

| Finnum nú eftirámat fyrir :math:`D(i,j)` með stærðunum
  :math:`D(i,j-1)` og :math:`D(i-1,j-1)`. Hér á eftir er
  :math:`R_j(h/2)` í hlutverki :math:`D(i,j-1)` og :math:`R_i(h)` í
  hlutverki :math:`D(i-1,j-1)`
| (:math:`h` er helmingað þegar við förum niður um eina línu).

Munum að :math:`R_i(h)` uppfyllir að

.. math:: f'(a) = R_j(h) + Kh^{2j} + O(h^{2j+1})

fyrir eitthvert :math:`K` í :math:`\mathbb R` og að

.. math::

   f'(a) = R_j(h/2) + K \left( \frac{h}{2} \right)^{2j}
     + O(h^{2j+1})

Ef við tökum mismun á hægri og vinstri hliðum þessara jafna, þá fáum við

.. math::

   0 = R_j(h) - R_j(h/2) + K \left(1 - \frac{1}{2^{2j}}\right)h^{2j}
     + O(h^{2j+1})

og ef við einangrum :math:`K` fæst

.. math::

   K = -\frac{4^{j}}{h^{2j}} \cdot \frac{R_j(h)-R_j(h/2)}{4^{j}-1} +
   O(h^{2j+1}).

Útleiðsla á fyrirframmati
~~~~~~~~~~~~~~~~~~~~~~~~~

Þá er skekkjan í nálgun á :math:`f'(a)` með :math:`R_j(h/2)` jöfn

.. math::

   \begin{aligned}
     e_j(h/2) &= f'(a) - R_j(h/2) \\
     &= K\left(\frac{h}{2}\right)^{2j} + O(h^{2j+1}) \\
     &= -\frac{R_j(h)-R_j(h/2)}{4^{j}-1} + O(h^{2j+1}) \\
     &\approx -\frac{R_j(h)-R_j(h/2)}{4^{j}-1}.\end{aligned}

Þar sem :math:`R_j(h/2)` er nálgun á :math:`f'(a)` af stigi
:math:`O(h^{2j+1})`, en :math:`R_{j+1}(h)` er nálgun á :math:`f'(a)` af
stigi :math:`O(h^{2i+3})` getum við slegið á :math:`e_{j+1}(h)` með
:math:`e_j(h/2)`. Ef við lækkum vísinn :math:`j+1` um einn gefur það
okkur matið

.. math::

   e_j(h) \approx \frac{R_{j-1}(h)-R_{j-1}(h/2)}{4^{j-1}-1} =
     \frac{D(i,j-1)-D(i-1,j-1)}{4^{j-1}-1}

sem er einmitt liðurinn í rakningarformúlunni fyrir :math:`D(i,j)`.

Sýnidæmi
~~~~~~~~

Látum :math:`f(x)=x/(x^2+4)^{2/3}` og :math:`a=-1`. Byrjum með
:math:`h=1` og notum svo rakningarformúluna til þess að fylla út
útgiskunartöfluna.

+-------------+------------------+------------------+------------------+------------------+
| :math:`h`   | :math:`D(i,1)`   | :math:`D(i,2)`   | :math:`D(i,3)`   | :math:`D(i,4)`   |
+=============+==================+==================+==================+==================+
| 1 .         | 0.25000000       |                  |                  |                  |
+-------------+------------------+------------------+------------------+------------------+
| 0.5         | 0.25151838       | 0.25202451       |                  |                  |
+-------------+------------------+------------------+------------------+------------------+
| 0.25        | 0.25104655       | 0.25088928       | 0.25081360       |                  |
+-------------+------------------+------------------+------------------+------------------+
| 0.125       | 0.25086355       | 0.25080254       | 0.25079676       | 0.25079649       |
+-------------+------------------+------------------+------------------+------------------+

Niðustaðan er: :math:`f'(-1)\approx   0.2507964`, með eftirámat á
skekkju :math:`-3\cdot 10^{-7}`.

Rétt gildi er :math:`0.25079647217924889177`.

Töluleg heildun
---------------

Gerum ráð fyrir að :math:`x_0,x_1, \ldots, x_n` séu punktar á bilinu
:math:`[a,b]` og að við þekkjum gildi :math:`f` í þessum punktum. Þá
getum við fundið brúunarmargliðuna :math:`p_n` gegnum punktana
:math:`(x_k,f(x_k))` og skrifað

.. math:: f(x) = p_n(x) + r_n(x),

þar sem leifin :math:`r_n` er gefin með

.. math:: r_n(x) = f[x_0,\ldots,x_n,x](x-x_0)\cdots(x-x_n).

 Nú er auðvelt að reikna heildi margliða, svo við nálgum heildi
:math:`f` með

.. math::

   \int\limits_a^b f(x) dx \approx 
     I_n(f) := \int\limits_a^b p_n(x) dx

 og skekkjan í þessari nálgun er gefin með

.. math:: e_n = \int\limits_a^b r_n(x) dx.

 Þessi aðferð er kölluð *Newton-Cotes-heildun*.

Newton-Cotes -heildun
~~~~~~~~~~~~~~~~~~~~~

Hugsum okkur að brúunarpunktarnir :math:`x_0, \ldots, x_n` séu ólíkir.
Þá getum við skrifað :math:`p_n` með Lagrange-margliðum

.. math::

   p_n(x) = \sum\limits_{k=0}^n f(x_k) \ell_k(x),
     \quad
     \ell_k(x) = \prod\limits_{\stackrel{j=0}{j \not= k}}^n
     \frac{(x-x_j)}{(x_k-x_j)},

og þá er heildi :math:`p_n` jafnt

.. math::

   \int\limits_a^b p_n(x) dx = 
     \sum\limits_{k=0}^n f(x_k) A_k,
     \quad \text{þar sem} \quad
     A_k = \int\limits_a^b \ell_k(x) dx.

Athugið að gildi :math:`A_k` veltur aðeins á brúunarpunktunum
:math:`x_0, \ldots,
x_n` en ekki gildum :math:`f(x_k)`. Ef það á að heilda mörg föll yfir
sama bil er því hægt að reikna gildi :math:`A_k` í eitt skipti fyrir öll
og endurnýta þau svo.

Sýnidæmi
~~~~~~~~

Metum heildi :math:`f(x) = e^{-x}\cos(x)` og
:math:`g(x) = \sin (\frac{x^2}{2})` yfir bilið :math:`[0,2]` með að nota
skiptipunktana :math:`x_0 = 0`, :math:`x_1 = 1` og :math:`x_2 = 2`.
Lagrange-margliðurnar sem við eiga eru

.. math::

   \ell_0(x) = \frac{(x-1)(x-2)}{2}, \quad
     \ell_1(x) = -x(x-2), \quad
     \ell_2(x) = \frac{x(x-1)}{2}

svo við fáum að

.. math::

   \begin{gathered}
     A_0 = \frac{1}{2} \int\limits_0^2 (x-1)(x-2) dx = \frac{1}{3},
     \qquad
     A_1 = -\int\limits_0^2 x(x-2) dx = \frac{4}{3}, \\
     A_2 = \frac{1}{2} \int\limits_0^2 x(x-1) dx = \frac{1}{3}.\end{gathered}

Nú eru stuðlarnir fundnir og því fáum við

.. math::

   \begin{aligned}
     \int\limits_0^2 f(x) dx &\approx
     f(0)\frac{1}{3} + f(1)\frac{4}{3} + f(2)\frac{1}{3}\\
     &= \frac{1 + 4e^{-1}\cos(1) + e^{-2}\cos(2)}{3}
     \approx 0.59581\end{aligned}

og

.. math::

   \begin{aligned}
     \int\limits_0^2 g(x) dx &\approx
     g(0)\frac{1}{3} + g(1)\frac{4}{3} + g(2)\frac{1}{3}\\
    & = \frac{4\sin(1/2) + \sin(2)}{3} 
     \approx 0.91972.\end{aligned}

Gildi heildanna eru :math:`\int\limits_0^2 f(x) dx \approx 0.58969` og
:math:`\int\limits_0^2 g(x) dx \approx 0.99762` með 5 réttum aukastöfum
svo nálgunargildin verða að teljast nokkuð góð miðað við hversu lítið
fór í þau.

Trapisuregla
~~~~~~~~~~~~

Nú ætlum við að leiða út formúlur fyrir helstu reglum fyrir nálgun á
heildum. Sú fyrsta er *trapisuregla*.

Veljum :math:`x_0 = a` og :math:`x_1 = b` sem skiptipunktana okkar. Þá
er graf :math:`p_1` línustrikið gegnum :math:`(a,f(a))` og
:math:`(b,f(b))`,

.. math::

   p_1(x) = f(a) \ell_0(x) + f(b) \ell_1(x)
     = f(a)\frac{b-x}{b-a} + f(b) \frac{x-a}{b-a}

og vigtirnar eru

.. math:: A_0 = \int\limits_a^b \ell_0(x) = \frac{b-a}{2} = A_1,

 svo

.. math::

   \int\limits_a^b f(x) dx \approx 
     \frac{b-a}{2}\left(f(a)+f(b)\right).

 Trapisureglan er kölluð þessu nafni því með henni nálgum við heildi
:math:`f` með flatarmáli trapisunnar sem hefur hornpunktana
:math:`(a,0)`, :math:`(b,0)`, :math:`(b,f(b))` og :math:`(a,f(a))`.

Miðpunktsregla
~~~~~~~~~~~~~~

Enn einfaldari er miðpunktsreglan, þá veljum við aðeins einn
skiptipunkt, :math:`x_0 = \frac{1}{2}(a+b)`, og brúunarmargliðan verður
fastamargliðan :math:`p_0(x) = f(x_0)`. Þá er

.. math:: \int\limits_a^b f(x) dx \approx (b-a)f\left(\frac{a+b}{2}\right)

Regla Simpsons
~~~~~~~~~~~~~~

Nú veljum við þrjá skiptipunkta, :math:`x_0 = a`, :math:`x_1 = b` og
:math:`x_2 =
\frac{1}{2}(a+b)`. Til einföldunar skulum við hliðra fallinu :math:`f`
um miðpunkt bilsins :math:`m=\tfrac{1}{2}(a+b)`.

Við skilgreinum :math:`\alpha=\tfrac 12(b-a)` og
:math:`g(x) = f\big(x+m\big)`

Þá hliðrast :math:`a`, :math:`m` og :math:`b` yfir í :math:`-\alpha`,
:math:`0` og :math:`\alpha` og

.. math::

   \int\limits_{-\alpha}^{\alpha} g(x) dx = 
     \int\limits_a^b f(x) dx.

Lagrange margliðurnar og vigtirnar eru

.. math::

   \begin{aligned}
     l_0(x) &= \frac{(x-\alpha)x}{(-\alpha-\alpha)(-\alpha - 0)} 
     = \frac{(x-\alpha)x}{2\alpha^2} \\
     A_0 &= \int_{-\alpha}^{\alpha} l_0(x)\,dx = \frac{\alpha}{3} \\
     l_1(x) &= \frac{(x-(-\alpha))(x-0)}{(\alpha - ( -\alpha))(\alpha - 0)}
     = \frac{(x+\alpha)x}{2\alpha^2}\\
     A_1 &= \int_{-\alpha}^{\alpha} l_1(x)\,dx = \frac{\alpha}{3}\\
     l_2(x) &= \frac{(x-(\alpha))(x-\alpha)}{0-(-\alpha)(0-\alpha)}
     = \frac{(x+\alpha)(x-\alpha)}{-\alpha^2}\\
     A_2 &= \int_{\alpha}^{\alpha} l_2(x)\,dx = \frac{4\alpha}{3}\end{aligned}

Nálgunarformúlan verður þá

.. math::

   \begin{aligned}
     \int_a^b f(x) \, dx = \int\limits_{-\alpha}^{\alpha} g(x) \, dx
     &\approx \frac{\alpha}{3}g(-\alpha) + \frac{\alpha}{3}g(\alpha) 
     + \frac{4\alpha}{3}g(0)\\
     &=(b-a)\left( \frac{1}{6}f(a) + \frac{4}{6}f
       \left( \frac{a+b}{2}\right) + \frac{1}{6} f(b)  \right)\end{aligned}

Ef við tökum brúunarmargliðu gegnum :math:`a`, :math:`b` og
:math:`\frac{1}{2}(a+b)` með :math:`\frac{1}{2}(a+b)` tvöfaldan þá fáum
við 3. stigs brúunarmargliðu

.. math:: p_3(x) = p_2(x) + g[-\alpha, \alpha, 0, 0](x+\alpha)(x-\alpha)x

Heildið yfir seinni liðinn hægra megin er 0 því margliðan
:math:`(x+a)(x-a)x` er oddstæð, en heildið yfir fyrri liðinn er

.. math:: \frac \alpha3(g(-\alpha) + 4g(0) + g(\alpha)).

 Út kemur því Simpson-regla.

Samsettu reglurnar
~~~~~~~~~~~~~~~~~~

Þar sem Newton-Cotes heildun notar brúunarmargliður fylgja henni nokkur
vandamál.

Ef okkur finnst nákvæmnin í nálguninni vera of lítil getum við ekki
búist við að hún batni við að fjölga skiptipunktum; þá hækkar stig
margliðunnar líklega sem orsakar sveiflukenndari hegðun.

Eins er ekki gott að halda sig við margliður af lægra stigi; ef bilið
sem á að heilda yfir er stórt væri mikil tilviljun að 1., 2. eða 3.
stigs brúunarmargliða nálgaði fallið vel á öllu bilinu.

Lausnin á þessu vandamáli er í sama anda og fyrir splæsibrúun. Við
veljum skiptingu

.. math:: a  =x_0 < x_1 < \ldots < x_n = b

á bilinu :math:`[a,b]`.

Um heildi gildir að

.. math:: \int\limits_a^bf(x)\, dx = \sum\limits_{k=1}^n \ \ \int\limits_{x_{k-1}}^{x_k} f(x) \, dx

svo við getum nálgað heildi :math:`f` á sérhverju litlu hlutbili
:math:`[x_{k-1},x_k]` með að heilda brúunarmargliðu af lágu stigi og
lagt öll gildin saman til að fá nálgun á heildi :math:`f` yfir allt
bilið.

Þegar ákveðin regla er notuð til að nálga heildi :math:`f` á sérhverju
hlutbili er þetta kölluð *samsetta* útgáfa reglunnar. Einfalt er að
leiða út samsettar útgáfur reglanna að ofan.

Samsetta trapisureglan
~~~~~~~~~~~~~~~~~~~~~~

Á sérhverju hlutbili er

.. math::

   \int\limits_{x_{k-1}}^{x_k} f(x) \, dx
     \approx
     \frac{x_k-x_{k-1}}{2}(f(x_{k-1}) + f(x_k))

svo

.. math::

   \int\limits_a^b f(x) \, dx
     \approx
     \sum\limits_{k=1}^n \frac{x_k-x_{k-1}}{2}(f(x_{k-1}) + f(x_k)).

Ef öll hlutbilin eru jafn löng og :math:`h = x_k-x_{k-1}`, þá fæst

.. math::

   \begin{gathered}
     \int\limits_a^b f(x) \, dx \\
     \approx 
     h\left( \frac{1}{2}f(a) + f(a+h) + f(a+2h) 
       + \cdots + f(a+(n-1)h) + \frac{1}{2}f(b) \right).\end{gathered}

Samsetta miðpunktsreglan
~~~~~~~~~~~~~~~~~~~~~~~~

Fljótséð er að

.. math::

   \int\limits_a^b f(x) \, dx
     \approx
     \sum\limits_{k=1}^n (x_k-x_{k-1})f
     \left(
       \frac{x_{k-1}+x_k}{2}
     \right)

Ef öll hlutbilin eru jafn löng verður formúlan

.. math::

   \int\limits_a^b f(x) \, dx
     \approx
     h \sum\limits_{k=1}^n f \left(\frac{x_{k-1}+x_k}{2}\right)

Samsetta Simpson
~~~~~~~~~~~~~~~~

Hér er venjan að velja :math:`2n+1` jafndreifða skiptipunkta og fá
:math:`n` jafn stór hlutbil. Þá er :math:`h = \frac{b-a}{2n}`,
:math:`x_k = a + kh` fyrir :math:`k =
0,\ldots,2n` og hlutbilin eru :math:`[x_{2k-2},x_{2k}]` fyrir
:math:`k = 1,
\ldots, n`.

Á hverju hlutbili er

.. math::

   \int\limits_{x_{2k-2}}^{x_{2k}} f(x) \, dx
     \approx
     2h \left(
       \frac{1}{6} f(x_{2k-2}) + \frac{4}{6} f(x_{2k-1}) 
       + \frac{1}{6} f(x_{2k})
     \right)

svo að

.. math::

   \begin{aligned}
     \int\limits_a^b f(x) \, dx
     \approx &
     \sum\limits_{k=1}^n
     \bigg(
       \frac{h}{3}
       \Big(
         f(x_{2k-2}) + 4f(x_{2k-1}) + f(x_{2k})
       \Big)
     \bigg) \\
     = &
     \frac{h}{3}
     \Big( 
       f(a) + 4f(a+h) + 2f(a+2h)+ 4f(a+3h) + 2f(a+4h) \\
       &+ \cdots + 2f(a+(2n-2)h) + 4f(a+(2n-1)h) + f(b).
     \Big)\end{aligned}

Skekkjumat
~~~~~~~~~~

Rifjum upp grunnhugmyndina að baki nálgunarformúlunum. Við veljum
brúunarpunkta :math:`x_0, \ldots, x_n` í :math:`[a,b]`, látum
:math:`p_n` vera tilsvarandi brúunarmargliðu og skrifum

.. math:: f(x) = p_n(x) + r_n(x)

þar sem :math:`r_n(x) = f[x_0, \ldots , x_n, x](x-x_0) \cdots (x-x_n)`.
Þá er nálgunin

.. math:: \int_a^b f(x)\,dx \approx \int_a^b p_n(x)\,dx

 með skekkjuna

.. math:: \int_a^b r_n(x)\,dx

 Nú viljum við meta skekkjuheildið.

Meðalgildissetningin fyrir heildi
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Við skekkjumatið í þessum kafla munum við þurfa að nota eftirafarandi
setningu nokkrum sinnum. **Setning (Meðalgildissetningin fyrir
heildi):** Ef :math:`G:[a,b] \to {{\mathbb  R}}` er samfellt fall og
:math:`{\varphi}` er heildanlegt fall sem skiptir ekki um formerki á
bilinu :math:`[a,b]` þá er til tala :math:`\eta \in [a,b]` þannig að

.. math:: \int_a^b G(x){\varphi}(x)\, dx = G(\eta) \int_a^b {\varphi}(x)\, dx.

Trapisuregla
~~~~~~~~~~~~

.. math:: r_1(x) = f[-\alpha, \alpha, x](x+\alpha)(x-\alpha)

Athugum að

.. math:: (x+\alpha)(x-\alpha) = (x^2 - \alpha^2)

skiptir ekki um formerki á bilinu :math:`]-\alpha, \alpha[`. Þá gefur
meðalgildissetningin fyrir heildi að til er :math:`\eta \in [a,b]`
þannig að\ 

.. math::

   \begin{aligned}
     \int_a^b r_1(x)\,dx 
     &= f[-\alpha, \alpha, \eta]
     \int_{-\alpha}^{\alpha}(x^2 - \alpha^2)\,dx\\
     &= \frac{f''(\xi)}{2!} \left( - \frac{4}{3}\alpha^3 \right)\\
     &= \frac{-f''(\xi)}{2!}\frac{(b-a)^3}{6}, \qquad \xi \in [a,b]\end{aligned}

Niðurstaða:

.. math::

   \int_a^b f(x)\,dx = (b-a)
     \left( \frac{1}{2} f(a) + \frac{1}{2}f(b) \right) 
     - \frac{1}{12} f''(\xi)(b-a)^3

Skekkjumat í samsettu reglunni
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ef við lítum á samsettu trapisuregluna með jafna skiptingu þar sem
hlutbilin eru :math:`[x_i,
x_{i+1}]`, þá fáum við skekkjuna

.. math:: - \frac{h^3}{12}f''(\xi_i), \qquad \xi_i \in [x_i, x_{i+1}]

Ef við leggjum saman og beitum milligildissetningunni, þá fáum við

.. math::

   \int_a^b f(x)\,dx = T(h) - \frac{h^2}{12}(b-a)f''(\xi), \qquad 
     \xi \in [a,b]

að því gefnu að :math:`f\in C^2 [a,b]`.

Ath: Hér er :math:`T(h)` útkoman úr samsettu Trapisureglunni með jafna
skiptingu :math:`h = \frac{b-a}n`.

Skekkja í miðpunktsreglu
~~~~~~~~~~~~~~~~~~~~~~~~

Til einföldunar skoðum við bilið :math:`[-\alpha,\alpha]`. Veljum
miðpunktinn tvöfaldan

.. math::

   \begin{aligned}
     &p_1(x) = f(0) + f'(0)x\\
     &r_1(x) = f[0,0,x]x^2\end{aligned}

Athugum að heildið af :math:`f'(0)x` yfir :math:`[-\alpha,\alpha]` er 0.
Nú skiptir :math:`x^2` ekki um formerki og því gefur meðalgildisreglan
fyrir heildi að til er :math:`\eta \in [-\alpha,\alpha]` þannig að

.. math::

   \begin{aligned}
     \int_a^b r_1(x)\,dx 
     &= \int_{-\alpha}^{\alpha} f[0,0,x]x^2 \,dx\\
     &= f[0,0,\eta]\int_{-\alpha}^\alpha x^2\,dx\\
     &= \frac{f''(\xi)}{2!}2\frac{\alpha^3}{3}\\
     &= \frac{(b-a)^3}{24}\cdot f''(\xi)\end{aligned}

Þar sem :math:`\xi` fæst úr skekkjumatinu fyrir brúunarmargliður (kafli
5).

Skekkja í samsettu miðpunktsreglu
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Fyrir hvert bil fáum við skekkjulið:

.. math:: \frac{h^3}{24}\cdot f''(\xi_i)

Leggjum saman skekkjuliðina og beitum milligildissetningunni, þá fæst að
til er :math:`\xi` þannig að:

.. math::

   \int_a^b f(x)\,dx = h \sum_{i=1}^n 
     f\left(a+ (i - \frac{1}{2})h\right) + \frac{b-a}{24}f''(\xi)h^2

Skekkja í reglu Simpsons
~~~~~~~~~~~~~~~~~~~~~~~~

.. math::

   \int_a^b f(x)\,dx \approx (b-a) 
     \left( 
       \frac{1}{6}f(a) + \frac{4}{6}f
       \left( \frac{1}{2}(a+b) \right) + \frac{1}{6}f(b)
     \right)

Leiddum út þessa formúlu með því að taka brúunarmargliðu :math:`p_3(x)`
með punktana :math:`-\alpha, \alpha, 0, 0`. Skekkjan er

.. math::

   f(x) - p_3(x) = f[-\alpha, \alpha, 0, 0, x]
     (x+\alpha)(x-\alpha)x^2

þar með er skekkjan í formúlu Simpsons:

.. math::

   \int_{-\alpha}^{\alpha}f[-\alpha, \alpha, 0, 0, x]
     (x+\alpha)(x-\alpha)x^2 \,dx

Fallið :math:`x\mapsto (x+\alpha)(x-\alpha)x^2 = (x^2 - \alpha^2)x^2` er
:math:`\leq 0` á :math:`[-\alpha, \alpha]`. Þar með gefur
meðalgildissetningin fyrir heildi að til er
:math:`\eta \in [-\alpha, \alpha]` þannig að skekkjan er

.. math::

   \begin{gathered}
     f[-\alpha, \alpha, 0, 0, \eta]
     \int_{-\alpha}^{\alpha}(x^2 - \alpha^2)x^2 \,dx \\
     = \frac{f^{(4)}(\xi)}{4!}\cdot \frac{(-4)}{15}\cdot \alpha^5
     = \frac{-f^{(4)}(\xi)}{90}\left(\frac{b-a}{2}\right)^5, \qquad 
     \xi \in [a,b]\end{gathered}

Þar sem :math:`\xi` fæst úr skekkjumatinu fyrir Newton aðferðina (glæra
5.55).

Skekkja samsettu Simpsonreglu
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Skiptum :math:`[a,b]` í :math:`n` jafnlöng bil og látum :math:`h` vera
helming hlutbillengdarinnar,

.. math:: h = \frac{(b-a)}{2n}.

Þá er

.. math::

   \begin{aligned}
     \int\limits_a^b f(x) \, dx
     \approx &
     \sum\limits_{k=1}^n
     \bigg(
       \frac{h}{3}
       \Big(
         f(x_{2k-2}) + 4f(x_{2k-1}) + f(x_{2k})
       \Big)
     \bigg) \\
     = &
     \frac{h}{3}
     \Big( 
       f(a) + 4f(a+h) + 2f(a+2h)+ 4f(a+3h) + 2f(a+4h) \\
       &+ \cdots + 2f(a+(2n-2)h) + 4f(a+(2n-1)h) + f(b)
     \Big)\end{aligned}

Ef við beitum skekkjumatinu á sérhvert bilanna þá fáum við

.. math:: \frac{-f^{(4)}(\xi_i)}{90}h^5

sem skekkju með :math:`\xi_i \in [x_i, x_i+1]`. Heildarskekkjan verður

.. math::

   -\sum_{i=1}^n \frac{f^{(4)}(\xi_i)}{90}h^5 
     = \frac{-h^5}{90}\cdot \sum_{i=1}^n f^{(4)}(\xi_i)

Nú gefur meðalgildisreglan að til er :math:`\xi \in [a,b]` þannig að

.. math:: f^{(4)}(\xi) = \frac{1}{n} \sum_{i=1}^n f^{(4)}(\xi_i)

Nú er :math:`nh = \frac{(b-a)}{2}` þar með er skekkjan:

.. math::

   \frac{-h^5}{90}\cdot nf^{(4)}(\xi) 
     = \frac{-(b-a)}{180}f^{(4)}(\xi)\cdot h^4

Ef við táknum útkomuna úr samsettu Simpsonsreglunni fyrir
:math:`h=\frac{b-a}{2n}` með :math:`S(h)` þá fæst að til er
:math:`\xi \in [a,b]` þannig að

.. math:: \int_a^b f(x)\,dx = S(h) - \frac{(b-a)}{180}f^{(4)}(\xi)h^4

Romberg-útgiskun
----------------

Á sama hátt og við gátum bætt nálgun okkar á afleiðu falls með að nota
Richardson útgiskun getum við bætt nálgun á heildi.

Aðferðin virkar í aðalatriðum eins fyrir heildi og afleiður, en til að
fá sem bestar upplýsingar um samleitni hennar skulum við leiða út
formúluna fyrir trapisureglunni aftur.

Euler-Maclauren-formúlan
~~~~~~~~~~~~~~~~~~~~~~~~

Fyrir samfellt fall :math:`f : [0,1] \to \mathbb R` sem er
:math:`2n`-sinnum samfellt deildanlegt gildir Euler-Maclauren formúlan

.. math::

   \begin{aligned}
     \int\limits_0^1 f(t) \, dt 
     =&  \frac{1}{2}\left( f(0) + f(1) \right) 
     + \sum\limits_{k=1}^{n-1} A_{2k}
     \left( f^{(2k-1)}(0) - f^{(2k-1)}(1)\right) \\
     & - A_{2n}f^{(2n)}(\xi), \qquad \xi \in [0,1]\end{aligned}

Hér eru stuðlarnir :math:`A_k` þannig að :math:`k!A_k` verði
Bernoulli-talan númer :math:`k`. Þessar tölur eru stuðlar í veldaröðinni

.. math:: \frac{x}{e^x -1} = \sum\limits_{k=0}^{\infty}A_kx^k

(Það þarf að hafa töluvert fyrir því að sanna þessa formúlu)

Afleiðing af Euler-Maclaurin-formúlu
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Látum nú :math:`f : [a,b] \to \mathbb R` vera :math:`2n`-sinnum samfellt
deildanlegt fall. Ef við búum til skiptingu
:math:`a= x_0 < x_1 < \cdots <
x_n = b` með jöfn hlutbil :math:`h = x_{i+1} - x_i` og beitum síðan
Euler-Maclauren formúlunni á :math:`g(t) = f(x_i + ht)` fæst

.. math::

   \begin{aligned}
      \int_{x_i}^{x_{i+1}} f(x)\,dx 
     = & h\int_0^1 \underbrace{f(x_i + ht)}_{g(t)}\,dt \\
     = & {\color{blue} h \left( \frac{1}{2}f(x_i) + \frac{1}{2}f(x_{i+1})\right) }\\
      & +    \sum_{k=1}^{n-1}A_{2k}h^{2k}\left( f^{(2k-1)}(x_i) -
       f^{(2k-1)}(x_{i+1}) \right) \\
       & - A_{2n}h^{2n+1}f^{(2n)}(\xi_i), \end{aligned}

þar sem :math:`\xi_i \in [x_i, x_{i+1}]`.

Nú innleiðum við

.. math::

   \begin{aligned}
     T(h) 
     &:= \sum_{i=0}^{n-1}
     {\color{blue} h \left( \frac{1}{2} f(x_i) + 
     \frac{1}{2}f(x_{i+1}) \right)}\\
     &= h\left( \frac{1}{2}f(a) + f(a+h) 
       + \cdots + f(a+(n-1)h) + \frac{1}{2}f(a+nh)\right)\end{aligned}

og fáum síðan:

.. math::

   \begin{aligned}
     \int\limits_a^b f(x)\, dx 
     = & T(h) + \sum_{k=1}^{n-1}A_{2k}h^{2k} 
     \left( f^{(2k-1)}(a) - f^{(2k-1)}(b) \right) \\
     & - A_{2n}h^{2n+1} \sum_{i=0}^{n-1} f^{(2n)}(\xi_i)\end{aligned}

Nú gefur milligildissetningin að til er :math:`\xi \in [a,b]` þannig að

.. math::

   \frac{1}{n} \sum\limits_{k=0}^{n-1} f^{(2n)}(\xi_i)
     = f^{(2n)}(\xi)

Notum okkur nú að :math:`nh = b-a` og fáum að

.. math::

   \begin{aligned}
     \int\limits_a^b f(x) \, dx 
     = & T(h) + \sum_{k=1}^{n-1}A_{2k}h^{2k} 
     \left( f^{(2k-1)}(a) - f^{(2k-1)}(b) \right) \\
     & - A_{2n} h^{2n}(b-a)f^{(2n)}(\xi).\end{aligned}

Niðurstaðan er að samsetta trapisureglan er

.. math::

   \int\limits_a^b f(x) \, dx 
     = T(h) + c_2h^2 + c_4h^4 + \cdots + c_{2m-2}h^{2m-2} 
     + c_{2n}h^{2m}f^{(2m)}(\xi)

Ítrekun á samsettu trapisureglunni með helmingun
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Hugsum okkur nú að við viljum reikna út :math:`T(h_j)` fyrir
:math:`h_j =(b-a)/
2^j`, :math:`j = 1,2,\ldots` og að við viljum nýta öll fallgildi í
:math:`T(h_{j-1})` til að reikna út :math:`T(h_j)`. Rakningarformúlan er

.. math:: T(h_j) = \frac{1}{2} T(h_{j-1}) + h_j \sum_{k=1}^{2^{j-1}} f(a+(2k-1)h_j)

Athugið að hér er bilinu :math:`[a,b]` skipt í :math:`2^j` hlutbil.

Reikniritið fyrir Romberg-heildun
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Romberg-heildun er hugsuð nákvæmlega eins og Richardson-útgiskunin: Við
reiknum út línu fyrir línu í töflunni:

.. math::

   \begin{array}{cccccc}
       i\\
       1 & R(1,1)\\
       2 & R(2,1) & R(2,2)\\
       3 & R(3,1) & R(3,2) & R(3,3)\\
       4 & R(4,1) & R(4,2) & R(4,3) & R(4,4)\\
       \vdots & \vdots & \vdots & \vdots & \vdots & \ddots
     \end{array}

þar sem

.. math::

   \begin{aligned}
     &R(i,1) = T(h_i) \qquad i = 1,2,\ldots\\
     &R(i,j) = \frac{4^{j-1} R(i,j-1) - R(i-1,j-1)}{4^{j-1} - 1}.\end{aligned}

 Með þessu fæst
:math:`\int\limits_a^b f(x)\, dx = R(k,k) + O(h_k^{2k})`, þar sem
:math:`k` er síðasta línan sem við reiknum í töflunni að ofan.

Skekkjumat í Romberg heildun
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Skekkjumatið er hægt að finna með nákvæmlega sama hætti í fyrir
Richardson útgiskuna. Þ.e. við getum notað síðustu viðbót sem eftirámat
fyrir skekkjuna, þetta mat er

.. math:: e \approx \frac{1}{4^{j-1}-1}\left( R(i,j-1) - R(i-1,j-1)\right)

þegar þessi stærð er komin niður fyrir fyrirfram gefin skekkjumörk er
hætt. Kennslubókin vill fara aðeins varlegar í þetta og stingur upp á

.. math:: e \approx \frac{1}{2^{j-1}}\left( R(i,j-1) - R(i-1,j-1)\right),

 sjá bls. 500.

| Athugið að það er ekki nauðsynlegt að hafa :math:`h_1` sem allt bilið
  :math:`[a,b]`, það er ekkert sem kemur í veg fyrir það að við byrjum
  með :math:`h_1 = \frac{b-a}{m}`, og helmingum svo;
  :math:`h_2 = \frac{b-a}{2m}`, :math:`h_3 = \frac{b-a}{4m}`,
  :math:`\ldots`.
| Almennt er þá :math:`h_j=\frac{b-a}{2^{j-1}m}`.

Fræðilegar spurningar
---------------------

#. Hver er meginhugmyndin í tölulegri deildun og heildun?

#. Hvað eru *frammismunur* og *bakmismunur* til þess að nálga afleiðu?

#. Hvernig er *miðsettur mismunakvóti* fyrir fyrsta stigs afleiðu
   skilgreindur og hver er skekkjan í nálgun á afleiðu falls með honum?

#. Hvernig er *miðsettur mismunakvóti* fyrir annars stigs afleiðu
   skilgreindur og hvernig er skekkjan í nálgun á annarri afleiðu með
   honum?

#. Hvernig eru brúnunarmargliður notaðar til þess að reikna út afleiðu
   falls :math:`f` í punkti :math:`a` og hver er skekkjan í slíkri
   nálgun?

#. Lýsið fyrsta skrefinu i Richardson-útgiskun þar sem formúlan
   :math:`f'(a)=R_0(h)+a_2h^2+a_4h^4+O(h^6)` er endurbætt þannig að út
   komi skekkja sem er :math:`O(h^4)`.

#. Lýsið Richardson-útgiskunartöflunni.

#. Hvaða skekkjumat er notað í Richardson-útgiskun?

#. Hvernig er almenna aðferðin sem notar brúunarmargliður til þess að
   nálga heildi og nefnd er Newton-Cotes-heildun og hvernig er
   skekkjuformúlan í henni?

#. Hvernig er trapisuregla til þess að nálga heildi og aðferðarskekkja
   hennar?

#. Hvernig er miðpunktsregla til þess að nálga heildi og aðferðarskekkja
   hennar?

#. Hvernig er Simpson-regla til þess að nálga heildi og aðferðarskekkja
   hennar?

#. Hvernig er samsetta trapisureglan og aðferðarskekkja hennar?

#. Hvernig er samsetta miðpunktsreglan og aðferðarskekkja hennar?

#. Hvernig er samsetta Simpson-reglan og aðferðarskekkja hennar?

#. Hvernig er rakningarformúla fyrir samsettu trapisureglunni?

#. Lýsið reikniritinu fyrir Romberg-heildun.

#. Hver er skekkjan í eftirámatinu í Romberg-heildun?
