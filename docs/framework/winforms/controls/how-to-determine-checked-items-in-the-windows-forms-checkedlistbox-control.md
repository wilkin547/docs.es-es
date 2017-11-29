---
title: "Cómo: Determinar los elementos activados en el control CheckedListBox de formularios Windows Forms"
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
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f45006b437ad0a2fa537e6b8ea4312ab0060c882
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>Cómo: Determinar los elementos activados en el control CheckedListBox de formularios Windows Forms
Cuando se presentan los datos en un formulario Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, puede iterar a través de la colección almacenada en la <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> propiedad o paso a través de la lista mediante el <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método para determinar qué elementos están activados. El <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método toma un número de índice de elemento como argumento y devuelve `true` o `false`. Al contrario de lo que cabría esperar, el <xref:System.Windows.Forms.ListBox.SelectedItems%2A> y <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> propiedades no determinan qué elementos están activados, determinan qué elementos están resaltados.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>Para determinar los elementos activados en un control CheckedListBox  
  
1.  Recorrer en iteración el <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> colección, comenzando por 0, puesto que la colección está basada en cero. Tenga en cuenta que este método le dará el número del elemento en la lista de elementos activados, no en la lista global. Por lo que si no se comprueba el primer elemento de la lista y el segundo elemento esté activado, el código siguiente muestra texto como "Checked Item 1 = MyListItem2".  
  
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
       for(int x = 0; x <= checkedListBox1.CheckedItems.Count - 1 ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
    MessageBox.Show (s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x <= checkedListBox1->CheckedItems->Count - 1; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - O  
  
2.  Recorrer paso a paso la <xref:System.Windows.Forms.CheckedListBox.Items%2A> colección, comenzando por 0, puesto que la colección está basada en cero y llame al método el <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> método para cada elemento. Tenga en cuenta que este método le dará el número del elemento en la lista global, por lo que si el primer elemento de la lista no se comprueba y se comprueba el segundo elemento, se mostrará algo parecido a "elemento 2 = MyListItem2".  
  
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
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)
