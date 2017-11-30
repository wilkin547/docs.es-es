---
title: "Información general sobre el control RichTextBox (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4278f569a789ca6e8466e0b8e71557446b63955e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="richtextbox-control-overview-windows-forms"></a>Información general sobre el control RichTextBox (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.RichTextBox> control se utiliza para mostrar, escribir y manipular texto con formato. El <xref:System.Windows.Forms.RichTextBox> control hace todo lo que el <xref:System.Windows.Forms.TextBox> no de control, pero también puede mostrar las fuentes, colores y vínculos; Cargar texto e imágenes incrustadas desde un archivo; y buscar caracteres especificados. El <xref:System.Windows.Forms.RichTextBox> control se utiliza normalmente para manipular texto y proporcionar funciones de presentación similares a las aplicaciones de procesamiento de textos como Microsoft Word. Como el <xref:System.Windows.Forms.TextBox> (control), el <xref:System.Windows.Forms.RichTextBox> control puede mostrar barras de desplazamiento; pero a diferencia del <xref:System.Windows.Forms.TextBox> (control), su valor predeterminado es mostrar las barras de desplazamiento horizontal y vertical según sea necesario y tiene una configuración adicional de la barra de desplazamiento.  
  
## <a name="working-with-the-richtextbox-control"></a>Trabajar con el control RichTextBox  
 Al igual que con la <xref:System.Windows.Forms.TextBox> (control), se establece el texto mostrado el <xref:System.Windows.Forms.RichTextBox.Text%2A> propiedad. El <xref:System.Windows.Forms.RichTextBox> control tiene numerosas propiedades para dar formato al texto. Para obtener más información sobre estas propiedades, consulte [Cómo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) y [Cómo: Establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Para manipular archivos, el <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> y <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> métodos pueden mostrar y escribir varios formatos de archivo como texto sin formato, texto sin formato Unicode y formato de texto enriquecido (RTF). Los formatos de archivo posibles se muestran en <xref:System.Windows.Forms.RichTextBoxStreamType>. Puede usar el <xref:System.Windows.Forms.RichTextBox.Find%2A> método para buscar las cadenas de texto o caracteres específicos.  
  
 También puede usar un <xref:System.Windows.Forms.RichTextBox> control de vínculos de estilo Web estableciendo la <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> propiedad `true` y escribir código para controlar la <xref:System.Windows.Forms.RichTextBox.LinkClicked> eventos. Para obtener más información, consulte [Cómo: Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Puede impedir que el usuario manipule una parte o todo el texto en el control estableciendo la <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> propiedad `true`.  
  
 Puede deshacer y rehacer la mayoría de las operaciones de edición en una <xref:System.Windows.Forms.RichTextBox> control mediante una llamada a la <xref:System.Windows.Forms.TextBoxBase.Undo%2A> y <xref:System.Windows.Forms.RichTextBox.Redo%2A> métodos. El <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> método le permite determinar si la última operación deshecha por el usuario puede volver a aplicar al control.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox (control)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
