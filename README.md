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
    -
    inheritance:
    - default
    - g:essentials_builder
    - g:towny_builder
    info:
      prefix: '&2'
      build: true
      suffix: ''
  Moderator:
    default: false
    permissions: []
    inheritance:
    - builder
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
    permissions: []
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
