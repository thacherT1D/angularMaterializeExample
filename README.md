##Adding Materialize to Angular

Assuming that you already have a working knowledge of javascript and Angular 1 -- this document will walk you through setting up a basic angular app with the angular-materialize directive based on Materialize CSS.

The styling in this example is very light, but it is setup to add any functional angular-materialize components.

Materialize and angular-materialize are very similar, but not exactly the same -- there are things that work in materialize and not in angular-materialize. The most recent documentation on what works or doesn't is available in the [angular-materialize directive docs](http://krescruz.github.io/angular-materialize/#!)

To view this demo project on your computer:
* clone this repo (fork if you like)
* cd into the folder
* run `python -m SimpleHTTPServer 8000`
* go to `http://localhost:8000/#/` in your browser

Using a simple app structure:
-- index.html
-- app.js
-- style.css

**Outline of an index.html file**

`<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <!-- Materialize CSS -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.6/css/materialize.min.css">
  <!-- Add your own CSS in this file -->
  <link rel="stylesheet" href="style.css">
  <title></title>
</head>
<body>
  <div ng-app="app">
    <nav>
      <div class="blue darken-3 nav-wrapper">
        <a href="#" class="brand-logo"></a>
        <ul id="nav-mobile" class="right">
          <li><a ui-sref="home">Home</a></li>
          <li><a ui-sref="about">About</a></li>
          <li><a ui-sref="user.profile">User</a></li>
        </ul>
      </div>
    </nav>
    <div class="container">
      <h2>A page Using Materialize</h2>
      <p>Below are a few of the available materialize css features for display.</p>
      <div class="container">
        <div class="slider" slider>
          <ul class="slides">
            <li>
              <img src="http://lorempixel.com/580/250/nature/1"> <!-- random image -->
              <div class="caption center-align">
                <h3>This is our big Tagline!</h3>
                <h5 class="light grey-text text-lighten-3">Here's our small slogan.</h5>
              </div>
            </li>
            <li>
              <img src="http://lorempixel.com/580/250/nature/2"> <!-- random image -->
              <div class="caption left-align">
                <h3>Left Aligned Caption</h3>
                <h5 class="light grey-text text-lighten-3">Here's our small slogan.</h5>
              </div>
            </li>
            <li>
              <img src="http://lorempixel.com/580/250/nature/3"> <!-- random image -->
              <div class="caption right-align">
                <h3>Right Aligned Caption</h3>
                <h5 class="light grey-text text-lighten-3">Here's our small slogan.</h5>
              </div>
            </li>
            <li>
              <img src="http://lorempixel.com/580/250/nature/4"> <!-- random image -->
              <div class="caption center-align">
                <h3>This is our big Tagline!</h3>
                <h5 class="light grey-text text-lighten-3">Here's our small slogan.</h5>
              </div>
            </li>
          </ul>
        </div>
      </div>
      <div class="container">
        <div input-field>
          <input type="text" ng-model="dummyInputs.inputFieldInput" length="150">
          <label>Input label</label>
        </div>
      </div>
      <div class="container">
        <p>
          Prefect’s bathroom Trelawney veela squashy armchairs, SPEW: Gamp’s Elemental Law of Transfiguration. Magic Nagini bezoar, Hippogriffs Headless Hunt giant squid petrified. Beuxbatons flying half-blood revision schedule, Great Hall aurors Minerva McGonagall Polyjuice Potion. Restricted section the Burrow Wronski Feint gnomes, quidditch robes detention, chocolate frogs. Errol parchment knickerbocker glory Avada Kedavra Shell Cottage beaded bag portrait vulture-hat. Twin cores, Aragog crimson gargoyles, Room of Requirement counter-clockwise Shrieking Shack. Snivellus second floor bathrooms vanishing cabinet Wizard Chess, are you a witch or not?
        </p>
      </div>

      <div class="container">
        <div nouislider ng-model="value" min="5" max="300"></div>
      </div>
      <div>
        <div class="container">
          <div class="row">
            <div class="col s12">
              <ul tabs reload="allTabContentLoaded">
                <li class="tab col s3"><a href="#test1">Test 1</a></li>
                <li class="tab col s3"><a class="active" href="#test2">Test 2</a></li>
                <li class="tab col s3"><a href="#test3">Test 3</a></li>
                <li class="tab col s3"><a href="#test4">Test 4</a></li>
              </ul>
            </div>
          </div>
        </div>
        <div class="container">
          <div class="row">

            <div id="test1" class="col s12">Thestral dirigible plums, Viktor Krum hexed memory charm Animagus Invisibility Cloak three-headed Dog. Half-Blood Prince Invisibility Cloak cauldron cakes, hiya Harry! Basilisk venom Umbridge swiveling blue eye Levicorpus, nitwit blubber oddment tweak. Chasers Winky quills The Boy Who Lived bat spleens cupboard under the stairs flying motorcycle. Sirius Black Holyhead Harpies, you’ve got dirt on your nose. Floating candles Sir Cadogan The Sight three hoops disciplinary hearing. Grindlewald pig’s tail Sorcerer's Stone biting teacup. Side-along dragon-scale suits Filch 20 points, Mr. Potter.</div>
            <div id="test2" class="col s12">Squashy armchairs dirt on your nose brass scales crush the Sopophorous bean with flat side of silver dagger, releases juice better than cutting. Full moon Whomping Willow three turns should do it lemon drops. Locomotor trunks owl treats that will be 50 points, Mr. Potter. Witch Weekly, he will rise again and he will come for us, headmaster Erumpent horn. Fenrir Grayback horseless carriages ‘zis is a chance many would die for!</div>
            <div id="test3" class="col s12">Alohamora wand elf parchment, Wingardium Leviosa hippogriff, house dementors betrayal. Holly, Snape centaur portkey ghost Hermione spell bezoar Scabbers. Peruvian-Night-Powder werewolf, Dobby pear-tickle half-moon-glasses, Knight-Bus. Padfoot snargaluff seeker: Hagrid broomstick mischief managed. Snitch Fluffy rock-cake, 9 ¾ dress robes I must not tell lies. Mudbloods yew pumpkin juice phials Ravenclaw’s Diadem 10 galleons Thieves Downfall. Ministry-of-Magic mimubulus mimbletonia Pigwidgeon knut phoenix feather other minister Azkaban. Hedwig Daily Prophet treacle tart full-moon Ollivanders You-Know-Who cursed. Fawkes maze raw-steak Voldemort Goblin Wars snitch Forbidden forest grindylows wool socks.</div>
            <div id="test4" class="col s12">Red hair crookshanks bludger Marauder’s Map Prongs sunshine daisies butter mellow Ludo Bagman. Beaters gobbledegook N.E.W.T., Honeydukes eriseD inferi Wormtail. Mistletoe dungeons Parseltongue Eeylops Owl Emporium expecto patronum floo powder duel. Gillyweed portkey, keeper Godric’s Hollow telescope, splinched fire-whisky silver Leprechaun O.W.L. stroke the spine. Chalice Hungarian Horntail, catherine wheels Essence of Dittany Gringotts Harry Potter. Prophecies Yaxley green eyes Remembrall horcrux hand of the servant. Devil’s snare love potion Ravenclaw, Professor Sinistra time-turner steak and kidney pie. Cabbage Daily Prophet letters from no one Dervish and Banges leg.</div>
          </div>
        </div>
      </div>
      <div class="container">

      </div>
    </div>
  </div>
  <footer class="blue darken-3 page-footer">
    <div class="footer-copyright">
      <div class="container">
      </div>
    </div>
  </footer>
</div>

<!-- JavaScript for: jQuery, angular, materialize, and angular-materialize. All of which are needed for Angular + Materialize -->
<script type="text/javascript" src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
<script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.5/angular.min.js"></script>

<!-- If you do not want to use Materialize remove the next two lines -->
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/materialize/0.97.6/js/materialize.min.js"></script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/angular-materialize/0.1.9/angular-materialize.min.js"></script>
<!-- UI Router -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/angular-ui-router/0.3.1/angular-ui-router.min.js"></script>
<!-- Your Scripts -->
<script src="app.js"></script>

</body>
</html>
`


**Outline of an app.js file**

`angular
  .module('app', [
    'ui.materialize'
  ])
`

**References for this article**
[Materialize CSS Main Page](http://materializecss.com/)
[angular-materialize directive docs](http://krescruz.github.io/angular-materialize/)
[Harry Potter Ipsum](http://www.christinachern.com/hpipsum/))
