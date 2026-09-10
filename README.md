# EZDisplay Homebrew tap

A personal Homebrew tap, `davidnoyes/homebrew-tap`. It holds one cask,
[EZDisplay][ezdisplay], a macOS menu bar app for display resolution, refresh
rate, HDR, color mode, and mirroring.

## Install

```sh
brew install --cask davidnoyes/tap/ezdisplay
```

There is no need to run `brew tap` first. Naming the tap in the install
argument taps it.

## Why this tap exists

Homebrew's own cask repository takes only apps that pass Gatekeeper. EZDisplay
is signed by its own certificate rather than by an Apple Developer ID one, so
macOS refuses its first launch, and a personal tap is the only route.

After installing, open **System Settings > Privacy & Security**, find the
message naming EZDisplay, and choose **Open Anyway**. That is once per machine,
because every release is signed by the same certificate.

To let EZDisplay control the volume keys, grant it Accessibility in
**System Settings > Privacy & Security > Accessibility**.

## Updating

EZDisplay updates itself from its About panel, so the cask sets `auto_updates`
and `brew upgrade` leaves it alone. To take a newer cask anyway, run
`brew upgrade --greedy`.

## How the cask is maintained

Do not edit `Casks/ezdisplay.rb` by hand. The release workflow in the EZDisplay
repository rewrites it on every tagged release, from the template at
[`etc/ezdisplay.rb`][template]. Edit the template instead.

[ezdisplay]: https://github.com/davidnoyes/EZDisplay
[template]: https://github.com/davidnoyes/EZDisplay/blob/main/etc/ezdisplay.rb
