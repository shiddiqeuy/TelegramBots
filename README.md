# Telegram Bot Java Library
[![Build Status](https://travis-ci.org/rubenlagus/TelegramBots.svg?branch=master)](https://travis-ci.org/rubenlagus/TelegramBots)
[![Jitpack](https://jitpack.io/v/rubenlagus/TelegramBots.svg)](https://jitpack.io/#rubenlagus/TelegramBots)
[![Telegram](http://trellobot.doomdns.org/telegrambadge.svg)](https://telegram.me/JavaBotsApi)

A simple to use library to create Telegram Bots in Java

## Contributions
Feel free to fork this project, work on it and then make a pull request against **DEV** branch. Most of the times I will accept them if they add something valuable to the code.

Please, **DO NOT PUSH ANY TOKEN OR API KEY**, I will never accept a pull request with that content.

## Webhooks vs GetUpdates
Both ways are supported, but I recommend long polling method.

## Usage

Just import add the library to your project using [Maven, Gradle, ...](https://jitpack.io/#rubenlagus/TelegramBots/v2.3.5) or download the jar(including all dependencies) from [here](https://github.com/rubenlagus/TelegramBots/releases/tag/v2.3.5)

In order to use Long Polling mode, just create your own bot extending `org.telegram.telegrambots.bots.TelegramLongPollingBot`.

If you like to use Webhook, extend `org.telegram.telegrambots.bots.TelegramWebhookBot`


Once done, you just need to create a `org.telegram.telegrambots.TelegramBotsApi`and register your bots:

```java

    // Example taken from https://github.com/rubenlagus/TelegramBotsExample
    public class Main {
        public static void main(String[] args) {
    
            TelegramBotsApi telegramBotsApi = new TelegramBotsApi();
            try {
                telegramBotsApi.registerBot(new ChannelHandlers());
                telegramBotsApi.registerBot(new DirectionsHandlers());
                telegramBotsApi.registerBot(new RaeHandlers());
                telegramBotsApi.registerBot(new WeatherHandlers());
                telegramBotsApi.registerBot(new TransifexHandlers());
                telegramBotsApi.registerBot(new FilesHandlers());
            } catch (TelegramApiException e) {
                e.printStackTrace();
            }
        }
    }

```

For detailed explanation, visite our [How To](HOWTO.md) (thanks Clevero)


## Example bots
Open them and send them */help* command to get some information about their capabilities:

https://telegram.me/weatherbot (**Use custom keyboards**)

https://telegram.me/directionsbot (**Basic messages**)

https://telegram.me/filesbot (**Send files by file_id**)

https://telegram.me/TGlanguagesbot (**Send files uploding them**)

https://telegram.me/RaeBot (**Inline support**)

https://telegram.me/SnowcrashBot (**Webhook support**)

You can see code for those bots at [TelegramBotsExample](https://github.com/rubenlagus/TelegramBotsExample) project.

## Telegram Bot API
This library use [Telegram bot API](https://core.telegram.org/bots), you can find more information following the link.

## Questions or Suggestions
Feel free to create issues [here](https://github.com/rubenlagus/TelegramBots/issues) as you need or join the [chat](https://telegram.me/JavaBotsApi)

## License 

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
