# [MALVEKE] Pokemon Trading


<figure>
    <img src="./docs/images/youtube.png" />
    <figcaption>MALVEKE Prototype V2.3</figcaption>
</figure>

<div align="center">

**Official** | **Unleashed** | **RogueMaster** | **Xtreme**
:- | :- | :- | :- 
[![FlipC.org](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero/badge?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=official)](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=official)|[![FlipC.org](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero/badge?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=unleashed)](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=unleashed)|[![FlipC.org](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero/badge?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=roguemaster)](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=roguemaster)|[![FlipC.org](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero/badge?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=xtreme)](https://flipc.org/EstebanFuentealba/MALVEKE-Flipper-Zero?branch=main&root=flipper_companion_apps%2Fapplications%2Fexternal%2Fmalveke_pokemon_trading&firmware=xtreme)
</div>
<br>

<p align='center'>
<a href="https://www.tindie.com/stores/efuentealba/?ref=offsite_badges&utm_source=sellers_efuentealba&utm_medium=badges&utm_campaign=badge_large"><img src="https://d2ss6ovg47m0r5.cloudfront.net/badges/tindie-larges.png" alt="I sell on Tindie" width="200" height="104"></a>
</p>

## Introduction

This is a Pokemon exchange application from Flipper Zero to Game Boy [(Generaction I)](https://bulbapedia.bulbagarden.net/wiki/Generation_I). Flipper Zero emulates a "Slave" Game Boy connected to a Game Link Cable to be able to exchange any Pokemon from the First Generation (Red, Blue, Yellow) to a real Game Boy.

It currently trades a Pokemon based on your choice of Pokemon, Level, Stats and 4 Moves.

## MALVEKE for Flipper Zero with Cable Link.

Connect your ***GAME BOY*** through the link cable to the `EXT1` port on the **MALVEKE** board.


<p align='center'>
    <br />
    <img src="../../../../assets/GAME-BOY-MALVEKE-connection-EXT1.png" width="400" />
    <br />
</p>

## Instructions for use.

These instructions assume that you are starting at the Flipper Zero desktop. Otherwise, press the Back button until you are at the desktop.

- Press the `OK` button on the Flipper to open the main menu.
- Choose `Applications` from the menu.
- Choose `GPIO` from the submenu.
- Choose `Pokemon Trading`
- The Flipper Zero will show the main menu of the application. The first option is to select the Pokemon to trade.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-1.png" width="400" />
        <br />
    </p>

- Press the `LEFT`/`RIGHT` buttons to paginate the selection of Pokemon by 1.
- Press the `UP`/`DOWN` buttons to paginate the selection of Pokemon by 10.
- Press the `OK` button to select the Pokemon to trade and return to the main menu

    <p align='center'>
         <br />
        <img src="./docs/images/flipper-zero-flat-2.png" width="400" /><br />
    </p>

- The traded Pokemon's nickname can be set. When a Pokemon is selected, the nickname defaults to the species name in all caps. This mimics a Pokemon without a customized nickname. In order to reset this nickname to its default, clear the text entry field, press `OK` on the `Save` button. This will fill the text box with the default name. Press `Save` again to set this name.
  - **Note:** The Nidoran♀ and Nidoran♂ names will not properly render. This is because the Flipper currently cannot print unicode characters to screen. Following the above instructions will fill the text entry field with `NIDORAN ` with a space after it. This space is the unrenderable ♀/♂ symbol. Once traded, it will be correctly named.
  - **Note:** Only alphanumeric characters are supported in the Pokemon's nickname at this time.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-1-1.png" width="400" />
        <br />
    </p>

- The Pokemon's level can be adjusted as well by hitting `OK` on the level option. The minimum level is `2` and the maximum is `100`. The level is input via a text box. (Levels below 2 cause an underflow glitch in Gen I games that would cause the level to jump to 100, so if you want this just set the Pokemon's level to 100)
    
    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-3.png" width="400" />
        <br />
    </p>

- The `Select Moves` menu is used to pick the set the traded Pokemon's moves. They are pre-populated with the moveset that the Pokemon would know at level 1. Selecting a move slot will bring up an alphabetical index of moves. Additionally, `No Move` and `Default` can be quickly selected. Note that any move after the first `No Move` is ignored. 

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-7.png" width="400" />
        <br />
    </p>

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-8.png" width="400" />
        <br />
    </p>

- The `Select Types` menu can change the traded Pokemon's types. The type(s) are pre-set to what the selected Pokemon normally is.
  - Pokemon with a single type will have the same type set for both types.
  - **Note:** Unlike other menus, changing either type immediately saves it. Pressing `Back` will keep any changes. This will be addressed in a later version. If you need to revert to the default types, a different Pokemon can be selected and the desired Pokemon re-selected.
  - **Note:** When changing the type(s), the Pokemon's in-game stats will _NOT_ reflect the chosen type(s). Additionally, these may be overwritten back to default in-game if the Pokemon uses a move that affects types (e.g. `Transform`) or the Pokemon evolves.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-8-1.png" width="400" />
        <br />
    </p>

- The Pokemon's stats can also be influenced. The current settings are:
  - `Random IV, Zero EV` Mimics stats of a caught wild Pokemon.
  - `Random IV, Max EV / Level` IV is randomized, but EV is set to the maximum a trained Pokemon could be for its current level.
  - `Randon IV, Max EV` IV is randomized, EV is set to the absolute max for a perfectly trained Pokemon.
  - `Max IV, Zero EV` Mimics stats of a caught wild Pokemon, but with the maximum IV possible.
  - `Max IV, Max EV / Level` IV is max, EV is set to the maximum a trained Pokemon could be for its current level.
  - `Max IV, Max EV` Absolutely perfect and overly powerful Pokemon.
 
    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-5.png" width="400" />
        <br />
    </p>

- The `OT ID#` and `OT Name` of the Pokemon can also be set. The `OT ID#` must be between `0` and `65535`. Setting the `OT ID#` and `OT Name` to the same as your current trainer's causes the game to believe it was a wild caught Pokemon and not one that was traded. This means high level Pokemon will still obey you without badges, but, will not get the experience boost of a traded Pokemon.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-6.png" width="400" /><br />
    </p>

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-6-1.png" width="400" /><br />
    </p>

- Finally, select `Trade PKMN` to start the trade process.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-6-2.png" width="400" /><br />
    </p>

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-9.png" width="400" /><br />
    </p>
    
- On your Game Boy, you should connect the  **Game Link Cable** to the Game Boy and in the game, go to the nearest  **Pokemon Center**.

    <p align='center'>
        <br />
        <img src="./docs/images/game_boy_pokemon_center.png" width="400" /><br />
    </p>

- Talk to the girl at the counter on the right. The girl will tell us that we have to save the game before playing, we will answer **YES** by pressing the **A** button.

    <p align='center'>
        <br />
        <img src="./docs/images/game_boy_save.png" width="400" /><br />
    </p>

- The Flipper Zero will show that we are connected.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-10.png" width="400" /><br />
    </p>

- On the Game Boy, we will be asked which option we want, and we select **TRADE CENTER**.

    <p align='center'>
        <br />
        <img src="./docs/images/game_boy_save_trade.png" width="400" /><br />
    </p>

- You will enter the Trade Center where you must press the A button on the Game Boy on your side of the table.

    <p align='center'>
        <br />
        <img src="./docs/images/game_boy_trade_room_2.png" width="400" /><br />
    </p>

- Flipper Zero will remain on a waiting screen with the Pokemon you selected.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-10.png" width="400" /><br />
    </p>

- You will see your Pokemon and the Pokemon you selected on the Flipper Zero, in this case, `Mew`. You must select the Pokemon you want to trade and press **TRADE**.

    <p align='center'>
        <br />
        <img src="./docs/images/game_boy_trade_list_select_trade.png" width="400" /><br />
    </p>

- You must confirm the selected trade by selecting **TRADE**.

    <p align='center'>
        <br />
        <img src="./docs/images/game_boy_trade_list_select_trade_confirm.png" width="400" /><br />
    </p>

- Flipper Zero will remain on a waiting screen with the Pokemon you selected.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-11.png" width="400" /><br />
    </p>

- Finally, the Pokemon exchange will start from **Flipper Zero** to the **Game Boy**.

    <p align='center'>
        <br />
        <img src="./docs/images/flipper-zero-flat-12.png" width="400" /><br />
    </p>

- Once the trade is complete, both the **Game Boy** and the **Flipper Zero** will return to the `WAITING` state. If the **Game Boy** selects `CANCEL`, the **Flipper Zero** will return to the `READY` state. The <img src="./docs/images/back.png" /> BACK button can be pressed to return to the main menu. The traded Pokemon can be modified, or completely changed, if desired. Once the **Flipper Zero** Re-enters the Trade screen, and the **Game Boy** re-selects the trade table in-game, another trade can be completed. This allows for trading multiple Pokemon without having to reset the **Game Boy** each time.

    If the Flipper Zero gets stuck at the end of the exchange, you must reboot it by pressing the <img src="./docs/images/left.png" /> LEFT + <img src="./docs/images/back.png" /> BACK key combination.

    <p align='center'>
        <br />
        <img src="./docs/images/reboot.png" width="400" /><br />
    </p>

## How does it work?

The method used to communicate 2 Game Boys is based on the SPI protocol, which is a very simple serial communication protocol in which a master device communicates with one or more slave devices. The protocol is bidirectional and synchronous, and uses three basic signals:

- A clock signal (CLK).
- An output signal (Serial Out or SO).
- An input signal (Serial In or SI).

In the Game Boy, games store data in an internal shift register that is used to send and receive information. The SPI protocol used by the Game Boy uses the clock signal to indicate when data is being transferred.

The Game Boy link protocol is synchronous and requires the slave device to respond at the same rate as the master device. The master device supplies an 8KHz clock (data transfer rate of 1KB/s). The time window for responding is only **~120μs**. However, the slave device has no restrictions and can respond when it receives data. The clock can vary and there is no lower limit.

<p align='center'>
<br />
<img src="./docs/images/gb_spi.png" width="400" /><br />
</p>

_An example GB SPI transfer. Here, the master sends 0xD9 (217) and the slave sends 0x45 (69)._

<br />

You can learn more about it in the following video. [**Analyzing the Different Versions of the Link Cable**](https://youtu.be/h1KKkCfzOws?t=151).


## GUI

To generate the graphical interface, the [**FUI-Editor**](https://ilin.pt/stuff/fui-editor/) tool was used. Additionally, the original sprites from the game Pokemon Yellow, which are found in the [**Disassembly of Pokemon Yellow**](https://github.com/pret/pokeyellow/tree/master/gfx/pokemon/front) repository, were used.

For each image, the color `#aaa` was transformed to `#fff` so that Flipper Zero would render it correctly. To do this, a batch process was used in [Photopea](https://www.photopea.com/), the online image editor.

##  Tested In
- Game Boy Color (GBC)
- Game Boy Advance (GBA)

## Contributors
[![Contributors](https://contrib.rocks/image?repo=EstebanFuentealba/Flipper-Zero-Game-Boy-Pokemon-Trading)](https://github.com/EstebanFuentealba/Flipper-Zero-Game-Boy-Pokemon-Trading/graphs/contributors)


## Links

- [Flipper Zero firmware source code](https://github.com/flipperdevices/flipperzero-firmware)
- Adan Scotney's Pokemon [trade protocol specification](http://www.adanscotney.com/2014/01/spoofing-pokemon-trades-with-stellaris.html) and implementation
- Derek Jamison - [Youtube Channel](https://www.youtube.com/@MrDerekJamison)
- Matt Penny - [GBPlay Blog](https://blog.gbplay.io/)
- [Pokémon data structure (Generation I)](<https://bulbapedia.bulbagarden.net/wiki/Pok%C3%A9mon_data_structure_(Generation_I)>)
- [Disassembly of Pokemon Yellow](https://github.com/pret/pokeyellow)
- [Arduino-Spoofing-Gameboy-Pokemon-Trades](https://github.com/EstebanFuentealba/Arduino-Spoofing-Gameboy-Pokemon-Trades)
- [🎮 Gameboy link cable breakout PCB](https://github.com/Palmr/gb-link-cable)

<p align='center'>
<br />
<br />
From Talcahuano 🇨🇱 with ❤ 
</p>
