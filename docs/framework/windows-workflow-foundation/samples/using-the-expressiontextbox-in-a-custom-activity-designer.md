---
title: "Uso de la ExpressionTextBox en un diseñador de actividad personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 85fe8dcbd0ef5e774ab81ed167ff937ec2e09d83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="02bf9-102">Uso de la ExpressionTextBox en un diseñador de actividad personalizado</span><span class="sxs-lookup"><span data-stu-id="02bf9-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="02bf9-103">En este ejemplo se muestra cómo utilizar el objeto <xref:System.Activities.Presentation.View.ExpressionTextBox> en un diseñador de actividad personalizado.</span><span class="sxs-lookup"><span data-stu-id="02bf9-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="02bf9-104">La actividad personalizada, `MultiAssign`, asigna dos valores de cadena a dos variables de cadena.</span><span class="sxs-lookup"><span data-stu-id="02bf9-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="02bf9-105">Algunos controles de <xref:System.Activities.Presentation.View.ExpressionTextBox> se enlazan a argumentos <xref:System.Activities.InArgument> y otros a argumentos <xref:System.Activities.OutArgument>.</span><span class="sxs-lookup"><span data-stu-id="02bf9-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="02bf9-106">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="02bf9-106">Sample details</span></span>  
 <span data-ttu-id="02bf9-107">`ArgumentToExpressionConverter` es el convertidor de tipos utilizado cuando se enlazan expresiones a argumentos.</span><span class="sxs-lookup"><span data-stu-id="02bf9-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="02bf9-108">`ConverterParameter` debe establecerse en `In` o en `Out`, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="02bf9-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="02bf9-109">No se admite `InOut`.</span><span class="sxs-lookup"><span data-stu-id="02bf9-109">`InOut` is not supported.</span></span>  
  
 <span data-ttu-id="02bf9-110">El `UseLocationExpression` atributo se usa en `OutArgument`s para especificar que la expresión debe ser una expresión de valor L ("valor izquierdo" o "valor de ubicación").</span><span class="sxs-lookup"><span data-stu-id="02bf9-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="02bf9-111">En la mayoría de los casos, una expresión de valor L es un identificador de Visual Basic válido que se usa para indicar que el argumento `OutArgument` que se devuelve es una variable o nombre de argumento.</span><span class="sxs-lookup"><span data-stu-id="02bf9-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>  
  
 <span data-ttu-id="02bf9-112">El atributo `MaxLines` se establece en uno en este ejemplo y `MinLines` no se establece.</span><span class="sxs-lookup"><span data-stu-id="02bf9-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="02bf9-113">Esto indica que <xref:System.Activities.Presentation.View.ExpressionTextBox> representa el tamaño fijo de una línea, independientemente de la cantidad de texto que escriba el usuario.</span><span class="sxs-lookup"><span data-stu-id="02bf9-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="02bf9-114">Para permitir que <xref:System.Activities.Presentation.View.ExpressionTextBox> aumente de tamaño para ajustarse a los datos proporcionados por el usuario, establezca el valor de `MaxLines` como mayor que `MinLines`.</span><span class="sxs-lookup"><span data-stu-id="02bf9-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>  
  
 <span data-ttu-id="02bf9-115">ExpressionTextBox solo se puede enlazar a argumentos y no a propiedades CLR.</span><span class="sxs-lookup"><span data-stu-id="02bf9-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="02bf9-116">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="02bf9-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="02bf9-117">Abra el archivo ExpressionTextBoxSample.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02bf9-117">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExpressionTextBoxSample.sln file.</span></span>  
  
2.  <span data-ttu-id="02bf9-118">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="02bf9-118">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="02bf9-119">Para ejecutar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="02bf9-119">To run this sample</span></span>  
  
1.  <span data-ttu-id="02bf9-120">Agregue a la solución una aplicación de consola de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02bf9-120">Add a new Workflow Console Application to the solution.</span></span>  
  
2.  <span data-ttu-id="02bf9-121">Agregue una referencia a la **ExpressionTextBoxSample** proyecto desde el nuevo proyecto de aplicación de consola de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02bf9-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>  
  
3.  <span data-ttu-id="02bf9-122">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="02bf9-122">Build the solution.</span></span>  
  
4.  <span data-ttu-id="02bf9-123">Arrastre el **MultiAssign** actividad en el cuadro de herramientas y colóquelo en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02bf9-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02bf9-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="02bf9-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="02bf9-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="02bf9-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="02bf9-126">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02bf9-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="02bf9-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="02bf9-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="02bf9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="02bf9-128">See Also</span></span>  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [<span data-ttu-id="02bf9-129">Desarrollar aplicaciones con el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="02bf9-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
