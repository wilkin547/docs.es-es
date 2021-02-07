---
description: 'Más información sobre: control de errores en una actividad de diagrama de flujo mediante TryCatch'
title: Control de errores en una actividad de diagrama de flujo utilizando TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 9ab323117e5b26696a07624117e8acc8c0beacff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755357"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a><span data-ttu-id="94e0c-103">Control de errores en una actividad de diagrama de flujo utilizando TryCatch</span><span class="sxs-lookup"><span data-stu-id="94e0c-103">Fault Handling in a Flowchart Activity Using TryCatch</span></span>

<span data-ttu-id="94e0c-104">En este ejemplo se muestra cómo se puede usar la actividad <xref:System.Activities.Statements.TryCatch> dentro de una actividad de flujo de control compleja.</span><span class="sxs-lookup"><span data-stu-id="94e0c-104">This sample shows how the <xref:System.Activities.Statements.TryCatch> activity can be used within a complex control flow activity.</span></span>

<span data-ttu-id="94e0c-105">En este ejemplo, se pasan un código de la promoción y el número de hijos como variables a una actividad <xref:System.Activities.Statements.Flowchart> que calcula un descuento en función de fórmulas que corresponden al código de promoción.</span><span class="sxs-lookup"><span data-stu-id="94e0c-105">In this sample, a promotion code and number of children are passed as variables to a <xref:System.Activities.Statements.Flowchart> activity that calculates a discount based on formulae that correspond to the promotion code.</span></span> <span data-ttu-id="94e0c-106">En el ejemplo se incluyen las versiones de código imperativo y de diseñador de flujo de trabajo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="94e0c-106">The sample includes imperative code and workflow designer versions of the sample.</span></span>

<span data-ttu-id="94e0c-107">En la siguiente tabla se detallan las variables de la actividad `CreateFlowchartWithFaults`.</span><span class="sxs-lookup"><span data-stu-id="94e0c-107">The following table details the variables for the `CreateFlowchartWithFaults` activity.</span></span>

|<span data-ttu-id="94e0c-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94e0c-108">Parameters</span></span>|<span data-ttu-id="94e0c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="94e0c-109">Description</span></span>|
|----------------|-----------------|
|<span data-ttu-id="94e0c-110">promoCode</span><span class="sxs-lookup"><span data-stu-id="94e0c-110">promoCode</span></span>|<span data-ttu-id="94e0c-111">El código de la promoción.</span><span class="sxs-lookup"><span data-stu-id="94e0c-111">The promotion code.</span></span> <span data-ttu-id="94e0c-112">Escriba:  String</span><span class="sxs-lookup"><span data-stu-id="94e0c-112">Type: String</span></span><br /><br /> <span data-ttu-id="94e0c-113">Los posibles valores con descripción en paréntesis:</span><span class="sxs-lookup"><span data-stu-id="94e0c-113">The possible values with description in parentheses:</span></span><br /><br /> <span data-ttu-id="94e0c-114">-Single (único)</span><span class="sxs-lookup"><span data-stu-id="94e0c-114">-   Single (Single)</span></span><br /><span data-ttu-id="94e0c-115">-MNK (casado y sin hijos).</span><span class="sxs-lookup"><span data-stu-id="94e0c-115">-   MNK (Married with no kids.)</span></span><br /><span data-ttu-id="94e0c-116">-MWK (casado con niños).</span><span class="sxs-lookup"><span data-stu-id="94e0c-116">-   MWK (Married with kids.)</span></span>|
|<span data-ttu-id="94e0c-117">numKids</span><span class="sxs-lookup"><span data-stu-id="94e0c-117">numKids</span></span>|<span data-ttu-id="94e0c-118">El número de hijos.</span><span class="sxs-lookup"><span data-stu-id="94e0c-118">The number of children.</span></span> <span data-ttu-id="94e0c-119">Tipo: int</span><span class="sxs-lookup"><span data-stu-id="94e0c-119">Type: int</span></span>|

<span data-ttu-id="94e0c-120">La actividad `CreateFlowchartWithFaults` utiliza una actividad <xref:System.Activities.Statements.FlowSwitch%601> que activa el argumento `promoCode` y calcula el descuento mediante la siguiente fórmula.</span><span class="sxs-lookup"><span data-stu-id="94e0c-120">The `CreateFlowchartWithFaults` activity uses a <xref:System.Activities.Statements.FlowSwitch%601> activity that switches on the `promoCode` argument and calculates the discount using the following formula.</span></span>

|<span data-ttu-id="94e0c-121">Valor de `promoCode`</span><span class="sxs-lookup"><span data-stu-id="94e0c-121">Value of `promoCode`</span></span>|<span data-ttu-id="94e0c-122">Descuento (%)</span><span class="sxs-lookup"><span data-stu-id="94e0c-122">Discount (%)</span></span>|
|--------------------------|--------------------|
|<span data-ttu-id="94e0c-123">Single</span><span class="sxs-lookup"><span data-stu-id="94e0c-123">Single</span></span>|<span data-ttu-id="94e0c-124">10</span><span class="sxs-lookup"><span data-stu-id="94e0c-124">10</span></span>|
|<span data-ttu-id="94e0c-125">MNK</span><span class="sxs-lookup"><span data-stu-id="94e0c-125">MNK</span></span>|<span data-ttu-id="94e0c-126">15</span><span class="sxs-lookup"><span data-stu-id="94e0c-126">15</span></span>|
|<span data-ttu-id="94e0c-127">MWK</span><span class="sxs-lookup"><span data-stu-id="94e0c-127">MWK</span></span>|<span data-ttu-id="94e0c-128">15 + (1 – 1/ `numberOfKids` ) \* 10 **Nota:**  potencialmente, este cálculo puede producir una excepción <xref:System.DivideByZeroException> .</span><span class="sxs-lookup"><span data-stu-id="94e0c-128">15 + (1 – 1/`numberOfKids`)\*10 **Note:**  Potentially, this calculation can throw a <xref:System.DivideByZeroException>.</span></span> <span data-ttu-id="94e0c-129">Por tanto, el cálculo del descuento se incluye en una actividad <xref:System.Activities.Statements.TryCatch> que detecta la excepción <xref:System.DivideByZeroException> y establece el descuento en cero.</span><span class="sxs-lookup"><span data-stu-id="94e0c-129">So, the discount calculation is wrapped in a <xref:System.Activities.Statements.TryCatch> activity that catches the <xref:System.DivideByZeroException> exception and sets the discount to zero.</span></span>|

#### <a name="to-use-this-sample"></a><span data-ttu-id="94e0c-130">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="94e0c-130">To use this sample</span></span>

1. <span data-ttu-id="94e0c-131">Con Visual Studio 2010, abra el archivo de solución FlowchartWithFaultHandling. sln.</span><span class="sxs-lookup"><span data-stu-id="94e0c-131">Using Visual Studio 2010, open the FlowchartWithFaultHandling.sln solution file.</span></span>

2. <span data-ttu-id="94e0c-132">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="94e0c-132">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="94e0c-133">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="94e0c-133">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94e0c-134">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="94e0c-134">The samples may already be installed on your computer.</span></span> <span data-ttu-id="94e0c-135">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="94e0c-135">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="94e0c-136">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="94e0c-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="94e0c-137">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="94e0c-137">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`

## <a name="see-also"></a><span data-ttu-id="94e0c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="94e0c-138">See also</span></span>

- [<span data-ttu-id="94e0c-139">Flujos de trabajo del diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="94e0c-139">Flowchart Workflows</span></span>](../flowchart-workflows.md)
- [<span data-ttu-id="94e0c-140">Excepciones</span><span class="sxs-lookup"><span data-stu-id="94e0c-140">Exceptions</span></span>](../exceptions.md)
