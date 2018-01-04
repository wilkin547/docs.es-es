---
title: "Información general sobre el control PrintPreviewDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintPreviewDialog
helpviewer_keywords: PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed071a4d38a0167ac9414ee7d383736dd38a62a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a>Información general sobre el control PrintPreviewDialog (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control es un cuadro de diálogo preconfigurado que se utiliza para mostrar cómo un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) aparecerá cuando se imprima. Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo. El control contiene botones para imprimir, acercar, mostrar una o varias páginas y cerrar el cuadro de diálogo.  
  
## <a name="key-properties-and-methods"></a>Métodos y propiedades claves  
 Ninguna propiedad clave del control <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, que establece el documento en una vista previa. El documento debe ser un <xref:System.Drawing.Printing.PrintDocument> objeto. Para mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.Form.ShowDialog%2A> método. El suavizado puede hacer que el texto aparezca más suave, pero también puede hacer que la pantalla sea más lenta; para utilizarla, establezca la <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> propiedad `true`.  
  
 Algunas propiedades están disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> que la <xref:System.Windows.Forms.PrintPreviewDialog> contiene. (No es necesario agregar este <xref:System.Windows.Forms.PrintPreviewControl> al formulario; se incluye automáticamente dentro de la <xref:System.Windows.Forms.PrintPreviewDialog> cuando se agrega el cuadro de diálogo al formulario.) Ejemplos de propiedades disponibles a través de la <xref:System.Windows.Forms.PrintPreviewControl> son la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> propiedades, que determinan el número de páginas que se muestran horizontal y verticalmente en el control. Puede tener acceso a la <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> propiedad como `PrintPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], o `printPreviewDialog1->PrintPreviewControl->Columns` en [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.PrintPreviewDialog>  
 [Información general sobre el control PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)  
 [PrintPreviewDialog (control)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
