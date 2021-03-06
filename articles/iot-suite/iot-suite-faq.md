<properties
  pageTitle="Azure IoT Suite FAQ | Microsoft Azure"
  description="Frequently asked questions for IoT Suite"
  services=""
  suite="iot-suite"
  documentationCenter=""
  authors="aguilaaj"
  manager="timlt"
  editor=""/>

<tags
  ms.service="iot-suite"
  ms.devlang="na"
  ms.topic="get-started-article"
  ms.tgt_pltfrm="na"
  ms.workload="na"
  ms.date="05/09/2016"
  ms.author="araguila"/>
   
# Frequently asked questions for IoT Suite

### What's the difference between deleting a resource group in the Azure portal and clicking delete on a preconfigured solution in azureiotsuite.com?

- If you delete the preconfigured solution in [azureiotsuite.com][lnk-azureiotsuite], you delete all the resources that were provisioned when you created the preconfigured solution; if you added additional resources to the resource group, these are also deleted. 

- If you delete the resource group in the [Azure portal][lnk-azure-portal], you only delete the resources in that resource group; you will also need to delete the Azure Active Directory application associated with the preconfigured solution in the [Azure classic portal][lnk-classic-portal].

### How many DocumentDB instances can I provision in a subscription?

Five. You can create an [Azure support ticket][link-azuresupportticket] to raise this limit, but by default, you can only provision five DocumentDB instances per subscription. As a result, you can only provision up to five remote monitoring preconfigured solutions in a given subscription.

### How many Free Bing Maps APIs can I provision in a subscription?

Two. You can create only two Free Bing Maps APIs in a subscription. The remote monitoring solution is provisioned by default with a Free Bing Maps API. As a result, you can only provision up to two remote monitoring solutions in a subscription with no modifications.

### I have a remote monitoring solution deployment with a static map, how do I add an interactive Bing map? 
1. Get your Bing Maps API for Enterprise QueryKey from [Azure portal][lnk-azure-portal]: 
 1. Navigate to the Resource Group where your Bing Maps API for Enterprise is in the [Azure portal][lnk-azure-portal].
 2. Click All Settings, then Key Management. 
 3. You'll notice two keys: MasterKey and QueryKey. Copy the value for QueryKey.

     > [AZURE.NOTE] Don't have a Bing Maps API for Enterprise account? Create one in the [Azure portal][lnk-azure-portal] by clicking + New, searching for Bing Maps API for Enterprise and follow prompts to create.

2. Pull down the latest code from the [Azure-IoT-Remote-Monitoring][lnk-remote-monitoring-github].

3. Run a local or cloud deployment following commandline deployment guidance in the /docs/ folder in the repository. 

4. After you've run a local or cloud deployment, look in your root folder for the *.user.config file created during deployment. Open this file in a text editor. 

5. Change the following line to include the value you copied fror your QueryKey: 
   
  `<setting name="MapApiQueryKey" value="" />`

### Can I create a preconfigured solution if I have Microsoft Azure for DreamSpark?
At this time, you cannot create a preconfigured solution with a [Microsoft Azure for DreamSpark][lnk-dreamspark] account. However, you can create a [free trial account for Azure][lnk-30daytrial] in just a couple of minutes that will enable you create a preconfigured solution.

### How do I delete an AAD tenant?

See Eric Golpe's blog post [Walkthrough of Deleting an Azure AD Tenant][lnk-delete-aad-tennant].

[link-azuresupportticket]: https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade 
[lnk-azure-portal]: https://portal.azure.com
[lnk-azureiotsuite]: https://www.azureiotsuite.com/
[lnk-classic-portal]: https://manage.windowsazure.com
[lnk-remote-monitoring-github]: https://github.com/Azure/azure-iot-remote-monitoring 
[lnk-dreamspark]: https://www.dreamspark.com/Product/Product.aspx?productid=99 
[lnk-30daytrial]: https://azure.microsoft.com/free/
[lnk-delete-aad-tennant]: http://blogs.msdn.com/b/ericgolpe/archive/2015/04/30/walkthrough-of-deleting-an-azure-ad-tenant.aspx
