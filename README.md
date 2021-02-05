# **MoPub with SuezX Asynchronous Ad Tag**

## Ad Formats Supported
- Banner 320x50
- Banner 300x250
- Banner 320x480

## MoPub SDK Integration
- [Android](https://developers.mopub.com/publishers/android/integrate/)
- [iOS](https://developers.mopub.com/publishers/ios/integrate/)

## MoPub SDK Initialization
- [Android](https://developers.mopub.com/publishers/android/initialize/)
- [iOS](https://developers.mopub.com/publishers/ios/initialize/)

## Banner Ad
- [Android](https://developers.mopub.com/publishers/android/banner/)
- [iOS](https://developers.mopub.com/publishers/ios/banner/)

## Interstitial Ad
- [Android](https://developers.mopub.com/publishers/android/interstitial/)
- [iOS](https://developers.mopub.com/publishers/ios/interstitial/)

## Mediation - Custom JavaScript Network

### 1. Create an [Order](https://developers.mopub.com/publishers/ui/manage-orders/)
Navigate to the **Orders** tab and click **Create Order** in the top right corner.
<img width="1440" alt="mopub_order_1" src="https://user-images.githubusercontent.com/56753557/97270262-38032280-1872-11eb-98fb-b4afd21767a7.png">

Enter an order name, an advertiser name and a description.
<img width="1440" alt="mopub_order_2" src="https://user-images.githubusercontent.com/56753557/97270271-3c2f4000-1872-11eb-94ef-95059a8e5d56.png">

### 2. Create a [Line Item](https://developers.mopub.com/publishers/ui/manage-line-items/)
Click on the order to which you want to add a line item and click **New line item** in the top right corner.
<img width="1440" alt="mopub_line_tem_1" src="https://user-images.githubusercontent.com/56753557/97270279-3fc2c700-1872-11eb-9cab-fac0f51cffbc.png">

Enter a line item name. Select a type of **Network line item**, a priority of **1** and a network of **[Custom JS network](https://developers.mopub.com/publishers/mediation/networks/custom-networks/)**. Paste the tag below in HTML. Use the SuezX publisher ID (e.g. "TPMN") and inventory ID (e.g. 99999) provided by your TPMN account manager.
~~~
<div id="div1" style="padding: 0px"></div>
<script type="text/javascript" src="https://static.tpmn.co.kr/suez_sb/ads.js"></script>
<script>
function callbackSuezAd(status) {
    if (status == "ERROR") {
        loaded=true; 
        window.location="mopub://failLoad";
    }
};
SuezJS.loadAd({
divid: "div1",
adverid: "%eudid!",
publisherid: YOUR_PUBLISHER_ID_AS_STRING_HERE,
inventoryid: YOUR_INVENTORY_ID_AS_INTEGER_HERE}, callbackSuezAd);
</script>
~~~
<img width="1440" alt="mopub_line_tem_2" src="https://user-images.githubusercontent.com/56753557/97270287-42252100-1872-11eb-8786-a0245fdd6c9c.png">

Select the app and ad unit to which you want to connect the ad tag.
<img width="1440" alt="mopub_line_tem_3" src="https://user-images.githubusercontent.com/56753557/97270291-44877b00-1872-11eb-93ab-1a9b2d50c8e7.png">
