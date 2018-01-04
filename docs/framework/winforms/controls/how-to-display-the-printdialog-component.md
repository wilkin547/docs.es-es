---
title: "Cómo: Mostrar el componente PrintDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d955febe528add4b774766a3b204f96eef5a119d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-the-printdialog-component"></a>Cómo: Mostrar el componente PrintDialog
El <xref:System.Windows.Forms.PrintDialog> componente es el cuadro de diálogo de impresión de Windows estándar que muchos de los usuarios estarán familiarizados con. Dado que los usuarios cómodos con él, sería beneficioso para su uso la <xref:System.Windows.Forms.PrintDialog> componente.  
  
### <a name="to-display-the-printdialog-component"></a>Mostrar el componente PrintDialog  
  
-   Llame a la <xref:System.Windows.Forms.Form.ShowDialog%2A> método desde el código de la aplicación.  
  
     Una vez que se muestre el componente, los usuarios interactuarán con él y establecerán las propiedades del trabajo de impresión. Éstas se guardan en el <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` clase (y el <xref:System.Drawing.Printing.PageSettings> de la clase, si el usuario tiene acceso a la [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) a través de la <xref:System.Windows.Forms.PrintDialog> componente) asociados a ese trabajo de impresión. A continuación, puede realizar llamadas a las propiedades que establecen para determinar los detalles del trabajo de impresión.  
  
## <a name="see-also"></a>Vea también  
 [Crear trabajos de impresión estándar de formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [Capturar datos proporcionados por el usuario de un componente PrintDialog en tiempo de ejecución](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [PrintPreviewDialog (control)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [PrintDialog (componente)](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)  
 [Controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/index.md)
