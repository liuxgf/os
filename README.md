<p align="center">
  <a href="#build-framework">
   <img src="https://raw.githubusercontent.com/armbian/build/master/.github/armbian-logo.png" alt="Armbian logo" width="144">
  </a><br>
  <strong>Armbian OS</strong><br>
<br>
<a href=https://github.com/armbian/os/actions/workflows/complete-artifact-matrix-all.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/complete-artifact-matrix-all.yml?logo=githubactions&label=Artifacts&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os/actions/workflows/repository-update.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/repository-update.yml?logo=githubactions&label=Repository&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os/actions/workflows/full-distro-build-and-test.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/full-distro-build-and-test.yml?logo=githubactions&label=Deboostrap&style=for-the-badge&branch=main"></a> <a href=https://github.com/armbian/os#latest-smoke-tests-results><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/smoke-tests.yml?logo=githubactions&label=Smoke%20tests&style=for-the-badge&branch=main"></a>
</p>


## What does this project do?

- Builds quarterly [stable](https://www.armbian.com/download/), daily [rolling](https://github.com/armbian/os/releases/latest) and weekly [community](https://github.com/armbian/community/releases/latest) Armbian OS images
- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date to secure fast rebuild process
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Reversion Firefox, Thunderbird and Chromium to higher (9) epoch version then its Snapd counterparts (1)
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases
- Tests packages upgrade sucess on real hardware
- Tests build [supported and community supported desktops](https://github.com/armbian/os/actions/workflows/full-distro-build-and-test.yml)

## How to enable images?

Build lists are generated [automatic](https://github.com/armbian/os/blob/main/.github/workflows/recreate-matrix.yml#L59-L211C94) based on [support policy](https://docs.armbian.com/User-Guide_Board-Support-Rules/) and with help of [templates](userpatches/), .blacklist and .map files.

## How to add description to download pages?

Each kernel branch can have additional description which is stoed in [kernel-description.json](kernel-description.json) and automatically updated upon changes.

## When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after artifacts cache update is done succesfully
- Smoke tests starts once per day at 5:30 AM UTC
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config / template is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

## Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=center>6.6.51-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/pokahuneto><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>6886</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/unosevucaw><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3721</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=center>6.6.44-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/adibowujar><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>92</td><td align=right>1807</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.6.44-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ecepeceqex><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>758</td><td align=right>2697</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.6.51-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/arevatawaw><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3120</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/wokikunala><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5559</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/upiturikow><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>830</td><td align=right>7254</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/sisenutoze><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3616</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=#><img src=https://img.shields.io/static/v1?label=&message=N/A&color=white></a></td><td align=right>870</td><td align=right>4006</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1s href=#khadas-vim1s>Khadas VIM1S</a></td><td align=center>5.15.137-legacy-meson-s4t7</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/kotijuloji><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>92</td><td align=right>4103</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-4b href=#rockpi-4b>Rockpi 4B</a></td><td align=center>6.6.51-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/wijomenoya><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>6400</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zolikihuca><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>6205</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.6.51-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/onapoweqoc><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>6649</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/losidofeqo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>5649</td><td align=right>beta</td></tr><tr><td align="left"><a id=cubietruck href=#cubietruck>Cubietruck</a></td><td align=center>6.6.44-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/zagesasomo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>511</td><td align=right>1028</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=center>6.6.44-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/epamikitar><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>773</td><td align=right>2704</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zaworinoca><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>8897</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.6.51-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ehezikekof><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>5249</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.51-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/cubamehejo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>434</td><td align=right>5245</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=center>6.6.51-current-rockchip</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/qofafaqoko><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>868</td><td align=right>4599</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=#><img src=https://img.shields.io/static/v1?label=&message=N/A&color=white></a></td><td align=right>870</td><td align=right>7141</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.51-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ezibeguveb><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>891</td><td align=right>6549</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.6.51-current-imx6</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ufalitorih><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>388</td><td align=right>2253</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>5.15.137-legacy-meson-s4t7</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ejekisebuj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>608</td><td align=right>13178</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidxu4 href=#odroidxu4>Odroid XU4</a></td><td align=center>6.6.51-current-odroidxu4</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/goxaqihoqu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>859</td><td align=right>7359</td><td align=right>beta</td></tr><tr><td align="left"><a id=lime-a64 href=#lime-a64>A64 OLinuXino</a></td><td align=center>6.6.44-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/urewubelez><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>871</td><td align=right>2708</td><td align=right>beta</td></tr><tr><td align="left"><a id=clearfogpro href=#clearfogpro>Clearfog Pro</a></td><td align=center>6.6.51-current-mvebu</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/olucojuqom><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>897</td><td align=right>2221</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>6.1.75-vendor-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/sakokumiso><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>2241</td><td align=right>16333</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>6.10.10-current-rockchip-rk3588</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ihomabefad><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>2248</td><td align=right>15924</td><td align=right>beta</td></tr></table>
<!--END_SECTION:data-section-->

## Would you like to join spare hardware to this automated testings?

All you need to do is:

- deploy any latest Armbian image to hardware
- provide IP address
- [contact us](https://www.armbian.com/contact/)

Device has to be always on and easily accesible for you to re-image in case of failed upgrade.

## Development

- [Pull request](https://github.com/armbian/build/pulls)
- [Weekly developers meetings](https://forum.armbian.com/events/)
- [Forums for developers](https://forum.armbian.com/forum/4-advanced-users-development/)

## Download prebuilt images

- [quarterly released **standard support** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)
- [weekly released **community maintained** builds](https://github.com/armbian/community/releases/latest)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
