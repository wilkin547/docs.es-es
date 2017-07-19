---
title: "C&#243;mo: Obtener acceso a elementos espec&#237;ficos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms | Microsoft Docs"
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
  - "CheckedListBox (control) [Windows Forms], obtener acceso a elementos"
  - "cuadros combinados, obtener acceso a elementos"
  - "ComboBox (control) [Windows Forms], obtener acceso a elementos"
  - "cuadros de lista, obtener acceso a elementos"
  - "ListBox (control) [Windows Forms], obtener acceso a elementos"
  - "ListBox (control) [Windows Forms], devolver información de elemento"
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Obtener acceso a elementos espec&#237;ficos de un control ComboBox, CheckedListBox o ListBox de formularios Windows Forms
Obtener acceso a elementos determinados de un cuadro combinado, de un cuadro de lista o de un cuadro de lista con marcas de verificación de un formulario Windows Forms resulta una tarea fundamental,  ya que permite determinar mediante programación qué hay en una lista, en cualquier posición dada.  
  
### Para obtener acceso a un elemento específico  
  
1.  efectúe una consulta en la colección `Items`  mediante el índice del elemento específico:  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 <xref:System.Windows.Forms.CheckedListBox>   
 [Controles de formularios Windows Forms usados para mostrar opciones](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)