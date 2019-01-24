---
title: Procedimiento Determinar los elementos activados en el Control CheckedListBox de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: e1f8f7fa1f3f351314ac1d454d591f46654d8f81
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643603"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="eea50-102">Procedimiento Determinar los elementos activados en el Control CheckedListBox de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="eea50-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="eea50-103">Cuando se presentan datos en un formulario Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, puede iterar a través de la colección almacenada en el <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> propiedad o paso a través de la lista mediante el <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método para determinar qué elementos están activados.</span><span class="sxs-lookup"><span data-stu-id="eea50-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="eea50-104">El <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método toma un número de índice del elemento como argumento y devuelve `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="eea50-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="eea50-105">Al contrario de lo que cabría esperar, el <xref:System.Windows.Forms.ListBox.SelectedItems%2A> y <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> propiedades no determinan qué elementos están activados, determinan qué elementos se resaltan.</span><span class="sxs-lookup"><span data-stu-id="eea50-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="eea50-106">Para determinar los elementos activados en un control CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="eea50-106">To determine checked items in a CheckedListBox control</span></span>  
  
1.  <span data-ttu-id="eea50-107">Recorrer en iteración el <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> colección, empezando en 0, dado que la colección está basado en cero.</span><span class="sxs-lookup"><span data-stu-id="eea50-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="eea50-108">Tenga en cuenta que este método le dará el número de elemento en la lista de elementos activados, no en la lista global.</span><span class="sxs-lookup"><span data-stu-id="eea50-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="eea50-109">Por lo que si no se comprueba el primer elemento en la lista y el segundo elemento está activado, el código siguiente mostrará texto como "elemento activado 1 = MyListItem2".</span><span class="sxs-lookup"><span data-stu-id="eea50-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - <span data-ttu-id="eea50-110">O</span><span class="sxs-lookup"><span data-stu-id="eea50-110">or -</span></span>  
  
2.  <span data-ttu-id="eea50-111">Recorrer paso a paso el <xref:System.Windows.Forms.CheckedListBox.Items%2A> colección, empezando en 0, ya que está basado en cero, la colección y llamar a la <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="eea50-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="eea50-112">Tenga en cuenta que este método le dará el número de elemento en la lista global, por lo que si el primer elemento de la lista no está activada y el segundo elemento está activado, mostrará algo parecido a "elemento 2 = MyListItem2".</span><span class="sxs-lookup"><span data-stu-id="eea50-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eea50-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="eea50-113">See also</span></span>
- [<span data-ttu-id="eea50-114">Controles de formularios Windows Forms usados para mostrar opciones</span><span class="sxs-lookup"><span data-stu-id="eea50-114">Windows Forms Controls Used to List Options</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
