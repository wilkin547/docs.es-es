---
title: 'Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
ms.openlocfilehash: ac5fb17e527bcbcb55f98ec0ced06c152555ce6c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410080"
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a><span data-ttu-id="43f52-102">Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43f52-102">How to: Log Messages When the Application Starts or Shuts Down (Visual Basic)</span></span>

<span data-ttu-id="43f52-103">Puede usar los objetos `My.Application.Log` y `My.Log` para registrar información sobre los eventos que se producen en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="43f52-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="43f52-104">En este ejemplo se muestra cómo usar el método `My.Application.Log.WriteEntry` con los eventos `Startup` y `Shutdown` para escribir información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="43f52-104">This example shows how to use the `My.Application.Log.WriteEntry` method with the `Startup` and `Shutdown` events to write tracing information.</span></span>  
  
### <a name="to-access-the-applications-event-handler-code"></a><span data-ttu-id="43f52-105">Para acceder a código de controlador de eventos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="43f52-105">To access the application's event-handler code</span></span>  
  
1. <span data-ttu-id="43f52-106">Seleccione un proyecto en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="43f52-106">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="43f52-107">En el menú **Proyecto** , elija **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="43f52-107">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="43f52-108">Haga clic en la pestaña **Aplicación** .</span><span class="sxs-lookup"><span data-stu-id="43f52-108">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="43f52-109">Haga clic en el botón **Ver eventos de aplicaciones** para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="43f52-109">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="43f52-110">Se abre el archivo ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="43f52-110">This opens the ApplicationEvents.vb file.</span></span>  
  
### <a name="to-log-messages-when-the-application-starts"></a><span data-ttu-id="43f52-111">Para registrar mensajes cuando se inicia la aplicación</span><span class="sxs-lookup"><span data-stu-id="43f52-111">To log messages when the application starts</span></span>  
  
1. <span data-ttu-id="43f52-112">Tenga el archivo ApplicationEvents.vb abierto en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="43f52-112">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="43f52-113">En el menú **General** , elija **Eventos MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="43f52-113">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2. <span data-ttu-id="43f52-114">En el menú **Declaraciones** , elija **Inicio**.</span><span class="sxs-lookup"><span data-stu-id="43f52-114">On the **Declarations** menu, choose **Startup**.</span></span>  
  
     <span data-ttu-id="43f52-115">La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> antes de que se ejecute la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="43f52-115">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> event before the main application runs.</span></span>  
  
3. <span data-ttu-id="43f52-116">Agregue el método `My.Application.Log.WriteEntry` al controlador de eventos `Startup` .</span><span class="sxs-lookup"><span data-stu-id="43f52-116">Add the `My.Application.Log.WriteEntry` method to the `Startup` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#1)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a><span data-ttu-id="43f52-117">Para registrar mensajes cuando se cierra la aplicación</span><span class="sxs-lookup"><span data-stu-id="43f52-117">To log messages when the application shuts down</span></span>  
  
1. <span data-ttu-id="43f52-118">Tenga el archivo ApplicationEvents.vb abierto en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="43f52-118">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="43f52-119">En el menú **General** , elija **Eventos MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="43f52-119">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2. <span data-ttu-id="43f52-120">En el **declaraciones** menú, elija **Apagar**.</span><span class="sxs-lookup"><span data-stu-id="43f52-120">On the **Declarations** menu, choose **Shutdown**.</span></span>  
  
     <span data-ttu-id="43f52-121">La aplicación genera el evento <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> después de la ejecución de la aplicación principal, pero antes del cierre.</span><span class="sxs-lookup"><span data-stu-id="43f52-121">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> event after the main application runs, but before it shuts down.</span></span>  
  
3. <span data-ttu-id="43f52-122">Agregue el método `My.Application.Log.WriteEntry` al controlador de eventos `Shutdown` .</span><span class="sxs-lookup"><span data-stu-id="43f52-122">Add the `My.Application.Log.WriteEntry` method to the `Shutdown` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="43f52-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43f52-123">Example</span></span>  

 <span data-ttu-id="43f52-124">Puede usar el **Diseñador de proyectos** para acceder a los eventos de aplicación en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="43f52-124">You can use the **Project Designer** to access the application events in the Code Editor.</span></span> <span data-ttu-id="43f52-125">Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="43f52-125">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 [!code-vb[VbVbalrMyApplicationLog#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="43f52-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="43f52-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="43f52-127">Página Aplicación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43f52-127">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="43f52-128">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="43f52-128">Working with Application Logs</span></span>](working-with-application-logs.md)
