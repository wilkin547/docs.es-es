---
title: "C&#243;mo: Crear listas principal-detalle con el control DataGrid de Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGrid (control) [Windows Forms], listas principal-detalle"
  - "listas principal-detalle"
  - "tablas relacionadas, mostrar en un control DataGrid"
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Crear listas principal-detalle con el control DataGrid de Windows Forms
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Si un objeto <xref:System.Data.DataSet> contiene una serie de tablas relacionadas, puede utilizar dos controles <xref:System.Windows.Forms.DataGrid> para mostrar los datos en formato principal\-detalle.  De este modo, un control <xref:System.Windows.Forms.DataGrid> se designa como cuadrícula principal y el otro como cuadrícula de detalles.  Al seleccionar una entrada en la lista principal, la lista de detalles muestra todas las entradas secundarias relacionadas.  Por ejemplo, si el objeto <xref:System.Data.DataSet> contiene una tabla Customers y una tabla relacionada Orders, se especificaría la tabla Customers como cuadrícula principal y la tabla Orders como cuadrícula de detalles.  Al seleccionar un cliente en la cuadrícula principal, la cuadrícula de detalles mostraría todos los pedidos asociados con ese cliente en la tabla Orders.  
  
### Para establecer una relación principal\-detalle mediante programación  
  
1.  Cree dos nuevos controles <xref:System.Windows.Forms.DataGrid> y establezca sus propiedades.  
  
2.  Agregue tablas al conjunto de datos.  
  
3.  Declare una variable de tipo <xref:System.Data.DataRelation> para representar la relación que desea crear.  
  
4.  Cree una instancia de la relación; para ello, especifique un nombre para la relación y la tabla, columna y elemento que enlazarán las dos tablas.  
  
5.  Agregue la relación a la colección <xref:System.Data.DataSet.Relations%2A> del objeto <xref:System.Data.DataSet>.  
  
6.  Utilice el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> de <xref:System.Windows.Forms.DataGrid> para enlazar las cuadrículas a <xref:System.Data.DataSet>.  
  
     El ejemplo siguiente muestra cómo establecer una relación principal\-detalle entre las tablas Customers y Orders de un objeto <xref:System.Data.DataSet> \(`ds`\) generado previamente.  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## Vea también  
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)