---
title: InvokeMethod
ms.date: 03/30/2017
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
ms.openlocfilehash: 12d028515c34c0e3593c90b81a5589fb05f36b82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517743"
---
# <a name="invokemethod"></a><span data-ttu-id="33485-102">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="33485-102">InvokeMethod</span></span>
<span data-ttu-id="33485-103">En este ejemplo se muestran las maneras diferentes de utilizar la actividad <xref:System.Activities.Statements.InvokeMethod> para invocar métodos de una clase.</span><span class="sxs-lookup"><span data-stu-id="33485-103">This sample shows the different ways of using the <xref:System.Activities.Statements.InvokeMethod> activity to invoke methods of a class.</span></span>  
  
 <span data-ttu-id="33485-104">Un método pertenece a una clase y representa un conjunto contenido de operaciones.</span><span class="sxs-lookup"><span data-stu-id="33485-104">A method belongs to a class and represents a contained set of operations.</span></span> <span data-ttu-id="33485-105">La actividad <xref:System.Activities.Statements.InvokeMethod> proporciona la capacidad de llamar a los métodos en objetos o tipos, pasar parámetros y obtener el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="33485-105">The <xref:System.Activities.Statements.InvokeMethod> activity gives you the ability to call methods against objects or types, pass in parameters, and get the return value.</span></span> <span data-ttu-id="33485-106">Los métodos se pueden invocar sincrónica o asincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="33485-106">Methods can be invoked synchronously or asynchronously.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="33485-107">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="33485-107">Sample Details</span></span>  
 <span data-ttu-id="33485-108">En este ejemplo se utiliza la actividad <xref:System.Activities.Statements.InvokeMethod> para realizar los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="33485-108">This sample uses the <xref:System.Activities.Statements.InvokeMethod> activity to perform the following scenarios:</span></span>  
  
1.  <span data-ttu-id="33485-109">Invoque un método de instancia sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="33485-109">Invoke an instance method without parameters.</span></span>  
  
2.  <span data-ttu-id="33485-110">Invocar un método de instancia con dos parámetros (<xref:System.String> y <xref:System.Int32>).</span><span class="sxs-lookup"><span data-stu-id="33485-110">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>).</span></span>  
  
3.  <span data-ttu-id="33485-111">Invocar un método de instancia con dos parámetros (<xref:System.String> y <xref:System.Int32>) y una matriz de parámetros de tipo <xref:System.String>[].</span><span class="sxs-lookup"><span data-stu-id="33485-111">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>) and a parameter array of type <xref:System.String>[].</span></span>  
  
4.  <span data-ttu-id="33485-112">Invocar un método de instancia con dos parámetros de tipo <xref:System.Int32> y un resultado de tipo <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="33485-112">Invoke an instance method with two parameters of type <xref:System.Int32> and a result of type <xref:System.Int32>.</span></span> <span data-ttu-id="33485-113">En este escenario, el valor de resultado se enlaza a una variable y se utiliza en otra actividad.</span><span class="sxs-lookup"><span data-stu-id="33485-113">In this scenario, the result value is bound to a variable and used in another activity.</span></span> <span data-ttu-id="33485-114">Se muestra en la consola utilizando la actividad <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="33485-114">It is displayed in the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
5.  <span data-ttu-id="33485-115">Invocar un método estático con dos parámetros de tipo <xref:System.String> y <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="33485-115">Invoke a static method with two parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
6.  <span data-ttu-id="33485-116">Invocar un método de instancia con un parámetro genérico de tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="33485-116">Invoke an instance method with one generic parameter of type <xref:System.String>.</span></span>  
  
7.  <span data-ttu-id="33485-117">Invocar un método estático con dos parámetros genéricos de tipo <xref:System.String> y <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="33485-117">Invoke a static method with two generic parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
8.  <span data-ttu-id="33485-118">Invocar un método de instancia que tiene un parámetro pasado por referencia de tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="33485-118">Invoke an instance method that has one parameter passed by reference of type <xref:System.String>.</span></span> <span data-ttu-id="33485-119">En este escenario, el parámetro de referencia se enlaza a una variable (`outParam`) y se utiliza en otra actividad.</span><span class="sxs-lookup"><span data-stu-id="33485-119">In this scenario, the reference parameter is bound to a variable (`outParam`) and used in another activity.</span></span> <span data-ttu-id="33485-120">Se muestra en la consola utilizando la actividad <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="33485-120">It is displayed on the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
9. <span data-ttu-id="33485-121">Invoque un método de instancia asincrónico.</span><span class="sxs-lookup"><span data-stu-id="33485-121">Invoke an asynchronous instance method.</span></span>  
  
10. <span data-ttu-id="33485-122">Invocar dos métodos diferentes en la misma instancia de un objeto utilizando dos actividades <xref:System.Activities.Statements.InvokeMethod>.</span><span class="sxs-lookup"><span data-stu-id="33485-122">Invoke two different methods on the same instance of an object using two <xref:System.Activities.Statements.InvokeMethod> activities.</span></span>  
  
11. <span data-ttu-id="33485-123">Almacenar un valor en una instancia de un objeto.</span><span class="sxs-lookup"><span data-stu-id="33485-123">Store a value in an instance of an object.</span></span>  
  
12. <span data-ttu-id="33485-124">Recuperar un valor de una instancia de un objeto.</span><span class="sxs-lookup"><span data-stu-id="33485-124">Retrieve a value from an instance of an object.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="33485-125">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="33485-125">To use this sample</span></span>  
 <span data-ttu-id="33485-126">Este ejemplo se proporciona en dos versiones.</span><span class="sxs-lookup"><span data-stu-id="33485-126">This sample is provided in two versions.</span></span> <span data-ttu-id="33485-127">La primera versión de este ejemplo muestra el uso de <xref:System.Activities.Statements.InvokeMethod> mediante código C# utilizando el modelo de programación de Windows Workflow Foundation (WF) y puede encontrarse en la carpeta CodedWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="33485-127">The first version of this sample demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> through C# code using the Windows Workflow Foundation (WF) programming model and can be found under the CodedWorkflow\CS folder.</span></span> <span data-ttu-id="33485-128">La segunda versión muestra el uso de <xref:System.Activities.Statements.InvokeMethod> utilizando XAML y se puede encontrar en la carpeta DesignerWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="33485-128">The second version demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> using XAML and can be found under the DesignerWorkflow\CS folder.</span></span>  
  
#### <a name="to-run-the-coded-workflow-sample"></a><span data-ttu-id="33485-129">Para ejecutar el ejemplo de flujo de trabajo codificado</span><span class="sxs-lookup"><span data-stu-id="33485-129">To run the coded workflow sample</span></span>  
  
1.  <span data-ttu-id="33485-130">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución InvokeMethodUsage.sln en la carpeta CodedWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="33485-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the CodedWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="33485-131">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="33485-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="33485-132">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="33485-132">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-designer-workflow-sample"></a><span data-ttu-id="33485-133">Para ejecutar el ejemplo de flujo de trabajo de diseñador</span><span class="sxs-lookup"><span data-stu-id="33485-133">To run the designer workflow sample</span></span>  
  
1.  <span data-ttu-id="33485-134">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución InvokeMethodUsage.sln en la carpeta DesignerWorkflow\CS.</span><span class="sxs-lookup"><span data-stu-id="33485-134">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the DesignerWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="33485-135">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="33485-135">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="33485-136">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="33485-136">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33485-137">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="33485-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="33485-138">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="33485-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="33485-139">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="33485-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="33485-140">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="33485-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`