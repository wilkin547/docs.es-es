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
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="eacdd-102">Cómo: Enumerar un subconjunto de colas de impresión</span><span class="sxs-lookup"><span data-stu-id="eacdd-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="eacdd-103">Una situación común que se enfrenta a los profesionales de tecnologías de la información (TI) que administran un conjunto de impresoras de toda la compañía es generar una lista de impresoras que tienen ciertas características.</span><span class="sxs-lookup"><span data-stu-id="eacdd-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="eacdd-104">Esta funcionalidad se proporciona mediante el método <xref:System.Printing.PrintServer.GetPrintQueues%2A> de un objeto <xref:System.Printing.PrintServer> y la enumeración <xref:System.Printing.EnumeratedPrintQueueTypes>.</span><span class="sxs-lookup"><span data-stu-id="eacdd-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eacdd-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eacdd-105">Example</span></span>  
 <span data-ttu-id="eacdd-106">En el ejemplo siguiente, el código comienza creando una matriz de marcas que especifican las características de las colas de impresión que deseamos Mostrar.</span><span class="sxs-lookup"><span data-stu-id="eacdd-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="eacdd-107">En este ejemplo, estamos buscando colas de impresión que se instalan localmente en el servidor de impresión y que se comparten.</span><span class="sxs-lookup"><span data-stu-id="eacdd-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="eacdd-108">La enumeración <xref:System.Printing.EnumeratedPrintQueueTypes> proporciona muchas otras posibilidades.</span><span class="sxs-lookup"><span data-stu-id="eacdd-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="eacdd-109">A continuación, el código crea un objeto <xref:System.Printing.LocalPrintServer>, una clase derivada de <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="eacdd-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="eacdd-110">El servidor de impresión local es el equipo en el que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eacdd-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="eacdd-111">El último paso significativo es pasar la matriz al método <xref:System.Printing.PrintServer.GetPrintQueues%2A>.</span><span class="sxs-lookup"><span data-stu-id="eacdd-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="eacdd-112">Por último, los resultados se presentan al usuario.</span><span class="sxs-lookup"><span data-stu-id="eacdd-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="eacdd-113">Puede ampliar este ejemplo si tiene el bucle `foreach` que recorre cada cola de impresión para realizar un filtrado adicional.</span><span class="sxs-lookup"><span data-stu-id="eacdd-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="eacdd-114">Por ejemplo, puede filtrar las impresoras que no admiten la impresión a dos caras al hacer que el bucle llame a cada método <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> de una cola de impresión y probar el valor devuelto para la presencia de dúplex.</span><span class="sxs-lookup"><span data-stu-id="eacdd-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacdd-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eacdd-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="eacdd-116">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="eacdd-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="eacdd-117">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="eacdd-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="eacdd-118">Escritor de documentos XPS de Microsoft</span><span class="sxs-lookup"><span data-stu-id="eacdd-118">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
