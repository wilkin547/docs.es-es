---
title: Información general sobre el componente PrintDialog
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728669"
---
# <a name="printdialog-component-overview-windows-forms"></a>Información general sobre el componente PrintDialog (formularios Windows Forms)

El Windows Forms componente [PrintDialog](printdialog-component-windows-forms.md) es un cuadro de diálogo preconfigurado que se usa para seleccionar una impresora, elegir las páginas que se van a imprimir y determinar otros valores de configuración relacionados con la impresión en aplicaciones basadas en Windows. Utilizar como una solución sencilla para la impresora y la selección de configuración relacionada con la impresión en lugar de configurar su propio cuadro de diálogo. Puede permitir que los usuarios impriman muchas partes de sus documentos: Imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios. El componente de <xref:System.Windows.Forms.PrintDialog> hereda de la clase <xref:System.Windows.Forms.CommonDialog>.

## <a name="working-with-the-component"></a>Trabajar con el componente

Utilice el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución. Este componente tiene propiedades relacionadas con un solo trabajo de impresión (clase<xref:System.Drawing.Printing.PrintDocument>) o con la configuración de una impresora individual (clase<xref:System.Drawing.Printing.PrinterSettings>). Cualquiera de ellas, a su vez, se puede compartir entre varias impresoras.

Cuando se agrega a un formulario, el componente de <xref:System.Windows.Forms.PrintDialog> aparece en la bandeja en la parte inferior del Diseñador de Windows Forms en Visual Studio.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PrintDialog>
- [PrintDialog (componente)](printdialog-component-windows-forms.md)
