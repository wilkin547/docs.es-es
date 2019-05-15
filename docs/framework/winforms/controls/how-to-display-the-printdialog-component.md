---
title: Cómo mostrar el componente PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: de0acc655bbcf0cfc017d594545fae56cc27f981
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637451"
---
# <a name="how-to-display-the-printdialog-component"></a>Cómo mostrar el componente PrintDialog

El <xref:System.Windows.Forms.PrintDialog> componente es el cuadro de diálogo de impresión de Windows estándar que muchos de los usuarios estarán familiarizados con. Dado que los usuarios cómodos con él, le resultará beneficioso para su uso el <xref:System.Windows.Forms.PrintDialog> componente.

## <a name="to-display-the-printdialog-component"></a>Mostrar el componente PrintDialog

- Llame a la <xref:System.Windows.Forms.Form.ShowDialog%2A> método desde el código de la aplicación.

     Una vez que se muestre el componente, los usuarios interactuarán con él y establecerán las propiedades del trabajo de impresión. Éstas se guardan en el <xref:System.Drawing.Printing.PrinterSettings> clase (y el <xref:System.Drawing.Printing.PageSettings> clase, si el usuario tiene acceso a la [componente PageSetupDialog](pagesetupdialog-component-windows-forms.md) a través de la <xref:System.Windows.Forms.PrintDialog> componente) asociado con ese trabajo de impresión. A continuación, puede realizar llamadas a las propiedades que establecen para determinar los detalles del trabajo de impresión.

## <a name="see-also"></a>Vea también

- [Cómo: Crear trabajos de impresión estándar de Windows Forms](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [Cómo: Captura de datos de usuario de un componente PrintDialog en tiempo de ejecución](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [PrintPreviewDialog (control)](printpreviewdialog-control-windows-forms.md)
- [PrintDialog (componente)](printdialog-component-windows-forms.md)
- [Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
- [Controles de formularios Windows Forms](index.md)
