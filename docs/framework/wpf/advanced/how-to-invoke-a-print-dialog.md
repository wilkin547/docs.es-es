---
title: "C&#243;mo: Invocar un cuadro de di&#225;logo de impresi&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "invocar cuadros de diálogo Imprimir"
  - "cuadros de diálogo de impresión, invocar"
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Invocar un cuadro de di&#225;logo de impresi&#243;n
Para proporcionar la capacidad de imprimir desde la aplicación, basta con crear y abrir un objeto <xref:System.Windows.Controls.PrintDialog>.  
  
## Ejemplo  
 El control <xref:System.Windows.Controls.PrintDialog> proporciona un punto de entrada único para la configuración de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] y el envío de trabajos de [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].  El control es fácil utilizar y pueden crearse instancias de él mediante marcado [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] o código.  En el ejemplo siguiente se muestra cómo crear instancias del control, abrirlo mediante código e imprimir desde él.  También se muestra cómo asegurarse de que el cuadro de diálogo permita al usuario establecer un intervalo de páginas concreto.  En el ejemplo de código se da por hecho que existe un archivo FixedDocumentSequence.xps en la raíz de la unidad de disco C:.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Una vez abierto el cuadro de diálogo, el usuario podrá seleccionar una de las impresoras instaladas en el equipo.  También dispondrá de la opción de seleccionar el [Escritor de documentos XPS de Microsoft](http://go.microsoft.com/fwlink/?LinkId=147319) para crear un archivo [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] en lugar de imprimir.  
  
> [!NOTE]
>  El control <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName> de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que se explica en este tema, no se debe confundir con el componente <xref:System.Windows.Forms.PrintDialog?displayProperty=fullName> de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  
  
 En sentido estricto, puede utilizar el método <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> sin llegar a abrir nunca el cuadro de diálogo.  En este sentido, el control se puede utilizar como componente de impresión oculto.  No obstante, por motivos de rendimiento, es preferible utilizar el método <xref:System.Printing.PrintQueue.AddJob%2A> o uno de los numerosos métodos <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> y <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> de <xref:System.Windows.Xps.XpsDocumentWriter>.  Para obtener más información al respecto, vea [Imprimir archivos XPS mediante programación](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md).  
  
## Vea también  
 <xref:System.Windows.Controls.PrintDialog>   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Escritor de documentos XPS de Microsoft](http://go.microsoft.com/fwlink/?LinkId=147319)