---
title: "Información general sobre el componente PageSetupDialog (formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 082dbff66c8a0f06635936011f802c99b88e41df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Información general sobre el componente PageSetupDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.PageSetupDialog> componente es un cuadro de diálogo preconfigurado que se utiliza para establecer los detalles de la página para la impresión en aplicaciones basadas en Windows. Utilícelo en la aplicación basada en Windows como una solución sencilla para los usuarios para establecer preferencias de la página en lugar de configurar su propio cuadro de diálogo. Puede habilitar los usuarios establezcan ajustes de borde y margen, encabezados y pies de página y orientación vertical u horizontal. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.  
  
## <a name="key-properties-and-methods"></a>Métodos y propiedades claves  
 Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución. Este componente se puede establecer propiedades relacionadas con una sola página (<xref:System.Drawing.Printing.PrintDocument> clase) o a cualquier documento (<xref:System.Drawing.Printing.PageSettings> clase). Además, el <xref:System.Windows.Forms.PageSetupDialog> componente puede utilizarse para determinar configuraciones específicas de la impresora, que se almacenan en la <xref:System.Drawing.Printing.PrinterSettings> clase.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.PageSetupDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
