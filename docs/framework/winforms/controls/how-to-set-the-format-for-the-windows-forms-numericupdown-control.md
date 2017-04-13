---
title: "C&#243;mo: Establecer el formato del control NumericUpDown de formularios Windows Forms | Microsoft Docs"
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
  - "NumericUpDown (control) [Windows Forms], aplicar formato a valores"
  - "controles de flechas, aplicar formato a valores numéricos"
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Establecer el formato del control NumericUpDown de formularios Windows Forms
Puede configurar cómo se muestran los valores en el control <xref:System.Windows.Forms.NumericUpDown> de formularios Windows Forms.  La propiedad <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0.  La propiedad <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> determina si se insertará un separador entre cada tres dígitos decimales; el valor predeterminado es `false`.  El control puede mostrar valores en formato hexadecimal, en lugar de formato decimal, si se establece la propiedad <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> en `true`; el valor predeterminado es `false`.  
  
### Para dar formato al valor numérico  
  
-   Para mostrar un valor decimal, establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> en un entero y la propiedad <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> en `true` o `false`.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     O bien  
  
-   Para mostrar un valor hexadecimal, establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> en `true`.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  Aunque se muestre un valor en el formulario en formato hexadecimal, las pruebas que realice sobre la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> comprobarán su valor decimal.  
  
## Vea también  
 <xref:System.Windows.Forms.NumericUpDown>   
 [NumericUpDown \(Control\)](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Información general sobre el control NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)