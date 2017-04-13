---
title: "C&#243;mo: Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "CheckedListBox (control) [Windows Forms], agregar y quitar elementos"
  - "cuadros combinados, agregar elementos"
  - "cuadros combinados, quitar elementos"
  - "ComboBox (control) [Windows Forms], agregar y quitar elementos"
  - "cuadros de lista, agregar elementos"
  - "cuadros de lista, quitar elementos"
  - "ListBox (control) [Windows Forms], agregar y quitar elementos"
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Agregar y quitar elementos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms
Es posible agregar elementos a cuadros combinados, cuadros de lista y cuadros de lista con marcas de verificación de formularios Windows Forms de varias maneras, puesto que estos controles pueden enlazarse con distintos orígenes de datos.  Sin embargo, este tema muestra el método más sencillo y no necesita ningún enlace de datos.  Los elementos que se muestra suelen ser cadenas, aunque puede utilizarse cualquier tipo de objeto.  El texto que se muestra en el control es el valor que devuelve el método `ToString`  del objeto.  
  
### Para agregar elementos  
  
1.  Agregue la cadena u objeto a la lista mediante el método `Add` de la clase `ObjectCollection`.  Se hace referencia a la colección mediante la propiedad `Items` :  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     O bien  
  
2.  Inserte la cadena o el objeto en el punto que desee de la lista por medio del método `Insert` :  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     O bien  
  
3.  Asigne una matriz completa a la colección `Items` :  
  
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
  
### Para quitar un elemento  
  
1.  Llame al método `Remove`  o `RemoveAt`  para eliminar elementos.  
  
     `Remove`  tiene un argumento que especifica el elemento que se va a quitar. `RemoveAt`  quita el elemento con el número de índice especificado.  
  
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
  
### Para quitar todos los elementos  
  
1.  Llame al método `Clear` para quitar todos los elementos de la colección:  
  
    ```vb  
    ListBox1.Items.Clear()  
  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Cómo: Ordenar el contenido de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)   
 [Cuándo utilizar un control ComboBox de formularios Windows Forms en lugar de un control ListBox](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)