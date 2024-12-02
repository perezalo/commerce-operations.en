---
title: 'MDVA-37984: Visual Merchandiser not working correctly when staging updates are applied'
description: The MDVA-37984 patch solves the issue where the Visual Merchandiser's "Match product by rule" functionality does not filter products correctly when staging updates are applied. This patch is available when the [Quality Patches Tool (QPT)](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/announcements/commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches) 1.1.9 is installed. The patch ID is MDVA-37984. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5.
feature: Categories, Merchandising, Products, Staging
role: Admin
exl-id: 3aeb74a4-b6f7-453a-a8f6-45a345aaa74f
---
# MDVA-37984: Visual Merchandiser not working correctly when staging updates are applied

The MDVA-37984 patch solves the issue where the Visual Merchandiser's "Match product by rule" functionality does not filter products correctly when staging updates are applied. This patch is available when the [Quality Patches Tool (QPT)](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/announcements/commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches) 1.1.9 is installed. The patch ID is MDVA-37984. Please note that the issue is scheduled to be fixed in Adobe Commerce 2.4.5.

## Affected products and versions

**The patch is created for Adobe Commerce version:**

* Adobe Commerce (all deployment methods) 2.4.2

**Compatible with Adobe Commerce versions:**

* Adobe Commerce (all deployment methods) 2.4.1 - 2.4.3-p1

>[!NOTE]
>
>The patch might become applicable to other versions with new Quality Patches Tool releases. To check if the patch is compatible with your Adobe Commerce version, update the `magento/quality-patches` package to the latest version and check the compatibility on the [[!DNL Quality Patches Tool]: Search for patches page](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/announcements/commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches). Use the patch ID as a search keyword to locate the patch.

## Issue

The Visual Merchandiser's "Match product by rule" functionality does not filter products correctly when staging updates are applied.

<u>Steps to reproduce</u>:

1. Create a schedule update for any existing product.
    * Set different values for `entity_id` and `row_id`.
1. Create a new configurable product and then a simple product (so the new product `entity_id` and `row_ids` are different as well).
    * To make it easier to replicate the issue, set a distinguishable qty value for the simple product - for example 5000.
1. Go to a category > **Products in category** and enable **Match products by rule**.
1. Now select "Quantity" as the attribute, "Greater" as the operator, and "4500" as the value.
1. Click **save**.

<u>Expected results</u>:

The newly created configurable product is listed.

<u>Actual results</u>:

The newly created configurable product is not listed.

## Apply the patch

To apply individual patches, use the following links depending on your deployment method:

* Adobe Commerce or Magento Open Source on-premises: [[!DNL Quality Patches Tool] > Usage](/help/tools/quality-patches-tool/usage.md) in the [!DNL Quality Patches Tool] guide.
* Adobe Commerce on cloud infrastructure: [Upgrades and Patches > Apply Patches](https://experienceleague.adobe.com/docs/commerce-cloud-service/user-guide/develop/upgrade/apply-patches.html) in the Commerce on Cloud Infrastructure guide.

## Related reading

To learn more about Quality Patches Tool, refer to:

* [Quality Patches Tool released: a new tool to self-serve quality patches](https://experienceleague.adobe.com/en/docs/commerce-knowledge-base/kb/announcements/commerce-announcements/magento-quality-patches-released-new-tool-to-self-serve-quality-patches) in the support knowledge base.
* [Check if patch is available for your Adobe Commerce issue using Quality Patches Tool](/help/tools/quality-patches-tool/patches-available-in-qpt/check-patch-for-magento-issue-with-magento-quality-patches.md) in the [!DNL Quality Patches Tool] guide.

For info about other patches available in QPT, refer to [[!DNL Quality Patches Tool]: Search for patches](https://experienceleague.adobe.com/tools/commerce-quality-patches/index.html) in the [!DNL Quality Patches Tool] guide.