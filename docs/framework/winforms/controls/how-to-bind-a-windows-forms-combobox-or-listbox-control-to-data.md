---
title: "Cómo: Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b671910ac77b7456492cab871ace3abb61ac7fd7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="ad4fd-102">Cómo: Enlazar un control ComboBox o ListBox de formularios Windows Forms a datos</span><span class="sxs-lookup"><span data-stu-id="ad4fd-102">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="ad4fd-103">Puede enlazar la <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.ListBox> a los datos para realizar tareas como examinar datos en una base de datos, escribir nuevos datos o modificar datos existentes.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-103">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="ad4fd-104">Para enlazar un control ComboBox o ListBox</span><span class="sxs-lookup"><span data-stu-id="ad4fd-104">To bind a ComboBox or ListBox control</span></span>  
  
1.  <span data-ttu-id="ad4fd-105">Establecer el `DataSource` propiedad a un objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-105">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="ad4fd-106">Posibles orígenes de datos incluyen un <xref:System.Windows.Forms.BindingSource> enlazado a datos, una tabla de datos, una vista de datos, un conjunto de datos, la vista de datos de un administrador, una matriz o cualquier clase que implemente la <xref:System.Collections.IList> interfaz.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-106">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="ad4fd-107">Para obtener más información, consulte [orígenes de datos compatibles con formularios Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ad4fd-107">For more information, see [Data Sources Supported by Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="ad4fd-108">Si va a enlazar a una tabla, establecer el `DisplayMember` propiedad en el nombre de una columna en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-108">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="ad4fd-109">\- o -</span><span class="sxs-lookup"><span data-stu-id="ad4fd-109">\- or -</span></span>  
  
     <span data-ttu-id="ad4fd-110">Si va a enlazar a un <xref:System.Collections.IList>, establezca el miembro de presentación en una propiedad pública del tipo en la lista.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-110">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    >  <span data-ttu-id="ad4fd-111">Si se enlazan a un origen de datos que no implementa la <xref:System.ComponentModel.IBindingList> interfaz, como un <xref:System.Collections.ArrayList>, no se actualizará los datos del control enlazado cuando se actualiza el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-111">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="ad4fd-112">Por ejemplo, si tiene un cuadro combinado enlazado a un <xref:System.Collections.ArrayList> y se agregan datos a la <xref:System.Collections.ArrayList>, estos nuevos elementos no aparecerán en el cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-112">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="ad4fd-113">Sin embargo, puede forzar el cuadro combinado para actualizarse mediante una llamada a la <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> y <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> métodos en la instancia de la <xref:System.Windows.Forms.BindingContext> clase a la que está enlazado el control.</span><span class="sxs-lookup"><span data-stu-id="ad4fd-113">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad4fd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad4fd-114">See Also</span></span>  
 <xref:System.Windows.Forms.ComboBox>  
 <xref:System.Windows.Forms.ListBox>  
 [<span data-ttu-id="ad4fd-115">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad4fd-115">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="ad4fd-116">Enlace de datos y Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad4fd-116">Data Binding and Windows Forms</span></span>](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="ad4fd-117">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="ad4fd-117">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
