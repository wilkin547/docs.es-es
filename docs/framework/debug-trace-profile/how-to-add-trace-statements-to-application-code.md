---
title: Procedimiento para agregar instrucciones de seguimiento al código de una aplicación
description: Obtenga información sobre cómo agregar instrucciones de seguimiento al código de la aplicación en .NET. Los métodos que se usan con más frecuencia para el seguimiento son los métodos para escribir la salida en los agentes de escucha.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], conditional writes based on switches
- trace statements
- WriteLineIf method
- tracing [.NET Framework], adding trace statements
- Assert method, tracing code
- trace switches, conditional writes based on switches
- WriteIf method
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
ms.openlocfilehash: 6beecf39d4372a194a9110ed8942b998443934d4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244215"
---
# <a name="how-to-add-trace-statements-to-application-code"></a><span data-ttu-id="e8b77-104">Procedimiento para agregar instrucciones de seguimiento al código de una aplicación</span><span class="sxs-lookup"><span data-stu-id="e8b77-104">How to: Add Trace Statements to Application Code</span></span>

<span data-ttu-id="e8b77-105">Los métodos que se usan con mayor frecuencia para seguimiento son los métodos para escribir los resultados en agentes de escucha: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert** y **Fail**.</span><span class="sxs-lookup"><span data-stu-id="e8b77-105">The methods used most often for tracing are the methods for writing output to listeners: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, and **Fail**.</span></span> <span data-ttu-id="e8b77-106">Estos métodos se pueden dividir en dos categorías: **Write**, **WriteLine** y **Fail** emiten resultados de forma incondicional, mientras que **WriteIf**, **WriteLineIf** y **Assert** prueban una condición booleana y escriben o no escriben en función del valor de la condición.</span><span class="sxs-lookup"><span data-stu-id="e8b77-106">These methods can be divided into two categories: **Write**, **WriteLine**, and **Fail** all emit output unconditionally, whereas **WriteIf**, **WriteLineIf**, and **Assert** test a Boolean condition, and write or do not write based on the value of the condition.</span></span> <span data-ttu-id="e8b77-107">**WriteIf** y **WriteLineIf** emiten resultados si la condición es `true` y **Assert** emite resultados si la condición es `false`.</span><span class="sxs-lookup"><span data-stu-id="e8b77-107">**WriteIf** and **WriteLineIf** emit output if the condition is `true`, and **Assert** emits output if the condition is `false`.</span></span>  
  
 <span data-ttu-id="e8b77-108">Al diseñar la estrategia de depuración y traza, debe pensar cómo desea presentar los resultados.</span><span class="sxs-lookup"><span data-stu-id="e8b77-108">When designing your tracing and debugging strategy, you should think about how you want the output to look.</span></span> <span data-ttu-id="e8b77-109">Si hay varias instrucciones **Write** con información no relacionada, se creará un registro difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="e8b77-109">Multiple **Write** statements filled with unrelated information will create a log that is difficult to read.</span></span> <span data-ttu-id="e8b77-110">Por otro lado, usar **WriteLine** para colocar instrucciones relacionadas en líneas independientes puede dificultar la distinción de la información que pertenece.</span><span class="sxs-lookup"><span data-stu-id="e8b77-110">On the other hand, using **WriteLine** to put related statements on separate lines may make it difficult to distinguish what information belongs together.</span></span> <span data-ttu-id="e8b77-111">En general, use varias instrucciones **Write** cuando desee combinar información de varios orígenes para crear un único mensaje informativo y use la instrucción **WriteLine** cuando desee crear un único mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="e8b77-111">In general, use multiple **Write** statements when you want to combine information from multiple sources to create a single informative message, and use the **WriteLine** statement when you want to create a single, complete message.</span></span>  
  
### <a name="to-write-a-complete-line"></a><span data-ttu-id="e8b77-112">Para escribir una línea completa</span><span class="sxs-lookup"><span data-stu-id="e8b77-112">To write a complete line</span></span>  
  
1. <span data-ttu-id="e8b77-113">Llame al método <xref:System.Diagnostics.Trace.WriteLine%2A> o <xref:System.Diagnostics.Trace.WriteLineIf%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8b77-113">Call the <xref:System.Diagnostics.Trace.WriteLine%2A> or <xref:System.Diagnostics.Trace.WriteLineIf%2A> method.</span></span>  
  
     <span data-ttu-id="e8b77-114">Se agrega un retorno de carro al final del mensaje que devuelve este método, para que el siguiente mensaje devuelto por **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** comience en la línea siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8b77-114">A carriage return is appended to the end of the message this method returns, so that the next message returned by **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the following line:</span></span>  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,
       "Error in AppendData procedure.");  
    ```  
  
### <a name="to-write-a-partial-line"></a><span data-ttu-id="e8b77-115">Para escribir una línea parcial</span><span class="sxs-lookup"><span data-stu-id="e8b77-115">To write a partial line</span></span>  
  
1. <span data-ttu-id="e8b77-116">Llame al método <xref:System.Diagnostics.Trace.Write%2A> o <xref:System.Diagnostics.Trace.WriteIf%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8b77-116">Call the <xref:System.Diagnostics.Trace.Write%2A> or <xref:System.Diagnostics.Trace.WriteIf%2A> method.</span></span>  
  
     <span data-ttu-id="e8b77-117">El siguiente mensaje generado por **Write**, **WriteIf**, **WriteLine** o **WriteLineIf** empezará en la misma línea que el mensaje generado por la instrucción **Write** o **WriteIf**:</span><span class="sxs-lookup"><span data-stu-id="e8b77-117">The next message put out by a **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the same line as the message put out by the **Write** or **WriteIf** statement:</span></span>  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
    ```  
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a><span data-ttu-id="e8b77-118">Para comprobar que se cumplen ciertas condiciones antes o después de ejecutar un método</span><span class="sxs-lookup"><span data-stu-id="e8b77-118">To verify that certain conditions exist either before or after you execute a method</span></span>  
  
1. <span data-ttu-id="e8b77-119">Llame al método <xref:System.Diagnostics.Trace.Assert%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8b77-119">Call the <xref:System.Diagnostics.Trace.Assert%2A> method.</span></span>  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="e8b77-120">Puede usar **Assert** con la depuración y el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e8b77-120">You can use **Assert** with both tracing and debugging.</span></span> <span data-ttu-id="e8b77-121">En este ejemplo se envía la pila de llamadas a cualquier agente de escucha de la colección **Listeners**.</span><span class="sxs-lookup"><span data-stu-id="e8b77-121">This example outputs the call stack to any listener in the **Listeners** collection.</span></span> <span data-ttu-id="e8b77-122">Para más información, vea [Aserciones en el código administrado](/visualstudio/debugger/assertions-in-managed-code) y <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e8b77-122">For more information, see [Assertions in Managed Code](/visualstudio/debugger/assertions-in-managed-code) and <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b77-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8b77-123">See also</span></span>

- <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e8b77-124">Seguimiento e instrumentación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e8b77-124">Tracing and Instrumenting Applications</span></span>](tracing-and-instrumenting-applications.md)
- [<span data-ttu-id="e8b77-125">Procedimiento para crear, inicializar y configurar modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e8b77-125">How to: Create, Initialize and Configure Trace Switches</span></span>](how-to-create-initialize-and-configure-trace-switches.md)
- [<span data-ttu-id="e8b77-126">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e8b77-126">Trace Switches</span></span>](trace-switches.md)
- [<span data-ttu-id="e8b77-127">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e8b77-127">Trace Listeners</span></span>](trace-listeners.md)
