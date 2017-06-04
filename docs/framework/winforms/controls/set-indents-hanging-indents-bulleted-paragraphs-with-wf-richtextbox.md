---
title: "C&#243;mo: Establecer sangr&#237;as, sangr&#237;as francesas y p&#225;rrafos con vi&#241;etas con el control RichTextBox de formularios Windows Forms | Microsoft Docs"
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
  - ".rtf (archivos), aplicar formato en el control RichTextBox"
  - "ejemplos [Windows Forms], cuadros de texto"
  - "RichTextBox (control) [Windows Forms], establecer sangría y viñetas"
  - "RTF (archivos), aplicar formato en el control RichTextBox"
  - "cuadros de texto, viñetas"
  - "cuadros de texto, establecer sangría"
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Establecer sangr&#237;as, sangr&#237;as francesas y p&#225;rrafos con vi&#241;etas con el control RichTextBox de formularios Windows Forms
El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms tiene numerosas opciones para dar formato al texto que muestra.  Para dar a los párrafos seleccionados el formato de lista con viñeta, puede establecer la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>.  También puede utilizar las propiedades <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> y <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> para establecer la sangría de los párrafos con respecto a los bordes izquierdo y derecho del control, así como al borde izquierdo de las demás líneas de texto.  
  
### Para dar a un párrafo el formato de lista con viñetas  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> en `true`.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### Para aplicar sangría a un párrafo  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> en un entero que represente la distancia en píxeles entre el borde izquierdo del control y el borde izquierdo del texto.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> en un entero que represente la distancia en píxeles entre el borde izquierdo de la primera línea de texto del párrafo y el borde izquierdo de las subsiguientes líneas del mismo párrafo.  El valor de la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> se aplica sólo a las líneas de un párrafo ajustadas bajo la primera línea.  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> en un entero que represente la distancia en píxeles entre el borde derecho del control y el borde derecho del texto.  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  Todas estas propiedades afectan a cualquier párrafo que tenga texto seleccionado y también al texto que se escriba después del punto de inserción actual.  Por ejemplo, cuando un usuario selecciona una palabra dentro de un párrafo y a continuación ajusta la sangría, la nueva configuración se aplicará a todo el párrafo que contiene la palabra, así como a los párrafos que se escriban a continuación del párrafo seleccionado.  Para obtener información sobre cómo seleccionar texto mediante programación, vea [TextBoxBase.Select \(Método\)](frlrfSystemWindowsFormsTextBoxBaseClassSelectTopic).  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)