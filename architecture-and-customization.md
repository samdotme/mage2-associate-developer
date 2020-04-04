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

**Friendly name**|**composer.json type**|**Description**
:-----:|:-----:|:-----:
Metapackage|metapackage|Technically, a Composer package type, not a Magento component type. A metapackage consists of only a composer.json file that specifies a list of components and their dependencies. For example, both Magento Open Source and Magento Commerce are metapackages.
Module|magento2-module|Code that modifies Magento application behavior. You can upload a single module to the Magento Marketplace or your module can be dependent on some parent package.
Theme|magento2-theme|Code that modifies the look and feel of the storefront or Magento Admin.
Language package|magento2-language|Translations for the storefront or Admin.
Library|magento2-library|Support for libraries located in lib/internal instead of in the vendor directory.
Component|magento2-component|The package formed of the files that must be located in root (index.php, .htaccess, etc). This includes dev/tests and setup as well for now.

Source: https://devdocs.magento.com/guides/v2.3/extension-dev-guide/prepare/dev-modtypes.html

</p>
</details>