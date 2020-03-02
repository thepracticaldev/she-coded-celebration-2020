<!-- TODO: Ridhwana: still need to format -->

# She Coded Setup & Configuration Instructions:

## Steps that need to be taken:
2. The new she coded page needs to be configured with a slug url of (maybe) shecoded2020. Once it's configured and ready, test this page. Thereafter the PR https://github.com/thepracticaldev/dev.to/pull/6357 (which removes the existing she coded pages) needs to be merged and deployed. Once we've deployed the PR we can then go to the internal pages config and change the slug on the pages to shecoded.

3. The following images need to first be uploaded manually to our amazon server so that they can be referenced from the html files:

<!-- * Shecoded_logo_2020.png: https://dev-to-uploads.s3.amazonaws.com/i/0j0cbs668sni2hclgx1o.png

* Shecoded_display_ad_2020: https://dev-to-uploads.s3.amazonaws.com/i/v266t6xk90yv7uyric8b.png

* Shecoded_hero_banner_background_2020: https://dev-to-uploads.s3.amazonaws.com/i/qrv582ufepl23dombtnc.png

* Shecoded_sticker_2020.png: https://dev-to-uploads.s3.amazonaws.com/i/wldub08qchqrq2u3c8it.png

* Shecoded_sidebar_header_2020.png: https://dev-to-uploads.s3.amazonaws.com/i/dzl4rng9l4iskyxhx5oq.png

* She_coded_main_background_2020.png: https://dev-to-uploads.s3.amazonaws.com/i/2b2spes1e3sby7g1dwq0.jpg

* She_coded_tag_campaign_background_2020.png: https://dev-to-uploads.s3.amazonaws.com/i/4dxgme0dqehcug69o8qe.png -->

	<!-- Note: The files can be found on the google drive under the following folders:
HTML Files can be found in the She Coded Campaign HTML folder
https://drive.google.com/drive/folders/1AtvmY4nu3ikkqB38o6tp-Xj-wO5lh77u?usp=sharing
Assets can me found in the She Coded Campaign Assets (https://drive.google.com/drive/folders/14VzBLL2rrENwuEYKENwl3bTQBo7Hg39Y?usp=sharing) -->

  <!-- Once the assets are uploaded, you will need to replace the url’s in the html files with the new urls.
  Please add the urls below or next to the a/b/c in point 2 so that we can keep track of them and use them in development as well. -->



UX Flow:




Setup and Configuration
The instructions below reference the UX Flow Diagram. Please use them hand in hand,
Phase 1: Soft Launch (March 2)
HomePage Sidebar (DisplayAd)

HTML File: /She Coded Campaign HTML Files/display_ad.html
Assets required: shecoded_logo_2020.png, shecoded_display_ad_2020.png
Component to edit: Display_Ads


Steps:
Go to https://dev.to/admin/display_ads
Click on New Display ad
Add the relevant information
Placement area will be sidebar_right
Add the body html to Body Markdown. HTML can be found in She Coded Campaign HTML Files/display_ad.html
Remember to replace the 2 asset urls in the html file based on the urls for your images
Publish and Approve once it’s ready to go live

The display ad should pop up on the homepage as follows:


She Coded Page

HTML File: She Coded Campaign HTML Files/shecoded.html
Assets required: shecoded_main_background_2020.jpg, shecoded_sticker_2020.png, shecoded_logo_2020.png
Component to edit: Internal Pages

Steps:
Go to https://dev.to/internal/pages
Click on New Page
Add the relevant information
The slug should first be shecoded2020 until we remove the shecoded hardcoded route from the repo
Add the body html from the file  /She Coded Campaign HTML/shecoded.html
Remember to replace the 3 assets in the html file based on your urls for your images
Template is full_within_layout
Is top level path should be ticked


Editor
(No changes were made here, but the prompts need to be updated)
Phase 2: Full Takeover
HomePage Hero Banner
HTML File: /She Coded Campaign HTML Files/hero_banner.html
Assets required: shecoded_logo_2020.png, shecoded_hero_banner_2020.png, shecoded_sticker_2020.png
Component to edit: HTML Variant



Steps:
Go to https://dev.to/html_variants
Click on New
Add the relevant information
Add a unique name (Keep this name for later)
Add the body html from the file  /She Coded Campaign HTML Files/hero_banner.html
Remember to replace the 3 assets in the html file based on your the urls for your images
Group should be campaign
Publish and Approve once it’s ready to go live (on my development environment the approved button wasn’t showing up and I had to go into the console, not sure if that’s the case on prod or just something weird with my dev environment)  Once approved it will show up.
If you do end up needing to use the console, it will be something along the lines of:
			h = HtmlVariant.last //double check this is the right object
			h.approved = true
			h.save!
NOTE: don’t worry that the campaign width of the banner is 310px on the preview within the internal interface, we need to most likely remove it but this will not affect the display to the user.
4. The banner will not pop up until you have set the config to use the hero banner:
Navigate to https://dev.to/internal/config
Go the the Campaign section
Enter in the unique name that you had given the HTMLVariant in 3a.
Save the config


The hero banner should now pop up on the homepage as follows:

Expected Behaviour:
When you click on the close button, the campaign banner will not show up again. If you’re testing and want it to show up again, then set document.cookie = 'heroBanner=true' in your console.
Phase 2 Sidebar with articles
HTML File: None Required
Assets required: shecoded_sidebar_header_2020.png
Component to edit: Campaign Config


Steps:
Go to https://dev.to/internal/config
Make sure you have the right permissions to edit
Go to the campaign section
Add the link for the shecoded_sidebar_header_2020.png asset (the url for the image that you uploaded) to Campaign sidebar image
Tick Campaign sidebar enabled
Add some tags that you want to show up in the sidear
Then update the config

Remember that only approved shecoded tags will show up on the tags page.

The sidebar will be displayed as follows:



SheCoded Tag Page

https://dev-internal.slack.com/archives/CSZCB4QB0/p1582905252002800
