---
title: 'Solución del problema: Agentes de escucha de registro (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 12282df50bc42d2a153a9aa8db01f2654acd91ce
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299532"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="021bf-102">Solución del problema: Agentes de escucha de registro (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="021bf-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="021bf-103">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="021bf-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="021bf-104">Para determinar qué agentes de escucha de registro reciben esos mensajes, vea [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="021bf-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="021bf-105">El objeto `Log` puede usar el filtrado del registro para limitar la cantidad de información que registra.</span><span class="sxs-lookup"><span data-stu-id="021bf-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="021bf-106">Si los filtros se configuran de manera incorrecta, los registros pueden contener información equivocada.</span><span class="sxs-lookup"><span data-stu-id="021bf-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="021bf-107">Para más información sobre el filtrado, vea [Tutorial: Filtrar el resultado de My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="021bf-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="021bf-108">En cambio, si un registro se configura incorrectamente, puede necesitar más información sobre su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="021bf-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="021bf-109">Puede obtener esta información mediante la propiedad `TraceSource` avanzada del registro.</span><span class="sxs-lookup"><span data-stu-id="021bf-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="021bf-110">Para determinar los agentes de escucha de registro del objeto Log con código</span><span class="sxs-lookup"><span data-stu-id="021bf-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="021bf-111">Importe el espacio de nombres <xref:System.Diagnostics> al principio del archivo de código.</span><span class="sxs-lookup"><span data-stu-id="021bf-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="021bf-112">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="021bf-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="021bf-113">Cree una función que devuelva una cadena compuesta por información de cada uno de los agentes de escucha del registro.</span><span class="sxs-lookup"><span data-stu-id="021bf-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="021bf-114">Pase la colección de los agentes de escucha de seguimiento del registro a la función `GetListeners` y muestre el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="021bf-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="021bf-115">Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="021bf-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="021bf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="021bf-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="021bf-117">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="021bf-117">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="021bf-118">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="021bf-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
