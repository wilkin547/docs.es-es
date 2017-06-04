---
title: "Informaci&#243;n general sobre el control RichTextBox (formularios Windows Forms) | Microsoft Docs"
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
  - "RichTextBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "RichTextBox (control) [Windows Forms], acerca del control RichTextBox"
  - "cuadros de texto, acerca de los cuadros de texto"
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Informaci&#243;n general sobre el control RichTextBox (formularios Windows Forms)
El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms se utiliza para mostrar, escribir y manipular texto con formato.  El control <xref:System.Windows.Forms.RichTextBox> hace todo lo que realiza el control <xref:System.Windows.Forms.TextBox>, pero además puede efectuar las siguientes operaciones: mostrar fuentes, colores y vínculos; cargar texto e imágenes incrustadas desde un archivo; y buscar caracteres especificados.  El control <xref:System.Windows.Forms.RichTextBox> suele utilizarse para manipular texto y proporcionar características de presentación similares a las de aplicaciones de procesador de textos tales como Microsoft Word.  Al igual que el control <xref:System.Windows.Forms.TextBox>, el control <xref:System.Windows.Forms.RichTextBox> puede mostrar barras de desplazamiento; sin embargo, a diferencia del control <xref:System.Windows.Forms.TextBox>, su configuración predeterminada es mostrar tanto barras de desplazamiento horizontales como verticales según se precise, y posee configuraciones adicionales para las barras de desplazamiento.  
  
## Trabajar con el control RichTextBox  
 Como sucede con el control <xref:System.Windows.Forms.TextBox>, el texto que se muestra se establece con la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A>.  El control <xref:System.Windows.Forms.RichTextBox> tiene numerosas propiedades para dar formato al texto.  Para obtener información detallada sobre estas propiedades, vea [Cómo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) y [Cómo: Establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md).  Para manipular archivos, los métodos <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> y <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> pueden mostrar y escribir varios formatos de archivo, entre ellos texto sin formato, texto sin formato Unicode y formato de texto enriquecido \(RTF\).  Los posibles formatos de archivo se enumeran en [RichTextBoxStreamType Enumeration](frlrfSystemWindowsFormsRichTextBoxStreamTypeClassTopic).  Puede utilizar el método <xref:System.Windows.Forms.RichTextBox.Find%2A> para buscar cadenas de texto o caracteres específicos.  
  
 También puede utilizar un control <xref:System.Windows.Forms.RichTextBox> para vínculos de Web estableciendo la propiedad <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> en `true` y escribiendo código para controlar el evento <xref:System.Windows.Forms.RichTextBox.LinkClicked>.  Para obtener más información, vea [Cómo: Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md).  Para evitar que el usuario manipule una parte o la totalidad del texto del control, puede establecer la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> en `true`.  
  
 Puede deshacer y rehacer la mayoría de las operaciones de edición en un control <xref:System.Windows.Forms.RichTextBox> llamando a los métodos <xref:System.Windows.Forms.TextBoxBase.Undo%2A> y <xref:System.Windows.Forms.RichTextBox.Redo%2A>.  El método <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> permite determinar si la última operación deshecha por el usuario puede aplicarse de nuevo al control.  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)