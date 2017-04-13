---
title: "C&#243;mo: Ver m&#250;ltiples l&#237;neas en el control TextBox de formularios Windows Forms | Microsoft Docs"
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
  - "retorno de carro"
  - "CRLF"
  - "fin de línea"
  - "avance de línea"
  - "MultiLine (propiedad del control TextBox)"
  - "nueva línea"
  - "ScrollBars (propiedad), del control TextBox"
  - "TextBox (control) [Windows Forms], ver múltiples líneas"
  - "WordWrap (propiedad)"
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Ver m&#250;ltiples l&#237;neas en el control TextBox de formularios Windows Forms
De forma predeterminada, el control <xref:System.Windows.Forms.TextBox> de formularios Windows Forms muestra una única línea de texto y no muestra barras de desplazamiento.  Si la longitud del texto es mayor que el espacio disponible, sólo estará visible parte del texto.  Se puede cambiar este comportamiento predeterminado si se establecen las propiedades <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> y <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en los valores apropiados.  
  
### Para mostrar un retorno de carro en el control TextBox  
  
-   Para mostrar un retorno de carro en un control <xref:System.Windows.Forms.TextBox> de varias líneas, utilice la propiedad <xref:System.Environment.NewLine%2A>.  
  
     Tenga en cuenta que la interpretación de los caracteres de escape \(\\\) es específica del lenguaje.  Visual Basic utiliza `Chr$(13) & Chr$(10)` para la combinación de caracteres de retorno de carro y avance de línea.  
  
### Para ver múltiples líneas en el control TextBox  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.TextBox.Multiline%2A> en `true`.  Si el valor de <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> es `true` \(el valor predeterminado\), el texto del control aparecerá en uno o más párrafos; de lo contrario, aparecerá como una lista, en la que algunas líneas pueden quedar cortadas en el borde del control.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.TextBox.ScrollBars%2A> en un valor apropiado.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars>|Utilice este valor si el texto va a ser un párrafo que casi siempre cabrá en el control.  Los usuarios pueden utilizar el puntero del mouse para moverse por el control si el texto resulta demasiado grande como para mostrarlo todo a la vez.|  
    |<xref:System.Windows.Forms.ScrollBars>|Utilice este valor si desea mostrar una lista de líneas, algunas de las cuales pueden ser más largas que el ancho del control <xref:System.Windows.Forms.TextBox>.|  
    |<xref:System.Windows.Forms.ScrollBars>|Utilice este valor si la lista puede ser más larga que el alto del control.|  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> en un valor apropiado.  
  
    |Valor|Descripción|  
    |-----------|-----------------|  
    |`false`|El texto del control no se ajustará automáticamente, así que se desplazará hacia la derecha hasta encontrar un salto de línea.  Utilice este valor si eligió barras de desplazamiento <xref:System.Windows.Forms.ScrollBars> o <xref:System.Windows.Forms.ScrollBars>.|  
    |`true` \(valor predeterminado\)|La barra de desplazamiento horizontal no aparecerá.  Utilice este valor si anteriormente eligió los valores <xref:System.Windows.Forms.ScrollBars> o <xref:System.Windows.Forms.ScrollBars> para las barras de desplazamiento con el fin de mostrar uno o más párrafos.|  
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de sólo lectura](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)   
 [Cómo: Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)