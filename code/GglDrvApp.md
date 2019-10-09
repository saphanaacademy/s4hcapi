### Code for S4HC APIs and Open Connectors Dev Video

**********************

Part 1 > App View Table (xml)

**********************

```
<Table width="auto" id="productlist" items="{/A_PlannedOrder}" updateFinished="onListUpdateFinished" noDataText="No planned orders data" class="sapUiResponsiveMargin">
	<headerToolbar>
		<Toolbar id="lineItemsToolbar">
			<Button text="Upload to Google Drive" press="onUploadToGoogleDrive"></Button>
		</Toolbar>
	</headerToolbar>
	<columns>
		<Column>
			<Text text="Planned Order"/>
		</Column>
		<Column minScreenWidth="Tablet" demandPopin="true">
			<Text text="Supplier"/>
		</Column>
		<Column minScreenWidth="Tablet" demandPopin="true" hAlign="End">
			<Text text="Quantity"/>
		</Column>
	</columns>
	<items>
		<ColumnListItem>
			<cells>
				<ObjectIdentifier title="{PlannedOrder}-{Material}" text="{MaterialName}"/>
				<Text text="{ProductionPlant}"/>
				<ObjectNumber number="{ path: 'TotalQuantity'}"/>
			</cells>
		</ColumnListItem>
	</items>
</Table>
```

**********************

Part 2 > Neo-App (json)

**********************

```
{
	"path": "/DPE_APIM_DEST",
	"target": {
		"type": "destination",
		"name": "DPE_APIM_DEST"
	},
	"description": "API Management"
},
```

**********************

Part 3 > App Controller (js)

**********************

```
onUploadToGoogleDrive: function () {

	sap.ui.core.BusyIndicator.show();
			
	var oModel = this.getView().getModel();
	
	var oExport = new sap.ui.core.util.Export({
		exportType: new sap.ui.core.util.ExportTypeCSV({
			separatorChar: ";",
			charSet: "UTF-8"
		}),
		models: oModel,
		rows: {
			path: "/A_PlannedOrder"
		},
		columns: [
			{
				name: "Planned Order",
				template: {
					content: {
						path: "PlannedOrder"
					}
				}
			}, 
			{
				name: "Production Plant",
				template: {
					content: {
						path: "ProductionPlant"				
					}
				}
			}, 
			{
				name: "Material",
				template: {
					content: {
						path: "Material"
					}
				}
			}, 
			{
				name: "Quantity",
				template: {
					content: {
						path: "TotalQuantity"
					}
				}
			}
		]
	});
	
	oExport.generate().done(function (data) {
		
		var xhr = new XMLHttpRequest();	

		xhr.onreadystatechange = function () {
			if (xhr.readyState === XMLHttpRequest.DONE) {
				sap.ui.core.BusyIndicator.hide();
				MessageToast.show(xhr.responseText);
			}
		};

		xhr.open('POST', '/DPE_OPENCONN_APIM_DEST</yourid#trial>/GoogleDrive/files/?path=%2Fdata.csv', false);

		var formData = new FormData();
		formData.append("file", data);
		xhr.send(formData);
	
	}).always(function () {
		this.destroy();
		});
	
}
```
