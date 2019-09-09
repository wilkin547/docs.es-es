---
title: Información general sobre el componente PrintDocument (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928989"
---
# <a name="printdocument-component-overview-windows-forms"></a>Información general sobre el componente PrintDocument (formularios Windows Forms)

El componente [PrintDocument](printdocument-component-windows-forms.md) de Windows Forms se usa para establecer las propiedades que describen lo que desea imprimir y la capacidad de imprimir el documento en aplicaciones basadas en Windows. Se puede utilizar junto con el componente [PrintDialog](printdialog-component-windows-forms.md) para controlar todos los aspectos de la impresión del documento.

## <a name="working-with-the-printdocument-component"></a>Trabajo con el componente PrintDocument

Dos de los principales escenarios que implican <xref:System.Drawing.Printing.PrintDocument> al componente son:

- Trabajos de impresión sencillos, tales como la impresión de un archivo de texto individual. En tal caso, debe agregar el componente <xref:System.Drawing.Printing.PrintDocument> a un Windows Form y, a continuación, agregar la lógica de programación que imprime <xref:System.Drawing.Printing.PrintDocument.PrintPage> un archivo en el controlador de eventos. La lógica de programación debe culminar con <xref:System.Drawing.Printing.PrintDocument.Print%2A> el método para imprimir el documento. Este método envía a <xref:System.Drawing.Graphics> la impresora un objeto, <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> contenido en la <xref:System.Drawing.Printing.PrintPageEventArgs> propiedad de la clase. Para obtener un ejemplo en el que se muestra cómo imprimir un documento <xref:System.Drawing.Printing.PrintDocument> de texto mediante [el componente, consulte Cómo: Imprime un archivo de texto de varias páginas en](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)Windows Forms.

- Trabajos de impresión más complejos como, por ejemplo, una situación en la que se desee reutilizar la lógica de impresión escrita. En tal caso, debe derivar un nuevo componente <xref:System.Drawing.Printing.PrintDocument> del componente e invalidar (vea [invalidaciones](../../../visual-basic/language-reference/modifiers/overrides.md) para Visual Basic o [invalidar](../../../csharp/language-reference/keywords/override.md) para C#) <xref:System.Drawing.Printing.PrintDocument.PrintPage> el evento.

Cuando se agrega a un formulario, el <xref:System.Drawing.Printing.PrintDocument> componente aparece en la bandeja en la parte inferior del diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [PrintDocument (Componente, Windows Forms)](printdocument-component-windows-forms.md)
