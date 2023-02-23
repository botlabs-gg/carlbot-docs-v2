?> Consider using the [Dashboard](https://carl.gg)

## Quick Setup

<!-- tabs:start -->

<!-- tab:Prefix Commands -->
1. Choose a channel with `!log channel [channel]`
2. Select which events you want to be logged with `!log <event>` where event is an event found in the [Events List](#events-list).
3. Split up logging into separate channel by using the commands found in [Logging Commands](#logging-commands).

?> The `!log aio` command automatically creates a category, fills it with five channels and splits up logging into them.

<!-- tab:Slash Commands -->
1. Choose a channel with `/log channel [channel]`
2. Select which events you want to be logged with `/log config [event]` where event is an event found in the [Events List](#events-list).
3. Split up logging into separate channel by using the commands found in [Logging Commands](#logging-commands).

?> The `/log aio` command automatically creates a category, fills it with five channels and splits up logging into them.

<!-- tabs:end -->


## Logging Commands

<!-- tabs:start -->

<!-- tab:Prefix Commands -->
| Name              | Example           | Usage                                                                         |
| ----------------- | ----------------- | ----------------------------------------------------------------------------- |
| **log channel [channel]** | `!log channel #logs` | Sets the default channel where logged events go. Leave empty to clear the channel. |
| **log [event]**   | `!log timeout`    | Toggles an event from being logged or not. Leave blank to see current config. |
| **log messagechannel [channel]** | `!log messagechannel #msglog` | Sets the channel where message events are logged.  |
| **log memberchannel [channel]** | `!log memberchannel #memberlog` | Sets the channel where member events are logged.  |
| **log joinchannel [channel]** | `!log joinchannel #joinlog` | Sets the channel where the bot logs joining and leaving.|
| **log serverchannel [channel]** | `!log serverchannel #svlog` | Sets the channel where updates to the server are logged. |
| **log voicechannel [channel]** | `!log voicechannel #vclog` | Sets the channl where members joining/moving between/leaving voice channels are logged. |
| **log ignore <channels/members...>** | `!log ignore @Carl-bot #staff` | Ignores message events posted in the channels or by the members. |
| **log unignore <channels/members...>** | `!log unignore @Carl-bot` | Stops ignoring the channels and/or members.      |
| **log <prefix\|ip> \<prefix>** | `!log ip !` | Ignores message deletions, edits and messages within purges starting with the prefix. |
| **log <removeprefix\|up> \<prefix>** | `!log up !` | Stops ignoring the prefix in message deletions, edits and messages within purges. |
| **log export**    | `!log export`     | Exports the settings used in this server.                                     |
| **log [import\|custom] \<perms>** | `!log import 1337` | Imports the settings.                                        |
| **log aio**       | `!log aio`        | Creates a category, fills it with five channels and splits up logging into them. |

<!-- tab:Slash Commands -->
| Name              | Example           | Usage                                                                         |
| ----------------- | ----------------- | ----------------------------------------------------------------------------- |
| **log channel [channel]** | `/log channel #logs` | Sets the default channel where logged events go. Leave empty to clear the channel. |
| **log config [event]**   | `/log config timeout`    | Toggles an event from being logged or not. Leave blank to see current config. |
| **log message_channel [channel]** | `/log message_channel #msglog` | Sets the channel where message events are logged.|
| **log member_channel [channel]** | `/log member_channel #memberlog` | Sets the channel where member events are logged.|
| **log join_channel [channel]** | `/log join_channel #joinlog` | Sets the channel where the bot logs joining and leaving. |
| **log server_channel [channel]** | `/log server_channel #svlog` | Sets the channel where updates to the server are logged. |
| **log voice_channel [channel]** | `/log voice_channel #vclog` | Sets the channl where members joining/moving between/leaving voice channels are logged. |
| **log ignore \<ignore>** | `/log ignore @Carl-bot #staff` | Ignores message events posted in the channels or by the members. |
| **log unignore \<unignore>** | `/log unignore @Carl-bot` | Stops ignoring the channels and/or members.                 |
| **log prefix \<prefix>** | `/log prefix !` | Ignores message deletions, edits and messages within purges starting with the prefix. |
| **log remove_prefix \<prefix>** | `/log remove_prefix !` | Stops ignoring the prefix in message deletions, edits and messages within purges. |
| **log export**    | `/log export`     | Exports the settings used in this server.                                     |
| **log import \<code>** | `/log import 1337` | Imports the settings.                                                   |
| **log aio**       | `/log aio`        | Creates a category, fills it with five channels and splits up logging into them. |

<!-- tabs:end -->

### Events List
Each event that Carl-bot logs has an associated value and channel.

| Event                 | Logging                                   | Value         | Channel                           |
| --------------------- | ----------------------------------------- | ------------- | --------------------------------- |
| delete                | Deleted messages                          | 1             | messagechannel                    |
| edit                  | Message edits                             | 2             | messagechannel
| purge                 | Bulk message deletion                     | 4             | messagechannel
| discord               | Discord invites posted                    | 2097152       | messagechannel
| role                  | Member role updates                       | 8             | memberchannel                     |
| avatar                | Avatar updates                            | 32            | memberchannel                     |
| bans                  | Bans and unbans                           | 192           | memberchannel                     |
| ban                   | Just bans                                 | 64            | memberchannel                     |
| unban                 | Just unbans                               | 128           | memberchannel                     |
| timeout               | Timeouts given                            |               | memberchannel                     |
| removetimeout         | Timeouts removed                          |               | memberchannel                     |
| join                  | Joined the server                         | 256           | joinchannel                       |
| leave                 | Left the server                           | 512           | joinchannel                       |
| name                  | Name and nickname changes                 |               | memberchannel                     |
| channels              | Channel creations, updates and deletions  | 7168          | serverchannel                     |
| channelcreate         | Channel creation                          | 1024          | serverchannel                     |
| channelupdate         | Channel updates                           | 2048          | serverchannel                     |
| channeldelete         | Channel deletions                         | 4096          | serverchannel                     |
| allroles              | Role creations, updates and deletions     | 458752        | serverchannel                     |
| rolecreate            | Role creation                             | 65536         | serverchannel                     |
| roleupdate            | Role updates                              | 131072        | serverchannel                     |
| roledelete            | Role deletions                            | 262144        | serverchannel                     |
| emoji                 | Emoji creations, updates and deletions    | 1048576       | serverchannel                     |
| server                | Server updates                            | 524288        | serverchannel                     |
| voice                 | All voice channel events                  | 57344         | voicechannel                      |
| voicejoin             | Members joining voice channels            | 8192          | voicechannel                      |
| voicemove             | Members changing voice channels           | 16384         | voicechannel                      |
| voiceleave            | Members leaving voice channels            | 32768         | voicechannel                      |
| everything            | All events                                | 4194303       | depends                           |
| nothing               | No events                                 | 0             |                                   |
| default               | Some messages and member events           | 1019          | depends                           |