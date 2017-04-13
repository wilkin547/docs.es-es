---
title: "C&#243;mo: Determinar los elementos activados en el control CheckedListBox de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "casillas, determinar el estado activado"
  - "CheckedListBox (control) [Windows Forms], determinar el estado activado"
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Determinar los elementos activados en el control CheckedListBox de formularios Windows Forms
Cuando presente datos en un control <xref:System.Windows.Forms.CheckedListBox> de formularios Windows Forms, puede recorrer en iteración la colección almacenada en la propiedad <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> o desplazarse por la lista con el método <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> para determinar qué elementos están activados.  El método <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> toma un número de índice del elemento como argumento y devuelve `true` o `false`.  Al contrario de lo que podría esperarse, las propiedades <xref:System.Windows.Forms.ListBox.SelectedItems%2A> y <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> no determinan qué elementos están activados, sino que determinan los elementos resaltados.  
  
### Para determinar los elementos activados en un control CheckedListBox  
  
1.  Recorra en iteración la colección <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>, empezando por el elemento de índice 0, puesto que la colección está basada en 0.  Tenga en cuenta que este método le dará el número de elemento de la lista de elementos activados, no de la lista general.  Por lo tanto, si el primer elemento de la lista no está activado y el segundo sí lo está, el código siguiente mostrará texto como "Checked Item 1 \= MyListItem2".  
  
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
  
     O bien  
  
2.  Desplácese por la colección <xref:System.Windows.Forms.CheckedListBox.Items%2A>, empezando por el elemento de índice 0, puesto que la colección está basada en 0, e invoque al método <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> para cada elemento.  Tenga en cuenta que este método dará el número de elemento en la lista global; por tanto, si el primer elemento de la lista no está activado y el segundo sí lo está, se mostrará algo como "Item 2 \= MyListItem2".  
  
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
  
## Vea también  
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)