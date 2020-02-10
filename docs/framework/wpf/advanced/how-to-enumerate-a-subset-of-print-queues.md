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
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094545"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Cómo: Enumerar un subconjunto de colas de impresión
Una situación común que se enfrenta a los profesionales de tecnologías de la información (TI) que administran un conjunto de impresoras de toda la compañía es generar una lista de impresoras que tienen ciertas características. Esta funcionalidad se proporciona mediante el método <xref:System.Printing.PrintServer.GetPrintQueues%2A> de un objeto <xref:System.Printing.PrintServer> y la enumeración <xref:System.Printing.EnumeratedPrintQueueTypes>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el código comienza creando una matriz de marcas que especifican las características de las colas de impresión que deseamos Mostrar. En este ejemplo, estamos buscando colas de impresión que se instalan localmente en el servidor de impresión y que se comparten. La enumeración <xref:System.Printing.EnumeratedPrintQueueTypes> proporciona muchas otras posibilidades.  
  
 A continuación, el código crea un objeto <xref:System.Printing.LocalPrintServer>, una clase derivada de <xref:System.Printing.PrintServer>. El servidor de impresión local es el equipo en el que se ejecuta la aplicación.  
  
 El último paso significativo es pasar la matriz al método <xref:System.Printing.PrintServer.GetPrintQueues%2A>.  
  
 Por último, los resultados se presentan al usuario.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Puede ampliar este ejemplo si tiene el bucle `foreach` que recorre cada cola de impresión para realizar un filtrado adicional. Por ejemplo, puede filtrar las impresoras que no admiten la impresión a dos caras al hacer que el bucle llame a cada método <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> de una cola de impresión y probar el valor devuelto para la presencia de dúplex.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Documentos en WPF](documents-in-wpf.md)
- [Información general sobre impresión](printing-overview.md)
- [Escritor de documentos XPS de Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer)
