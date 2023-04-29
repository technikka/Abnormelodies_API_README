<img src="abnormelodies-logo-plain-grey-600px.png" title="abnormelodies logo" alt="abnormelodies logo" width="300px">

# abnormelodies - API

The abnormelodies API is a melody generator. It accepts a range of parameters (e.g., key, time signature, note durations) and constructs a melody from them, responding with musicXML describing the melody. The XML is explicit in describing the tone and notation properties of the melody, even implementing its own beaming service.

This project began with the purpose of inspiring song writers in the melody creation process. With "random", unusual, and sometimes bizarre output-- the idea is that even one measure could trigger something inside the writer, a new direction to take.

Currently I have this API in use with a react app front-end which provides a fun playground for anyone interested in melody creation, and even an educational tool.


#### Note On Music Theory

I'm not a learned musician nor did I have much knowledge of music theory before beginning this project. I think I gained enough of an understanding to accurately implement the 'rules' of music required by this project, but it should be considered a work-in-progress.


#### Accessing The API

This API, though not publically available for use yet, can be interacted with through my react app: [abnormelodies.com](abnormelodies.com)

You can check out the react app's repository here: [abnormelodies - UI](https://github.com/technikka/Abnormelodies_FrontEnd)


## Technologies Used

* Ruby 3.1.0
* Rails 7.0.4
* PostgreSQL
* musicXML
* Action Mailer (Rails)
* [nokogiri gem](https://github.com/sparklemotion/nokogiri)
* [rest-client gem](https://github.com/rest-client/rest-client)
* [rack-cors gem](https://github.com/cyu/rack-cors)


## Description

abnormelodies does not try to be a sophisticated AI composer. It is meant to produce random and funky pieces.

Version 1.0 implements these features:

* Two different scales: Major and Minor
* Compatible with any Key and Register Range
* Note class currently supports whole, half, quarter, and eighth notes.
* Triplet class currently supports the half-note triplet.
* Two note augmentation classes: Dots and Ties.
* Rest class currently supports whole, half, quarter, and eighth rests.
* Time Signature class currently supports 4/4, 3/4 and 6/8 time.
* Rules class currently implements 'Smooth Resolve'. When this rule is set to true, longer durations will be preferred near the end of the melody.
* Beaming Service which determines where notes should be beamed together in notation, for easier display of the melody.
* Clef class which currently selects Bass, Tenor, or Treble clef, for notation purposes.

This project is currently the back-end for abnormelodies.com and so also validates CAPTCHA keys, stores user feedback in a database and implements a mailer to send feedback to the admin (me).


### What's Next

Features that will likely be released with the next version include:

* Characters, whose traits influence the type of melody created. E.g., 'Antsy Adam' might prefer repeat triplets and rarely choose a rest. A fully functioning Character class is already implemented, currently only supporting the default character.

* Many more rule types, the basis for character traits but also selectable on their own.

* More duration and augmentation types. For example: the sixteenth note and rest, more triplet choices, slurs and staccato notes.
