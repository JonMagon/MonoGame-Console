# MonoGame Console

````
PM> Install-Package MonoGame.Console.WindowsDX
````

![monogameconsole-screenshot](http://s28.postimg.org/gquhv868d/monoconsole.gif "Screenshot")

[MonoGame](http://monogame.net) is an open source implementation of the Microsoft XNA 4.x Framework. 

MonoGame Console - terminal emulator ([XNAGameConsole](http://code.google.com/p/xnagameconsole/) fork) with full unicode & MonoGame support.

## Supported Platforms

* Windows (DirectX)

## Features
* [Add your own commands](http://code.google.com/p/xnagameconsole/wiki/AddingCommands)
* [Customizable Options](http://code.google.com/p/xnagameconsole/wiki/ConsoleOptions)
* [Clipboard Support](http://code.google.com/p/xnagameconsole/wiki/ClipboardSupport)
* [External Writing](http://code.google.com/p/xnagameconsole/wiki/WritingToTheConsole)
* Command Auto-Complete
* Command History 

## Quick Start

* Create a XNB file with your SpriteFont or use default from repository "Content" folder
* Add a code below to your Initialize() logic

            Services.AddService(typeof(SpriteBatch), spriteBatch);

            GameConsole console = new GameConsole(this, spriteBatch, new GameConsoleOptions
              {
                  ToggleKey = 192, 
                  Font = Content.Load<SpriteFont>("ConsoleFont"),
                  FontColor = Color.LawnGreen,
                  Prompt = "~>",
                  PromptColor = Color.Crimson,
                  CursorColor = Color.OrangeRed,
                  BackgroundColor = new Color(Color.Black, 150),
                  PastCommandOutputColor = Color.Aqua,
                  BufferColor = Color.Gold
              });

            console.AddCommand("ping", a =>
            {
                // TODO your logic
                return String.Format("pong");
            });

* Run game and press '~' (tilda) to open console

## License

MonoGame Console is released under GNU GPL v3.

