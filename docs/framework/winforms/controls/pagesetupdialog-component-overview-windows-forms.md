---
title: Información general sobre el componente PageSetupDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 30ac782cae830ac996132046cbbc57392067c0ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932540"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Información general sobre el componente PageSetupDialog (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.PageSetupDialog> componente es un cuadro de diálogo preconfigurado que se usa para establecer los detalles de la página para la impresión en aplicaciones basadas en Windows. Usar dentro de la aplicación basada en Windows como una solución sencilla para los usuarios para establecer preferencias de la página en lugar de configurar su propio cuadro de diálogo. Puede habilitar a los usuarios establecer los ajustes de borde y margen, encabezados y pies de página y orientación vertical u horizontal. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.  
  
## <a name="key-properties-and-methods"></a>Los métodos y propiedades de clave  
 Use el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución. Este componente se puede establecer propiedades relacionadas con una sola página (<xref:System.Drawing.Printing.PrintDocument> clase) o a cualquier documento (<xref:System.Drawing.Printing.PageSettings> clase). Además, el <xref:System.Windows.Forms.PageSetupDialog> componente se puede usar para determinar la configuración de impresora específico, que se almacena en la <xref:System.Drawing.Printing.PrinterSettings> clase.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.PageSetupDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PageSetupDialog>
- [PageSetupDialog (componente)](pagesetupdialog-component-windows-forms.md)
