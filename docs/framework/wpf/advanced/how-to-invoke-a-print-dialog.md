---
title: Procedimiento Invocar un cuadro de diálogo de impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: cd7b06030e0fb2bba74590ee80c07c34047c5b47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950608"
---
# <a name="how-to-invoke-a-print-dialog"></a>Procedimiento Invocar un cuadro de diálogo de impresión
Para proporcionar la capacidad de imprimir desde la aplicación, puede simplemente crear y abrir un <xref:System.Windows.Controls.PrintDialog> objeto.  
  
## <a name="example"></a>Ejemplo  
 El control <xref:System.Windows.Controls.PrintDialog> proporciona un único punto de entrada para [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y envío de trabajos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. El control es fácil de usar y se puede crear una instancia de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] él mediante el marcado o el código. En el ejemplo siguiente se muestra cómo crear una instancia de y abrir el control en el código y cómo imprimir desde él. También se muestra cómo asegurarse de que el cuadro de diálogo proporciona al usuario la opción de configurar un intervalo específico de páginas. En el código de ejemplo se supone que hay un archivo FixedDocumentSequence. XPS en la raíz de la unidad C:.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una vez abierto el cuadro de diálogo, los usuarios podrán seleccionar entre las impresoras instaladas en su equipo. También tendrán la opción de seleccionar el escritor de [documentos XPS de Microsoft](https://go.microsoft.com/fwlink/?LinkId=147319) para crear un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivo en lugar de imprimirlo.  
  
> [!NOTE]
> El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que se describe en este tema, no se debe confundir con <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> el componente de Windows Forms.  
  
 En realidad, puede utilizar el <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> método sin abrir el cuadro de diálogo. En ese sentido, el control se puede usar como un componente de impresión no visible. Sin embargo, por motivos de rendimiento, <xref:System.Printing.PrintQueue.AddJob%2A> sería mejor utilizar el método o uno de los muchos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> métodos y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de. <xref:System.Windows.Xps.XpsDocumentWriter> Para obtener más información, consulte [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md) y.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.PrintDialog>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
- [Escritor de documentos XPS de Microsoft](https://go.microsoft.com/fwlink/?LinkId=147319)
