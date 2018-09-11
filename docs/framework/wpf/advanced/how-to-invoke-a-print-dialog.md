---
title: 'Cómo: Invocar un cuadro de diálogo de impresión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 271652fe9e98f9a381da5655bd313e12f8ee917d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44273279"
---
# <a name="how-to-invoke-a-print-dialog"></a>Cómo: Invocar un cuadro de diálogo de impresión
Para proporcionar la capacidad de imprimir desde la aplicación, simplemente puede crear y abrir un <xref:System.Windows.Controls.PrintDialog> objeto.  
  
## <a name="example"></a>Ejemplo  
 El control <xref:System.Windows.Controls.PrintDialog> proporciona un único punto de entrada para [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y envío de trabajos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. Es fácil de usar el control y se pueden crear instancias mediante el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado o código. En el ejemplo siguiente se muestra cómo crear instancias y abrir el control de código y cómo imprimir a partir de él. También muestra cómo asegurarse de que el cuadro de diálogo le ofrecerá la opción de establecer un intervalo de páginas específico. El código de ejemplo se supone que hay un archivo FixedDocumentSequence.xps en la raíz de la unidad C:.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una vez abierto el cuadro de diálogo, los usuarios podrán seleccionar desde las impresoras instaladas en su equipo. También tendrá la opción de seleccionar el [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) para crear un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivo en lugar de imprimir.  
  
> [!NOTE]
>  El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que se describe en este tema, no debe confundirse con el <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente de Windows Forms.  
  
 En realidad, puede usar el <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> método sin siquiera abrir el cuadro de diálogo. En ese sentido, el control puede usarse como un componente de impresión oculto. Pero por motivos de rendimiento, sería mejor usar ya sea el <xref:System.Printing.PrintQueue.AddJob%2A> método o a uno de los muchos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos de la <xref:System.Windows.Xps.XpsDocumentWriter>. Para obtener más información acerca de esto, consulte [impresión de archivos XPS mediante programación](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) y.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.PrintDialog>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Escritor de documentos XPS de Microsoft](https://go.microsoft.com/fwlink/?LinkId=147319)
