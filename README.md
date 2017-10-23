# mem

```
$ cd /path/to/mem
$ cd themes
$ git clone https://github.com/milligramme/magnesium.git
```

## new post

```
$ hugo new post/yyyy-mm-dd.md
```

## run server

```
$ cd /path/to/mem
$ hugo server -D
```

open http://localhost:1313


## auto launch setting (macOS)


create log at first

```
$ touch /tmp/mem-hugo.out
$ touch /tmp/mem-hugo.err
```

create sample plist

```
$ cd ~/Library/LaunchAgents
$ touch example.plist
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
	<dict>
		<key>KeepAlive</key>
		<true/>
		<key>Label</key>
		<string>mem-hugo</string>
		<key>ProgramArguments</key>
		<array>
			<string>/usr/local/bin/hugo</string>
			<string>server</string>
			<string>-D</string>
			<string>--watch</string>
			<string>--port=4472</string>
		</array>
		<key>RunAtLoad</key>
		<true/>
		<key>WorkingDirectory</key>
		<string>/path/to/mem</string>
		<key>StandardOutPath</key>
		<string>/tmp/mem-hugo.out</string>
		<key>StandardErrorPath</key>
		<string>/tmp/mem-hugo.err</string>
	</dict>
</plist>
```

auto launch enable

```
$ launchctl load ~/Library/LaunchAgents/example.plist
```

auto launch enable

```
$ launchctl load ~/Library/LaunchAgents/example.plist
```

open localhost:4472


## set `dev.workingdir` in config.toml

to edit with TexeMate using URL Scheme if necessary

```toml
[params.dev]
  # Local working dir to edit with [TextMate](https://macromates.com/)
  # This works under Development Mode.(env HUGO_ENV=DEV)
  workingdir = "/path/to/content"
```
