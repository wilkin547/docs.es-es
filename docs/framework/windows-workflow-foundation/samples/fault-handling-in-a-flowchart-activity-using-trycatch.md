---
title: Control de errores en una actividad de diagrama de flujo utilizando TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 56215ecf1b5f2b54333271f2086b831f564ff7c3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507504"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="ac409-102">Control de errores en una actividad de diagrama de flujo utilizando TryCatch</span><span class="sxs-lookup"><span data-stu-id="ac409-102">Fault Handling in a Flowchart Activity Using TryCatch</span></span>
<span data-ttu-id="ac409-103">En este ejemplo se muestra cómo se puede usar la actividad <xref:System.Activities.Statements.TryCatch> dentro de una actividad de flujo de control compleja.</span><span class="sxs-lookup"><span data-stu-id="ac409-103">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>

 <span data-ttu-id="ac409-104">En este ejemplo, se pasan un código de la promoción y el número de hijos como variables a una actividad <xref:System.Activities.Statements.Flowchart> que calcula un descuento en función de fórmulas que corresponden al código de promoción.</span><span class="sxs-lookup"><span data-stu-id="ac409-104">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="ac409-105">En el ejemplo se incluyen las versiones de código imperativo y de diseñador de flujo de trabajo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ac409-105">The sample includes imperative code and workflow designer versions of the sample.</span></span>

 <span data-ttu-id="ac409-106">En la siguiente tabla se detallan las variables de la actividad `CreateFlowchartWithFaults`.</span><span class="sxs-lookup"><span data-stu-id="ac409-106">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>

|<span data-ttu-id="ac409-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac409-107">Parameters</span></span>|<span data-ttu-id="ac409-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac409-108">Description</span></span>|
|----------------|-----------------|
|<span data-ttu-id="ac409-109">promoCode</span><span class="sxs-lookup"><span data-stu-id="ac409-109">promoCode</span></span>|<span data-ttu-id="ac409-110">El código de la promoción.</span><span class="sxs-lookup"><span data-stu-id="ac409-110">The promotion code.</span></span> <span data-ttu-id="ac409-111">Tipo: String</span><span class="sxs-lookup"><span data-stu-id="ac409-111">Type: String</span></span><br /><br /> <span data-ttu-id="ac409-112">Los posibles valores con descripción en paréntesis:</span><span class="sxs-lookup"><span data-stu-id="ac409-112">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="ac409-113">-Única (Single)</span><span class="sxs-lookup"><span data-stu-id="ac409-113">-   Single (Single)</span></span><br /><span data-ttu-id="ac409-114">-MNK (casado sin hijos).</span><span class="sxs-lookup"><span data-stu-id="ac409-114">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="ac409-115">-MWK (casado con hijos).</span><span class="sxs-lookup"><span data-stu-id="ac409-115">-   MWK (Married with kids.)</span></span>|
|<span data-ttu-id="ac409-116">numKids</span><span class="sxs-lookup"><span data-stu-id="ac409-116">numKids</span></span>|<span data-ttu-id="ac409-117">El número de hijos.</span><span class="sxs-lookup"><span data-stu-id="ac409-117">The number of children.</span></span> <span data-ttu-id="ac409-118">Tipo: int</span><span class="sxs-lookup"><span data-stu-id="ac409-118">Type: int</span></span>|

 <span data-ttu-id="ac409-119">La actividad `CreateFlowchartWithFaults` utiliza una actividad <xref:System.Activities.Statements.FlowSwitch%601> que activa el argumento `promoCode` y calcula el descuento mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="ac409-119">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>

|<span data-ttu-id="ac409-120">Valor de `promoCode`</span><span class="sxs-lookup"><span data-stu-id="ac409-120">Value of `promoCode`</span></span>|<span data-ttu-id="ac409-121">Descuento (%)</span><span class="sxs-lookup"><span data-stu-id="ac409-121">Discount (%)</span></span>|
|--------------------------|--------------------|
|<span data-ttu-id="ac409-122">Single</span><span class="sxs-lookup"><span data-stu-id="ac409-122">Single</span></span>|<span data-ttu-id="ac409-123">10</span><span class="sxs-lookup"><span data-stu-id="ac409-123">10</span></span>|
|<span data-ttu-id="ac409-124">MNK</span><span class="sxs-lookup"><span data-stu-id="ac409-124">MNK</span></span>|<span data-ttu-id="ac409-125">15</span><span class="sxs-lookup"><span data-stu-id="ac409-125">15</span></span>|
|<span data-ttu-id="ac409-126">MWK</span><span class="sxs-lookup"><span data-stu-id="ac409-126">MWK</span></span>|<span data-ttu-id="ac409-127">15 + (1 – 1 /`numberOfKids`)\*10 **Nota:**  Este cálculo podría producir una excepción <xref:System.DivideByZeroException>.</span><span class="sxs-lookup"><span data-stu-id="ac409-127">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="ac409-128">Por tanto, el cálculo del descuento se incluye en una actividad <xref:System.Activities.Statements.TryCatch> que detecta la excepción <xref:System.DivideByZeroException> y establece el descuento en cero.</span><span class="sxs-lookup"><span data-stu-id="ac409-128">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="ac409-129">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac409-129">To use this sample</span></span>

1.  <span data-ttu-id="ac409-130">Con Visual Studio 2010, abra el archivo de solución FlowchartWithFaultHandling.sln.</span><span class="sxs-lookup"><span data-stu-id="ac409-130">Using Visual Studio 2010, open the FlowchartWithFaultHandling.sln solution file.</span></span>

2.  <span data-ttu-id="ac409-131">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="ac409-131">To build the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="ac409-132">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="ac409-132">To run the solution, press F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="ac409-133">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ac409-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ac409-134">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ac409-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac409-135">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ac409-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac409-136">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ac409-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a><span data-ttu-id="ac409-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac409-137">See also</span></span>
- [<span data-ttu-id="ac409-138">Flujos de trabajo del diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="ac409-138">Flowchart Workflows</span></span>](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
- [<span data-ttu-id="ac409-139">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ac409-139">Exceptions</span></span>](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
