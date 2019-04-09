---
title: Filtrar Habilitar AutoComplete en los controles ToolStrip de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: 48c1d24ce2e966f9c078593655da2bc9d84252c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112117"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="1e07f-102">Filtrar Habilitar AutoComplete en los controles ToolStrip de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e07f-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="1e07f-103">El procedimiento siguiente combina una <xref:System.Windows.Forms.ToolStripLabel> con un <xref:System.Windows.Forms.ToolStripComboBox> que se puede desplegar hacia abajo mostrar una lista de elementos, tales como recientemente de los sitios Web visitados.</span><span class="sxs-lookup"><span data-stu-id="1e07f-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="1e07f-104">Si el usuario escribe un carácter que coincide con el primer carácter de uno de los elementos de la lista, el elemento se muestra inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="1e07f-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e07f-105">Finalización automática funciona con `ToolStrip` controles de la misma manera que funciona con controles tradicionales como <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1e07f-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="1e07f-106">Para habilitar AutoComplete en un control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1e07f-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1.  <span data-ttu-id="1e07f-107">Crear un <xref:System.Windows.Forms.ToolStrip> controlar y agregarle elementos.</span><span class="sxs-lookup"><span data-stu-id="1e07f-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2.  <span data-ttu-id="1e07f-108">Establecer el <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> propiedad de la etiqueta y el cuadro combinado para <xref:System.Windows.Forms.ToolStripItemOverflow.Never> para que la lista esté siempre disponible sin tener en cuenta el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="1e07f-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3.  <span data-ttu-id="1e07f-109">Agregar palabras a la colección de elementos de la <xref:System.Windows.Forms.ToolStripComboBox> control.</span><span class="sxs-lookup"><span data-stu-id="1e07f-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4.  <span data-ttu-id="1e07f-110">Establecer el <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> propiedad del cuadro combinado para <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span><span class="sxs-lookup"><span data-stu-id="1e07f-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5.  <span data-ttu-id="1e07f-111">Establecer el <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> propiedad del cuadro combinado para <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span><span class="sxs-lookup"><span data-stu-id="1e07f-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1e07f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e07f-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [<span data-ttu-id="1e07f-113">Información sobre el control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1e07f-113">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="1e07f-114">Arquitectura del control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1e07f-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="1e07f-115">Resumen de la tecnología ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1e07f-115">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
