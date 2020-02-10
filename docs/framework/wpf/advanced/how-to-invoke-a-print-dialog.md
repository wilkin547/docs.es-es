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
ms.openlocfilehash: f7ef3312d876324b44b055d70fd22e3fba075ec6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095182"
---
# <a name="how-to-invoke-a-print-dialog"></a>Cómo: Invocar un cuadro de diálogo de impresión
Para proporcionar la capacidad de imprimir desde la aplicación, puede simplemente crear y abrir un objeto de <xref:System.Windows.Controls.PrintDialog>.  
  
## <a name="example"></a>Ejemplo  
 El control <xref:System.Windows.Controls.PrintDialog> proporciona un único punto de entrada para el envío de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y trabajo XPS. El control es fácil de usar y se puede crear una instancia de él mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado o código. En el ejemplo siguiente se muestra cómo crear una instancia de y abrir el control en el código y cómo imprimir desde él. También se muestra cómo asegurarse de que el cuadro de diálogo proporciona al usuario la opción de configurar un intervalo específico de páginas. En el código de ejemplo se supone que hay un archivo FixedDocumentSequence. XPS en la raíz de la unidad C:.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una vez abierto el cuadro de diálogo, los usuarios podrán seleccionar entre las impresoras instaladas en su equipo. También tendrán la opción de seleccionar el escritor de [documentos XPS de Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer) para crear un archivo XML Paper Specification (XPS) en lugar de imprimirlo.  
  
> [!NOTE]
> El control <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> de WPF, que se describe en este tema, no se debe confundir con el componente <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> de Windows Forms.  
  
 En realidad, puede usar el método <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> sin abrir nunca el cuadro de diálogo. En ese sentido, el control se puede usar como un componente de impresión no visible. Sin embargo, por motivos de rendimiento, sería mejor utilizar el método <xref:System.Printing.PrintQueue.AddJob%2A> o uno de los muchos métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de la <xref:System.Windows.Xps.XpsDocumentWriter>. Para obtener más información, consulte [Imprimir archivos XPS mediante programación](how-to-programmatically-print-xps-files.md) y.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.PrintDialog>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
- [Escritor de documentos XPS de Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer)
