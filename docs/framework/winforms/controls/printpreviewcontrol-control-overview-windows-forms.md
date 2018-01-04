---
title: "Información general sobre el control PrintPreviewControl (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d50e772cf870d47314a25347f4909367062ffb94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Información general sobre el control PrintPreviewControl (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> se usa para mostrar un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) tal y como aparecerá cuando se imprima. Este control no tiene botones ni otros elementos de la interfaz de usuario, por lo que normalmente utiliza <xref:System.Windows.Forms.PrintPreviewControl> solo si desea volver a escribir su propia interfaz de usuario de vista previa de impresión. Si desea que la interfaz de usuario estándar, utilice un <xref:System.Windows.Forms.PrintPreviewDialog> el control; vea [información general del Control PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) para obtener información general.  
  
## <a name="key-properties"></a>Propiedades clave  
 Ninguna propiedad clave del control <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, que establece el documento en una vista previa. El documento debe ser un <xref:System.Drawing.Printing.PrintDocument> objeto. Para obtener información general de creación de documentos para la impresión, consulte [general sobre el componente PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) y [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md). El <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propiedades determinan el número de páginas que se muestran horizontal y verticalmente en el control. Suavizado de contorno puede hacer que el texto aparezca más suave, pero también puede hacer que la pantalla sea más lenta; para utilizarla, establezca la <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> propiedad `true`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [Información general del control PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [PrintPreviewControl (control)](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
