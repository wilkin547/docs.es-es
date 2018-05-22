---
title: 'Cómo: Registrar excepciones en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: b8ec45f43438f8181d9e045cdf43c81db34e4242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="241b5-102">Cómo: Registrar excepciones en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="241b5-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="241b5-103">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre excepciones que se producen en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="241b5-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="241b5-104">Estos ejemplos muestran cómo usar el método `My.Application.Log.WriteException` para registrar excepciones que detecta explícitamente y excepciones que no se controlan.</span><span class="sxs-lookup"><span data-stu-id="241b5-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="241b5-105">Para registrar información de seguimiento, use el método `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="241b5-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="241b5-106">Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="241b5-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="241b5-107">Para registrar una excepción controlada</span><span class="sxs-lookup"><span data-stu-id="241b5-107">To log a handled exception</span></span>  
  
1.  <span data-ttu-id="241b5-108">Cree el método que generará la información de excepción.</span><span class="sxs-lookup"><span data-stu-id="241b5-108">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  <span data-ttu-id="241b5-109">Use un bloque `Try...Catch` para detectar la excepción.</span><span class="sxs-lookup"><span data-stu-id="241b5-109">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  <span data-ttu-id="241b5-110">Coloque el código que podría generar una excepción en el bloque `Try`.</span><span class="sxs-lookup"><span data-stu-id="241b5-110">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="241b5-111">Quite la marca de comentario de las líneas `Dim` y `MsgBox` para generar una excepción <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="241b5-111">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  <span data-ttu-id="241b5-112">En el bloque `Catch`, use el método `My.Application.Log.WriteException` para escribir la información de excepción.</span><span class="sxs-lookup"><span data-stu-id="241b5-112">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     <span data-ttu-id="241b5-113">En el ejemplo siguiente se muestra el código completo para registrar una excepción controlada.</span><span class="sxs-lookup"><span data-stu-id="241b5-113">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="241b5-114">Para registrar una excepción no controlada</span><span class="sxs-lookup"><span data-stu-id="241b5-114">To log an unhandled exception</span></span>  
  
1.  <span data-ttu-id="241b5-115">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="241b5-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="241b5-116">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="241b5-116">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="241b5-117">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="241b5-117">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="241b5-118">Haga clic en el botón **Ver eventos de aplicaciones** para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="241b5-118">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="241b5-119">Se abre el archivo ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="241b5-119">This opens the ApplicationEvents.vb file.</span></span>  
  
4.  <span data-ttu-id="241b5-120">Tenga el archivo ApplicationEvents.vb abierto en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="241b5-120">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="241b5-121">En el menú **General** , elija **Eventos MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="241b5-121">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5.  <span data-ttu-id="241b5-122">En el menú **Declaraciones**, pulse **UnhandledException**.</span><span class="sxs-lookup"><span data-stu-id="241b5-122">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="241b5-123">La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> antes de que se ejecute la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="241b5-123">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6.  <span data-ttu-id="241b5-124">Agregue el método `My.Application.Log.WriteException` al controlador de eventos `UnhandledException` .</span><span class="sxs-lookup"><span data-stu-id="241b5-124">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     <span data-ttu-id="241b5-125">En el siguiente ejemplo se muestra el código completo para registrar una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="241b5-125">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="241b5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="241b5-126">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [<span data-ttu-id="241b5-127">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="241b5-127">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="241b5-128">Escribir mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="241b5-128">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [<span data-ttu-id="241b5-129">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información</span><span class="sxs-lookup"><span data-stu-id="241b5-129">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [<span data-ttu-id="241b5-130">Tutorial: Cambiar el lugar donde My.Application.Log escribe información</span><span class="sxs-lookup"><span data-stu-id="241b5-130">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
