---
title: "C&#243;mo: Establecer y devolver valores num&#233;ricos con el control NumericUpDown de formularios Windows Forms | Microsoft Docs"
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
  - "valores numéricos, Windows Forms"
  - "NumericUpDown (control) [Windows Forms], establecer y devolver valores"
  - "controles de Windows Forms, NumericUpDown"
  - "Windows Forms, valores numéricos"
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Establecer y devolver valores num&#233;ricos con el control NumericUpDown de formularios Windows Forms
El valor numérico del control <xref:System.Windows.Forms.NumericUpDown> de formularios Windows Forms está determinado por su propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A>.  Puede escribir pruebas condicionales para el valor del control tal como lo haría con cualquier otra propiedad.  Una vez establecida la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A>, puede ajustarla directamente si escribe código que ejecute operaciones sobre ella o llama a los métodos <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
### Para establecer el valor numérico  
  
1.  Asigne un valor a la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> en el código o en la ventana Propiedades.  
  
    ```vb  
    NumericUpDown1.Value = 55  
  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     O bien  
  
2.  Llame a los métodos <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> o <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> para aumentar o reducir el valor en la cantidad especificada en la propiedad <xref:System.Windows.Forms.NumericUpDown.Increment%2A>.  
  
    ```vb  
    NumericUpDown1.UpButton()  
  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### Para devolver el valor numérico  
  
-   Obtenga acceso a la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> en el código.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.NumericUpDown>   
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=fullName>   
 [NumericUpDown \(Control\)](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Información general sobre el control NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)