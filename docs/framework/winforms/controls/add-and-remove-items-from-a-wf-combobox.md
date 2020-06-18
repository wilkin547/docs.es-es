---
title: Agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox
ms.date: 03/30/2017
description: Obtenga información sobre cómo agregar y quitar un Windows Forms controles ComboBox, ListBox y CheckedListBox simplemente y sin enlace de datos.
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: f3701257bbe410bf03c4c21700705e87b581bf2e
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904447"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="3f333-103">Procedimiento para agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f333-103">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="3f333-104">Los elementos se pueden agregar a un Windows Forms cuadro combinado, un cuadro de lista o un cuadro de lista activado de diversas formas, ya que estos controles pueden estar enlazados a diversos orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="3f333-104">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="3f333-105">Sin embargo, en este tema se muestra el método más sencillo y no se requiere ningún enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="3f333-105">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="3f333-106">Los elementos que se muestran suelen ser cadenas; sin embargo, se puede usar cualquier objeto.</span><span class="sxs-lookup"><span data-stu-id="3f333-106">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="3f333-107">El texto que se muestra en el control es el valor devuelto por el método del objeto `ToString` .</span><span class="sxs-lookup"><span data-stu-id="3f333-107">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="3f333-108">Para agregar elementos</span><span class="sxs-lookup"><span data-stu-id="3f333-108">To add items</span></span>  
  
1. <span data-ttu-id="3f333-109">Agregue la cadena o el objeto a la lista utilizando el `Add` método de la `ObjectCollection` clase.</span><span class="sxs-lookup"><span data-stu-id="3f333-109">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="3f333-110">Se hace referencia a la colección mediante la `Items` propiedad:</span><span class="sxs-lookup"><span data-stu-id="3f333-110">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="3f333-111">O</span><span class="sxs-lookup"><span data-stu-id="3f333-111">or -</span></span>  
  
2. <span data-ttu-id="3f333-112">Inserte la cadena u objeto en el punto deseado de la lista con el `Insert` método:</span><span class="sxs-lookup"><span data-stu-id="3f333-112">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="3f333-113">O</span><span class="sxs-lookup"><span data-stu-id="3f333-113">or -</span></span>  
  
3. <span data-ttu-id="3f333-114">Asigne una matriz completa a la `Items` colección:</span><span class="sxs-lookup"><span data-stu-id="3f333-114">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="3f333-115">Para quitar un elemento</span><span class="sxs-lookup"><span data-stu-id="3f333-115">To remove an item</span></span>  
  
1. <span data-ttu-id="3f333-116">Llame al `Remove` `RemoveAt` método o para eliminar elementos.</span><span class="sxs-lookup"><span data-stu-id="3f333-116">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="3f333-117">`Remove`tiene un argumento que especifica el elemento que se va a quitar.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="3f333-117">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="3f333-118">quita el elemento con el número de índice especificado.</span><span class="sxs-lookup"><span data-stu-id="3f333-118">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="3f333-119">Para quitar todos los elementos</span><span class="sxs-lookup"><span data-stu-id="3f333-119">To remove all items</span></span>  
  
1. <span data-ttu-id="3f333-120">Llame al `Clear` método para quitar todos los elementos de la colección:</span><span class="sxs-lookup"><span data-stu-id="3f333-120">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3f333-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f333-121">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="3f333-122">Procedimiento para ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3f333-122">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="3f333-123">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="3f333-123">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="3f333-124">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="3f333-124">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
