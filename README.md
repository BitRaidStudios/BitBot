
# BitBot

BitBot is a free and open-source discord bot

## Getting started:

### Setting it up:

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

1. Rename `config.json.example` to `config.json` and fill in the details.
2. Run `$ node app.js`.

## Features:

### Roles:

There are two flavours of roles, **groups** and **subroles**.

**Group roles** are configured in the `roles.roles` section of `config.json`. A group role requires a unique ID and a name matching a configured role on the server. `assignableRoles` is a list of the IDs that can be assigned using the `role` command. `defaultRoles` are the IDs of the group roles a user is automatically assigned on joining the server.

**Subroles** are managed via the `subrole` command. Subroles can be created and deleted with `subrole new` and `subrole delete`. Once added, a `subrole` can be assigned to one or many parents with `subrole add`, or removed with `subrole remove`. Lastly, availably subroles can be shown with `subrole list` and `subrole list <group name>`.

### Permissions:

By default a command is available to everyone. To limit the availability of a command, create a new group in `config.json` under `permissions.permissiongroups`. Only the role IDs listed in the `roles` section of the group will be able to use a command listed in `commands`.

### Links:

Rename `links.json.example` to `links.json`. Available links can be listed be calling the `links` command without parameters.

To use the `define` command, which uses the [Oxford Dictionary API](https://developer.oxforddictionaries.com/), fill in the `app_id` and `app_key`.

### Quiz

Rename `quizconfig.json.example` to `quizconfig.json`. Add `timeToAnswer` and `timeToJoin` to the file (in seconds).

### Message Filter

To filter messages, use the `messagefilter` section of `config.json`. If you have a channel specified with the name of `*`, all channels will be filtered off it's blacklist and whitelist, as well as their own.

The filter uses [Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions).

### Available commands:

Available commands can be listed with the `help` command.

The order in which plugins and commands appear in the help command can be configured with `pluginorder.json.example`. Rename it to `pluginorder.json` and create an entry for each plugin, specifying the desired sort order. The order of commands under a plugin heading is configured by the order of the commands in the plugin's `.commands` member.

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Node.js](https://nodejs.org/en/) - Javascript runtime

## Contributing

Please read [CONTRIBUTING.md](https://github.com/BitRaidStudios/BitBot/blob/master/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags).

## Authors

* **Kenan Ajkunic**

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
