---
title: Información general sobre el componente PageSetupDialog
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744332"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Información general sobre el componente PageSetupDialog (formularios Windows Forms)

El componente <xref:System.Windows.Forms.PageSetupDialog> de Windows Forms es un cuadro de diálogo preconfigurado que se usa para establecer los detalles de la página para imprimir en aplicaciones basadas en Windows. Úselo en su aplicación basada en Windows como una solución sencilla para que los usuarios establezcan preferencias de página en lugar de configurar su propio cuadro de diálogo. Puede permitir que los usuarios establezcan ajustes de borde y margen, encabezados y pies de página, así como orientación vertical u horizontal. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios.

## <a name="key-properties-and-methods"></a>Propiedades y métodos clave

Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución. Este componente tiene propiedades que se pueden establecer relacionadas con una sola página (clase<xref:System.Drawing.Printing.PrintDocument>) o con cualquier documento (clase<xref:System.Drawing.Printing.PageSettings>). Además, el componente de <xref:System.Windows.Forms.PageSetupDialog> se puede utilizar para determinar la configuración específica de la impresora, que se almacena en la clase <xref:System.Drawing.Printing.PrinterSettings>.

Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.PageSetupDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.PageSetupDialog>
- [PageSetupDialog (componente)](pagesetupdialog-component-windows-forms.md)
