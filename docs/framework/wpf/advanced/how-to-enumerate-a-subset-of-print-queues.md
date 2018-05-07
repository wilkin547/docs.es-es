---
title: 'Cómo: Enumerar un subconjunto de colas de impresión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: 3e616b3b61b4b1b561d5bdb7e51525f391901a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Cómo: Enumerar un subconjunto de colas de impresión
Una situación común que enfrentan profesionales de informática (TI) administrar un conjunto de toda la compañía de las impresoras consiste en generar una lista de impresoras que tienen ciertas características. Esta funcionalidad se proporciona mediante la <xref:System.Printing.PrintServer.GetPrintQueues%2A> método de un <xref:System.Printing.PrintServer> objeto y el <xref:System.Printing.EnumeratedPrintQueueTypes> enumeración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el código comienza creando una matriz de marcas que especifican las características de las colas de impresión que desea enumerar. En este ejemplo, estamos buscando las colas de impresión que se instalan localmente en el servidor de impresión y se comparten. El <xref:System.Printing.EnumeratedPrintQueueTypes> enumeración proporciona muchas otras posibilidades.  
  
 El código, a continuación, crea un <xref:System.Printing.LocalPrintServer> objeto, una clase derivada de <xref:System.Printing.PrintServer>. El servidor de impresión local es el equipo en el que se ejecuta la aplicación.  
  
 El último paso significativo consiste en pasar la matriz a la <xref:System.Printing.PrintServer.GetPrintQueues%2A> método.  
  
 Por último, los resultados se presentan al usuario.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Puede ampliar este ejemplo manteniendo la `foreach` bucle que recorre cada cola de impresión se realizan más de filtrado. Por ejemplo, podría dejar fuera las impresoras que no admiten la impresión a dos caras haciendo que la llamada de bucle cada cola de impresión <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> método y probar el valor devuelto para la presencia de impresión a doble cara.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Documentos en WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Información general sobre impresión](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Escritor de documentos XPS de Microsoft](http://go.microsoft.com/fwlink/?LinkId=147319)
