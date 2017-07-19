---
title: "Informaci&#243;n general sobre el control NumericUpDown (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NumericUpDown"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "control de botones de número, Windows Forms"
  - "NumericUpDown (control) [Windows Forms], acerca del control NumericUpDown"
  - "control de botón de número, Windows Forms"
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre el control NumericUpDown (formularios Windows Forms)
El control <xref:System.Windows.Forms.NumericUpDown> es similar a una combinación de un cuadro de texto y un par de flechas en las que el usuario puede hacer clic para ajustar un valor.  El control muestra y establece un valor numérico único a partir de una lista de opciones de valor numérico fijo.  Para incrementar y reducir el número, el usuario puede hacer clic en los botones hacia arriba y hacia abajo, presionar las teclas de dirección ARRIBA y ABAJO, o escribir un número en la parte del cuadro de texto del control.  Al presionar la tecla de dirección ARRIBA, el número se mueve hacia arriba hacia el valor máximo; al presionar la tecla de dirección ABAJO, el número se mueve hacia el mínimo.  
  
 Debido a su versátil funcionalidad, este control es una elección obvia, por ejemplo, si desea crear un control de volumen para una aplicación de reproducción de música.  El control <xref:System.Windows.Forms.NumericUpDown> se utiliza en muchas aplicaciones del Panel de control de Windows.  
  
## Propiedades y métodos principales  
 Los números mostrados en el cuadro de texto de control pueden presentarse en una variedad de formatos, incluso el hexadecimal.  Para obtener más información, vea [Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md).  Las propiedades principales del control son <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> \(valor predeterminado 100\), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> \(valor predeterminado 0\) y <xref:System.Windows.Forms.NumericUpDown.Increment%2A> \(valor predeterminado 1\).  La propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> establece el número seleccionado actualmente en el control.  La propiedad <xref:System.Windows.Forms.NumericUpDown.Increment%2A> establece la cantidad en la que se ajusta el valor cuando el usuario hace clic en un botón arriba o abajo.  Cuando el foco se desplaza fuera del control, la entrada escrita se valida frente a los valores numéricos máximo y mínimo.  Se puede aumentar la velocidad del control por los números, si el usuario presiona la teclas de flecha arriba y abajo, con la propiedad <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A>.  Las propiedades principales del control son <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.  
  
## Vea también  
 <xref:System.Windows.Forms.NumericUpDown>   
 [NumericUpDown \(Control\)](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)