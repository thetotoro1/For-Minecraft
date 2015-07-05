# Group inheritance
#
# Any inherited groups prefixed with a g: are global groups
# and are inherited from the GlobalGroups.yml.
#
# Groups without the g: prefix are groups local to this world
# and are defined in the this groups.yml file.
#
# Local group inheritances define your promotion tree when using 'manpromote/mandemote'

groups:
  Default:
    default: true
    permissions:
    - -bukkit.command.kill
    inheritance:
    - g:groupmanager_default
    - g:bukkit_default
    - g:essentials_default
    - g:towny_default
    info:
      prefix: '&e'
      build: false
      suffix: ''
  Builder:
    default: false
    permissions:
    -essentials.kit
    -essentials.back
    -essentials.delhome
    -essentials.home
    -essentials.home.bed
    -essentials.sethome
    -essentials.sethome.bed
    inheritance:
    - default
    - g:essentials_builder
    - g:towny_builder
    info:
      prefix: '&2'
      build: true
      suffix: ''
  Trusted:
    default: false
    permissions:
    -essentials.hat
    -essentials.back.ondeath
    -essentials.home.others
    -essentials.sethome.multiple
    inheritance:
    - builder
    - g:essentials_builder
    - g:towny_builder
    info:
      prefix: '&2'
      build: true
      suffix: ''
  Moderator:
    default: false
    permissions:
    -essentials.bigtree
    -essentials.break
    -essentials.fly
    -essentials.fly.safelogin
    -essentials.itemspawn.exempt
    -essentials.heal
    -essentials.heal.cooldown.bypass
    -essentials.others
    -essentials.itemspawn
    -essentials.nuke
    inheritance:
    - trusted
    - g:groupmanager_moderator
    - g:bukkit_moderator
    - g:essentials_moderator
    - g:towny_moderator
    - g:vanish_moderator
    info:
      prefix: '&5'
      build: true
      suffix: ''
  Admin:
    default: false
    permissions:
    -essentials.break.bedrock
    -essentials.enchant
    -essentials.enchantments.allowunsafe
    -essentials.exp
    -essentials.exp.give
    -essentials.exp.give.others
    -essentials.exp.others
    -essentials.exp.set
    -essentials.exp.set.others
    -essentails.feed
    -essentials.feed.cooldown.bypass
    -essentials.others
    -essentials.firework
    -essentials.fly.others
    -essentials.gamemode
    -essentials.gamemode.others
    -essentials.give
    -essentials.kit.exemtdelay
    -essentials.kit.others
    -essentials.kits.*
    inheritance:
    - moderator
    - g:groupmanager_admin
    - g:bukkit_admin
    - g:essentials_admin
    - g:towny_admin
    - g:vanish_admin
    info:
      prefix: '&c'
      build: true
      suffix: ''
  Owner:
    default: false
    permissions:
    - '*'
    - -vanish.*
    inheritance:
    - admin
    info:
      prefix: '&4'
      build: true
      suffix: ''
