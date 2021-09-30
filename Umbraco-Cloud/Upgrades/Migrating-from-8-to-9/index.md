---
versionFrom: 9.0.0
meta.Title: "Migrate Umbraco 8 Cloud Project to Umbraco 9"
meta.Description: "How to upgrade your Umbraco 8 cloud project to Umbraco 9"
state: complete
verified-against: 9.0.0
update-links: true
---


# Migrate Umbraco 8 Cloud Project to Umbraco 9

This article will provide steps on how to migrate an Umbraco 8 Cloud project to Umbraco 9. However, even though this article is oriented towards Umbraco Cloud users, the majority of the steps will be the same if you host your Umbraco site elsewhere.

## Prerequisites

* An Umbraco 8 Cloud project
* A clean project running the latest version of Umbraco 9

:::note
We strongly recommend having at least 2 environments on the Umbraco 9 project.

Should something fail during the migration, the Development environment can always be removed and re-added in order to start over on a clean slate.
:::

## Step 1: Schema and Content Migration

1. Clone down the Umbraco 8 Cloud project
2. Run the project locally and restore Content and Media
3. Clone down the Development environment from the Umbraco 9 Cloud project
4. Create a folder name `Data` in `~/src/UmbracoProject/umbraco/`
5. **Copy** `~/App_Data/Umbraco.mdf`
6. Paste it into `~/src/UmbracoProject/umbraco/Data`
7. Open the V9 project in your favourite editor
8. Add a connection string to `appsettings.Development.json` pointing to the database you just copied, this connection string will look like `"Data Source=|DataDirectory|\\Umbraco.sdf;Flush Interval=1;"`, for more information about the connection string see the [configuration documentation](../../../Reference/V9-Config/ConnectionStringsSettings/index.md)
9. Enable unattended upgrades, see [unattended config](../../../Reference/V9-Config/UnattendedSettings/index.md) for more information on how to do this.
   1. This is not strictly required, and can be removed afterwards, the reason why you should enable this is because Umbraco ID won't work before the migrations has been run, however if unattended upgrade is disabled you need to log in to run the migrations, a real chicken and egg issue. However if you *really* don't want to enable it, you can configure a local SMTP server like [PaperCut](https://github.com/ChangemakerStudios/Papercut-SMTP), and use the forgotten pasword functionality to still get access to the admin account. 
10. Run the V9 project, you will see the migrations run in the console, once you're presented with the login screen, you should restart your project, to ensure that Umbraco ID will work properly
11. Now you can login and see that your schema and content already exists in the backoffice.

