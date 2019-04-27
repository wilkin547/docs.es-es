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
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011858"
---
# <a name="windows-forms-print-support"></a>Funcionalidad para imprimir en formularios Windows Forms
Impresión en Windows Forms consiste principalmente en usar el [PrintDocument (componente)](../controls/printdocument-component-windows-forms.md) componente para permitir al usuario a imprimir y el [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Componente](../controls/printdialog-component-windows-forms.md) y [componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) componentes que ofrecen una interfaz gráfica conocida para los usuarios acostumbrados al sistema operativo Windows.  
  
 Normalmente, se crea una nueva instancia de la <xref:System.Drawing.Printing.PrintDocument> componente, establecer las propiedades que describen qué imprimir con la <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings> clases y llame a la <xref:System.Drawing.Printing.PrintDocument.Print%2A> método para imprimir el documento.  
  
 Durante el transcurso de impresión desde una aplicación basada en Windows, la <xref:System.Drawing.Printing.PrintDocument> componente mostrará un cuadro de diálogo de impresión de anulación alertar a los usuarios al hecho de que se está produciendo la impresión y para permitir que el trabajo de impresión se puede cancelar.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Crear trabajos de impresión estándar de Windows Forms](how-to-create-standard-windows-forms-print-jobs.md)  
 Explica cómo utilizar el <xref:System.Drawing.Printing.PrintDocument> componente para imprimir desde un formulario de Windows.  
  
 [Cómo: Captura de datos de usuario de un componente PrintDialog en tiempo de ejecución](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Explica cómo modificar opciones de impresión seleccionadas mediante programación con el <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [Cómo: Seleccionar las impresoras conectadas al equipo de un usuario en Windows Forms](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Describe cómo cambiar la impresora para imprimir en usando el <xref:System.Windows.Forms.PrintDialog> componente en tiempo de ejecución.  
  
 [Cómo: Imprimir gráficos en Windows Forms](how-to-print-graphics-in-windows-forms.md)  
 Describe cómo enviar gráficos a la impresora.  
  
 [Cómo: Imprimir un archivo de texto de varias páginas en Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Describe cómo enviar texto a la impresora.  
  
 [Cómo: Los trabajos de impresión de formularios de Windows completo](how-to-complete-windows-forms-print-jobs.md)  
 Explica cómo alertar a los usuarios a la finalización de un trabajo de impresión.  
  
 [Cómo: Imprimir un formulario de Windows](how-to-print-a-windows-form.md)  
 Muestra cómo imprimir una copia del formulario actual.  
  
 [Cómo: Imprimir en Windows Forms a través de la vista previa de impresión](how-to-print-in-windows-forms-using-print-preview.md)  
 Se muestra cómo usar un <xref:System.Windows.Forms.PrintPreviewDialog> para imprimir un documento.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [PrintDocument (Componente, Windows Forms)](../controls/printdocument-component-windows-forms.md)  
 Explica el uso de la <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 [PrintDialog (componente)](../controls/printdialog-component-windows-forms.md)  
 Explica el uso de la <xref:System.Windows.Forms.PrintDialog> componente.  
  
 [PrintPreviewDialog (control)](../controls/printpreviewdialog-control-windows-forms.md)  
 Explica el uso de la <xref:System.Windows.Forms.PrintPreviewDialog> control.  
  
 [PageSetupDialog (componente)](../controls/pagesetupdialog-component-windows-forms.md)  
 Explica el uso de la <xref:System.Windows.Forms.PageSetupDialog> componente.  
  
 <xref:System.Drawing.Printing>  
 Describe las clases en el <xref:System.Drawing.Printing> espacio de nombres.
