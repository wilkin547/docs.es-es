---
title: Procedimiento para agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: bd6614c76c63a44a7367ac7c7113c4db260c9a02
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640448"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="e97b8-102">Procedimiento para agregar y quitar elementos de un control ComboBox, ListBox o CheckedListBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e97b8-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="e97b8-103">Los elementos se pueden agregar a un cuadro combinado de Windows Forms, cuadro de lista, o activado la casilla de lista en una variedad de formas, ya que estos controles se pueden enlazar a una variedad de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="e97b8-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="e97b8-104">Sin embargo, en este tema se muestra el método más sencillo y no requiere ningún enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="e97b8-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="e97b8-105">Los elementos mostrados normalmente son cadenas; Sin embargo, puede utilizarse cualquier objeto.</span><span class="sxs-lookup"><span data-stu-id="e97b8-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="e97b8-106">El texto que se muestra en el control es el valor devuelto por el objeto `ToString` método.</span><span class="sxs-lookup"><span data-stu-id="e97b8-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="e97b8-107">Para agregar elementos</span><span class="sxs-lookup"><span data-stu-id="e97b8-107">To add items</span></span>  
  
1. <span data-ttu-id="e97b8-108">Agregue la cadena u objeto a la lista mediante el uso de la `Add` método de la `ObjectCollection` clase.</span><span class="sxs-lookup"><span data-stu-id="e97b8-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="e97b8-109">Se hace referencia a la colección utilizando el `Items` propiedad:</span><span class="sxs-lookup"><span data-stu-id="e97b8-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="e97b8-110">O</span><span class="sxs-lookup"><span data-stu-id="e97b8-110">or -</span></span>  
  
2. <span data-ttu-id="e97b8-111">Insertar la cadena u objeto en el punto deseado en la lista con el `Insert` método:</span><span class="sxs-lookup"><span data-stu-id="e97b8-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="e97b8-112">O</span><span class="sxs-lookup"><span data-stu-id="e97b8-112">or -</span></span>  
  
3. <span data-ttu-id="e97b8-113">Asigne una matriz completa a la `Items` colección:</span><span class="sxs-lookup"><span data-stu-id="e97b8-113">Assign an entire array to the `Items` collection:</span></span>  
  
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
  
### <a name="to-remove-an-item"></a><span data-ttu-id="e97b8-114">Para quitar un elemento</span><span class="sxs-lookup"><span data-stu-id="e97b8-114">To remove an item</span></span>  
  
1. <span data-ttu-id="e97b8-115">Llame a la `Remove` o `RemoveAt` método para eliminar elementos.</span><span class="sxs-lookup"><span data-stu-id="e97b8-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="e97b8-116">`Remove` tiene un argumento que especifica el elemento que se va a quitar.`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="e97b8-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="e97b8-117">Quita el elemento con el número de índice especificado.</span><span class="sxs-lookup"><span data-stu-id="e97b8-117">removes the item with the specified index number.</span></span>  
  
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
  
### <a name="to-remove-all-items"></a><span data-ttu-id="e97b8-118">Para quitar todos los elementos</span><span class="sxs-lookup"><span data-stu-id="e97b8-118">To remove all items</span></span>  
  
1. <span data-ttu-id="e97b8-119">Llame a la `Clear` método para quitar todos los elementos de la colección:</span><span class="sxs-lookup"><span data-stu-id="e97b8-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e97b8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e97b8-120">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="e97b8-121">Cómo: Ordenar el contenido de un Windows Forms control ComboBox, ListBox o CheckedListBox (Control)</span><span class="sxs-lookup"><span data-stu-id="e97b8-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="e97b8-122">Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="e97b8-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="e97b8-123">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="e97b8-123">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
