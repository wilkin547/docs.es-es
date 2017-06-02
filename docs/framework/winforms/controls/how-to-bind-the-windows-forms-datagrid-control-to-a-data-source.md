---
title: "C&#243;mo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos | Microsoft Docs"
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
  - "controles enlazados"
  - "controles enlazados, DataGrid (control)"
  - "enlace de datos, DataGrid (control)"
  - "controles enlazados a datos, DataGrid"
  - "DataGrid (control) [Windows Forms], enlace de datos"
  - "conjuntos de datos [Windows Forms], enlazar a un control DataGrid"
  - "controles de Windows Forms, enlace de datos"
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 El control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms está diseñado especialmente para mostrar información sobre un origen de datos.  Enlaza el control en tiempo de ejecución llamando al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.  Aunque se pueden mostrar datos de diversos orígenes de datos, los más comunes son los conjuntos de datos y las vistas de datos.  
  
### Para enlazar el control DataGrid mediante programa  
  
1.  Escriba código para llenar el conjunto de datos.  
  
     Si el origen de datos es un conjunto de datos o una vista de datos basado en una tabla de un conjunto de datos, agregue código al formulario para rellenar el conjunto de datos.  
  
     El código exacto depende del lugar del que vaya a obtener los datos el conjunto de datos.  Si el conjunto de datos se va a rellenar directamente a partir de la base de datos, normalmente se invoca al método `Fill`  de un adaptador de datos, como en el ejemplo siguiente, que rellena un conjunto de datos denominado `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Si el conjunto de datos se rellena a partir de un servicio Web XML, normalmente creará una instancia del servicio en el código y, a continuación, invocará a uno de sus métodos para devolver un conjunto de datos.  A continuación, combinará el conjunto de datos del servicio Web XML con el conjunto de datos local.  El ejemplo siguiente muestra cómo crear una instancia de un servicio Web XML denominado `CategoriesService`, llamar a su método `GetCategories` y combinar el conjunto de datos resultante con un conjunto de datos local denominado `DsCategories1`:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2.  Invoque al método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del control <xref:System.Windows.Forms.DataGrid> y pásele el origen de datos y un miembro de datos.  Si no necesita pasar explícitamente un miembro de datos, pase una cadena vacía.  
  
    > [!NOTE]
    >  Si está enlazando la cuadrícula por primera vez, puede establecer las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> del control.  Sin embargo, no podrá restablecer estas propiedades una vez que las haya establecido.  Por lo tanto, se recomienda utilizar siempre el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.  
  
     El ejemplo siguiente muestra cómo se puede enlazar mediante programa con la tabla Customers de un conjunto de datos denominado `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Si la tabla Customers es la única tabla en el conjunto de datos, también puede enlazar la cuadrícula del modo siguiente:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  \(Opcional\) Agregue los estilos de tabla y de columna adecuados a la cuadrícula.  Si no hay estilos de tabla, verá la tabla, pero con un formato mínimo y con todas las columnas visibles.  
  
## Vea también  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)