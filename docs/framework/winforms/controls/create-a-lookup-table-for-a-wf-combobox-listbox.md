---
title: 'Cómo: Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: 212cc229d8a496be11c84e30dbf3a0eedb952006
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529384"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>Cómo: Crear una tabla de búsqueda para un control ComboBox, ListBox o CheckedListBox de Windows Forms
A veces resulta útil mostrar datos en un formato fácil de usar en un formulario de Windows Forms y, no obstante, almacenar los datos en un formato más coherente para su programa. Por ejemplo, un formulario de pedido de comida puede mostrar los elementos del menú por nombre en un cuadro de lista. Sin embargo, la tabla de datos que registra el pedido contendría los números de identificador únicos que representan la comida. En las siguientes tablas se proporciona un ejemplo en el que se indica cómo almacenar y mostrar datos de formulario de pedido de comida.  
  
### <a name="orderdetailstable"></a>OrderDetailsTable  
  
|OrderID|ItemID|Cantidad|  
|-------------|------------|--------------|  
|4085|12|1|  
|4086|13|3|  
  
### <a name="itemtable"></a>ItemTable  
  
|Id.|nombre|  
|--------|----------|  
|12|Patata|  
|13|Pollo|  
  
 En este escenario, una tabla, **OrderDetailsTable**, almacena la información real que interesa mostrar y guardar. Pero para ahorrar espacio, lo hace en un modo bastante críptico. La otra tabla, **ItemTable**, contiene sólo información relativa al aspecto sobre qué identificador número equivale a qué nombre de comida y nada acerca de los pedidos de comida en Sí.  
  
 El **ItemTable** está conectado a la <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, o <xref:System.Windows.Forms.CheckedListBox> control mediante tres propiedades. El `DataSource` propiedad contiene el nombre de esta tabla. El `DisplayMember` propiedad contiene la columna de datos de esa tabla que desea mostrar en el control (el nombre de la comida). El `ValueMember` propiedad contiene la columna de datos de esa tabla que incluye la información almacenada (el número de Id.).  
  
 El **OrderDetailsTable** está conectada al control mediante su colección de enlaces, tiene acceso a través del <xref:System.Windows.Forms.Control.DataBindings%2A> propiedad. Cuando se agrega un objeto de enlace a la colección, se conecta una propiedad de control a un miembro de datos específico (la columna de números de Id.) de un origen de datos (el **OrderDetailsTable**). Cuando se realiza una selección en el control, la entrada de formulario se guarda en esta tabla.  
  
### <a name="to-create-a-lookup-table"></a>Para crear una tabla de búsqueda  
  
1.  Agregue un control <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox> o <xref:System.Windows.Forms.CheckedListBox> al formulario.  
  
2.  Conéctese a su origen de datos.  
  
3.  Establezca a una relación de datos entre las dos tablas. Vea [Introducción a los objetos DataRelation](http://msdn.microsoft.com/library/89d8a881-8265-41f2-a88b-61311ab06192).  
  
4.  Establezca las siguientes propiedades. Puede establecerse en código o en el diseñador.  
  
    |Property|Parámetro|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|La tabla que contiene la información sobre qué número de identificador equivale a qué elemento. En el escenario anterior, se trata de `ItemTable`.|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|La columna de la tabla de origen de datos que desea mostrar en el control. En el escenario anterior, se trata de `"Name"` (para establecer en el código, utilice las comillas).|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|La columna de la tabla de origen de datos que contiene la información almacenada. En el escenario anterior, se trata de `"ID"` (para establecer en el código, utilice las comillas).|  
  
5.  En un procedimiento llame al método <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> de la clase <xref:System.Windows.Forms.ControlBindingsCollection> para enlazar la propiedad <xref:System.Windows.Forms.ListControl.SelectedValue%2A> del control a la tabla que registra la entrada de formulario. También puede hacer esto en el diseñador en lugar de en el código, accediendo del control <xref:System.Windows.Forms.Control.DataBindings%2A> propiedad en el **propiedades** ventana. En el escenario anterior, se trata de `OrderDetailsTable`, y la columna es `"ItemID"`.  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Enlace de datos y Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Información general sobre ListBox (Control)](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 [Información general sobre el control ComboBox](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 [CheckedListBox Control Overview](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
