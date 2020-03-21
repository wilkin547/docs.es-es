---
title: Determinar elementos comprobados en CheckedListBox Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5d93a63e9c1c6aae91ecfe83590c59450a565afe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182190"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Cómo: Determinar los elementos activados en el control CheckedListBox de formularios Windows Forms
Al presentar datos en <xref:System.Windows.Forms.CheckedListBox> un control de formularios Windows Forms, <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> puede recorrer en iteración <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> la colección almacenada en la propiedad o recorrer la lista mediante el método para determinar qué elementos se comprueban. El <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método toma un número de `true` índice `false`de elemento como argumento y devuelve o . Contrariamente a lo que <xref:System.Windows.Forms.ListBox.SelectedItems%2A> <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> cabría esperar, las propiedades y no determinan qué elementos se comprueban; determinan qué elementos se resaltan.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Para determinar los elementos comprobados en un control CheckedListBox  
  
1. Repasar en <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> iteración la colección, a partir de 0 ya que la colección se basa en cero. Tenga en cuenta que este método le dará el número de elemento en la lista de elementos marcados, no la lista general. Por lo tanto, si el primer elemento de la lista no está marcado y el segundo elemento está marcado, el código siguiente mostrará texto como "Elemento comprobado 1 - MyListItem2".  
  
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
  
     - O bien  
  
2. Pase por <xref:System.Windows.Forms.CheckedListBox.Items%2A> la colección, a partir de 0 ya que la colección está basada en cero y llame al <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método para cada elemento. Tenga en cuenta que este método le dará el número de elemento en la lista general, por lo que si el primer elemento de la lista no está marcado y el segundo elemento está marcado, mostrará algo como "Elemento 2 - MyListItem2".  
  
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
  
## <a name="see-also"></a>Consulte también

- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
