---
title: Información general sobre el componente PrintDocument (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 96bca5d96722098f76059c58c32b3fea0ff78cd2
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211730"
---
# <a name="printdocument-component-overview-windows-forms"></a>Información general sobre el componente PrintDocument (formularios Windows Forms)

El componente [PrintDocument](printdocument-component-windows-forms.md) de Windows Forms se usa para establecer las propiedades que describen lo que desea imprimir y la capacidad de imprimir el documento en aplicaciones basadas en Windows. Se puede utilizar junto con el componente [PrintDialog](printdialog-component-windows-forms.md) para controlar todos los aspectos de la impresión del documento.

## <a name="working-with-the-printdocument-component"></a>Trabajo con el componente PrintDocument

Dos de los principales escenarios que implican la <xref:System.Drawing.Printing.PrintDocument> componente son:

- Trabajos de impresión sencillos, tales como la impresión de un archivo de texto individual. En tal caso agregaría el <xref:System.Drawing.Printing.PrintDocument> componente a un formulario de Windows, a continuación, agregue lógica de programación que imprime un archivo en el <xref:System.Drawing.Printing.PrintDocument.PrintPage> controlador de eventos. La lógica de programación debe culminar en el <xref:System.Drawing.Printing.PrintDocument.Print%2A> método para imprimir el documento. Este método envía un <xref:System.Drawing.Graphics> objeto, incluido en el <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> clase a la impresora. Para obtener un ejemplo que muestra cómo imprimir un documento de texto utilizando la <xref:System.Drawing.Printing.PrintDocument> componente, vea [Cómo: Imprimir un archivo de texto de varias páginas en Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).

- Trabajos de impresión más complejos como, por ejemplo, una situación en la que se desee reutilizar la lógica de impresión escrita. En tal caso, deberá derivar un nuevo componente de la <xref:System.Drawing.Printing.PrintDocument> componente y la invalidación (vea [invalida](~/docs/visual-basic/language-reference/modifiers/overrides.md) para Visual Basic o [invalidar](~/docs/csharp/language-reference/keywords/override.md) para C#) la <xref:System.Drawing.Printing.PrintDocument.PrintPage> eventos.

Cuando se agrega a un formulario, el <xref:System.Drawing.Printing.PrintDocument> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [PrintDocument (Componente, Windows Forms)](printdocument-component-windows-forms.md)
