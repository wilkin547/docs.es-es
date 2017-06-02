---
title: "C&#243;mo: Crear una tabla de b&#250;squeda para un control ComboBox, ListBox o CheckedListBox de Windows Forms | Microsoft Docs"
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
  - "CheckedListBox (control) [Windows Forms], crear tablas de búsqueda"
  - "cuadros combinados, tablas de búsqueda"
  - "ComboBox (control) [Windows Forms], tabla de búsqueda"
  - "cuadros de lista, tablas de búsqueda"
  - "ListBox (control) [Windows Forms], crear tablas de búsqueda"
  - "ListBox (control) [Windows Forms], tablas de búsqueda"
  - "tablas de búsqueda"
  - "tablas de búsqueda, crear para controles"
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Crear una tabla de b&#250;squeda para un control ComboBox, ListBox o CheckedListBox de Windows Forms
A veces resulta útil mostrar datos en un formato fácil de usar en un formulario de Windows Forms y, no obstante, almacenar los datos en un formato más coherente para su programa.  Por ejemplo, un formulario de pedido de comida puede mostrar los elementos del menú por nombre en un cuadro de lista.  Sin embargo, la tabla de datos que registra el pedido contendría los números de identificador únicos que representan la comida.  En las siguientes tablas se proporciona un ejemplo en el que se indica cómo almacenar y mostrar datos de formulario de pedido de comida.  
  
### OrderDetailsTable  
  
|OrderID|ItemID|Cantidad|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### ItemTable  
  
|Id.|Nombre|  
|---------|------------|  
|12|Patata|  
|13|Pollo|  
  
 En este escenario, una tabla, OrderDetailsTable, almacena la información real que a usted le interesa mostrar y guardar.  Pero para ahorrar espacio, lo hace en un modo bastante críptico.  La otra tabla, ItemTable, solo contiene información relativa al aspecto sobre qué número de Id. de cliente equivale a qué nombre de comida y nada sobre los pedidos de comida en sí.  
  
 La tabla ItemTable está conectada al control <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> control mediante tres propiedades.  La propiedad  `DataSource`  contiene el nombre de esta tabla.  La propiedad  `DisplayMember` contiene la columna de datos de esa tabla que quiere mostrar en el control \(el nombre de la comida\).  La propiedad  `ValueMember`  contiene la columna de datos de esa con la información almacenada \(número de Id.\).  
  
 La tabla OrderDetailsTable está conectada al control mediante su colección de enlaces, a la que se accede mediante la propiedad <xref:System.Windows.Forms.Control.DataBindings%2A>.  Cuando se agrega un objeto de enlace a la colección, se conecta una propiedad de control a un miembro de datos específico \(la columna de números de Id.\) de un origen de datos \(la tabla OrderDetailsTable\).  Cuando se realiza una selección en el control, la entrada de formulario se guarda en esta tabla.  
  
### Para crear una tabla de búsqueda  
  
1.  Agregue un control <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al formulario.  
  
2.  Conéctese a su origen de datos.  
  
3.  Establezca a una relación de datos entre las dos tablas.  Consulte [Introducción a los objetos DataRelation](../Topic/Introduction%20to%20DataRelation%20Objects.md).  
  
4.  Establezca las siguientes propiedades.  Puede establecerse en código o en el diseñador.  
  
    |Propiedad|Configuración|  
    |---------------|-------------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|La tabla que contiene la información sobre qué número de identificador equivale a qué elemento.  En el escenario anterior es  `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|La columna de la tabla de origen de datos que desea mostrar en el control.  En el escenario anterior es  `"Name"`  \(para establecer en el código, utilice comillas\).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|La columna de la tabla de origen de datos que contiene la información almacenada.  En el escenario anterior es  `"ID"`  \(para establecer en el código, utilice comillas\).|  
  
5.  En un procedimiento llame al método <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> de la clase <xref:System.Windows.Forms.ControlBindingsCollection> para enlazar la propiedad <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del control a la tabla que registra la entrada de formulario.  También puede hacerlo en el Diseñador en lugar de en el código, accediendo a la propiedad <xref:System.Windows.Forms.Control.DataBindings%2A> del control en la ventana **Propiedades**.  En el escenario anterior es  `OrderDetailsTable` y la columna es  `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
  
    ```  
  
## Vea también  
 [Enlace de datos y formularios Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Información general sobre ListBox \(Control\)](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)   
 [Información general sobre el control ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)   
 [Información general sobre el control CheckedListBox](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)