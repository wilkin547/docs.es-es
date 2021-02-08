---
description: Más información sobre cómo usar ExpressionTextBox en un diseñador de actividad personalizado
title: Uso de la ExpressionTextBox en un diseñador de actividad personalizado
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: c333832c2f955354233371c6572f8ae27e5d8643
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787765"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="61cd5-103">Uso de la ExpressionTextBox en un diseñador de actividad personalizado</span><span class="sxs-lookup"><span data-stu-id="61cd5-103">Using the ExpressionTextBox in a Custom Activity Designer</span></span>

<span data-ttu-id="61cd5-104">En este ejemplo se muestra cómo utilizar el objeto <xref:System.Activities.Presentation.View.ExpressionTextBox> en un diseñador de actividad personalizado.</span><span class="sxs-lookup"><span data-stu-id="61cd5-104">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="61cd5-105">La actividad personalizada, `MultiAssign`, asigna dos valores de cadena a dos variables de cadena.</span><span class="sxs-lookup"><span data-stu-id="61cd5-105">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="61cd5-106">Algunos controles de <xref:System.Activities.Presentation.View.ExpressionTextBox> se enlazan a argumentos <xref:System.Activities.InArgument> y otros a argumentos <xref:System.Activities.OutArgument>.</span><span class="sxs-lookup"><span data-stu-id="61cd5-106">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>

## <a name="sample-details"></a><span data-ttu-id="61cd5-107">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="61cd5-107">Sample details</span></span>

 <span data-ttu-id="61cd5-108">`ArgumentToExpressionConverter` es el convertidor de tipos utilizado cuando se enlazan expresiones a argumentos.</span><span class="sxs-lookup"><span data-stu-id="61cd5-108">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="61cd5-109">`ConverterParameter` debe establecerse en `In` o en `Out`, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="61cd5-109">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="61cd5-110">No se admite `InOut`.</span><span class="sxs-lookup"><span data-stu-id="61cd5-110">`InOut` is not supported.</span></span>

 <span data-ttu-id="61cd5-111">El `UseLocationExpression` atributo se usa en `OutArgument` s para especificar que la expresión debe ser una expresión de valor L ("valor izquierdo" o "valor de ubicación").</span><span class="sxs-lookup"><span data-stu-id="61cd5-111">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="61cd5-112">En la mayoría de los casos, una expresión de valor L es un identificador de Visual Basic válido que se usa para indicar que el argumento `OutArgument` que se devuelve es una variable o nombre de argumento.</span><span class="sxs-lookup"><span data-stu-id="61cd5-112">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>

 <span data-ttu-id="61cd5-113">El atributo `MaxLines` se establece en uno en este ejemplo y `MinLines` no se establece.</span><span class="sxs-lookup"><span data-stu-id="61cd5-113">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="61cd5-114">Esto indica que <xref:System.Activities.Presentation.View.ExpressionTextBox> representa el tamaño fijo de una línea, independientemente de la cantidad de texto que escriba el usuario.</span><span class="sxs-lookup"><span data-stu-id="61cd5-114">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="61cd5-115">Para permitir que <xref:System.Activities.Presentation.View.ExpressionTextBox> aumente de tamaño para ajustarse a los datos proporcionados por el usuario, establezca el valor de `MaxLines` como mayor que `MinLines`.</span><span class="sxs-lookup"><span data-stu-id="61cd5-115">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>

 <span data-ttu-id="61cd5-116">ExpressionTextBox solo se puede enlazar a argumentos y no a propiedades CLR.</span><span class="sxs-lookup"><span data-stu-id="61cd5-116">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="61cd5-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="61cd5-117">To use this sample</span></span>

1. <span data-ttu-id="61cd5-118">Con Visual Studio 2010, abra el archivo ExpressionTextBoxSample. sln.</span><span class="sxs-lookup"><span data-stu-id="61cd5-118">Using Visual Studio 2010, open the ExpressionTextBoxSample.sln file.</span></span>

2. <span data-ttu-id="61cd5-119">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="61cd5-119">To build the solution, press CTRL+SHIFT+B.</span></span>

#### <a name="to-run-this-sample"></a><span data-ttu-id="61cd5-120">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="61cd5-120">To run this sample</span></span>

1. <span data-ttu-id="61cd5-121">Agregue a la solución una aplicación de consola de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="61cd5-121">Add a new Workflow Console Application to the solution.</span></span>

2. <span data-ttu-id="61cd5-122">Agregue una referencia al proyecto **ExpressionTextBoxSample** desde el nuevo proyecto de aplicación de consola de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="61cd5-122">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>

3. <span data-ttu-id="61cd5-123">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="61cd5-123">Build the solution.</span></span>

4. <span data-ttu-id="61cd5-124">Arrastre la actividad de **asignación Multiasignada** desde el cuadro de herramientas y colóquela en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="61cd5-124">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61cd5-125">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="61cd5-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="61cd5-126">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="61cd5-126">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="61cd5-127">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="61cd5-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="61cd5-128">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="61cd5-128">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="61cd5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="61cd5-129">See also</span></span>

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [<span data-ttu-id="61cd5-130">Desarrollar aplicaciones con el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="61cd5-130">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
