# Glozin - Multipurpose Shopify Theme by Next_Sky

![Glozin - Multipurpose Shopify Theme](https://github.com/user-attachments/assets/4b883aa7-7792-401a-9d37-370b44cbb0e6)

**Glozin - Multipurpose Shopify Theme**  
- **Total Downloads:** 3,000+
- **Ratings:** 4.88 on 5
- **Estimated Earnings:** $237,711+ (based on avg $79/theme)  
- **Top Features:** Modern multipurpose design, built-in mega menu, fast loading, product quick view, mobile optimization, and RTL support.
- **Store Link:** https://themeforest.net/item/glozin-multipurpose-shopify-theme-os-20/53006461

## What went wrong?
**[Glozin](https://themeforest.net/item/glozin-multipurpose-shopify-theme-os-20/53006461)** has got huge bug in their theme management system. And here's a way for you to use this $79 premium theme for free for a **Shopify Store**.

> [!NOTE]
> No need to download any file or anything! Everything will be done in shopify cms!
> **For making it easy, this repository of blank shopify template can be used or it can be downloaded as a zip file**.

Glozin delivers their theme updates, demo contents and all contents through an app called **NS - Discount in Cart**. 

- **App Store Link:** https://apps.shopify.com/discount-master-pro

The app relies on the **settings_scheme.json** of a theme. 

The block it relies on:

<pre lang="markdown">
{
  "name": "theme_info",
  "theme_name": "Glozin",
  "theme_version": "1.0",
  "theme_author": "Nextsky",
  "theme_documentation_url": "https://blueskytechco.gitbook.io/glozin-shopify",
  "theme_support_url": "https://support.nextsky.co"
}
</pre>

> [!CAUTION]
> Any code from this block should not be changed before updating or downloading demo or theme contents!


## How to Install the Glozin Shopify Theme for Free

1. Download the blank theme from this repository or use any blank/other theme's template you want.
2. Set the theme info block from above in **settings_scheme.json** file and save it.
![settings_scheme.json](https://github.com/user-attachments/assets/3b397db3-a750-445c-911b-2665d7d01d6a)
3. Go to the Shopify Admin Dashboard.
4. Navigate to **Online Store > Themes**.
5. Click **Upload Theme** and choose the Glozin `.zip` file.
6. Click **Upload** and wait for the upload to complete.
7. After uploading, go to this link to download the **[NS - Discount in Cart](https://apps.shopify.com/discount-master-pro)** app and install it.
8. From the settings option of the app, select the theme which is uploaded for downloading **Glozin** theme. In my case, it's name is **glozin**.
![NS - Discount in Cart settings](https://github.com/user-attachments/assets/d793e339-8ab6-4081-9cbe-fc7c4dc24fc3)
9.  After saving it, two more options will appear. <br>
![NS - Discount in Cart extra settings](https://github.com/user-attachments/assets/bc6c1708-31cf-4372-ab03-890d22ada0da)
10. Go to **Nextsky themes** and lots of option will be seen. From there, demos, metaobjets, theme's default contents, etc can be downloaded.
![Theme's options](https://github.com/user-attachments/assets/11f3dc0b-8574-4acb-8624-b7e6cedcc98d)

> [!NOTE]
> While downloading contents, **error may be shown** but the theme will be available in the **Themes** option under **Online Store**. 
> To check the theme, after upgrade or download, go to **Online Store** > **Themes**.
> To download demos, use **Import Themes** instead of **Update Theme**. Updating theme will only download the default contents of the theme.
> **Updating the theme will not update existing theme. It will only download a new theme with new codes from Glozin developers**.


## Bypass Purchase Activation!
![Purchase Activations](https://github.com/user-attachments/assets/0ced77a1-228a-45b5-8a71-02a1309e42dc)


1. Go to **Online Store** > **Themes** select the new theme and **edit code** not **customize!!!**.
2. **theme.js** is responsible for the **purchase activation** which can be found under **assets** in the code editor.
3. `BlsGlozinAdminLi` function is responsible for the activation screen. You can use any editor to find the function. Disable the initializer, `BlsGlozinAdminLi.init()`, to disable the purchase activation screen forever. 

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
// BlsGlozinAdminLi.init(); // disabled!!!
</pre>

## Hide Purchase Code Option

![Purchase Code Option](https://github.com/user-attachments/assets/9efae95f-eae0-40b7-9853-dad7a9761de8)

You can hide the **Purchase Code** option which is under **Theme Settings** by removing this code block from **settings_scheme.json** file

<pre lang="markdown">
{
  "name": "t:settings_schema.purchase_code.name",
  "settings": [
    {
      "type": "paragraph",
      "content": "t:settings_schema.purchase_code.info"
    },
    {
      "type": "textarea",
      "id": "purchase_code",
      "label": "t:settings_schema.purchase_code.name"
    },
    {
      "type": "paragraph",
      "content": "t:settings_schema.purchase_code.how_to_get.content"
    },
    {
      "type": "paragraph",
      "content": "t:settings_schema.purchase_code.buy_now.content"
    },
    {
      "type": "select",
      "id": "purchase_code_action",
      "label": "t:settings_schema.purchase_code.purchase_code_action.label",
      "default": "active",
      "options": [
        {
          "value": "active",
          "label": "t:settings_schema.purchase_code.purchase_code_action.active.label"
        },
        {
          "value": "remove",
          "label": "t:settings_schema.purchase_code.purchase_code_action.remove.label"
        }
      ]
    }
  ]
}
</pre>