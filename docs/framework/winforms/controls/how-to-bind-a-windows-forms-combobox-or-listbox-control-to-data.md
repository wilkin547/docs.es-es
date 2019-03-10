---
title: Filtrar Enlazar un Control de ListBox o ComboBox de formularios Windows Forms a datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], binding to controls
- list boxes [Windows Forms], data binding
- ComboBox control [Windows Forms], data binding
- data binding [Windows Forms], combo boxes
- ListBox control [Windows Forms], data binding
- combo boxes [Windows Forms], data binding
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- data-bound controls [Windows Forms], Windows Forms
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
ms.openlocfilehash: c8eb224cbb8ec7ab271edaed8bb25f9cc7fb8ddc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709931"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Filtrar Enlazar un Control de ListBox o ComboBox de formularios Windows Forms a datos
Puede enlazar el <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> a datos para realizar tareas como la exploración de datos en una base de datos, escribir nuevos datos o modificar datos existentes.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Para enlazar un control ComboBox o ListBox  
  
1.  Establecer el `DataSource` propiedad a un objeto de origen de datos. Posibles orígenes de datos incluyen un <xref:System.Windows.Forms.BindingSource> enlazado a datos, una tabla de datos, una vista de datos, un conjunto de datos, la vista de datos de un administrador, una matriz o cualquier clase que implementa el <xref:System.Collections.IList> interfaz. Para obtener más información, consulte [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2.  Si va a enlazar a una tabla, establecer el `DisplayMember` propiedad en el nombre de una columna del origen de datos.  
  
     \- o -  
  
     Si va a enlazar a un <xref:System.Collections.IList>, establezca el miembro de presentación a una propiedad pública del tipo en la lista.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
    ```  
  
    > [!NOTE]
    >  Si está enlazado a un origen de datos que no implementa la <xref:System.ComponentModel.IBindingList> interfaz, como un <xref:System.Collections.ArrayList>, no se actualizará los datos del control enlazado cuando se actualiza el origen de datos. Por ejemplo, si tiene un cuadro combinado enlazado a un <xref:System.Collections.ArrayList> y se agregan datos a la <xref:System.Collections.ArrayList>, estos nuevos elementos no aparecerán en el cuadro combinado. Sin embargo, puede forzar el cuadro combinado para actualizarse mediante una llamada a la <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> y <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> métodos en la instancia de la <xref:System.Windows.Forms.BindingContext> al que está enlazado el control de clases.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Enlace de datos y Windows Forms](../data-binding-and-windows-forms.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
