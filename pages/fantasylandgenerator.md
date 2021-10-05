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
    'This {2d6hexes}-hex desert is known for its {desertadjective} {desertfeature}. Beware, for there are {desertobstacle} that {deserthazard} in the area. It is the land of {desertmonster}, and also {desertmonster}.'
  ];
      
// - - - - - - - - - - D - E - S - E - R - T- - - - - - - - - - - - - - - - - - - - - - - - - - - -

gen_data['cesertbeast'] = [
    'Camels', 'Hyenas',  'Antelopes'
  ];
gen_data['desertadjective'] = [
    'wind-swept',
  ];
  gen_data['desertfeature'] = [
    'sky shrine',
  ];
  gen_data['desertobstacle'] = [
    'powerful winds',
  ];
  gen_data['deserthazard'] = [
    'could make you fall',
  ];
  gen_data['desertmonster'] = [
    'the Airwalkers, who {airwalkerwants}',
  ];

// - - - - - - - - - - A - R - C - T - I - C- - - - - - - - - - - - - - - - - - - - - - - - - - - -
      
gen_data['mainArctic'] = [
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
    'pastoral',
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
    'hovels',
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
    'Yak herds',
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
  ];
  gen_data['arctichazard'] = [
    'could make you fall',
    'could crumble',
    'are crackling with power',
    'slow travels',
    'are near high cliffs',
    'create bright glares',
    'are frightening',
    'could distract you',
    'fall suddenly',
    'get in your way',
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
    'attract {arcticBeast} riders',
    'are worshiped by the locals',
    'could crush you',
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
    'the Cacuses, who {cacusculture} {cacusproblem}',
    'the Cadejos, who {cadejowants}',
    'the {sabertoothcattotem} Sabertooth Cats',
    'the Centaurs, who {centaurculture} {centaurproblem}',
    'the {bluedracopedetotem} Blue Dracopedes',
    'a{cult} Cult that {cultwants}',
    'the Cyclops, who {cyclopsculture} {cyclopsproblem}',
    'the Cyclopskin, who {cyclopskinculture} {cyclopskinproblem}',
    'the Hill Dwarves, who {hilldwarfculture} {hilldwarfproblem}',
    'the Steam Elementals, who {steamelementalwants}',
    'the Goblins, who {goblinculture} {goblinproblem}',
    'a Sorcerous Cabbal that {sorcererwants}',
    'a Great Horde and their giant War {arcticBeast}',
    'a Warrior Clan {warriorwants}',
    'the Ogres, who {ogreculture} {ogreproblem}',

  ];
      
// - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -    
      
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
    'guide travelers to the closest inn',
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
    'run an academy for heroes',
    'joined the great horde',
    'coexist with the elves',
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
    'perform sacrifices for their patron',
    'agressively seek more members',
    'hunt rare materials for a ritual',
    'sell weird trinkets',
    'murder those who know too much',
    'put bounties on ex members',
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
    'are enslaved workers',
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
    'crave more power',
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
    'that protect the region',
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
    1. <a href="https://saltygoo.github.io/list/arctic">Cold climate monster list</a>

    </body>
</html>
