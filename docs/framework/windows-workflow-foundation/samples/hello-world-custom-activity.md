---
title: Actividad personalizada Hello World
ms.date: 03/30/2017
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
ms.openlocfilehash: 35ae5933515b3280b0d8d95157c8dd5f40f7b320
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515850"
---
# <a name="hello-world-custom-activity"></a><span data-ttu-id="a32dd-102">Actividad personalizada Hello World</span><span class="sxs-lookup"><span data-stu-id="a32dd-102">Hello World Custom Activity</span></span>
<span data-ttu-id="a32dd-103">Este ejemplo muestra varias características fundamentales de Windows Workflow Foundation (WF), incluido cómo crear una actividad personalizada simple.</span><span class="sxs-lookup"><span data-stu-id="a32dd-103">This sample demonstrates several key features of Windows Workflow Foundation (WF), including how to create a simple custom activity.</span></span> <span data-ttu-id="a32dd-104">Algunas de las características mostradas en este ejemplo crean una actividad personalizada en C# y utilizan argumentos `in` y `out`(<xref:System.Activities.InArgument> y <xref:System.Activities.OutArgument>).</span><span class="sxs-lookup"><span data-stu-id="a32dd-104">Some of the features demonstrated in this sample are creating a custom activity in C# and using `in` and `out` arguments (<xref:System.Activities.InArgument> and <xref:System.Activities.OutArgument>).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a32dd-105">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a32dd-105">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a32dd-106">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a32dd-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a32dd-107">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a32dd-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a32dd-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a32dd-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a><span data-ttu-id="a32dd-109">Crear un flujo de trabajo en código</span><span class="sxs-lookup"><span data-stu-id="a32dd-109">Creating a Workflow in Code</span></span>  
 <span data-ttu-id="a32dd-110">En este ejemplo, se crean dos actividades personalizadas utilizando el código de C#.</span><span class="sxs-lookup"><span data-stu-id="a32dd-110">In this sample, two custom activities are created using C# code.</span></span> <span data-ttu-id="a32dd-111">Ambas actividades personalizadas heredan directa o indirectamente de <xref:System.Activities.Activity%601> para devolver un único valor.</span><span class="sxs-lookup"><span data-stu-id="a32dd-111">Both custom activities inherit directly or indirectly from <xref:System.Activities.Activity%601> to return a single value.</span></span> <span data-ttu-id="a32dd-112">La ventaja de utilizar el valor devuelto genérico, en lugar de heredar de la clase <xref:System.Activities.Activity> no genérica, es que algunas actividades (como <xref:System.Activities.Statements.Assign>) pueden tener acceso al valor devuelto cuando se usa como parte de una actividad compuesta.</span><span class="sxs-lookup"><span data-stu-id="a32dd-112">The advantage of using the generic return value, instead of inheriting from the non-generic <xref:System.Activities.Activity> class, is that some activities (such as <xref:System.Activities.Statements.Assign>) are able to access the return value when used as part of a composed activity.</span></span>  
  
 <span data-ttu-id="a32dd-113">AppendString</span><span class="sxs-lookup"><span data-stu-id="a32dd-113">AppendString</span></span>  
 <span data-ttu-id="a32dd-114">Esta actividad hereda de <xref:System.Activities.Activity%601> y utiliza una actividad <xref:System.Activities.Statements.Assign> que concatena dos cadenas.</span><span class="sxs-lookup"><span data-stu-id="a32dd-114">This activity inherits from <xref:System.Activities.Activity%601>, and uses an <xref:System.Activities.Statements.Assign> activity that concatenates two strings together.</span></span>  
  
 <span data-ttu-id="a32dd-115">PrependString</span><span class="sxs-lookup"><span data-stu-id="a32dd-115">Prepend String</span></span>  
 <span data-ttu-id="a32dd-116">Esta actividad hereda directamente de <xref:System.Activities.CodeActivity%601> y crea funcionalidad similar a la actividad `AppendString`, que utiliza lógica implementada en código en lugar de crearse a partir de una actividad ya existente.</span><span class="sxs-lookup"><span data-stu-id="a32dd-116">This activity inherits directly from <xref:System.Activities.CodeActivity%601>, and creates similar functionality to the `AppendString` activity, which uses logic implemented in code rather than being composed of a pre-existing activity.</span></span>  
  
 <span data-ttu-id="a32dd-117">Este proyecto incluye los siguientes archivos.</span><span class="sxs-lookup"><span data-stu-id="a32dd-117">The following files are included in this project.</span></span>  
  
 <span data-ttu-id="a32dd-118">AppendString.cs</span><span class="sxs-lookup"><span data-stu-id="a32dd-118">AppendString.cs</span></span>  
 <span data-ttu-id="a32dd-119">La actividad personalizada que anexa las cadenas.</span><span class="sxs-lookup"><span data-stu-id="a32dd-119">The custom activity that appends strings together.</span></span> <span data-ttu-id="a32dd-120">Toma una cadena y combina con una cadena de texto literal "says hello world" para formar un mensaje completo como salida.</span><span class="sxs-lookup"><span data-stu-id="a32dd-120">It takes in a string and combines it with a literal text string " says hello world" to form a complete message as output.</span></span>  
  
 <span data-ttu-id="a32dd-121">PrependString.cs</span><span class="sxs-lookup"><span data-stu-id="a32dd-121">PrependString.cs</span></span>  
 <span data-ttu-id="a32dd-122">Esta actividad agrega una cadena predefinida como prefijo a una cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="a32dd-122">This activity prefixes a predefined string to an input string.</span></span>  
  
 <span data-ttu-id="a32dd-123">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="a32dd-123">Sequence1.xaml</span></span>  
 <span data-ttu-id="a32dd-124">Flujo de trabajo que utiliza las actividades personalizadas `AppendString` y `PrependString`.</span><span class="sxs-lookup"><span data-stu-id="a32dd-124">A workflow that uses the `AppendString` and `PrependString` custom activities.</span></span>  
  
 <span data-ttu-id="a32dd-125">Program.cs</span><span class="sxs-lookup"><span data-stu-id="a32dd-125">Program.cs</span></span>  
 <span data-ttu-id="a32dd-126">Programa que ejecuta el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a32dd-126">A program that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a32dd-127">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a32dd-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="a32dd-128">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución HelloWorld.sln.</span><span class="sxs-lookup"><span data-stu-id="a32dd-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="a32dd-129">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="a32dd-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a32dd-130">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="a32dd-130">To run the solution, press F5.</span></span>