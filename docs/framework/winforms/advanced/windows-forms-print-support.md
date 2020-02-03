---
title: Compatibilidad con impresión
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732495"
---
# <a name="windows-forms-print-support"></a>Funcionalidad para imprimir en Windows Forms
La impresión en Windows Forms consiste principalmente en el uso del componente de [componente PrintDocument](../controls/printdocument-component-windows-forms.md) para permitir que el usuario imprima, y el control de [control PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) , los componentes de [componente PrintDialog](../controls/printdialog-component-windows-forms.md) y [componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) para proporcionar una interfaz gráfica familiar a los usuarios acostumbrados al sistema operativo Windows.  
  
 Normalmente, se crea una nueva instancia del componente <xref:System.Drawing.Printing.PrintDocument>, se establecen las propiedades que describen lo que se va a imprimir mediante las clases <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> y se llama al método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para imprimir realmente el documento.  
  
 Durante el transcurso de la impresión desde una aplicación basada en Windows, el componente de <xref:System.Drawing.Printing.PrintDocument> mostrará un cuadro de diálogo anular impresión para avisar a los usuarios del hecho de que se está produciendo la impresión y permitir que se cancele el trabajo de impresión.  
  
## <a name="in-this-section"></a>En esta sección  
 [Crear trabajos de impresión estándar de formularios Windows Forms](how-to-create-standard-windows-forms-print-jobs.md)  
 Explica cómo utilizar el componente de <xref:System.Drawing.Printing.PrintDocument> para imprimir desde un Windows Form.  
  
 [Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Explica cómo modificar las opciones de impresión seleccionadas mediante programación con el <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Describe el cambio de la impresora que se va a imprimir con el componente de <xref:System.Windows.Forms.PrintDialog> en tiempo de ejecución.  
  
 [Cómo: Imprimir gráficos en Windows Forms](how-to-print-graphics-in-windows-forms.md)  
 Describe el envío de gráficos a la impresora.  
  
 [Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Describe el envío de texto a la impresora.  
  
 [Completar trabajos de impresión de formularios Windows Forms](how-to-complete-windows-forms-print-jobs.md)  
 Explica cómo avisar a los usuarios de la finalización de un trabajo de impresión.  
  
 [Imprimir Windows Forms](how-to-print-a-windows-form.md)  
 Muestra cómo imprimir una copia del formulario actual.  
  
 [Imprimir en Windows Forms a través de la vista previa de impresión](how-to-print-in-windows-forms-using-print-preview.md)  
 Muestra cómo utilizar un <xref:System.Windows.Forms.PrintPreviewDialog> para imprimir un documento.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [PrintDocument (componente)](../controls/printdocument-component-windows-forms.md)  
 Explica el uso del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
 [PrintDialog (componente)](../controls/printdialog-component-windows-forms.md)  
 Explica el uso del componente <xref:System.Windows.Forms.PrintDialog>.  
  
 [PrintPreviewDialog (control)](../controls/printpreviewdialog-control-windows-forms.md)  
 Explica el uso del control <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
 [PageSetupDialog (componente)](../controls/pagesetupdialog-component-windows-forms.md)  
 Explica el uso del componente <xref:System.Windows.Forms.PageSetupDialog>.  
  
 <xref:System.Drawing.Printing>  
 Describe las clases en el espacio de nombres <xref:System.Drawing.Printing>.
