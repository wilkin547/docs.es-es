---
title: Actividad For
ms.date: 03/30/2017
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
ms.openlocfilehash: 7a7023abb9057ab4b25552fbf9a81cd2ae2b4e88
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206268"
---
# <a name="for-activity"></a><span data-ttu-id="2f145-102">Actividad For</span><span class="sxs-lookup"><span data-stu-id="2f145-102">For Activity</span></span>
<span data-ttu-id="2f145-103">El ejemplo de For muestra cómo compilar una actividad personalizada que hereda de <xref:System.Activities.NativeActivity> y utilizarla en un flujo de trabajo para ejecutar un ejemplo del mundo real.</span><span class="sxs-lookup"><span data-stu-id="2f145-103">The For sample demonstrates how to build a custom activity that inherits from <xref:System.Activities.NativeActivity>, and use it in a workflow to execute a real world example.</span></span> <span data-ttu-id="2f145-104">La actividad personalizada incluida en este ejemplo funciones como la instrucción `for` de C#.</span><span class="sxs-lookup"><span data-stu-id="2f145-104">The custom activity included in this sample functions like the C# `for` statement.</span></span> <span data-ttu-id="2f145-105">T</span><span class="sxs-lookup"><span data-stu-id="2f145-105">T</span></span>  
  
 <span data-ttu-id="2f145-106">La actividad personalizada `For` tiene propiedades denominadas `InitAction`, `IterationAction`, `Condition` y `Body` que corresponden respectivamente a la instrucción de inicialización, instrucción iterativa, condición de continuación e instrucción de cuerpo de la instrucción `For` estándar de C#.</span><span class="sxs-lookup"><span data-stu-id="2f145-106">The `For` custom activity has properties named `InitAction`, `IterationAction`, `Condition`, and `Body` that correspond to the initialization statement, iterative statement, continuation condition, and body statement respectively found in the standard C# `For` statement.</span></span>  
  
 <span data-ttu-id="2f145-107">En la siguiente tabla se describen los archivos clave del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f145-107">The following table describes the key files in the sample.</span></span>  
  
|<span data-ttu-id="2f145-108">Archivo</span><span class="sxs-lookup"><span data-stu-id="2f145-108">File</span></span>|<span data-ttu-id="2f145-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f145-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="2f145-110">For.cs</span><span class="sxs-lookup"><span data-stu-id="2f145-110">For.cs</span></span>|<span data-ttu-id="2f145-111">Definición de clase para la actividad personalizada `For`, que amplía la clase <xref:System.Activities.NativeActivity> para proporcionar la funcionalidad de la instrucción `For` de C#.</span><span class="sxs-lookup"><span data-stu-id="2f145-111">Class definition for the `For` custom activity, which extends the <xref:System.Activities.NativeActivity> class to provide the functionality of the C# `For` statement.</span></span>|  
|<span data-ttu-id="2f145-112">Program.cs</span><span class="sxs-lookup"><span data-stu-id="2f145-112">Program.cs</span></span>|<span data-ttu-id="2f145-113">Aplicación cliente que realiza trabajo repetitivo básico en una colección mediante la actividad `For` personalizada.</span><span class="sxs-lookup"><span data-stu-id="2f145-113">A client application that performs basic iterative work on a collection using the custom `For` activity.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="2f145-114">Al utilizar la actividad personalizada `For`, asegúrese de que se establece la propiedad `Condition`; de lo contrario se podría producir un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="2f145-114">When using the `For` custom activity, ensure that the `Condition` property is set; otherwise an infinite loop could occur.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2f145-115">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="2f145-115">Demonstrates</span></span>  
 <span data-ttu-id="2f145-116">Cree una actividad personalizada que herede de <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="2f145-116">Create a custom activity that inherits from <xref:System.Activities.NativeActivity>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2f145-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="2f145-117">Discussion</span></span>  
 <span data-ttu-id="2f145-118">En la siguiente tabla se describen las propiedades de la actividad incluida en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2f145-118">The following table describes the properties of the activity included in this sample.</span></span>  
  
 <span data-ttu-id="2f145-119">InitAction</span><span class="sxs-lookup"><span data-stu-id="2f145-119">InitAction</span></span>  
 <span data-ttu-id="2f145-120">Instrucción de inicialización</span><span class="sxs-lookup"><span data-stu-id="2f145-120">Initialization statement</span></span>  
  
 <span data-ttu-id="2f145-121">IterationAction</span><span class="sxs-lookup"><span data-stu-id="2f145-121">IterationAction</span></span>  
 <span data-ttu-id="2f145-122">Instrucción iterativa</span><span class="sxs-lookup"><span data-stu-id="2f145-122">Iterative statement</span></span>  
  
 <span data-ttu-id="2f145-123">Condición</span><span class="sxs-lookup"><span data-stu-id="2f145-123">Condition</span></span>  
 <span data-ttu-id="2f145-124">Instrucción de continuación</span><span class="sxs-lookup"><span data-stu-id="2f145-124">Continuation statement</span></span>  
  
 <span data-ttu-id="2f145-125">Body</span><span class="sxs-lookup"><span data-stu-id="2f145-125">Body</span></span>  
 <span data-ttu-id="2f145-126">Instrucción de cuerpo</span><span class="sxs-lookup"><span data-stu-id="2f145-126">Body statement</span></span>  
  
 <span data-ttu-id="2f145-127">La actividad hereda de <xref:System.Activities.NativeActivity> para obtener acceso a las características en tiempo de ejecución, como la programación de actividades adicionales para ejecutarse, utilizando uno de los métodos `ScheduleActivity` de <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="2f145-127">The activity inherits from <xref:System.Activities.NativeActivity> to gain access to runtime features such as scheduling additional activities to run, using one of the `ScheduleActivity` methods of <xref:System.Activities.NativeActivityContext>.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2f145-128">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f145-128">To use this sample</span></span>  
  
1.  <span data-ttu-id="2f145-129">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución For.sln.</span><span class="sxs-lookup"><span data-stu-id="2f145-129">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the For.sln solution file.</span></span>  
  
2.  <span data-ttu-id="2f145-130">Compile la solución presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="2f145-130">Build the solution, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2f145-131">Ejecute la solución presionando F5.</span><span class="sxs-lookup"><span data-stu-id="2f145-131">Run the solution, by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2f145-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2f145-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2f145-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2f145-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2f145-134">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2f145-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2f145-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2f145-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`