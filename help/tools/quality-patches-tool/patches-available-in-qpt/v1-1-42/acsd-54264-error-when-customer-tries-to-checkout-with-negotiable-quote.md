---
title: 'ACSD-54264: Error when customer tries to check out with negotiable quote'
description: Apply the ACSD-54264 patch to fix the Adobe Commerce issue where an error message "You cannot update the requested attribute. Row ID:store_id" appears when a customer tries to check out with a negotiable quote from another store view.
feature: B2B, Checkout
role: Admin, Developer
exl-id: b1696228-b2ed-44eb-9e75-bf25ccf2f1cd
---
# ACSD-54264: Error appears when customer tries to check out with negotiable quote

The ACSD-54264 patch fixes the issue where an error message *You cannot update the requested attribute. Row ID: store_id* appears when a customer tries to check out with a negotiable quote from another store view. This patch is available when the [[!DNL Quality Patches Tool (QPT)]](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/announcements/commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches) 1.1.42 is installed. The patch ID is ACSD-54264. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.7.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.4.6-p2

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.0 - 2.4.6-p3

>[!NOTE]
>
>The patch might become applicable to other versions with new [!DNL Quality Patches Tool] releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://experienceleague.adobe.com/tools/commerce-quality-patches/index.html). Use the patch ID as a search keyword to locate the patch.

## Issue

An error message *You cannot update the requested attribute. Row ID: store_id* appears when a customer tries to check out with a negotiable quote from another store view.

<u>Prerequisites</u>:

Adobe Commerce B2B modules are installed and enabled.

<u>Steps to reproduce</u>:

1. Create an additional store view for the default website.
1. Enable the *[!UICONTROL B2B Quote]* in the configuration.
1. Log in as a company customer in one of the store views.
1. Add a product to the *[!UICONTROL Shopping Cart]*.
1. Submit the quote for review.
1. As an admin user, go to **[!UICONTROL Sales]** > **[!UICONTROL Quotes]** and submit the approved quote.
1. As the company customer, change the store view to a different store view.
1. Try to check out.

<u>Expected results</u>:

The customer places an order with this quote.

<u>Actual results</u>:

* The error happens while saving the shipping information:
  
    `You cannot update the request attribute. Row ID: store_id =#`

* The following error is logged:
  
    `report.CRITICAL: Magento\Framework\Exception\InputException: You cannot update the requested attribute. Row ID: store_id = 2. in /app/code/Magento/NegotiableQuote/Plugin/Quote/Model/QuoteUpdateValidator.php:100`
 
## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [[!DNL Quality Patches Tool] > Usage](/help/tools/quality-patches-tool/usage.md) in the [!DNL Quality Patches Tool] guide.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/develop/upgrade/apply-patches.html) in the Commerce on Cloud Infrastructure guide.

## Related reading

To learn more about [!DNL Quality Patches Tool], refer to:

* [[!DNL Quality Patches Tool] released: a new tool to self-serve quality patches](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/announcements/commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches) in the support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using [!DNL Quality Patches Tool]](/help/tools/quality-patches-tool/patches-available-in-qpt/check-patch-for-magento-issue-with-magento-quality-patches.md) in the [!UICONTROL Quality Patches Tool] guide.


For info about other patches available in QPT, refer to [[!DNL Quality Patches Tool]: Search for patches](https://experienceleague.adobe.com/tools/commerce-quality-patches/index.html) in the [!DNL Quality Patches Tool] guide.