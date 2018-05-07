---
title: Información general sobre el componente PrintDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0b0e516364277133efc83e7324345ccea8328690
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="printdialog-component-overview-windows-forms"></a>Información general sobre el componente PrintDialog (formularios Windows Forms)
Los formularios Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) componente es un cuadro de diálogo preconfigurado que se utiliza para seleccionar una impresora, elegir las páginas que se va a imprimir y determinar otra configuración relacionada con la impresión en aplicaciones basadas en Windows. Utilizar como una solución sencilla para la impresora y la selección de configuración relacionada con la impresión en lugar de configurar su propio cuadro de diálogo. Puede permitir que los usuarios impriman diversas partes de sus documentos: imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección. Al basarse en cuadros de diálogo estándar de Windows, crea aplicaciones cuya funcionalidad básica resultará de inmediato familiar a los usuarios. El <xref:System.Windows.Forms.PrintDialog> componente hereda de la <xref:System.Windows.Forms.CommonDialog> clase.  
  
## <a name="working-with-the-component"></a>Trabajar con el componente  
 Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo en tiempo de ejecución. Este componente tiene propiedades relacionadas con un único trabajo de impresión (<xref:System.Drawing.Printing.PrintDocument> clase) o la configuración de una impresora individual (<xref:System.Drawing.Printing.PrinterSettings> clase). Cualquiera de estos, a su vez, pueden estar compartido por varias impresoras.  
  
 Cuando se agrega a un formulario, el <xref:System.Windows.Forms.PrintDialog> componente aparece en la bandeja en la parte inferior del Diseñador de Windows Forms.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.PrintDialog>  
 [PrintDialog (componente)](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
