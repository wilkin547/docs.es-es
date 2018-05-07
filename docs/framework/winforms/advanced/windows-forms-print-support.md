---
title: Funcionalidad para imprimir en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 4ea04d0b6bb8ffa7182d5166ebd66b809adeed34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-print-support"></a>Funcionalidad para imprimir en formularios Windows Forms
Impresión en formularios Windows Forms consiste principalmente en utilizar el [PrintDocument (componente)](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) componente para permitir al usuario imprimir y el [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Componente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) y [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) componentes para proporcionar una interfaz gráfica familiar a los usuarios acostumbrados al sistema operativo Windows.  
  
 Normalmente, se crea una nueva instancia de la <xref:System.Drawing.Printing.PrintDocument> componente, establecer las propiedades que describen qué imprimir con la <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> clases y llame a la <xref:System.Drawing.Printing.PrintDocument.Print%2A> método realmente imprimir el documento.  
  
 En el transcurso de impresión desde una aplicación basada en Windows, la <xref:System.Drawing.Printing.PrintDocument> componente mostrará un cuadro de diálogo de impresión de anulación alertar a los usuarios al hecho de que se está produciendo la impresión y para permitir que el trabajo de impresión se cancele.  
  
## <a name="in-this-section"></a>En esta sección  
 [Crear trabajos de impresión estándar de formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 Explica cómo utilizar el <xref:System.Drawing.Printing.PrintDocument> componente imprimir desde un formulario Windows Forms.  
  
 [Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Explica cómo modificar opciones de impresión seleccionadas mediante programación con el <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Describe cómo cambiar la impresora para imprimir en usando el <xref:System.Windows.Forms.PrintDialog> componente en tiempo de ejecución.  
  
 [Cómo: Imprimir gráficos en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 Describe cómo enviar gráficos a la impresora.  
  
 [Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Describe cómo enviar texto a la impresora.  
  
 [Completar trabajos de impresión de formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 Explica cómo alertar a los usuarios hasta la finalización de un trabajo de impresión.  
  
 [Imprimir Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 Muestra cómo imprimir una copia del formulario actual.  
  
 [Imprimir en Windows Forms a través de la vista previa de impresión](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 Muestra cómo utilizar un <xref:System.Windows.Forms.PrintPreviewDialog> para imprimir un documento.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [PrintDocument (Componente, Windows Forms)](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 Explica el uso de la <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 [PrintDialog (componente)](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 Explica el uso de la <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [PrintPreviewDialog (control)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 Explica el uso de la <xref:System.Windows.Forms.PrintPreviewDialog> control.  
  
 [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 Explica el uso de la <xref:System.Windows.Forms.PageSetupDialog> componente.  
  
 <xref:System.Drawing.Printing>  
 Describe las clases en el <xref:System.Drawing.Printing> espacio de nombres.
