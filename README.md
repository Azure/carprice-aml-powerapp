# Car Price Predictor - Power App and Power Automate Solution

This repo provides the required Power App and Power Automate solution required to complete the example deployment detailed in the "Enabling Citizen AI with the Power Platform and Azure" reference:::image type="content" source="Images/1.CarPriceAppFrontEnd.png" alt-text="Screenshot of Power Apps Car Price App":::

### Deploy this scenario

To deploy this end to end example, you must:

1. Follow this tutorial to [quickly train an ML model to predict the price of a car based on a range of input features](https://docs.microsoft.com/en-us/azure/machine-learning/tutorial-designer-automobile-price-train-score) and [deploy it as a real time REST endpoint](https://docs.microsoft.com/en-us/azure/machine-learning/tutorial-designer-automobile-price-deploy).
2. In Azure ML, navigate to Endpoints -> Realtime Endpoints and drill down on the one you just created in the previous step. Copy REST Endpoint ending in /score and navigate to the ‘Consume’ pane and copy one of the “Authentication Key”:::image type="content" source="Images/2.AMLEndpoint.png" alt-text="Screenshot of AML Endpoint Pane":::
3. Download the sample [Car Price Predictor - Power App and Power Automate solution](https://github.com/Azure/carprice-aml-powerapp/tree/main/CarPricePredictor%20Solution) that you can reuse and customize as required in your own environment. This is a Power Platform solution package file. Learn more about Solution packages: [Solutions in Power Apps - Power Apps | Microsoft Docs](https://docs.microsoft.com/en-us/powerapps/maker/data-platform/solutions-overview).
4. Go to the [Power Apps Maker portal](https://make.powerapps.com) and sign in using your credentials. If you do not have an existing Power Apps subscription, you can sign up for a [trial subscription](https://make.powerapps.com/signup?redirect=marketing&utm_source=PAMarketing&utm_medium=body&utm_campaign=getstartedfree&email=) or use a [Developer Plan](https://powerapps.microsoft.com/en-us/developerplan/).
5. In the Power Apps Maker portal, select your target environment to deploy the solution package. It is recommended to deploy on an Environment designated for learning or development/test.:::image type="content" source="Images/3.PowerAppMakerPortal.png" alt-text="Screenshot of Power Apps Maker Portal":::
6. Once you have selected your Environment, click on “Solutions” on the left blade to get to the Solutions page. Click “Import”.:::image type="content" source="Images/4.PowerAPPSolutionPane.png" alt-text="Screenshot of Solutions pane ":::
7. Browse to your downloaded solution zip package and click “Next”.:::image type="content" source="Images/5.PowerAppImportSolution.png" alt-text="Screenshot of PowerApps Importing a solution":::
8. Review the import summary. Click on “Import” to complete the import process.:::image type="content" source="Images/6.PowerAppImportSummary.png" alt-text="Screenshot of Power Apps Solution Import Summary":::
9. Once import is successful, you should see the solution “AML PowerApps CarPrice Sample” installed.:::image type="content" source="Images/7.PowerAppImportSuccessful.png" alt-text="Screenshot of Power Apps Import Confirmation":::
10. Click on the Solution display name “AML PowerApps CarPrice Sample” to open the solution. Here we will see two assets – a Power Automate Cloud Flow named “CarPricePredictionFlow” and a Power Apps Canvas app named “Car Price Predictor”.:::image type="content" source="Images/8.PowerAppSolutionsList.png" alt-text="Screenshot of Power Apps Solutions List":::
11. Next, we will need to update the AML End Point URL and API key for our solution. Select the context menu for CarPricePredictionFlow (click on the ellipsis) and select “Edit”. This will now launch Power Automate editor.:::image type="content" source="Images/9.PowerAppSelectSolution.png" alt-text="Screenshot of Power Apps Select CarPrice Solution":::
12. In Power Automate, expand the steps “ML API Key” and “ML Endpoint”. Paste the Authentication Key and the REST end point URL copied from step (2) above, into the “Value” fields respectively. Make sure the URL includes /score at the end. Click “Save”.:::image type="content" source="Images/10.PowerAppUpdateEndpoint.png" alt-text="Screenshot of Power Apps Update AML Endpoint Details":::
13. You may now close Power Automate. From the Power Apps Maker portal, click on “Apps”. You should see the Car Price Predictor app installed. Click on it to launch the app.:::image type="content" source="Images/11.PowerAppInstallVerification.png" alt-text="Screenshot of Power Apps Verfication of Solution Install":::
14. Make some selections and enter some values to the calculator screen, then click “Predict”. This will invoke the Cloud Flow, which calls the REST end point to the car price predictor in Azure ML and returns the value back to the app.:::image type="content" source="Images/12.PowerAppsHitPredict.png" alt-text="Screenshot of Power Apps Car Price App Front End":::

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
