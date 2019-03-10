---
title: Información general sobre el componente PrintDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: dfd6979c596f47fbc9bf68e3866f7fbc9d1dc21c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723366"
---
# <a name="printdialog-component-overview-windows-forms"></a>Información general sobre el componente PrintDialog (formularios Windows Forms)
Los formularios de Windows [PrintDialog](printdialog-component-windows-forms.md) componente es un cuadro de diálogo preconfigurado que se utiliza para seleccionar una impresora, elegir las páginas para imprimir y determinar otra configuración relacionada con la impresión en aplicaciones basadas en Windows. Utilizar como una solución sencilla para la impresora y la selección de configuración relacionada con la impresión en lugar de configurar su propio cuadro de diálogo. Puede permitir que los usuarios impriman diversas partes de sus documentos: imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios. El <xref:System.Windows.Forms.PrintDialog> componente hereda de la <xref:System.Windows.Forms.CommonDialog> clase.  
  
## <a name="working-with-the-component"></a>Trabajar con el componente  
 Use el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución. Este componente tiene propiedades relacionadas con un único trabajo de impresión (<xref:System.Drawing.Printing.PrintDocument> clase) o la configuración de una impresora individual (<xref:System.Drawing.Printing.PrinterSettings> clase). Cualquiera de estos, a su vez, pueden compartirse entre varias impresoras.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.PrintDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.PrintDialog>
- [PrintDialog (componente)](printdialog-component-windows-forms.md)
