<html>
  <head>
    <title>Fantasy Land Generator</title>
    <script type="text/javascript">
// - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
// this is a completely self-contained random generator,
// implemented in HTML and JavaScript.
//
// to create a new random generator, simply copy this file
// and change the content of the gen_data array.
//
// the primary key of the gen_data array must be named 'main'.
// to increase the number of random things generated at a time,
// increase the number of rows of the output textarea.
//
// written and released to the public domain by drow [drow@bin.sh]
// http://creativecommons.org/publicdomain/zero/1.0/

// - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
// json format
// http://en.wikipedia.org/wiki/JSON

  let gen_data = {};

  gen_data['main'] = [
    '{mainarctic}', '{maindesert}',  '{mainforest}', 
  ];
      
// - - - - - - - - - - F - O - R - E - S - T- - - - - - - - - - - - - - - - - - - - - - - - - - - -

 gen_data['mainforest'] = [
    'This {2d4hexes}-hex forest is known for its {forestadjective} {forestfeature}. Beware, for there are {forestobstacle} that {foresthazard} in the area. It is the land of {forestmonster}, and also {forestmonster}.'
  ];
gen_data['forestbeast'] = [
    'Elks', 'Boars', 'Bears', 'Wolves', 'Bats', 'Centipedes', 'Snakes'
  ];
gen_data['forestadjective'] = [
    'colossal',
    'shady',
    'foggy',
    'riverside',
    'fishing',
    'singing',
    'bushy',
    'muddy',
    'humid',
    'dark',
    'poisonous',
    'forbidden',
    'gloomy',
    'thorny',
    'lush',
    'walled',
    'savage',
    'isolated',
    'turquoise',
    'settled',
    'sweet',
    'green',
    'dewy',
    'clear',
    'hillside',
    'eerie',
    'stormy',
  ];
  gen_data['forestfeature'] = [
    'menhirs',
    'caves',
    'lakes',
    'willows',
    'rapids',
    'trees',
    'pine-trees',
    'shacks',
    'undergrowth',
    'roots',
    'leaves',
    'idols',
    'dead trees',
    'maze',
    'oaks',
    'mine',
    'warrens',
    'firs',
    'ferns',
    'longhouse village',
    'berries',
    'clearings',
    'hot springs',
    'waterfalls',
    'mounds',
    'elven ruins',
    'power stones',
  ];
  gen_data['forestobstacle'] = [
    'ley lines',
    'fallen tree bridges',
    'thick fog walls',
    'willows',
    'rapids',
    'nervous {forestbird}',  
    'patches of dead leaves',  
    'vicious rusty bear traps',  
    'moss patches',  
    'roots',  
    'mushrooms',  
    'pagan idols',  
    'dead trees',  
    'maze-like paths',  
    'sentient trees',  
    'falling trees',  
    'hidden pit traps',  
    'shortcuts',  
    'branches',  
    'sacred {forestbeast}',  
    'aromatic berries',  
    'animal trails',  
    'steam clouds',  
    'waterfalls',  
    'boulders',  
    'elven runes',  
    'strange energies',  
  ];
  gen_data['foresthazard'] = [
    'are crackling with power',
    'are rotting and fragile',
    'can obscure your vision',
    'are full of sticky sap',
    'are treacherous',
    'could distract you',
    'you could sink into',
    'could maim you',
    'could make you slip and fall',
    'are where the light doesn’t reach',
    'are poisonous',
    'could curse you',
    'look like enemies',
    'could make you lost',
    'could hide the path',
    'were placed by lumberjacks',
    'attract Goblins',
    'could split the party',
    'are noisy',
    'are sacred for the locals',
    'could make you hungry',
    'lead to the fey world',
    'are boiling hot',
    'are violent',
    'attract Brigands',
    'could drive you mad',
    'augment magic',
  ];
  gen_data['forestmonster'] = [
    'the Athachs, who {athachculture} {athachproblem}',
    'the {battotem} Bats',
    'the {ahooltotem} Ahools',
    'the {olitiautotem} Olitiaus',
    'the {beartotem} Bears',
    'the {birdtotem} {forestbird}',
    'the {boartotem} Boars',
    'the Calytaurs, who {calytaurculture} {calytaurproblem}',
    'the {centipedetotem} Centipedes',
    'the {blackdracopedetotem} Black Dracopedes',
    'the {greendracopedetotem} Green Dracopedes',
    'a{cult} Cult that {cultwants}',
    'the {deathsheadtotem} Death’s Head Trees',
    'a {greendragontotem} Green Dragon who {greendragonwants}',
    'a Dryad who {dryadwants}',
    'the Hill Dwarves, who {hilldwarfculture} {hilldwarfproblem}',
    'the Goblins, who {goblinculture} {goblinproblem}',
    'a {mutteringsperpantstotem} Muttering Serpent who {mutteringsperpantswants}',
    'the {copperbacktotem} Copperback Snakes',
    'the Warrior Tribe of the {forestbeast} {warriorwants}',
    'the Azizas who {azizawants}',
    'the Centaurs, who {centaurculture} {centaurproblem}',
    'the Steam Elementals, who {steamelementalwants}',
    'the Water Elementals, who {waterelementalwants}',
    'the Ogres, who {ogreculture} {ogreproblem}',
    'the Elven Shadows who {elfshadowwants}',
    'a Sorcerous Cabbal that {sorcererwants}',

  ];

// - - - - - - - - - - D - E - S - E - R - T- - - - - - - - - - - - - - - - - - - - - - - - - - - -

 gen_data['maindesert'] = [
    'This {2d6hexes}-hex desert is known for its {desertadjective} {desertfeature}. Beware, for there are {desertobstacle} that {deserthazard} in the area. It is the land of {desertmonster}, and also {desertmonster}.'
  ];
gen_data['desertbeast'] = [
    'Camels', 'Hyenas', 'Antelopes', 'Basilisks', 'Bats', 'Beetles', 'Vultures', 'Ostriches', 'Centipedes', 'Cats', 'Bloodbeasts', 'Warthogs'
  ];
gen_data['desertadjective'] = [
    'wind-swept',
    'salt',
    'cavernous',
    'acacia-lined',
    'red',
    'war-ravaged',
    'bushy',
    'tepid',
    'marble',
    'aloe-filled',
    'blossoming',
    'rocky',
    'sun-kissed',
    'palm shaded',
    'cracked',
    'dangerous',
    'pastoral',
    'forbidden',
    'cyclopean',
    'coastal',
    'lonely',
    'magmatic',
    'savage',
    'gravel',
    'stormy',
    'giant',
    'settled',
    'muddy',
    'dusty',
    'dinosaur bone',
    'hillside',
  ];
  gen_data['desertfeature'] = [
    'sky shrine',
    'dry lake',
    'canyon',
    'rivulets',
    'holes',
    'old battle site',
    'valley',
    'mud ponds',
    'stadium',
    'haciendas',
    'cacti',
    'crags',
    'mesas',
    'water hole',
    'fissures',
    'rubbles',
    'outbacks',
    'idols',
    'wall',
    'tribeland',
    'pass',
    'sinkholes',
    'warrens',
    'sand shrine',
    'powerstones',
    'war camp',
    'tent villages',
    'puddles',
    'bushes',
    'mud huts',
    'mounds',
  ];
  gen_data['desertobstacle'] = [
    'powerful winds',
    'sulfurous mud pits',
    'steep cliffs',
    'poppies',
    'wasps',
    'dark winds',
    'nervous {desertbird}',  
    'tepid water sources',  
    'sheep herds',  
    'bushes',  
    'cacti',  
    'narrow passages',  
    'paths',  
    'heat pockets',  
    'shadowy cracks',  
    'loose stones',  
    'bird sounds',  
    'pagan idols',  
    'high walls',  
    'tremors',  
    'mirages',  
    'eruptions',  
    'hidden pit traps',  
    'gravel pits',  
    'wild energies',  
    'war horns',  
    'sacred {desertbeast}',  
    'mud puddles',  
    'tiny flies',  
    'snare traps',  
    'rockfalls',  
  ];
  gen_data['deserthazard'] = [
    'could make you fall',
    'are corrosive',
    'require equipment to cross',
    'are hallucinogenic',
    'attract Vyderacs',
    'are frightening',
    'could distract you',
    'could make you waste rations',
    'could get in your way',
    'are poisonous',
    'hide sharp needles',
    'hide ambushers',
    'are near precipices',
    'could dehydrate you',
    'shelter insects',
    'could make you trip',
    'could provoke a stampede',
    'could curse you',
    'could block your path',
    'attract giant Wurms',
    'could make you lost',
    'make the earth split',
    'attract Goblins',
    'could make you sink',
    'augment magic',
    'attract Scouts riding {desertbeast}',
    'are sacred for the locals',
    'could trap you',
    'can make you itchy',
    'set up by lizard people',
    'could crush you',
  ];
  gen_data['desertmonster'] = [
    'the Airwalkers, who {airwalkerwants}',
    'the {basilisktotem} Basilisks',
    'the {battotem} Bats',
    'the {olitiautotem} Olitiaus',
    'the {vyderactotem} Vyderacs',
    'the Bestial Terrors, who {bestialterrorwants}',
    'the {birdtotem} {desertbird}',
    'the {boltforagertotem} Boltforagers',
    'the Cacuses, who {cacusculture} {cacusproblem}',
    'the Cadejos, who {cadejowants}',
    'the {cactuscattotem} Cactus Cat',
    'the {sabertoothcattotem} Sabertooth Cats',
    'the {gianttressymtotem} Giant Tressym',
    'the Centaurs, who {centaurculture} {centaurproblem}',
    'the {centipedetotem} Centipedes',
    'the {blackdracopedetotem} Black Dracopedes',
    'the Chevalls, who {chevallwants}',
    'a{cult} Cult that {cultwants}',
    'the Cyclops, who {cyclopsculture} {cyclopsproblem}',
    'the Cyclopskins, who {cyclopskinculture} {cyclopskinproblem}',
    'a Donestre who {donestrewants}, yet {donestredo}',
    'a {redragontotem} Red Dragon who {redragonwants}',
    'the Goblins, who {goblinculture} {goblinproblem}',
    'the Earth Mephits, who {earthmephitwants}',
    'a Sorcerous Cabbal that {sorcererwants}',
    'the Great Horde and their giant War {desertbeast}',
    'the Warrior Tribe of the {desertbeast} {warriorwants}',
    'the {bloodbeasttotem} Bloodbeasts',
    'the {boartotem} Warthogs',
    'the Lizardfolks, who {lizardfolkculture} {lizardfolkproblem}',
    'the Ogres, who {ogreculture} {ogreproblem}',
  ];

// - - - - - - - - - - A - R - C - T - I - C- - - - - - - - - - - - - - - - - - - - - - - - - - - -
      
gen_data['mainarctic'] = [
    'This {2d6hexes}-hex cold region is known for its {arcticadjective} {arcticfeature}. Beware, for there are {arcticobstacle} that {arctichazard} in the area. It is the land of {arcticmonster}, and also {arcticmonster}.'
  ];
gen_data['arcticbeast'] = [
    'Elks', 'Yaks', 'Bears', 'Penguins', 'Wolves', 'Mammoths', 'Whooly Rhinos', 'Seals', 'Boars', 'Arassas', 'Ravens', 'Seagulls', 'Sabertooth Cats', 'Dracopedes',  'Geese',
  ];
gen_data['arcticadjective'] = [
    'wind-swept',
    'ice-covered',
    'mist-cloaked',
    'snow',
    'vast',
    'snowy',
    'war-ravaged',
    'coastal',
    'fir-lined',
    'isolated',
    'sinuous',
    'lichen-covered',
    'icicle-toothed',
    'forbidden',
    'cyclopean',
    'cold water',
    'fortified',
    'steaming',
    'savage',
    'stormy',
    'giant',
    'settled',
    'hillside',
    'fishing',
    'slushy',
  ];
  gen_data['arcticfeature'] = [
    'sky shrine',
    'crags',
    'loch',
    'caves',
    'plateaus',
    'floe',
    'old battle site',
    'bird colonies',
    'taiga',
    'tavern',
    'canyon',
    'tundra',
    'tunnels',
    'idols',
    'wall',
    'tribelands',
    'brewery',
    'hot springs',
    'warrens',
    'power stones',
    'war camp',
    'yurt villages',
    'mounds',
    'strait',
    'shacks',
  ];
  gen_data['arcticobstacle'] = [
    'powerful winds',
    'ice bridges',
    'ley lines',  
    'blizzards',  
    'ledges',  
    'snowy surfaces',  
    'dark winds',  
    'nervous {arcticbird}',  
    'snowfalls',  
    'steep slopes',
    'narrow passages',
    'Elk herds',
    'sharp icicles',
    'pagan idols',
    'big walls',
    'thunderstorms',
    'rope bridges',
    'steam vents',
    'hidden pit traps',
    'wild energies',
    'war horns',
    'sacred {arcticbeast}',
    'rockfalls',
    'giant nests',
    'vicious rusty bear traps',  
  ];
  gen_data['arctichazard'] = [
    'could make you fall',
    'are unstable',
    'are crackling with power',
    'slow travels',
    'are near high cliffs',
    'create bright glares',
    'are frightening',
    'could distract you',
    'fall suddenly',
    'could make you slip',
    'hide ambushers',
    'could provoke a stampede',
    'could pierce you',
    'could curse you',
    'could block your path',
    'are deafening',
    'require balance to navigate',
    'burn your skin',
    'attract goblins',
    'augment magic',
    'attract Scouts riding {arcticbeast}',
    'are sacred for the locals',
    'could crush you',
    'near the sea',
    'could maim you',
  ];
  gen_data['arcticmonster'] = [
    'the Airwalkers, who {airwalkerwants}',
    'the {arassastotem} Arassas',
    'the Athachs, who {athachculture} {athachproblem}',
    'the {arcticbattotem} Arctic Bats',
    'the {cavebeartotem} Cave Bears',
    'the {polarbeartotem} Polar Bears',
    'the Bestial Terrors, who {bestialterrorwants}',
    'the {birdtotem} {arcticbird}',
    'the {boartotem} Boars',
    'the Cadejos, who {cadejowants}',
    'the {sabertoothcattotem} Sabertooth Cats',
    'the Centaurs, who {centaurculture} {centaurproblem}',
    'the {bluedracopedetotem} Blue Dracopedes',
    'a{cult} Cult that {cultwants}',
    'the Cyclops, who {cyclopsculture} {cyclopsproblem}',
    'the Cyclopskins, who {cyclopskinculture} {cyclopskinproblem}',
    'the Hill Dwarves, who {hilldwarfculture} {hilldwarfproblem}',
    'the Steam Elementals, who {steamelementalwants}',
    'the Goblins, who {goblinculture} {goblinproblem}',
    'a Sorcerous Cabbal that {sorcererwants}',
    'the Great Horde and their giant War {arcticbeast}',
    'the Warrior Tribe of the {arcticbeast} {warriorwants}',
    'the Ogres, who {ogreculture} {ogreproblem}',
    'the {pelicantotem} Giant Pelicans',
    'the Calytaurs, who {calytaurculture} {calytaurproblem}',
  ];
      
// - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -    
      
   gen_data['2d4hexes'] = {
    '01-06': 'two',
    '07-19': 'three',
    '20-38': 'four',
    '39-63': 'five',
    '64-81': 'six',
    '82-94': 'seven',
    '95-00': 'eight',
  };
   gen_data['2d6hexes'] = {
    '01-03': 'two',
    '04-08': 'three',
    '09-17': 'four',
    '18-28': 'five',
    '29-42': 'six',
    '43-58': 'seven',
    '59-72': 'eight',
    '73-83': 'nine',
    '84-92': 'ten',
    '93-97': 'eleven',
    '98-00': 'twelve'
  };      
  gen_data['cult'] = [
    ' Fey', 'n Elemental', ' Demonic', 'n Ancient', 'n Eldritch', ' Death', ' Drug',
  ];
      
// - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -      
      
  gen_data['airwalkerwants'] = [
    'guide free souls to the plane of air',
    'teach sky dancing',
    'rob travelers and hide in the plane of air',
    'offer training to whoever can race them',
    'recently arrived here with a mysterious old woman',
    'are fleeing a natural disaster',
  ];
  gen_data['arassastotem'] = [
    'elusive',
    'furious',
    'blizzard-calling',
    'royal',
    'strong',
    'sacred',
  ];
  gen_data['athachculture'] = [
    'follow ley lines to the birthplace of the world',
    'herd sheep',
    'grow iron fruits',
    'practice rituals to provoke a new geological era',
    'violently protect the secrets of the druids',
    'ask tribute for safe passage',
  ];
  gen_data['athachproblem'] = [
    'under the guidance of the stars',
    'by feeding gems to a giant Earth Elemental',
    'under the cover of fog',
    'while being manipulated by fairies',
    'and build palaces of moss',
    'and love human flesh',
  ];
   gen_data['arcticbattotem'] = [
    'night-bringing',
    'snowy',
    'ominous',
    'food-preserving',
    'fluffy',
    'sacred',
  ];
   gen_data['cavebeartotem'] = [
    'strong',
    'thunderous',
    'giant',
    'cold-loving',
    'motherly',
    'sacred',
  ];
   gen_data['polarbeartotem'] = [
    'strong',
    'patient',
    'star-favored',
    'cold-loving',
    'motherly',
    'sacred',
  ];
  gen_data['bestialterrorwants'] = [
    'drag souls to the underworld every full moon',
    'reenact a famous battle every night',
    'refuse to acknowledge peace',
    'kill for their demon overlord',
    'are hunting the bearer of a famous weapon',
    'seek a traitor from the last war',
  ];  
   gen_data['birdtotem'] = [
    'singing',
    'migrating',
    'peaceful',
    'diurnal',
    'romantic',
    'sacred',
  ];  
   gen_data['arcticbird'] = [
    'Pinguins',
    'Crows',
    'Geese',
    'Seagulls',
  ];
   gen_data['desertbird'] = [
    'Starlings',
    'Vultures',
    'Casowaries',
    'Hawks',
  ];
   gen_data['forestbird'] = [
    'Sparrows',
    'Crows',
    'Magpies',
    'Songbirds',
  ];
   gen_data['boartotem'] = [
    'stubborn',
    'dirty',
    'delicious',
    'joyful',
    'sniffing',
    'sacred',
  ];
   gen_data['cacusculture'] = [
    'live on the edge of settlements',
    'control all the cattle',
    'train promising athletes',
    'lead a famous crime family',
    'are oil wrestling champions',
    'produce the best oil',
  ];  
   gen_data['cacusproblem'] = [
    'and steal from the locals in total impunity',
    'because they are favored by a god',
    'and are rumoured to hide a runaway noble',
    'to prepare for a big competition',
    'because of their silver tongue',
    'and whose land is considered neutral',
  ];  
   gen_data['cadejowants'] = [
    'lead drunkards to their death',
    'guide ghosts to parties',
    'guide travelers to a nearby inn',
    'protect a passage to the land of the dead',
    'can only be seen when drunk',
    'kill the blissful and protect the weary',
  ]; 
   gen_data['sabertoothcattotem'] = [
    'brave',
    'raging',
    'brooding',
    'pack-hunting',
    'royal',
    'sacred',
  ]; 
   gen_data['centaurculture'] = [
    'migrate with giant herds guided by the stars',
    'live off raiding and pillaging',
    'founded an academy for heroes',
    'joined the great horde',
    'coexist with Elves',
    'quest as knight errants',
  ];
   gen_data['centaurproblem'] = [
    'and for whom metal is blasphemous',
    'half of the year, and disappear in the fey world during the other half',
    'lest they turn into horses',
    'under the leadership of a Chevall',
    'after the collapse of their civilization',
    'and despise settlers',
  ]; 
   gen_data['bluedracopedetotem'] = [
    'draconic',
    'elemental',
    'winter-loving',
    'shy',
    'sheltered',
    'sacred',
  ]; 
   gen_data['cultwants'] = [
    'performs sacrifices for their patron',
    'agressively seeks more members',
    'hunts rare materials for a ritual',
    'sells weird trinkets',
    'murders those who know too much',
    'puts bounties on ex members',
  ]; 
   gen_data['cyclopsculture'] = [
    'live peacefully with their sheep',
    'herald the collapse of civilization',
    'hate the gods',
    'joined the great horde',
    'built the biggest {cyclopsstructure} of the world',
    'are feral',
  ]; 
   gen_data['cyclopsstructure'] = [
    'wall', 'fortress', 'maze', 'mill',
  ];
   gen_data['cyclopsproblem'] = [
    'and are actually good intended',
    'because the gods can see through their eyes',
    'and are worshiped by Orcs',
    'and take nothing seriously',
    'guided by their mountain-sized leader',
    'and are hunted by humans because of it',
  ];  
   gen_data['cyclopskinculture'] = [
    'live in caves',
    'live on rafts',
    'live as the upper caste among Orcs',
    'joined the great horde',
    'ride dinosaurs',
    'tend to a primeval temple',
  ];  
   gen_data['cyclopskinproblem'] = [
    'and are afraid of the sky and birds',
    'because they are half-elves',
    'because they are half-orcs',
    'because they see all humanoids as rivals',
    'guided by their mountain-sized Cyclops leader',
    'guided by their Beholder tyrant',
  ];  
   gen_data['hilldwarfculture'] = [
    'recently moved in to prospect',
    'run a big foundry',
    'run a a legendary brewery',
    'live in an old mine',
    'are part of an archeological expedition',
    'are roaming monster slayers',
  ];  
   gen_data['hilldwarfproblem'] = [
    'while drunk',
    'because they are exiles from the mountains',
    'hoping to retake their ancestral clanland',
    'and war against the fey',
    'and ride goats and dogs',
    'and worship a giant Earth Elemental',
  ];  
   gen_data['steamelementalwants'] = [
    'want the world covered in permanent fog',
    'protect a magical steam vent',
    'fight the winds',
    'fight the heat',
    'fight the rocks',
    'wish to return to the water plane',
  ];  
   gen_data['goblinculture'] = [
    'live in the trash pits of another civilization',
    'hide in tunnels',
    'hide their huts high in trees',
    'joined the great horde',
    'serve the Hobgoblin legion',
    'are enslaved',
  ];  
   gen_data['goblinproblem'] = [
    'because they fear daylight',
    'and are organized like the mob',
    'because their leader died',
    'because they are plagued by a Niblog',
    'because they are hunted by monsters',
    'with Hobgoblins and Bugbears',
  ];
   gen_data['sorcererwants'] = [
    'crave endless power',
    'hide among normal people',
    'transcended to another state of being',
    'agressively fight all trespassers',
    'hunt down those who persecuted them',
    'pursue sensory pleasures',
  ];  
   gen_data['warriorwants'] = [
    'who brutally conquered the region',
    'who are known for their craftsmanship',
    'who dress like animals',
    'that joined the great horde',
    'who are trying to find their ancestral home',
    'that protects the region',
  ];  
   gen_data['ogreculture'] = [
    'took over a castle',
    'joined the great horde',
    'grow giant vegetables in a secret farm',
    'live in huts in the outskirts of towns',
    'manage a gigantic inn',
    'joined a brigand group',
  ];  
   gen_data['ogreproblem'] = [
    'and are rumored to be local babies abducted by Hags',
    'with the help of leaderʼs magical item',
    'to search for a mythical recipe',
    'with Goblins as their intellectual leaders',
    'and live like kings',
    'and are actually pretty sweet',
  ]; 
   gen_data['basilisktotem'] = [
    'deadly',
    'humidity-hating',
    'mineral',
    'hypnotizing',
    'petrifying',
    'sacred',
  ];
   gen_data['battotem'] = [
    'nocturnal',
    'vampiric',
    'ominous',
    'medicinal',
    'frightening',
    'sacred',
  ];  
   gen_data['olitiautotem'] = [
    'deadly',
    'frightening',
    'kissing',
    'river-nesting',
    'nocturnal',
    'cursed',
  ];  
   gen_data['vyderactotem'] = [
    'matriarcal',
    'clumsy',
    'dancing',
    'swarming',
    'blood-drinking',
    'cursed',
  ]; 
   gen_data['boltforagertotem'] = [
    'sickly',
    'sunset-colored',
    'matutinal',
    'deadly',
    'repulsive',
    'cursed',
  ];  
   gen_data['cactuscattotem'] = [
    'sun-loving',
    'plant-dwelling',
    'dreamy',
    'drunken',
    'witchy',
    'sacred',
  ]; 
   gen_data['gianttressymtotem'] = [
    'wise',
    'feline',
    'regal',
    'flying',
    'sun-loving',
    'sacred',
  ];  
   gen_data['centipedetotem'] = [
    'deadly',
    'scavenging',
    'nightmarish',
    'medicinal',
    'earthy',
    'taboo',
  ]; 
   gen_data['blackdracopedetotem'] = [
    'draconic',
    'primeval',
    'venomous',
    'shy',
    'shade-loving',
    'sacred',
  ]; 
   gen_data['chevallwants'] = [
    'try to free all domesticated horses',
    'test the bonds between riders and mounts',
    'herd wild horses to the dream world',
    'kidnap horse-loving kids to transform them into chevalls',
    'hunger for a rare fruit',
    'give rides to an archfeyʼs ball',
  ]; 
   gen_data['donestrewants'] = [
    'wants to be accepted by the locals',
    'longs for a gift',
    'is scared to sleep alone',
    'needs advices on friendship',
    'wants travel companions',
    'has food to share',
  ];  
   gen_data['donestredo'] = [
    'eats people alive',
    'beats strangers to a pulp',
    'collects decapitated heads',
    'poisons people',
    'drowns people',
    'kills people in their sleep',
  ];  
   gen_data['redragontotem'] = [
    'treasure-hoarding',
    'cataclysmic',
    'tyranic',
    'metal-melting',
    'powerful',
    'sacred',
  ]; 
   gen_data['redragonwants'] = [
    'had its treasure stolen',
    'rules the area',
    'demands virginal sacrifices',
    'searches for a long lost dwarven hold',
    'wants a legendary artefact',
    'is worshipped like a god',
  ];  
   gen_data['earthmephitwants'] = [
    'deliver messages from their Earth Elemental master',
    'have complex aristocratic pedigrees',
    'need to cover the region in earth before the arrival of their master',
    'are hiding from their autoritative master back in the plane of earth',
    'recently spawned from the ground',
    'are gathering information for their stoic master',
  ];  
   gen_data['ahooltotem'] = [
    'nocturnal',
    'child-stealing',
    'sneaky',
    'dog-mimicking',
    'terrifying',
    'sacred',
  ];  
   gen_data['beartotem'] = [
    'burly',
    'lazy',
    'honey',
    'hibernating',
    'motherly',
    'sacred',
  ];
   gen_data['calytaurculture'] = [
    'ritually soil beautiful things',
    'lead a fertility cult',
    'hate all the gods',
    'are known for their cuisine',
    'roam the wilderness',
    'avoid strangers like plague',
  ];  
   gen_data['calytaurproblem'] = [
    'under the leardership a Cambion Pig',
    'and make charcuterie from human flesh',
    'because they want to summon a Nalfeshnee',
    'and were once humans',
    'and steal human babies',
    'and obsessed with hygiene',
  ]; 
   gen_data['greendracopedetotem'] = [
    'draconic',
    'primeval',
    'acidic',
    'shy',
    'humidity-loving',
    'sacred',
  ];  
   gen_data['deathsheadtotem'] = [
    'grieving',
    'ancestral',
    'secret-whispering',
    'tragic',
    'taboo',
    'holy',
  ]; 
   gen_data['greendragontotem'] = [
    'deadly',
    'forest-dwelling',
    'witchy',
    'suave',
    'dreaming',
    'worshipped',
  ]; 
   gen_data['greendragonwants'] = [
    'collects humanoids as pets',
    'plots against a rival',
    'hasn’t been invited to a noble’s wedding',
    'hates the Elves',
    'sleepwalks',
    'has discovered the agro-industrial potential of its poisonous breath',
  ];  
   gen_data['dryadwants'] = [
    'wants a human slave for every tree cut',
    'wars against the community encroaching her woods',
    'wants to regrow the forest',
    'longs for love',
    'is mustering an army of beasts',
    'shelters wounded animals',
  ]; 
   gen_data['mutteringsperpantstotem'] = [
    'contrarian',
    'half-real',
    'manipulative',
    'lonely',
    'taboo',
    'venerated',
  ]; 
   gen_data['mutteringsperpantswants'] = [
    'goads people into making bad decisions',
    'is removing all traces of its existence',
    'is behind a Cult of doubters',
    'needs adventurer to kill a rival',
    'loves to undermine confidence',
    'will reward the doubtless',
  ];  
   gen_data['copperbacktotem'] = [
    'sleep-inducing',
    'dancing',
    'metallic',
    'peaceful',
    'precise',
    'sacred',
  ]; 
   gen_data['azizawants'] = [
    'feed travelers for fear of being eaten themselves',
    'grow fruits with faces',
    'channel sunlight into magical fruits',
    'ride Giant Bees to pollenise giant flowers',
    'are addicted to powdered luck',
    'protect a giant fruit',
  ];
   gen_data['pelicantotem'] = [
    'marine',
    'gluttonous',
    'fishing',
    'dumb',
    'migrating',
    'sacred',
  ];
   gen_data['bloodbeasttotem'] = [
    'medicinal',
    'sucking',
    'filthy',
    'vampiric',
    'nightmarish',
    'cursed',
  ]; 
   gen_data['waterelementalwants'] = [
    'want to submerge the area',
    'protect a sacred source',
    'fight the sky',
    'fight forest fires',
    'dig out the earth',
    'want to return to the plane of water',
  ]; 
   gen_data['lizardfolkculture'] = [
    'carry in woven portable houses',
    'live in caves only accessible underwater',
    'inhabit ancient ruined pyramids',
    'live in the sewers of another civilization',
    'live atop Giant Tortoises',
    'settled the edges of a bottomless pit',
  ]; 
   gen_data['lizardfolkproblem'] = [
    'and believe the apocalypse can be delayed by sacrificing humans',
    'and herd dinosaurs',
    'and worship a titanic lizard',
    'because they are only here for their coming of age journey',
    'with their advanced technology',
    'and worship a demon in disguise',
  ]; 
   gen_data['elfshadowwants'] = [
    'despair to weild magic again',
    'are in eternal agony',
    'long to experience the pleasure of flesh again',
    'long to be freed from their torment',
    'wish to finish the dark ritual that cursed them',
    'serve a demon of lust',
  ]; 
// - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    </script>
  </head>
  <body>
    
  <h1>{{ page.title }}</h1>
    <h1>Fantasy Land Generator</h1>
  
    <p><textarea id="output" cols="90" rows="4" readonly></textarea></p>
    <p><input type="button" value="Generate" onclick="more_random();" /></p>
    <script src="data:text/javascript;base64,Ly8gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtIC0gLSAtCi8vIHJhbmRvbS5qcwovLwovLyB3cml0dGVuIGFuZCByZWxlYXNlZCB0byB0aGUgcHVibGljIGRvbWFpbiBieSBkcm93IDxkcm93QGJpbi5zaD4KLy8gaHR0cDovL2NyZWF0aXZlY29tbW9ucy5vcmcvcHVibGljZG9tYWluL3plcm8vMS4wLwoKJ3VzZSBzdHJpY3QnOwpmdW5jdGlvbiBtb3JlX3JhbmRvbSgpCgl7bGV0IGE9ZG9jdW1lbnQuZ2V0RWxlbWVudEJ5SWQoIm91dHB1dCIpOwoJdmFyIGI9MQoJYj1nZW5lcmF0ZV9saXN0KCJtYWluIixiKTsKCWEudmFsdWU9Yi5qb2luKCJcbiIpfQpmdW5jdGlvbiBnZW5lcmF0ZV90ZXh0KGEpe2lmKGE9Z2VuX2RhdGFbYV0paWYoYT1zZWxlY3RfZnJvbShhKSlyZXR1cm4gZXhwYW5kX3Rva2VucyhhKTtyZXR1cm4iIn0KZnVuY3Rpb24gZ2VuZXJhdGVfbGlzdChhLGIpe2xldCBjPVtdLGQ7Zm9yKGQ9MDtkPGI7ZCsrKWMucHVzaChnZW5lcmF0ZV90ZXh0KGEpKTtyZXR1cm4gY30KZnVuY3Rpb24gc2VsZWN0X2Zyb20oYSl7cmV0dXJuIGEuY29uc3RydWN0b3I9PUFycmF5P3NlbGVjdF9mcm9tX2FycmF5KGEpOnNlbGVjdF9mcm9tX3RhYmxlKGEpfQpmdW5jdGlvbiBzZWxlY3RfZnJvbV9hcnJheShhKXtyZXR1cm4gYVtNYXRoLmZsb29yKE1hdGgucmFuZG9tKCkqYS5sZW5ndGgpXX0KZnVuY3Rpb24gc2VsZWN0X2Zyb21fdGFibGUoYSl7dmFyIGI7aWYoYj1zY2FsZV90YWJsZShhKSl7Yj1NYXRoLmZsb29yKE1hdGgucmFuZG9tKCkqYikrMTtsZXQgYztmb3IoYyBpbiBhKXtsZXQgZD1rZXlfcmFuZ2UoYyk7aWYoYj49ZFswXSYmYjw9ZFsxXSlyZXR1cm4gYVtjXX19cmV0dXJuIiJ9CmZ1bmN0aW9uIHNjYWxlX3RhYmxlKGEpe2xldCBiPTAsYztmb3IoYyBpbiBhKWE9a2V5X3JhbmdlKGMpLGFbMV0+YiYmKGI9YVsxXSk7cmV0dXJuIGJ9CmZ1bmN0aW9uIGtleV9yYW5nZShhKXtsZXQgYjtyZXR1cm4oYj0vKFxkKyktMDAvLmV4ZWMoYSkpP1twYXJzZUludChiWzFdKSwxMDBdOihiPS8oXGQrKS0oXGQrKS8uZXhlYyhhKSk/W3BhcnNlSW50KGJbMV0pLHBhcnNlSW50KGJbMl0pXToiMDAiPT1hP1sxMDAsMTAwXTpbcGFyc2VJbnQoYSkscGFyc2VJbnQoYSldfQpmdW5jdGlvbiBleHBhbmRfdG9rZW5zKGEpe2Zvcih2YXIgYjtiPS97KFx3Kyl9Ly5leGVjKGEpOyl7Yj1iWzFdO2xldCBjO2E9KGM9Z2VuZXJhdGVfdGV4dChiKSk/YS5yZXBsYWNlKCJ7IitiKyJ9IixjKTphLnJlcGxhY2UoInsiK2IrIn0iLGIpfXJldHVybiBhfQptb3JlX3JhbmRvbSgpOw=="></script>
 
    <br>
    <br>
    The lands are generated using these monster lists:<br>
    <ol>
    <li><a href="https://saltygoo.github.io/list/arctic">Cold climate monster list</a></li>
    <li><a href="https://saltygoo.github.io/list/desert">Desert climate monster list</a></li>
    <li><a href="https://saltygoo.github.io/list/forest">Forest climate monster list</a></li>
    </ol>
    </body>
</html>
