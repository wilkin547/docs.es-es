---
title: Determinar los elementos activados en el control CheckedListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5854f7e6be759daeb604458ea8554d3c98ed39c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743242"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Cómo: Determinar los elementos activados en el control CheckedListBox de formularios Windows Forms
Al presentar los datos en un control <xref:System.Windows.Forms.CheckedListBox> de Windows Forms, puede recorrer en iteración la colección almacenada en la propiedad <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> o recorrer la lista con el método <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> para determinar qué elementos están comprobados. El método <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> toma un número de índice de elemento como argumento y devuelve `true` o `false`. Al contrario de lo que cabría esperar, las propiedades <xref:System.Windows.Forms.ListBox.SelectedItems%2A> y <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> no determinan qué elementos se comprueban; determinan qué elementos se resaltan.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Para determinar los elementos activados en un control CheckedListBox  
  
1. Recorrer en iteración la colección de <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>, empezando por 0 porque la colección es de base cero. Tenga en cuenta que este método le proporcionará el número de elemento en la lista de elementos activados, no la lista global. Por lo tanto, si el primer elemento de la lista no está activado y el segundo elemento está activado, el código siguiente mostrará texto como "Checked Item 1 = MyListItem2".  
  
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
  
2. Recorra paso a paso la colección de <xref:System.Windows.Forms.CheckedListBox.Items%2A>, empezando por 0 porque la colección es de base cero y llama al método <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> para cada elemento. Tenga en cuenta que este método le proporcionará el número de elemento en la lista general, por lo que si el primer elemento de la lista no está activado y el segundo elemento está activado, se mostrará algo parecido a "Item 2 = MyListItem2".  
  
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
