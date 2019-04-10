---
title: Filtrar Enumerar un subconjunto de colas de impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: adcfff0196bd0430ec1ae563fbd5489062de11f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217190"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Filtrar Enumerar un subconjunto de colas de impresión
Es una situación común que se enfrentan los profesionales de tecnologías (TI) de información que administra un conjunto de toda la compañía de impresoras generar una lista de impresoras que tienen ciertas características. Esta funcionalidad se proporciona mediante el <xref:System.Printing.PrintServer.GetPrintQueues%2A> método de un <xref:System.Printing.PrintServer> objeto y el <xref:System.Printing.EnumeratedPrintQueueTypes> enumeración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el código comienza creando una matriz de marcas que especifican las características de las colas de impresión que desea enumerar. En este ejemplo, examinamos las colas de impresión que se instalan localmente en el servidor de impresión y se comparten. El <xref:System.Printing.EnumeratedPrintQueueTypes> enumeración proporciona muchas otras posibilidades.  
  
 El código, a continuación, crea un <xref:System.Printing.LocalPrintServer> objeto, una clase derivada de <xref:System.Printing.PrintServer>. El servidor de impresión local es el equipo donde se ejecuta la aplicación.  
  
 Es el último paso significativo pasar la matriz a la <xref:System.Printing.PrintServer.GetPrintQueues%2A> método.  
  
 Por último, los resultados se presentan al usuario.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Puede extender este ejemplo haciendo que el `foreach` bucle que recorre cada cola de impresión se realizan más de filtrado. Por ejemplo, podría dejar fuera las impresoras que no admiten la impresión a dos caras haciendo que la llamada de bucle cada cola de impresión <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> método y prueba el valor devuelto para la presencia de dúplex.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
- [Escritor de documentos XPS de Microsoft](https://go.microsoft.com/fwlink/?LinkId=147319)
