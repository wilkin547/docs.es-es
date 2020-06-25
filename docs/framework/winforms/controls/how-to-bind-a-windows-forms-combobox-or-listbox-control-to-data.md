---
title: Enlazar un control ComboBox o ListBox a los datos
description: Obtenga información sobre cómo enlazar el cuadro combinado de Windows Forms y el cuadro de lista a los datos para realizar tareas como la exploración de datos en una base de datos, la entrada de nuevos datos o la edición de datos existentes.
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
ms.openlocfilehash: 0c07dc90ddc91061c5f34b5a237082cb444e89d9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324064"
---
# <a name="how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data"></a><span data-ttu-id="ce4b4-103">Procedimiento para enlazar un control ComboBox o ListBox de formularios Windows Forms a datos</span><span class="sxs-lookup"><span data-stu-id="ce4b4-103">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>
<span data-ttu-id="ce4b4-104">Puede enlazar los <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.ListBox> datos y a los datos para realizar tareas como la exploración de datos en una base de datos, la entrada de nuevos datos o la edición de datos existentes.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-104">You can bind the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.ListBox> to data to perform tasks such as browsing data in a database, entering new data, or editing existing data.</span></span>  
  
### <a name="to-bind-a-combobox-or-listbox-control"></a><span data-ttu-id="ce4b4-105">Para enlazar un control ComboBox o ListBox</span><span class="sxs-lookup"><span data-stu-id="ce4b4-105">To bind a ComboBox or ListBox control</span></span>  
  
1. <span data-ttu-id="ce4b4-106">Establezca la `DataSource` propiedad en un objeto de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-106">Set the `DataSource` property to a data source object.</span></span> <span data-ttu-id="ce4b4-107">Entre los orígenes de datos posibles se incluyen un <xref:System.Windows.Forms.BindingSource> enlazado a datos, una tabla de datos, una vista de datos, un conjunto de datos, un administrador de vistas de datos, una matriz o cualquier clase que implemente la <xref:System.Collections.IList> interfaz.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-107">Possible data sources include a <xref:System.Windows.Forms.BindingSource> bound to data, a data table, a data view, a dataset, a data view manager, an array, or any class that implements the <xref:System.Collections.IList> interface.</span></span> <span data-ttu-id="ce4b4-108">Para obtener más información, vea [orígenes de datos compatibles con Windows Forms](../data-sources-supported-by-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ce4b4-108">For more information, see [Data Sources Supported by Windows Forms](../data-sources-supported-by-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="ce4b4-109">Si va a enlazar a una tabla, establezca la `DisplayMember` propiedad en el nombre de una columna del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-109">If you are binding to a table, set the `DisplayMember` property to the name of a column in the data source.</span></span>  
  
     <span data-ttu-id="ce4b4-110">\- o -</span><span class="sxs-lookup"><span data-stu-id="ce4b4-110">\- or -</span></span>  
  
     <span data-ttu-id="ce4b4-111">Si va a enlazar a <xref:System.Collections.IList> , establezca el miembro de presentación en una propiedad pública del tipo en la lista.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-111">If you are binding to an <xref:System.Collections.IList>, set the display member to a public property of the type in the list.</span></span>  
  
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
    > <span data-ttu-id="ce4b4-112">Si está enlazado a un origen de datos que no implementa la <xref:System.ComponentModel.IBindingList> interfaz, como <xref:System.Collections.ArrayList> , los datos del control enlazado no se actualizarán cuando se actualice el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-112">If you are bound to a data source that does not implement the <xref:System.ComponentModel.IBindingList> interface, such as an <xref:System.Collections.ArrayList>, the bound control's data will not be updated when the data source is updated.</span></span> <span data-ttu-id="ce4b4-113">Por ejemplo, si tiene un cuadro combinado enlazado a un <xref:System.Collections.ArrayList> y los datos se agregan a <xref:System.Collections.ArrayList> , estos nuevos elementos no aparecerán en el cuadro combinado.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-113">For example, if you have a combo box bound to an <xref:System.Collections.ArrayList> and data is added to the <xref:System.Collections.ArrayList>, these new items will not appear in the combo box.</span></span> <span data-ttu-id="ce4b4-114">Sin embargo, puede forzar que el cuadro combinado se actualice llamando a <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> los <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> métodos y en la instancia de la <xref:System.Windows.Forms.BindingContext> clase a la que está enlazado el control.</span><span class="sxs-lookup"><span data-stu-id="ce4b4-114">However, you can force the combo box to be updated by calling the <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> and <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> methods on the instance of the <xref:System.Windows.Forms.BindingContext> class to which the control is bound.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4b4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce4b4-115">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="ce4b4-116">Enlace de datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce4b4-116">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="ce4b4-117">Enlace de datos y formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce4b4-117">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="ce4b4-118">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="ce4b4-118">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
