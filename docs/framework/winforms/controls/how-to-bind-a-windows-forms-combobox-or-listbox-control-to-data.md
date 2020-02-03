---
title: Enlazar un control ComboBox o ListBox a los datos
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
ms.openlocfilehash: 99d9b53b32d6faae888b134d4ed486980c05a75b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742034"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a>Cómo: Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos
Puede enlazar el <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> a los datos para realizar tareas como explorar datos en una base de datos, escribir nuevos datos o editar datos existentes.  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a>Para enlazar un control ComboBox o ListBox  
  
1. Establezca la propiedad `DataSource` en un objeto de origen de datos. Entre los orígenes de datos posibles se incluyen una <xref:System.Windows.Forms.BindingSource> enlazada a datos, una tabla de datos, una vista de datos, un conjunto de datos, un administrador de vistas de datos, una matriz o cualquier clase que implemente la interfaz <xref:System.Collections.IList>. Para obtener más información, vea [orígenes de datos compatibles con Windows Forms](../data-sources-supported-by-windows-forms.md).  
  
2. Si va a enlazar a una tabla, establezca la propiedad `DisplayMember` en el nombre de una columna del origen de datos.  
  
     \- O bien  
  
     Si va a enlazar a un <xref:System.Collections.IList>, establezca el miembro display en una propiedad pública del tipo en la lista.  
  
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
    > Si está enlazado a un origen de datos que no implementa la interfaz <xref:System.ComponentModel.IBindingList>, como una <xref:System.Collections.ArrayList>, los datos del control enlazado no se actualizarán cuando se actualice el origen de datos. Por ejemplo, si tiene un cuadro combinado enlazado a una <xref:System.Collections.ArrayList> y se agregan datos al <xref:System.Collections.ArrayList>, estos nuevos elementos no aparecerán en el cuadro combinado. Sin embargo, puede forzar que el cuadro combinado se actualice llamando a los métodos <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> y <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> en la instancia de la clase <xref:System.Windows.Forms.BindingContext> a la que está enlazado el control.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Enlace de datos en Windows Forms](../windows-forms-data-binding.md)
- [Enlace de datos y Windows Forms](../data-binding-and-windows-forms.md)
- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
