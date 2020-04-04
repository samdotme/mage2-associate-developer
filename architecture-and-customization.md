# 1. Magento Architecture and Customization Techniques

Weight: 33%

## Resources

[Magento Developer Documentation](https://devdocs.magento.com/)

## Study Material

### 1.1 Describe the Magento module-based architecture

#### What are the significant steps to add a new module?

<details>
<summary>show</summary>
<p>

1. Create the module folder.
2. Create the etc/module.xml file.
3. Create the registration.php file.
4. Run the `bin/magento setup:upgrade` script to install the new module.
5. Check that the module is working.

Source: https://devdocs.magento.com/videos/fundamentals/create-a-new-module/

</p>
</details>

####  What are the different Composer package types?

<details>
<summary>show</summary>
<p>

1. Metapackage `metapackage`
2. Module `magento2-module`
3. Theme `magento2-theme`
4. Language Package `magento2-language`
5. Library `magento2-library`
6. Component `magento2-component`

Source: https://devdocs.magento.com/guides/v2.3/extension-dev-guide/prepare/dev-modtypes.html

</p>
</details>

#### When would you place a module in the app/code folder versus another location? 

<details>
<summary>show</summary>
<p>

`app/code` is for code for that project alone (no sharing), `vendor` is for composer shared packages.

Source: https://community.magento.com/t5/Just-Ask-Alan/Why-two-locations-to-develop-themes/m-p/30431#M279

</p>
</details>

### 1.2 Describe the Magento directory structure

####  What are the naming conventions?

<details>
<summary>show</summary>
<p>

Modules are named in the form of `Vendor_ComponentName`.

Classes are named with `_` to denote file tree location. For example `Mage_Catalog_Model_Product` class is located in `/app/code/core/Mage/Catalog/Model/Product.php`.

Magento autoloader replaces all underscore characters (‘_’) with the category separator (‘/’) and looks for the file in one of the following categories:
- `/app/code/core`
- `/app/code/community`
- `/app/code/local`

Source: https://belvg.com/blog/get-ready-for-magento-certified-developer-exam-class-naming-conventions-and-their-relationship-with-the-autoloader.html

</p>
</details>

#### How are namespaces established? 

<details>
<summary>show</summary>
<p>

Namespaces are based on folder path. For example, a module located in `app/code/MyVendor/DaModule` will have a namespace of `\MyVendor\DaModule`. 

Source: https://magento.stackexchange.com/a/170336/80272

</p>
</details>

####  How can you identify the files responsible for some functionality?

<details>
<summary>show</summary>
<p>

**Common directories**

Following are some common module directories:

- `Block`: contains [PHP](https://glossary.magento.com/php) view classes as part of Model View Controller(MVC) vertical implementation of module logic.
- `Controller`: contains PHP controller classes as part of MVC vertical implementation of module logic.
- `etc`: contains configuration files; in particular, `module.xml`, which is required.
- `Model`: contains PHP model classes as part of MVC vertical implementation of module logic.
- `Setup`: contains classes for module database structure and data setup which are invoked when installing or upgrading.
- `ViewModel`: contains PHP model clasees as part of a model-view-viewmodel (MVVM) implementation. It allows developers to offload features and business logic from block classes into separate classes that are easier to maintain, test, and reuse.

**Additional directories**

Additional folders can be added for configuration and other ancillary functions for items like [plugin-ins](/guides/v2.3/extension-dev-guide/plugins.html), localization, and [layout](https://glossary.magento.com/layout) files.

- `Api`: contains any PHP classes exposed to the [API](https://glossary.magento.com/api).
- `Console`: contains CLI commands. For more info, see [Add CLI commands](/guides/v2.3/extension-dev-guide/cli-cmds/cli-add.html).
- `Cron`: contains cron job definitions.
- `CustomerData`: contains section files.
- `Helper`: contains aggregated functionality.
- `i18n`: contains localization files.
- `Observer`: contains files for executing commands from the listener.
- `Plugin`: contains any needed [plug-ins](/guides/v2.3/extension-dev-guide/plugins.html).
- `UI`: contains data generation files.
- `view`: contains view files, including static view files, design templates, email templates, and layout files.

</p>
</details>
