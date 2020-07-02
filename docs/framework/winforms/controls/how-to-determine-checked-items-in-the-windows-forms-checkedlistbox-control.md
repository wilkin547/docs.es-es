---
title: Determinar los elementos activados en el control CheckedListBox
description: Obtenga información sobre cómo determinar los elementos activados en el control CheckedListBox Windows Forms recorriendo en iteración la colección almacenada en la propiedad CheckedItems.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: fd8845ef83da7406ff4f1468506a23e3f4d386a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618355"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Procedimiento para determinar los elementos activados en el control CheckedListBox de formularios Windows Forms
Al presentar los datos en un <xref:System.Windows.Forms.CheckedListBox> control de Windows Forms, puede recorrer en iteración la colección almacenada en la <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> propiedad o recorrer la lista con el <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método para determinar qué elementos están comprobados. El <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método toma un número de índice de elemento como argumento y devuelve `true` o `false` . Contrariamente a lo que cabría esperar, <xref:System.Windows.Forms.ListBox.SelectedItems%2A> las <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> propiedades y no determinan qué elementos se comprueban; determinan qué elementos se resaltan.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Para determinar los elementos activados en un control CheckedListBox  
  
1. Recorrer en iteración la <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> colección, empezando por 0 porque la colección es de base cero. Tenga en cuenta que este método le proporcionará el número de elemento en la lista de elementos activados, no la lista global. Por lo tanto, si el primer elemento de la lista no está activado y el segundo elemento está activado, el código siguiente mostrará texto como "Checked Item 1 = MyListItem2".  
  
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
  
     - O  
  
2. Desplazarse por la <xref:System.Windows.Forms.CheckedListBox.Items%2A> colección, empezando por 0 porque la colección es de base cero y llama al <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método para cada elemento. Tenga en cuenta que este método le proporcionará el número de elemento en la lista general, por lo que si el primer elemento de la lista no está activado y el segundo elemento está activado, se mostrará algo parecido a "Item 2 = MyListItem2".  
  
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
  
## <a name="see-also"></a>Vea también

- [Controles de formularios Windows Forms usados para mostrar opciones](windows-forms-controls-used-to-list-options.md)
