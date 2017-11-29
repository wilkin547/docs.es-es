---
title: "Cómo: Invocar un cuadro de diálogo de impresión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ba541b367e56a809fa444528dccd69860c4de46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-a-print-dialog"></a>Cómo: Invocar un cuadro de diálogo de impresión
Para proporcionar la capacidad de imprimir desde la aplicación, simplemente puede crear y abrir un <xref:System.Windows.Controls.PrintDialog> objeto.  
  
## <a name="example"></a>Ejemplo  
 El control <xref:System.Windows.Controls.PrintDialog> proporciona un único punto de entrada para [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuración y envío de trabajos [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]. El control es fácil de usar y se pueden crear instancias mediante el uso de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o marcado del código. En el ejemplo siguiente se muestra cómo crear una instancia y abrir el control en el código y cómo imprimir desde él. También muestra cómo asegurarse de que el cuadro de diálogo le dará al usuario la opción de establecer un intervalo específico de páginas. El código de ejemplo se supone que hay un archivo FixedDocumentSequence.xps en la raíz de la unidad C:.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una vez abierto el cuadro de diálogo, los usuarios podrán seleccionar entre las impresoras instaladas en su equipo. También tendrá la opción de seleccionar la [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) para crear un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] archivo en lugar de imprimir.  
  
> [!NOTE]
>  El <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que se describe en este tema, no debe confundirse con el <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  
  
 En sentido estricto, puede usar el <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> método sin siquiera abrir el cuadro de diálogo. En ese sentido, el control puede usarse como componente de impresión oculto. Pero por razones de rendimiento, sería mejor usar la <xref:System.Printing.PrintQueue.AddJob%2A> método o a uno de los muchos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> métodos de la <xref:System.Windows.Xps.XpsDocumentWriter>. Para obtener más información al respecto, consulte [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) y.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.PrintDialog>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Escritor de documentos XPS de Microsoft](http://go.microsoft.com/fwlink/?LinkId=147319)
