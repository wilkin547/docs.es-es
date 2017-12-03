---
title: Directiva avanzada
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9752b5779f4fbb525488e88f2f11c98de7b4ba8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="advanced-policy"></a><span data-ttu-id="013f0-102">Directiva avanzada</span><span class="sxs-lookup"><span data-stu-id="013f0-102">Advanced Policy</span></span>
<span data-ttu-id="013f0-103">Este ejemplo amplía el ejemplo de directiva simple.</span><span class="sxs-lookup"><span data-stu-id="013f0-103">This sample extends the Simple Policy sample.</span></span> <span data-ttu-id="013f0-104">Además de las reglas de descuento residencial y descuento comercial del ejemplo de directiva simple, se han agregado varias nuevas reglas.</span><span class="sxs-lookup"><span data-stu-id="013f0-104">In addition to the residential discount and business discount rules from the Simple Policy example, several new rules have been added.</span></span>  
  
 <span data-ttu-id="013f0-105">Se agrega una regla de valor alto, que proporciona un descuento mayor para los pedidos de valor alto.</span><span class="sxs-lookup"><span data-stu-id="013f0-105">A high-value rule is added, which provides a bigger discount for high-value orders.</span></span> <span data-ttu-id="013f0-106">Se le proporciona un valor de prioridad menor que el de las dos reglas anteriores, para que sobrescriba el campo de descuento y tenga prioridad sobre la regla de descuento residencial o la de descuento comercial.</span><span class="sxs-lookup"><span data-stu-id="013f0-106">It is given a priority value less than the previous two rules so that it will overwrite the discount field and take precedence over both the residential and business discount rules.</span></span>  
  
 <span data-ttu-id="013f0-107">También se agrega una regla de cálculo del total, que calcula el total en función del nivel de descuento.</span><span class="sxs-lookup"><span data-stu-id="013f0-107">A calculate total rule is also added, which computes the total based on the discount level.</span></span> <span data-ttu-id="013f0-108">Muestra cómo hacer referencia a un método definido en la actividad de flujo de trabajo, y cómo utilizar las acciones Else.</span><span class="sxs-lookup"><span data-stu-id="013f0-108">It shows how to reference a method defined on the workflow activity, as well as how to use else actions.</span></span> <span data-ttu-id="013f0-109">Esta regla también muestra el comportamiento del encadenamiento, puesto que se evaluará siempre que cambie el campo de descuento.</span><span class="sxs-lookup"><span data-stu-id="013f0-109">This rule also demonstrates chaining behavior since it will be evaluated anytime the discount field changes.</span></span> <span data-ttu-id="013f0-110">Además, se muestra la atribución de método con RuleWriteAttribute en el método CalculateTotal.</span><span class="sxs-lookup"><span data-stu-id="013f0-110">Furthermore, method attributing is shown with the RuleWriteAttribute on the CalculateTotal method.</span></span> <span data-ttu-id="013f0-111">Esto hace que las reglas afectadas (ErrorTotalRule) se vuelvan a evaluar siempre que se ejecuta el método.</span><span class="sxs-lookup"><span data-stu-id="013f0-111">This causes impacted rules (ErrorTotalRule) to be re-evaluated whenever the method gets executed.</span></span>  
  
 <span data-ttu-id="013f0-112">La última regla agregada es la que detecta errores (en este caso, Total menor que 0).</span><span class="sxs-lookup"><span data-stu-id="013f0-112">The last rule added is one that detects errors (in this case, Total less than 0).</span></span> <span data-ttu-id="013f0-113">Si ocurre esto, se detiene la ejecución de la directiva.</span><span class="sxs-lookup"><span data-stu-id="013f0-113">If this occurs, the policy execution is halted.</span></span>  
  
 <span data-ttu-id="013f0-114">Finalmente, se agregan llamadas a `Console.Writeline` como acciones a cada regla para proporcionar más visibilidad de la ejecución de las reglas, a la vez que se muestra que es posible tener acceso a los métodos estáticos en tipos a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="013f0-114">Finally, `Console.Writeline` calls are added as actions to each rule to provide more visibility into rule execution, while also showing that it is possible to access static methods on referenced types.</span></span> <span data-ttu-id="013f0-115">También puede usar el seguimiento para obtener visibilidad en las reglas que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="013f0-115">You could also use tracking to get visibility into the rules that are executed.</span></span>  
  
 <span data-ttu-id="013f0-116">Este ejemplo hace uso de las clases siguientes.</span><span class="sxs-lookup"><span data-stu-id="013f0-116">The rules used in this sample are:</span></span>  
  
 <span data-ttu-id="013f0-117">**ResidentialDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="013f0-117">**ResidentialDiscountRule:**</span></span>  
  
 <span data-ttu-id="013f0-118">IF OrderValue > 500 AND CustomerType = Residential</span><span class="sxs-lookup"><span data-stu-id="013f0-118">IF OrderValue > 500 AND CustomerType = Residential</span></span>  
  
 <span data-ttu-id="013f0-119">THEN Discount = 5%</span><span class="sxs-lookup"><span data-stu-id="013f0-119">THEN Discount = 5%</span></span>  
  
 <span data-ttu-id="013f0-120">**BusinessDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="013f0-120">**BusinessDiscountRule:**</span></span>  
  
 <span data-ttu-id="013f0-121">IF OrderValue > 10000 AND CustomerType = Business</span><span class="sxs-lookup"><span data-stu-id="013f0-121">IF OrderValue > 10000 AND CustomerType = Business</span></span>  
  
 <span data-ttu-id="013f0-122">THEN Discount = 10%</span><span class="sxs-lookup"><span data-stu-id="013f0-122">THEN Discount = 10%</span></span>  
  
 <span data-ttu-id="013f0-123">**HighValueDiscountRule:**</span><span class="sxs-lookup"><span data-stu-id="013f0-123">**HighValueDiscountRule:**</span></span>  
  
 <span data-ttu-id="013f0-124">IF OrderValue > 20000</span><span class="sxs-lookup"><span data-stu-id="013f0-124">IF OrderValue > 20000</span></span>  
  
 <span data-ttu-id="013f0-125">THEN Discount = 15%</span><span class="sxs-lookup"><span data-stu-id="013f0-125">THEN Discount = 15%</span></span>  
  
 <span data-ttu-id="013f0-126">**TotalRule:**</span><span class="sxs-lookup"><span data-stu-id="013f0-126">**TotalRule:**</span></span>  
  
 <span data-ttu-id="013f0-127">IF Discount > 0</span><span class="sxs-lookup"><span data-stu-id="013f0-127">IF Discount > 0</span></span>  
  
 <span data-ttu-id="013f0-128">THEN CalculateTotal(OrderValue, Discount)</span><span class="sxs-lookup"><span data-stu-id="013f0-128">THEN CalculateTotal(OrderValue, Discount)</span></span>  
  
 <span data-ttu-id="013f0-129">ELSE Total = OrderValue</span><span class="sxs-lookup"><span data-stu-id="013f0-129">ELSE Total = OrderValue</span></span>  
  
 <span data-ttu-id="013f0-130">**ErrorTotalRule:**</span><span class="sxs-lookup"><span data-stu-id="013f0-130">**ErrorTotalRule:**</span></span>  
  
 <span data-ttu-id="013f0-131">IF Total \< 0</span><span class="sxs-lookup"><span data-stu-id="013f0-131">IF Total \< 0</span></span>  
  
 <span data-ttu-id="013f0-132">THEN Error = "Fired ErrorTotalRule"; Halt</span><span class="sxs-lookup"><span data-stu-id="013f0-132">THEN Error = "Fired ErrorTotalRule"; Halt</span></span>  
  
 <span data-ttu-id="013f0-133">La evaluación y ejecución de las reglas también se puede ver mediante el seguimiento y el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="013f0-133">Rule evaluation and execution can also be seen through tracing and tracking.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="013f0-134">Para compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="013f0-134">To build the sample</span></span>  
  
1.  <span data-ttu-id="013f0-135">Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="013f0-135">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="013f0-136">Compile la solución presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="013f0-136">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="013f0-137">Ejecute la solución sin depuración presionando CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="013f0-137">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="013f0-138">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="013f0-138">To run the sample</span></span>  
  
-   <span data-ttu-id="013f0-139">En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta AdvancedPolicy\bin\debug (o la carpeta AdvancedPolicy\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="013f0-139">In the SDK Command Prompt window, run the .exe file in the AdvancedPolicy\bin\debug folder (or the AdvancedPolicy \bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="013f0-140">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="013f0-140">The samples may already be installed on your computer.</span></span> <span data-ttu-id="013f0-141">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="013f0-141">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="013f0-142">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="013f0-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="013f0-143">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="013f0-143">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a><span data-ttu-id="013f0-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="013f0-144">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="013f0-145">Directiva simple</span><span class="sxs-lookup"><span data-stu-id="013f0-145">Simple Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
