**Info.json file documentation**

Integrated since version 3.0 from Jeedom, the file ``info.json`` is mandatory for the proper functioning of plugins, and their proper deployment on the Jeedom Market.

The info file.json is saved in the folder ``/plugin_info/`` of your plugin.

List of file variables ``info.json``

Fields marked with * are mandatory fields.

Fields                   | Values                                                                                                                   |
------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
``id`` *                     | Unique identifier of the plugin on the Jeedom Market. Must start with a letter. Without accents.                             |
``name`` *                   | Plugin name.                                                                                                            |
``description`` *            | Description of the plugin, as it will be displayed on the Jeedom Market Minimum 80 characters. (``<br/>`` for the new line.). Please note this is a table for the different languages of jeedom possible (look at the example of the template plugin)                                  |                                                                                     |
``utilization``                    | Additional information to the documentation on the use of the plugin.                                                    |
``licence`` *                | Type of license.                                                                                                          |
``author`` *                 | Name of the plugin author, as it will be displayed once the plugin is installed, in the plugin information.         |
``require`` *                | Jeedom minimum version.                                                                                                |
``category`` *               | Ranking category of the plugin on the Jeedom Market. **It is essential to respect the nomenclature in the table below** |
``display``                  | if the plugin uses a dedicated panel on the desktop, it is the name of the main file of this panel.                    |
``mobile``                   | If the plugin uses a dedicated panel on the Jeedom webApp, this is the name of the main file for this panel.   |
``changelog`` *              | Html link to Changelog.                                                                                              |
``documentation`` *          | Html link to plugin documentation.                                                                                |
``link`` -> ``video``               | Html link to a video presentation.                                                                                 |
``link`` -> ``forum``               | Html link to the forum on the official subject of the plugin.                                                                  |
``languages``                | List of languages available for the plugin: ``fr_FR``, ``en_US``, ``de_DE``, ``it_IT``, ``sp_SP`` , ``ru_RU``, ``pt_PT``            |
``compatibility``            | Plugin compatibility: miniplus, smart, docker, rpi, diy, mobileapp, v4.                                                   |
``hasDependency``            | «true» si le plugin doit installer des dépendances, sinon «false» ou absent.                                              |
``hasOwnDeamon``             | «true» si le plugin doit exécuter des deamons, sinon «false» ou absent.                                                   |
``maxDependancyInstallTime`` | Maximum time allowed for the installation of dependencies, expressed in minutes.                                            |
``specialAttributes`` | Allows plugins to request additional parameters on objects or users (look at the example of the plugin template)                                            |
``issue``                    | URL to the bugtracker if external (if not filled then you will receive an email)

**Example** :

[Plugin-template file / plugin_info / info.json](https://github.com/jeedom/plugin-template/blob/master/plugin_info/info.json)

**CATEGORY NOMENCLATURE**

Jeedom Market         | Info.JSON               |
--------------------- | ----------------------- |
Communication         | ``communication``           |
Comfort               | ``wellness``                |
Energy               | ``energy``                  |
Weather                 | ``weather``                 |
Monitoring            | ``monitoring``              |
Multimedia            | ``multimedia``              |
Nature                | ``nature``                  |
Connected objects      | ``devicecommunication``     |
Organization          | ``organization``            |
Home automation gateway  | ``home automation protocol``|
Programming         | ``programming``             |
Home automation protocol   | ``automation protocol``     |
Health                 | ``health``                  |
Security              | ``security``                |
Automatism           | ``automatisation``          |
