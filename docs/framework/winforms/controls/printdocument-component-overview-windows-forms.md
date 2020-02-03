---
title: '{1}'
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a82cc0cdcb8cfae796c9c6bf60ab73873f85a291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728543"
---
# <a name="printdocument-component-overview-windows-forms"></a>Información general sobre el componente PrintDocument (formularios Windows Forms)

El componente [PrintDocument](printdocument-component-windows-forms.md) de Windows Forms se usa para establecer las propiedades que describen lo que desea imprimir y la capacidad de imprimir el documento en aplicaciones basadas en Windows. Se puede utilizar junto con el componente [PrintDialog](printdialog-component-windows-forms.md) para controlar todos los aspectos de la impresión del documento.

## <a name="working-with-the-printdocument-component"></a>Trabajo con el componente PrintDocument

Dos de los principales escenarios que implican el componente <xref:System.Drawing.Printing.PrintDocument> son:

- Trabajos de impresión sencillos, tales como la impresión de un archivo de texto individual. En tal caso, agregaría el componente <xref:System.Drawing.Printing.PrintDocument> a Windows Forms y, a continuación, agregaría lógica de programación que imprime un archivo en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>. La lógica de programación debe culminar con el método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para imprimir el documento. Este método envía a la impresora un objeto <xref:System.Drawing.Graphics>, contenido en la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs>. Para obtener un ejemplo en el que se muestra cómo imprimir un documento de texto mediante el componente de <xref:System.Drawing.Printing.PrintDocument>, vea [Cómo: imprimir un archivo de texto de varias páginas en Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).

- Trabajos de impresión más complejos como, por ejemplo, una situación en la que se desee reutilizar la lógica de impresión escrita. En tal caso, debe derivar un nuevo componente del componente <xref:System.Drawing.Printing.PrintDocument> e invalidar (vea [invalidaciones](../../../visual-basic/language-reference/modifiers/overrides.md) para Visual Basic o [invalidar](../../../csharp/language-reference/keywords/override.md) para C#) el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.

Cuando se agrega a un formulario, el componente de <xref:System.Drawing.Printing.PrintDocument> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [PrintDocument (componente)](printdocument-component-windows-forms.md)
