# Car Price Predictor - Azure ML + Power App Solution

This repo provides the required Power App and Power Automate solution and step by step instructions required to complete the example deployment detailed in the "Enabling Citizen AI with the Power Platform and Azure" 
**Note:** A draft version of the document is available here: https://github.com/Azure/carprice-aml-powerapp/blob/main/V3%20DRAFT%20POWER%20APPS%20%2B%20AML%20Architecture.pdf

<p align ="center"><img src="/Images/1.CarPriceAppFrontEnd.png">

### Deploy this scenario

To deploy this end to end example, you must:

1. Follow this Azure ML tutorial to [quickly train an ML model to predict the price of a car based on a range of input features](https://docs.microsoft.com/en-us/azure/machine-learning/tutorial-designer-automobile-price-train-score) and [deploy it as a real time REST endpoint](https://docs.microsoft.com/en-us/azure/machine-learning/tutorial-designer-automobile-price-deploy).
2. In Azure ML, navigate to Endpoints -> Realtime Endpoints and drill down on the one you just created in the previous step. Copy REST Endpoint ending in /score and navigate to the ‘Consume’ pane and copy one of the “Authentication Key”<p align ="center"><img src="/Images/2.AMLEndpoint.png">
3. Download the sample [Car Price Predictor - Power App and Power Automate solution](https://github.com/Azure/carprice-aml-powerapp/tree/main/CarPricePredictor%20Solution) that you can reuse and customize as required in your own environment. This is a Power Platform solution package file. Learn more about Solution packages: [Solutions in Power Apps - Power Apps | Microsoft Docs](https://docs.microsoft.com/en-us/powerapps/maker/data-platform/solutions-overview).
4. Go to the [Power Apps Maker portal](https://make.powerapps.com) and sign in using your credentials. If you do not have an existing Power Apps subscription, you can sign up for a [trial subscription](https://make.powerapps.com/signup?redirect=marketing&utm_source=PAMarketing&utm_medium=body&utm_campaign=getstartedfree&email=) or use a [Developer Plan](https://powerapps.microsoft.com/en-us/developerplan/).
5. In the Power Apps Maker portal, select your target environment to deploy the solution package. It is recommended to deploy on an Environment designated for learning or development/test purpose.<p align ="center"><img src="/Images/3.PowerAppMakerPortal.png">
6. Once you have selected your Environment, click on “Solutions” on the left blade to get to the Solutions page. Click “Import”.<p align ="center"><img src="/Images/4.PowerAPPSolutionPane.png">
7. Select your downloaded solution zip file and click “Next”.<p align ="cemter"><img src="/Images/5.PowerAppImportSolution.png">
8. Review the import summary. Click on “Import” to complete the import process.<p align ="cemter"><img src="/Images/6.PowerAppImportSummary.png">
9. Once import is successful, you should see the solution “AML PowerApps CarPrice Sample” installed.<p align ="cemter"><img src="/Images/7.PowerAppImportSuccessful.png">
10. Click on the Solution display name “AML PowerApps CarPrice Sample” to open the solution. Here you will find two assets – a Power Automate Cloud Flow named “CarPricePredictionFlow” and a Power Apps Canvas app named “Car Price Predictor”.<p align ="cemter"><img src="/Images/8.PowerAppSolutionsList.png">
11. Next, we will need to update the AML End Point URL and Authentication key for our solution. Select the context menu for CarPricePredictionFlow (click on the ellipsis) and select “Edit”. This will now launch Power Automate editor.<p align ="cemter"><img src="/Images/9.PowerAppSelectSolution.png">
12. In Power Automate, expand the steps “ML API Key” and “ML Endpoint”. Paste the Authentication Key and the REST end point URL copied from step (2) above, into the “Value” fields respectively. Make sure the URL includes /score at the end. Click “Save”.<p align ="center"><img src="/Images/10.PowerAppUpdateEndpoint.png">
13. You may now close Power Automate. From the Power Apps Maker portal, click on “Apps”. You should see the Car Price Predictor app installed. Click on it to launch the app.<p align ="center"><img src="/Images/11.PowerAppInstallVerification.png">
14. Select a car make and change the values in the calculator screen, then click “Predict”. This will invoke the Cloud Flow, which calls the REST end point to the car price predictor in Azure ML and returns the value back to the app.<p align ="center"><img src="/Images/12.PowerAppsHitPredict.png">

### Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

### Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
