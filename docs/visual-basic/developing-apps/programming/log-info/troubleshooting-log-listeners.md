---
title: 'Solución de problemas: Agentes de escucha de registro'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: dd139935dae7fe4d1334b861e6590df29bab7202
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74346853"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="967c7-102">Solucionar problemas: Agentes de escucha del Registro (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="967c7-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="967c7-103">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="967c7-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="967c7-104">Para determinar qué agentes de escucha de registro reciben esos mensajes, vea [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="967c7-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="967c7-105">El objeto `Log` puede usar el filtrado del registro para limitar la cantidad de información que registra.</span><span class="sxs-lookup"><span data-stu-id="967c7-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="967c7-106">Si los filtros se configuran de manera incorrecta, los registros pueden contener información equivocada.</span><span class="sxs-lookup"><span data-stu-id="967c7-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="967c7-107">Para obtener más información sobre los filtros, vea [Tutorial: Filtrar el resultado de My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="967c7-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="967c7-108">En cambio, si un registro se configura incorrectamente, puede necesitar más información sobre su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="967c7-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="967c7-109">Puede obtener esta información mediante la propiedad `TraceSource` avanzada del registro.</span><span class="sxs-lookup"><span data-stu-id="967c7-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="967c7-110">Para determinar los agentes de escucha de registro del objeto Log con código</span><span class="sxs-lookup"><span data-stu-id="967c7-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="967c7-111">Importe el espacio de nombres <xref:System.Diagnostics> al principio del archivo de código.</span><span class="sxs-lookup"><span data-stu-id="967c7-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="967c7-112">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="967c7-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="967c7-113">Cree una función que devuelva una cadena compuesta por información de cada uno de los agentes de escucha del registro.</span><span class="sxs-lookup"><span data-stu-id="967c7-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="967c7-114">Pase la colección de los agentes de escucha de seguimiento del registro a la función `GetListeners` y muestre el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="967c7-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="967c7-115">Para obtener más información, consulta <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="967c7-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967c7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="967c7-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="967c7-117">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="967c7-117">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="967c7-118">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="967c7-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
