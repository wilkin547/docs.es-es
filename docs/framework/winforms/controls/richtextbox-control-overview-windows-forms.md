---
title: Información general sobre el control RichTextBox
ms.date: 03/30/2017
f1_keywords:
- RichTextBox
helpviewer_keywords:
- RichTextBox control [Windows Forms], about RichTextBox control
- text boxes [Windows Forms], about text boxes
ms.assetid: 95081194-3dd4-4b84-9545-dd373e491eca
ms.openlocfilehash: 0d40967d97622b23e9dcb07e861f190327e6baba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742395"
---
# <a name="richtextbox-control-overview-windows-forms"></a>Información general sobre el control RichTextBox (formularios Windows Forms)
El control de <xref:System.Windows.Forms.RichTextBox> de Windows Forms se usa para mostrar, escribir y manipular texto con formato. El control <xref:System.Windows.Forms.RichTextBox> hace todo lo que hace el control <xref:System.Windows.Forms.TextBox>, pero también puede mostrar fuentes, colores y vínculos. cargar texto e imágenes incrustadas desde un archivo; y buscar los caracteres especificados. El control <xref:System.Windows.Forms.RichTextBox> se usa normalmente para proporcionar funciones de manipulación y visualización de texto similares a las aplicaciones de procesamiento de texto como Microsoft Word. Al igual que el control <xref:System.Windows.Forms.TextBox>, el control <xref:System.Windows.Forms.RichTextBox> puede mostrar barras de desplazamiento; pero, a diferencia del control de <xref:System.Windows.Forms.TextBox>, su valor predeterminado es mostrar las barras de desplazamiento horizontal y vertical según sea necesario y tiene una configuración adicional de la barra de desplazamiento.  
  
## <a name="working-with-the-richtextbox-control"></a>Trabajar con el control RichTextBox  
 Al igual que con el control <xref:System.Windows.Forms.TextBox>, el texto que se muestra se establece mediante la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A>. El control <xref:System.Windows.Forms.RichTextBox> tiene numerosas propiedades para dar formato al texto. Para obtener más información sobre estas propiedades, consulte [Cómo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md) y [Cómo: Establecer sangrías, sangrías francesas y párrafos con viñetas con el control RichTextBox de formularios Windows Forms](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md). Para manipular archivos, los métodos <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> y <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> pueden mostrar y escribir varios formatos de archivo, como texto sin formato, texto sin formato Unicode y formato de texto enriquecido (RTF). Los posibles formatos de archivo se muestran en <xref:System.Windows.Forms.RichTextBoxStreamType>. Puede usar el método <xref:System.Windows.Forms.RichTextBox.Find%2A> para buscar cadenas de texto o caracteres específicos.  
  
 También puede utilizar un control de <xref:System.Windows.Forms.RichTextBox> para los vínculos de estilo Web si establece la propiedad <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> en `true` y escribe código para controlar el evento de <xref:System.Windows.Forms.RichTextBox.LinkClicked>. Para obtener más información, consulte [Cómo: Mostrar vínculos de estilo Web con el control RichTextBox de formularios Windows Forms](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md). Puede impedir que el usuario manipule parte o todo el texto del control estableciendo la propiedad <xref:System.Windows.Forms.RichTextBox.SelectionProtected%2A> en `true`.  
  
 Puede deshacer y rehacer la mayoría de las operaciones de edición en un control <xref:System.Windows.Forms.RichTextBox> llamando a los métodos <xref:System.Windows.Forms.TextBoxBase.Undo%2A> y <xref:System.Windows.Forms.RichTextBox.Redo%2A>. El método <xref:System.Windows.Forms.RichTextBox.CanRedo%2A> le permite determinar si la última operación deshecha por el usuario se puede volver a aplicar al control.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Información general sobre el control TextBox](textbox-control-overview-windows-forms.md)
