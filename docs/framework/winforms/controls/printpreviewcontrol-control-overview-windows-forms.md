---
title: Información general sobre el control PrintPreviewControl
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741440"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Información general sobre el control PrintPreviewControl (formularios Windows Forms)
El <xref:System.Windows.Forms.PrintPreviewControl> Windows Forms se usa para mostrar un [PrintDocument](printdocument-component-windows-forms.md) tal como aparecerá cuando se imprima. Este control no tiene botones ni otros elementos de la interfaz de usuario, por lo que normalmente utiliza <xref:System.Windows.Forms.PrintPreviewControl> solo si desea volver a escribir su propia interfaz de usuario de vista previa de impresión. Si desea usar la interfaz de usuario estándar, utilice un control de <xref:System.Windows.Forms.PrintPreviewDialog>; consulte [información general sobre el control PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md) para obtener información general.  
  
## <a name="key-properties"></a>Propiedades clave  
 La propiedad de clave del control es <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, que establece el documento cuya vista previa se va a obtener. El documento debe ser un objeto de <xref:System.Drawing.Printing.PrintDocument>. Para obtener información general sobre la creación de documentos para imprimir, consulte [información general sobre el componente PrintDocument](printdocument-component-overview-windows-forms.md) y [soporte de impresión Windows Forms](../advanced/windows-forms-print-support.md). Las propiedades <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> determinan el número de páginas que se muestran horizontal y verticalmente en el control. El suavizado de contorno puede hacer que el texto parezca más suave, pero también puede hacer que la pantalla sea más lenta. para usarlo, establezca la propiedad <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> en `true`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PrintPreviewControl>
- [Información general del control PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl (control)](printpreviewcontrol-control-windows-forms.md)
- [Controles y componentes de cuadros de diálogo](dialog-box-controls-and-components-windows-forms.md)
