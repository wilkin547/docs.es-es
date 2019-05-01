---
title: Información general sobre el control PrintPreviewControl (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: e9f1c2ae912b6beeba70c318b94a3052e2f99acb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012607"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Información general sobre el control PrintPreviewControl (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.PrintPreviewControl> se usa para mostrar un [PrintDocument](printdocument-component-windows-forms.md) tal y como aparecerá cuando se imprima. Este control no tiene botones ni otros elementos de la interfaz de usuario, por lo que normalmente utiliza <xref:System.Windows.Forms.PrintPreviewControl> solo si desea volver a escribir su propia interfaz de usuario de vista previa de impresión. Si desea que la interfaz de usuario estándar, use un <xref:System.Windows.Forms.PrintPreviewDialog> control; vea [información general del Control PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md) para obtener información general.  
  
## <a name="key-properties"></a>Propiedades clave  
 Propiedad de clave del control es <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, que establece el documento para la vista preliminar. El documento debe ser un <xref:System.Drawing.Printing.PrintDocument> objeto. Para obtener información general de la creación de documentos para la impresión, consulte [información general del componente PrintDocument](printdocument-component-overview-windows-forms.md) y [Windows Forms Print Support](../advanced/windows-forms-print-support.md). El <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propiedades determinan el número de páginas que se muestran horizontal y verticalmente en el control. Suavizado de contorno puede hacer que el texto aparezca más suave, pero también puede hacer que la pantalla sea más lenta; Para ello, establezca el <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> propiedad `true`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PrintPreviewControl>
- [Información general del control PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl (control)](printpreviewcontrol-control-windows-forms.md)
- [Controles y componentes de cuadros de diálogo](dialog-box-controls-and-components-windows-forms.md)
