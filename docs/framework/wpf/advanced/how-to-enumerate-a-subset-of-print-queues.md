---
title: Procedimiento Enumerar un subconjunto de colas de impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: e1cbd9e7332a5e021e1cf9fba75f6d21ae01582b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558571"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="5ecea-102">Procedimiento Enumerar un subconjunto de colas de impresión</span><span class="sxs-lookup"><span data-stu-id="5ecea-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="5ecea-103">Es una situación común que se enfrentan los profesionales de tecnologías (TI) de información que administra un conjunto de toda la compañía de impresoras generar una lista de impresoras que tienen ciertas características.</span><span class="sxs-lookup"><span data-stu-id="5ecea-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="5ecea-104">Esta funcionalidad se proporciona mediante el <xref:System.Printing.PrintServer.GetPrintQueues%2A> método de un <xref:System.Printing.PrintServer> objeto y el <xref:System.Printing.EnumeratedPrintQueueTypes> enumeración.</span><span class="sxs-lookup"><span data-stu-id="5ecea-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ecea-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ecea-105">Example</span></span>  
 <span data-ttu-id="5ecea-106">En el ejemplo siguiente, el código comienza creando una matriz de marcas que especifican las características de las colas de impresión que desea enumerar.</span><span class="sxs-lookup"><span data-stu-id="5ecea-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="5ecea-107">En este ejemplo, examinamos las colas de impresión que se instalan localmente en el servidor de impresión y se comparten.</span><span class="sxs-lookup"><span data-stu-id="5ecea-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="5ecea-108">El <xref:System.Printing.EnumeratedPrintQueueTypes> enumeración proporciona muchas otras posibilidades.</span><span class="sxs-lookup"><span data-stu-id="5ecea-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="5ecea-109">El código, a continuación, crea un <xref:System.Printing.LocalPrintServer> objeto, una clase derivada de <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="5ecea-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="5ecea-110">El servidor de impresión local es el equipo donde se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5ecea-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="5ecea-111">Es el último paso significativo pasar la matriz a la <xref:System.Printing.PrintServer.GetPrintQueues%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5ecea-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="5ecea-112">Por último, los resultados se presentan al usuario.</span><span class="sxs-lookup"><span data-stu-id="5ecea-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="5ecea-113">Puede extender este ejemplo haciendo que el `foreach` bucle que recorre cada cola de impresión se realizan más de filtrado.</span><span class="sxs-lookup"><span data-stu-id="5ecea-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="5ecea-114">Por ejemplo, podría dejar fuera las impresoras que no admiten la impresión a dos caras haciendo que la llamada de bucle cada cola de impresión <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> método y prueba el valor devuelto para la presencia de dúplex.</span><span class="sxs-lookup"><span data-stu-id="5ecea-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecea-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ecea-115">See also</span></span>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="5ecea-116">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="5ecea-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="5ecea-117">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="5ecea-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
- [<span data-ttu-id="5ecea-118">Escritor de documentos XPS de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5ecea-118">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
