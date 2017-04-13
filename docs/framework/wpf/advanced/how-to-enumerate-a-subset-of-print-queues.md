---
title: "C&#243;mo: Enumerar un subconjunto de colas de impresi&#243;n | Microsoft Docs"
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
  - "enumerar, subconjunto de colas de impresión"
  - "colas de impresión, enumerar subconjunto de"
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Enumerar un subconjunto de colas de impresi&#243;n
Una situación común a la que se enfrentan los profesionales de la tecnología de la información \(TI\) que administran el conjunto de impresoras de toda la compañía es generar una lista de impresoras que tienen determinadas características.  El método <xref:System.Printing.PrintServer.GetPrintQueues%2A> de un objeto <xref:System.Printing.PrintServer> y la enumeración <xref:System.Printing.EnumeratedPrintQueueTypes> proporcionan esta funcionalidad.  
  
## Ejemplo  
 En el ejemplo siguiente, el código comienza creando una matriz de marcadores que especifican las características de las colas de impresión que deseamos mostrar en la lista.  En este ejemplo, se buscan las colas de impresión que están instaladas localmente en el servidor de impresión y son compartidas.  La enumeración <xref:System.Printing.EnumeratedPrintQueueTypes> proporciona muchas otras posibilidades.  
  
 A continuación, el código crea un objeto <xref:System.Printing.LocalPrintServer>, una clase derivada de <xref:System.Printing.PrintServer>.  El servidor de impresión local es el equipo en el que se ejecuta la aplicación.  
  
 El último paso significativo consiste en pasar la matriz al método <xref:System.Printing.PrintServer.GetPrintQueues%2A>.  
  
 Por último, se presentan los resultados al usuario.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Puede extender este ejemplo haciendo que el bucle `foreach` que recorre todas las colas de impresión realice un filtrado mayor.  Por ejemplo, podría dejar fuera las impresoras que no admitan la impresión a dos caras haciendo que el bucle llame al método <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> de cada cola de impresión y pruebe el valor devuelto correspondiente a la presencia de la impresión a dos caras.  
  
## Vea también  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>   
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Escritor de documentos XPS de Microsoft](http://go.microsoft.com/fwlink/?LinkId=147319)