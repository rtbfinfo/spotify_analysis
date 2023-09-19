<script lang="ts">
    import Lenis from '@studio-freight/lenis';
    import { onMount } from 'svelte';

    import ScrollBloc from "./components/scrollBloc.svelte";
    import Hero from "./components/Hero.svelte";
    import Title from "./components/Title.svelte";
    import CardGraph from "./components/cardGraph.svelte";
    import ScrollExemple from './components/ScrollStructure.svelte';
    import SoundButton from './components/soundButton.svelte';
    import Navbar from './components/Navbar.svelte';
    import Quote from './components/Quote.svelte';

    onMount(()=> {
    //smooth scroll 
    const lenis = new Lenis()

    lenis.on('scroll', (e) => {
    })

    function raf(time) {
    lenis.raf(time)
    requestAnimationFrame(raf)
    }

    requestAnimationFrame(raf)

    })

    let graphText1 = `«&nbsp;<i>Le genre dominant aujourd'hui, ce n’est plus le rock. C'est le hip hop et tous ses dérivés&nbsp;</i>», observe Rudy Leonet. Pour ce spécialiste de la musique, ce style de musique fait la part belle aux formes courtes et catchy. «&nbsp;<i>Ce genre-là se prête parfaitement à ce type de format qui est compressible et restructuré à volonté en fonction des besoins et des demandes et des plates-formes.&nbsp;</i>»`

</script>

<Navbar/> 
<Hero/>            
<div class="h-screen bg-background rounded-2xl relative shadow-[ 0px_-20px_14px_-8px_rgba(5,247,130,0.78)]">
    <div class="max-w-3xl text-text px-4 pt-12 mx-auto text-lg">
        <p class="pt-6 first-letter:text-7xl first-letter:mr-3 first-letter:float-left">Il est petit, rond, vert barré de traits noirs et il a changé la musique pour toujours. Il y a 15 ans, le 7 octobre 2008, Spotify était lancé en version publique. Le but de cette plate-forme imaginée par les Suédois Daniel Ek et Martin Lorentzon&nbsp;: offrir de la musique à volonté moyennant des publicités ou un abonnement mensuel.</p>
        <p class="pt-6">La force de Spotify, c’est son algorithme qui vous connaît mieux que ne vous connaissait votre médiathécaire dans les années 90. Au point de vous proposer exactement ce que vous avez envie d’entendre au moment où votre humeur l’exige. Avec un revers à la médaille&nbsp;: le petit rond vert vous encercle dans des genres musicaux taillés pour vous plaire.</p>
        <p class="pt-6">Pour les artistes aussi, les choses ont changé. Du côté de la rémunération d’abord - quelques poignées de centimes par écoute sur Spotify - mais aussi dans la manière de composer de la musique. Vous allez le voir dans ce grand format qui compile des milliers de données&nbsp;: tout est une question de secondes cruciales…</p>
        <p class="pt-6 font-extrabold text-center">Ce récit commence avec du son. Cliquez sur le bouton ci-dessous pour l'activer.</p>

        <SoundButton />
    </div>
    <ScrollBloc />
    <ScrollExemple />

    <section class="Pourquoi max-w-3xl mx-auto mb-20">
        <Title
            txt='Spotify et la "règle des 30 secondes"'
            partie={1}
            color="bg-primary"/>
        <div class="max-w-3xl text-text px-4 mx-auto text-lg">
            <p class="pb-2 pt-6">Trente seconde&nbsp;: voilà le nœud du problème. «&nbsp;<i>Spotify demande au minimum 30 secondes d'écoute et c'est à partir de la 31ᵉ seconde d'écoute que l'artiste sera rémunéré pour l'écoute de sa chanson&nbsp;</i>», résume Rudy Leonet, spécialiste des musiques actuelles pour la RTBF.
                 Mais quelle rémunération&nbsp;?  De nombreux chiffres circulent. <a href='https://www.kicklabel.studio/comment-sont-remuneres-les-artistes-sur-spotify' target='_blank' rel=noreferrer>Un label spécialisé dans la diffusion de musique sur les plates-formes</a> évoque une «&nbsp;<i>rémunération moyenne de [ses] artistes à 0,0021€ par stream. Un million de streams sur Spotify équivaut donc à 2144 € environ,  soit environ 500 écoutes pour avoir 1€.&nbsp;</i>»
                 Tout dépend aussi des contrats négociés entre les petits ou grands artistes et Spotify lui-même. </p>
            <p class="pb-2 pt-6">Le géant suédois communique juste sur des chiffres généraux. «&nbsp;<i>Depuis sa création,
                 Spotify a versé presque 40 milliards de dollars de royalties aux ayants droit musicaux&nbsp;</i>», 
                 peut-on lire <a href='https://loudandclear.byspotify.com/fr-FR/' target='_blank' rel=noreferrer>sur le site loudandclear.byspotify.com</a>, une page qui vise à répondre aux attaques contre le business model de l’entreprise. 
                 La même source précise qu’«&nbsp;<i>à l’ère du streaming, les fans ne paient pas par titre. C’est pourquoi nous ne pensons pas qu’un ‘tarif par écoute’ 
                 soit un chiffre pertinent à analyser. À l’instar de tous les autres services de streaming majeurs, Spotify verse des royalties sur 
                 la base du nombre d’écoutes d’un ou une artiste par rapport à toutes les écoutes sur la plate-forme. On parle de ‘part d’écoutes’.&nbsp;</i>».</p>

                 <Quote 
                content="Un auditeur sur cinq zappe la chanson après cinq secondes"
                color="border-graphicPurple"/>
            
                 <p class="pb-2 pt-6">C'est logique&nbsp;: pour être écouté, il faut capter l’attention dès les premières notes… 
                et puis tout faire pour garder l’auditeur jusqu’aux trente secondes fatidiques. «&nbsp;<i>Quand on sait que 21% - donc un auditeur sur cinq - zappe 
                la chanson après cinq secondes parce qu'elle ne lui a pas donné satisfaction… l'idée c'est d'essayer, en 30 secondes, de dire un maximum 
                de choses pour retenir l'auditeur et pouvoir avoir la rétribution et la rémunération dues pour cette écoute&nbsp;</i>», professe Rudy Leonet.</p>
            <p class="pb-2 pt-6">Résultat, observe Christophe Pirenne, musicologue et professeur à l’UCLouvain, 
                «&nbsp;<i>ce qui arrive le plus souvent dans tous ces titres ultra-populaires, c’est que le ‘hook’, 
                cette petite mélodie d’accroche, doit venir presque tout de suite […] Mais ça, ça vaut pour une partie des répertoires.
                 La majeure partie des artistes restent quand même plutôt liés à des formes traditionnelles d'écriture ou de composition.&nbsp;</i>»</p>
            
                 <Quote 
                 content="C'est le côté catchy du titre qui va être prédominant"
                 color="border-graphicPurple"/>
            
            <p class="pb-2 pt-6">Rudy Leonet complète&nbsp;: «&nbsp;<i>On raccourcit les intros ou on les supprime. La voix doit arriver vite,
                 si possible avec le refrain déjà en ouverture. Un seul mot doit venir rapidement dans la chanson. C'est un moyen mnémotechnique de la retenir.
                  Donc on est tout de suite dans ce qui va procurer le plaisir le plus immédiat et le plus rapide.&nbsp;</i>» Et là, on songe immédiatement aux «&nbsp;<i>flowers&nbsp;</i>» (fleurs) 
                  qui ponctuent le refrain du titre éponyme de Miley Cyrus.</p>
            <p class="pb-2 pt-6"> «&nbsp;<i>Je pense que c'est le côté catchy du titre qui va être prédominant, 
                c'est la manière dont les gens vont l'intégrer, s'en souvenir, avoir envie de le chanter.
                 C'est quelque part dû à la construction même du morceau. Si le refrain qui revient plusieurs fois dans un titre arrive à la fin du titre,
                  c'est compliqué&nbsp;</i>», confirme Olivier Duerinckx, coordinateur Musical des Radios de la RTBF.</p>
        </div>
    </section>
    <section class="Pourquoi mx-auto mb-20">
        <Title
            txt='La preuve par les datas'
            partie={2}
            color="bg-graphicPink"/>
        <div class="max-w-3xl text-text px-4 mx-auto text-lg">
            <p class="pb-2 pt-6">Pour mieux comprendre l’évolution qui s’est jouée depuis le lancement de Spotify en 2008, 
                nous nous sommes plongés dans les chiffres. La plate-forme permet en effet d’extraire des données en grandes quantités pour des milliards de chansons.
                 Tout y est, ou presque&nbsp;: la durée du morceau, son mode (majeur, donc joyeux, ou mineur, donc triste), 
                 son caractère plus ou moins dansant, l’énergie qu’il dégage ou son tempo… </p>
            <p class="pb-2 pt-6">Mais pas question pour Spotify de donner le nombre d’écoutes réelles.
                 Il faudra se contenter d’une cote de «&nbsp;<i>popularité&nbsp;</i>» <a href='https://developer.spotify.com/documentation/web-api' target='_blank' rel=noreferrer>que l’entreprise définit comme</a> «&nbsp;<i>une valeur entre 0 et 100 où 100 est le plus populaire. 
                 Cette popularité est calculée par un algorithme et est basée, en grande partie, sur le nombre total d’écoute d’un morceau et à quel point ces écoutes sont récentes.&nbsp;</i>»</p>
            <p class="pb-2 pt-6 font-bold text-xl">Nous avons donc compilé les 100 titres les plus populaires année par année entre 2008 et 2023. Voici le résultat en graphiques.</p>
        </div>
        <div class="max-w-screen-lg mx-auto">

        <CardGraph 
            size="small"
            title="La pop au top"
            flourishId="14990472"
            textContent={ `«&nbsp;<i>Le genre dominant aujourd'hui, ce n’est plus le rock. C'est le hip hop et tous ses dérivés&nbsp;</i>»,
             observe Rudy Leonet. Pour ce spécialiste de la musique, ce style de musique fait la part belle aux formes courtes et catchy. 
             «&nbsp;<i>Ce genre-là se prête parfaitement à ce type de format qui est compressible et restructuré à volonté en fonction des besoins et des demandes et des plates-formes.&nbsp;</i>»`}/>
        <CardGraph 
            size="big"
            flourishId="14936027"
            title="34 secondes de moins"
            textContent={`La durée des titres est en chute libre depuis 15 ans pour perdre environ 34 secondes en moyenne entre 2008 et 2023. 
            Des titres globalement plus courts, c’est un bon moyen d’augmenter le nombre total d’écoutes… mais cela demande des ajustements en radio.
             Selon Olivier Duerinckx, «&nbsp;<i>d'une façon générale, les disques et les titres sont effectivement plus courts. Je pense qu'il y a encore quelques mois,
              quelques années, la durée moyenne était aux alentours de 3 minutes 20 ou 3 minutes 40 et maintenant on est clairement plutôt autour des trois minutes,
               ce qui nous a parfois obligés à rallonger nos conducteurs d'un titre parce que sinon on arrivait trop court en fin d’heure&nbsp;</i>».`}/>
        <CardGraph 
            size="small"
            flourishId="15019115" 
            title="3 minutes pour plaire"
            textContent={` Si on met en perspective la durée d’un morceau et sa popularité, une cible rouge se forme 
           &nbsp;: les titres «&nbsp;<i>qui marchent&nbsp;</i>» se situent majoritairement autour des 3 minutes. Bien sûr, il reste des 
            artistes qui obtiennent une bonne cote de popularité avec des morceaux longs. C’est ce qu’on pourrait appeler 
            «&nbsp;<i>l’exception Taylor Swift&nbsp;</i>»&nbsp;: quoi que la chanteuse américaine fasse, ça cartonne. Tel ce (long) «&nbsp;<i>All Too Well 
            (10 minutes version)&nbsp;</i>» en haut à droite du graphique. Quand on est une artiste internationale de cette envergure, on peut tout se permettre. `}/>
        </div>
    </section>
    <section class="max-w-3xl mx-auto mb-20">
        <Title
            txt="Quand la forme dicte le fond"
            partie={3}
            color="bg-graphicPurple"/>
        <div class="max-w-3xl text-text px-4 mx-auto text-lg">
            <p class="pb-2 pt-6">Ce n’est pas la première fois dans l’histoire de la musique que la technologie a influencé la forme.
                 «&nbsp;<i>Depuis qu'on a inventé l'enregistrement, le support dicte la forme</i>, résume Christophe Pirenne. <i>Quand les 78 tours sont arrivés,
                  où on pouvait enregistrer autour de trois minutes de musique, la musique populaire s'est pliée à ce format-là. Ça fait un peu plus d'un siècle maintenant
                   qu'on tourne avec des chansons qui ont été composées pour pouvoir entrer intégralement sur un support qui a d'abord été le 78 tours, puis le 45 tours, etc.&nbsp;</i>»</p>

                <Quote 
                content="Désormais, le but c'est d'être sur des playlists"
                color="border-graphicPurple"/>

            <p class="pb-2 pt-6">Le musicologue déroule encore le fil&nbsp;: «&nbsp;<i>Dans les années 70 ou 80  
                - soit au moment où on voulait fixer les gens sur la piste de danse - le support a dicté la forme,
                 avec le disco et les maxi-single. Et puis quand les CD sont arrivés, il fallait remplir un bazar 
                 qui pouvait contenir 82 ou 83 minutes de musique. Et donc là on a eu des albums beaucoup plus longs. 
                 Aujourd’hui, on revient complètement en arrière. La nouvelle norme avec le streaming, c'est de nouveau le single. 
                 Désormais, le but c'est d'être sur des playlists. Et vous ne pouvez pas y flanquer tout un album.&nbsp;</i>»</p>
            <p class="pb-2 pt-6">Rudy Leonet confirme et évoque le cas particulier de la radio&nbsp;: «&nbsp;<i>Tout mode de consommation a impliqué toujours son mode de fabrication.
                 Dans les années 70-80, les très très longs morceaux bénéficiaient de ce que l'on appelait un ‘radio edit’, c'est-à-dire un remontage où on compressait la chanson 
                 en trois minutes ou trois minutes 30, qui est à peu près le format classique qui a perduré pendant des dizaines d'années. C'était juste des petits aménagements,
                 mais ça ne défigurait pas la chanson et en tout cas, ça n'influençait pas la création originale qui avait son développement tel que l'avait voulu l'artiste.&nbsp;</i>»</p>
                 <img src="https://rtbfmedia.be/rtbfinfo/spotify_sound/pics/max_martin.jpg" alt="Max Martin, roi des tubes">
                 <p class="text-sm font-light border-l-4 p-1 mt-1 border-graphicPurple rounded-sm ">Max Martin, roi des tubes à l'origine du "...Baby One More Time" de Britney Spears et compositeur pour Taylor Swift. Ici aux Spotify's Secret Genius Awards le 1er novembre 2017 - Matt Winkelmeyer/Getty Images for Spotify</p>
                </div>
    </section>

    <section class="max-w-6xl mx-auto mb-20">
        <Title
            txt="Billboard Hot 100 et mainstream(ing)"
            partie={4}
            color="bg-secondary"/>
        <div class="max-w-3xl text-text px-4 mx-auto text-lg">
            <p class="pb-2 pt-6">Élargissons donc le spectre et regardons comment la musique populaire a évolué depuis le milieu du siècle dernier. 
                Nous nous sommes procuré un jeu de données gigantesque. Ce fichier de plusieurs milliers de lignes et de colonnes est l’œuvre de Chris Dalla Riva, 
                un musicien passionné de données. Celui qui est aussi l’auteur <a href='https://chrisdallariva.substack.com/' target='_blank' rel=noreferrer>du site Can’t Get Much Higher</a> a en effet compilé tous les titres du Billboard Hot 100 américain (le classement hebdomadaire des 100 chansons les plus populaires établi par le magazine américain Billboard) de
                puis la fin des années 50… et il a tout compté&nbsp;: la durée des morceaux, leur tonalité, le genre et l’âge des artistes. Cet analyste de données qui ne fait pas dans la demi-mesure a aussi chronométré à la main la durée des introductions de chaque morceau. Les résultats sont très parlants.</p>
            <p class="pb-2 pt-6">Premier enseignement&nbsp;: la durée moyenne des chansons a progressivement augmenté depuis les années 60 pour atteindre un pic dans 
                les années 90. Ensuite, cela n’a fait que décroître. C’est encore plus marqué pour la longueur des introductions, donc les quelques secondes avant que le 
                chanteur n’entre en scène. Dans les années 90, une intro pouvait allègrement dépasser les 20 secondes. Aujourd’hui, c’est beaucoup moins. Parfois 15 secondes, 
                parfois 5… parfois rien du tout.</p>
        </div>
        <div class="md:flex max-w-full mx-auto">
            <CardGraph 
                size="big"
                title="Durée moyenne des chansons du Billboard Hot 100"
                flourishId="14990731"
                textContent=""/>
            <CardGraph 
                size="big"
                title="Durée moyenne des intros du Billboard Hot 100"
                flourishId="14990758"
                textContent=""/>
        </div>
        <div class="max-w-3xl text-text px-4 mx-auto text-lg">
            <p class="pb-2 pt-6">Sur le graphique ci-dessous, nous avons placé toutes les chansons répertoriées par Chris Dalla Riva en ne gardant que celles dont l'intro fait 60 secondes ou moins. Pas de doute,
                 même si ce n’est sans doute pas la seule explication&nbsp;: l’arrivée d’une plate-forme de streaming comme Spotify coïncide avec
                  une baisse de la durée moyenne des introductions.</p>
            <p class="pt-6 text-xl text-text font-extrabold">Survolez les points du graphique pour découvrir une chanson en détails.</p>

        </div>
        <CardGraph 
            size="big"
            flourishId="14991590"
            title="Evolution de la durée des intros du Billboard Hot 100 (60 secondes ou moins)"
            textContent=""/>

    </section>
       
    <section class="max-w-3xl mx-auto mb-20">
        <Title
            txt="Une recette poussée jusqu’à l’absurde"
            partie={5}
            color="bg-primary"/>
        <div class="max-w-3xl text-text px-4 mx-auto text-lg">
            <p class="pb-4 pt-6">Dans l’industrie musicale, certains en ont même fait une spécialité.
                 Parmi ces «&nbsp;<i>hits makers&nbsp;</i>» il y a Max Martin, un Suédois qui a travaillé pour Katy Perry ou Britney Spears.
                  L’homme n’a pas attendu Spotify pour réduire la longueur des intros. Un titre comme «&nbsp;<i>…Baby One More Time&nbsp;</i>» 
                  (12 secondes d’intro et 3 min 30 de chanson au total en 1998), c’est lui. Même s’il se défend en interview d’avoir des formules prédéfinies, 
                  il semble avoir trouvé la recette du succès. Son nom figure dans pas moins de 25 titres du Billboard Hot 100.</p>
            <p class="pb-4 pt-6">Depuis, d’autres marchent dans ses traces. L’autrice-compositrice-interprète britannique Charli XCX <a href='https://www.theverge.com/2019/9/20/20836846/charli-xcx-new-album-streaming-spotify-dani-deahl-future-of-music' target='_blank' rel=noreferrer>confiait ainsi à The Verge</a> &nbsp;: 
                «&nbsp;<i>Si j’écris une chanson pour un autre grand artiste pop, je veux jouer le grand jeu. Un refrain dans les 30 premières secondes. Pas d'intro étrange et complaisante... 
                Un hook au début de l'intro, peut-être même en commençant par le refrain, le tout en moins de trois minutes&nbsp;</i>». L’artiste a bien compris l’enjeu&nbsp;: 
                «&nbsp;<i>Ce qui compte, c'est de savoir si on a réussi à les capter dans les cinq premières secondes. Et l'ont-ils ajouté à leur liste playlist&nbsp;?&nbsp;</i>»</p>
                <img src="https://rtbfmedia.be/rtbfinfo/spotify_sound/pics/charli_xcx.jpg" alt="charlie XCX">
                <p class="text-sm font-light border-l-4 p-1 mt-1 border-primary rounded-sm">L'artiste Charli XCX à Londres, le 17 septembre 2023 - Dave Benett/Getty Images for MAC Cosmetics</p>
                <p class="pb-4 pt-6">Ne nous faites pas dire ce que nous n’avons pas dit. Non, tous les genres musicaux n’ont pas changé à cause de Spotify. Et tous les artistes présents sur la plate-forme ne se soumettent pas sans discuter au diktat du chronomètre pour plaire au petit rond vert. Certains s’insurgent même. Tel le groupe britannique The Pocket Gods qui a sorti l’an dernier un album de 1000 chansons de 30 secondes intitulé «&nbsp;<i>Nobody makes money anymore&nbsp;</i>» («&nbsp;<i>plus personne ne gagne d’argent aujourd’hui&nbsp;</i>»). </p>
            <p class="pb-4 pt-6">Un album qui résonne comme un pied de nez à Spotify et à sa règle des 30 secondes. Une œuvre d’art unique aussi qui vaudra à ses créateurs déjantés un record au Guinness Book et une rencontre avec un des patrons de Spotify. «&nbsp;<i>Il faut 300 écoutes pour se payer une pinte. Les géants du streaming essayent de nous prendre notre âme, mais ils ne tueront jamais le Rock 'n' Roll&nbsp;</i>» chante en substance le groupe emmené par Mark Christopher Lee dans le premier morceau.
            
                <Quote 
                content="Il faut d'abord être sur quelque chose qui nous plaît"
                color="border-graphicPurple"/>
           
            
                <p class="pb-4 pt-6">Quand on lui demande combien cet album lui a rapporté sur Spotify, Mark Christopher Lee part d’un grand rire. Il évoque le chiffre d’1,6 million de streams pour un revenu total de 300 livres (350 euros environ). «&nbsp;<i>On n’est pas devenu riches avec ça&nbsp;</i>», s’amuse-t-il.</p>
            <p class="pb-4 pt-6">L’artiste que nous avons contacté en profite pour glisser ceci&nbsp;: «&nbsp;<i>On est à blâmer aussi en tant que consommateur parce qu’on veut tout gratuitement. Ce n’est pas juste la grande méchante industrie.&nbsp;</i>» Autant de propos qu'il développe dans un récent documentaire long de trois heures <a href='https://www.youtube.com/watch?v=ZDKGANItoCI' target='_blank' rel=noreferrer>et disponible gratuitement sur YouTube</a>. 
            <p class="pb-4 pt-6 mb-12">Certains musiciens ont beau suivre un même mouvement, seul compte au final le plaisir sur scène et dans les oreilles. «&nbsp;<i>Il faut d'abord être sur quelque chose qui nous plaît, qui nous parle et où il y a vraiment une sensation, il y a un feeling qui se passe. Et puis le format, on voit après, c'est quelque chose qu'on voit ensuite&nbsp;</i>», assure le musicien bruxellois Doowy. «&nbsp;<i>S'il n'y a pas l'émotion dans le morceau, que ce soit un single ou pas un single, s'il n'y a rien qui se passe, vous pouvez faire le plus beau des formats, ça restera un bel emballage, mais vide&nbsp;</i>», conclut l’interprète du tout récent «&nbsp;<i>Premières fois&nbsp;</i>»… qui commence avec 12 secondes d’intro pour se terminer au bout de 2 minutes et 41 secondes. Pile dans les temps.</p>
        </div>
    </section>
   
</div>

