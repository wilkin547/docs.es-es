---
description: 'Más información acerca de: Procedimiento: para registrar excepciones en Visual Basic'
title: Procedimiento para registrar excepciones
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: a4155de4e73c632edf071256976161cfdbffba77
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775219"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="b982b-103">Cómo: Registrar excepciones en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b982b-103">How to: Log Exceptions in Visual Basic</span></span>

<span data-ttu-id="b982b-104">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre excepciones que se producen en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b982b-104">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="b982b-105">Estos ejemplos muestran cómo usar el método `My.Application.Log.WriteException` para registrar excepciones que detecta explícitamente y excepciones que no se controlan.</span><span class="sxs-lookup"><span data-stu-id="b982b-105">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="b982b-106">Para registrar información de seguimiento, use el método `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="b982b-106">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="b982b-107">Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.</span><span class="sxs-lookup"><span data-stu-id="b982b-107">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="b982b-108">Para registrar una excepción controlada</span><span class="sxs-lookup"><span data-stu-id="b982b-108">To log a handled exception</span></span>  
  
1. <span data-ttu-id="b982b-109">Cree el método que generará la información de excepción.</span><span class="sxs-lookup"><span data-stu-id="b982b-109">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#9)]  
  
2. <span data-ttu-id="b982b-110">Use un bloque `Try...Catch` para detectar la excepción.</span><span class="sxs-lookup"><span data-stu-id="b982b-110">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#6)]  
  
3. <span data-ttu-id="b982b-111">Coloque el código que podría generar una excepción en el bloque `Try`.</span><span class="sxs-lookup"><span data-stu-id="b982b-111">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="b982b-112">Quite la marca de comentario de las líneas `Dim` y `MsgBox` para generar una excepción <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="b982b-112">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#7)]  
  
4. <span data-ttu-id="b982b-113">En el bloque `Catch`, use el método `My.Application.Log.WriteException` para escribir la información de excepción.</span><span class="sxs-lookup"><span data-stu-id="b982b-113">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#8)]  
  
     <span data-ttu-id="b982b-114">En el ejemplo siguiente se muestra el código completo para registrar una excepción controlada.</span><span class="sxs-lookup"><span data-stu-id="b982b-114">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#10)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="b982b-115">Para registrar una excepción no controlada</span><span class="sxs-lookup"><span data-stu-id="b982b-115">To log an unhandled exception</span></span>  
  
1. <span data-ttu-id="b982b-116">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="b982b-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b982b-117">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b982b-117">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="b982b-118">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="b982b-118">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="b982b-119">Haga clic en el botón **Ver eventos de aplicaciones** para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="b982b-119">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="b982b-120">Se abre el archivo ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="b982b-120">This opens the ApplicationEvents.vb file.</span></span>  
  
4. <span data-ttu-id="b982b-121">Tenga el archivo ApplicationEvents.vb abierto en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="b982b-121">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="b982b-122">En el menú **General** , elija **Eventos MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="b982b-122">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5. <span data-ttu-id="b982b-123">En el menú **Declaraciones**, pulse **UnhandledException**.</span><span class="sxs-lookup"><span data-stu-id="b982b-123">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="b982b-124">La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> antes de que se ejecute la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="b982b-124">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6. <span data-ttu-id="b982b-125">Agregue el método `My.Application.Log.WriteException` al controlador de eventos `UnhandledException` .</span><span class="sxs-lookup"><span data-stu-id="b982b-125">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#4)]  
  
     <span data-ttu-id="b982b-126">En el siguiente ejemplo se muestra el código completo para registrar una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="b982b-126">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="b982b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b982b-127">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="b982b-128">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b982b-128">Working with Application Logs</span></span>](working-with-application-logs.md)
- [<span data-ttu-id="b982b-129">Cómo: Escribir mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="b982b-129">How to: Write Log Messages</span></span>](how-to-write-log-messages.md)
- [<span data-ttu-id="b982b-130">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="b982b-130">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="b982b-131">Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="b982b-131">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](walkthrough-changing-where-my-application-log-writes-information.md)
