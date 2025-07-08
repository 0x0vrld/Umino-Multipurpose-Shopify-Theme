# Umino - Multipurpose Shopify Theme by Next_Sky

![Umino - Multipurpose Shopify Theme](https://github.com/user-attachments/assets/cf80d509-fd0e-4303-baf3-c45c9165c488)

**Umino - Multipurpose Shopify Theme**  
- **Total Downloads:** 2,590+
- **Ratings:** 4.92 on 5
- **Estimated Earnings:** $256,707+ (based on avg $99/theme)  
- **Top Features:** Modern multipurpose design, built-in mega menu, fast loading, product quick view, mobile optimization, and RTL support.
- **Store Link:** https://themeforest.net/item/umino-multipurpose-shopify-themes-os-20/42969030

## What went wrong?
**[Umino](https://themeforest.net/item/umino-multipurpose-shopify-themes-os-20/42969030)** has got huge bug in their theme management system. And here's a way for you to use this $99 premium theme for free for a **Shopify Store**.

> [!NOTE]
> No need to download any file or anything! Everything will be done in shopify cms!
> **For making it easy, this repository of blank shopify template can be used or it can be downloaded as a zip file**.

Umino delivers their theme updates, demo contents and all contents through an app called **NS - Discount in Cart**. 

- **App Store Link:** https://apps.shopify.com/discount-master-pro

The app relies on the **settings_scheme.json** of a theme. 

The block it relies on:

<pre lang="markdown">
{
  "name": "theme_info",
  "theme_name": "Umino",
  "theme_version": "1.0",
  "theme_author": "Blueskytechco Theme",
  "theme_documentation_url": "https:\/\/blueskytechcos-organization.gitbook.io\/umino-shopify\/",
  "theme_support_url": "https:\/\/support.blueskytechco.store\/"
}
</pre>

> [!CAUTION]
> Any code from this block should not be changed before updating or downloading demo or theme contents!


## How to Install the Umino Shopify Theme for Free

1. Download the blank theme from this repository or use any blank/other theme's template you want.
2. Set the theme info block from above in **settings_scheme.json** file and save it.
![settings_scheme.json](https://github.com/user-attachments/assets/f34660fe-58c5-4190-b9e5-9f3788db7314)
3. Go to the Shopify Admin Dashboard.
4. Navigate to **Online Store > Themes**.
5. Click **Upload Theme** and choose the Umino `.zip` file.
6. Click **Upload** and wait for the upload to complete.
7. After uploading, go to this link to download the **[NS - Discount in Cart](https://apps.shopify.com/discount-master-pro)** app and install it.
8. From the settings option of the app, select the theme which is uploaded for downloading **Umino** theme. In my case, it's name is **umino**.
![NS - Discount in Cart settings](https://github.com/user-attachments/assets/8ca6dda3-7a02-49ea-a3fa-dc2c8d5c1be8)
9.  After saving it, two more options will appear. <br>
![NS - Discount in Cart extra settings](https://github.com/user-attachments/assets/bc6c1708-31cf-4372-ab03-890d22ada0da)
10. Go to **Nextsky themes** and lots of option will be seen. From there, demos, metaobjects, theme's default contents, etc can be downloaded.
![Theme's options](https://github.com/user-attachments/assets/11f3dc0b-8574-4acb-8624-b7e6cedcc98d)

> [!NOTE]
> While downloading contents, **error may be shown** but the theme will be available in the **Themes** option under **Online Store**. 
> To check the theme, after upgrade or download, go to **Online Store** > **Themes**.
> To download demos, use **Import Themes** instead of **Update Theme**. Updating theme will only download the default contents of the theme.
> **Updating the theme will not update existing theme. It will only download a new theme with new codes from Umino developers**.


## Bypass Purchase Activation!
![Purchase Activations](https://github.com/user-attachments/assets/379552b7-d629-4445-8330-fe01bca0975e)


1. Go to **Online Store** > **Themes** select the new theme and **edit code** not **customize!!!**.
2. **theme.js** is responsible for the **purchase activation** which can be found under **assets** in the code editor.
3. `BlsUminoAdminLi` function is responsible for the activation screen. You can use any editor to find the function. Disable the initializer, `BlsUminoAdminLi.init()`, to disable the purchase activation screen forever. 

<pre lang="markdown">
    checkCookie: function (val) {
      const v = atob(getCookie('UHVyY2hhc2VDb2Rl'));
      if (val.length !== 0 && v == val) {
        return true;
      } else {
        return false;
      }
    },
  };
})();
// BlsUminoAdminLi.init(); // disabled!!!
</pre>

## Hide Purchase Code Option

![Purchase Code Option](https://github.com/user-attachments/assets/9efae95f-eae0-40b7-9853-dad7a9761de8)

You can hide the **Purchase Code** option which is under **Theme Settings** by removing this code block from **settings_scheme.json** file

<pre lang="markdown">
{
  "name": "t:settings_schema.purchase-code.name",
  "settings": [
    {
      "type": "header",
      "content": "t:settings_schema.purchase-code.settings.header.content"
    },
    {
      "type": "textarea",
      "id": "purchase_code",
      "label": "t:settings_schema.purchase-code.settings.purchase_code.label"
    },
    {
      "type": "paragraph",
      "content": "t:settings_schema.purchase-code.settings.paragraph__1.content"
    },
    {
      "type": "paragraph",
      "content": "t:settings_schema.purchase-code.settings.paragraph__2.content"
    },
    {
      "type": "select",
      "id": "purchase_code_action",
      "label": "t:settings_schema.purchase-code.settings.purchase_code_action.label",
      "options": [
        {
          "value": "active",
          "label": "t:settings_schema.purchase-code.settings.purchase_code_action.active"
        },
        {
          "value": "remove",
          "label": "t:settings_schema.purchase-code.settings.purchase_code_action.remove"
        }
      ],
      "default": "active"
    }
  ]
}
</pre>
