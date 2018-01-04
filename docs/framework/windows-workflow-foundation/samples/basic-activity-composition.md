---
title: "Composición de actividad básica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 047948552471b33af8690b526db7c416e87f897a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="basic-activity-composition"></a><span data-ttu-id="8ebdf-102">Composición de actividad básica</span><span class="sxs-lookup"><span data-stu-id="8ebdf-102">Basic Activity Composition</span></span>
<span data-ttu-id="8ebdf-103">En este ejemplo se muestra cómo crear actividades personalizadas y actividades proporcionadas por el sistema para compilar más actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-103">This sample demonstrates how to compose custom activities and system-provided activities to build more custom activities.</span></span>  
  
 <span data-ttu-id="8ebdf-104">El flujo de trabajo que usa la actividad Survey programa el estudio con una lista de preguntas y, a continuación, genera las respuestas recibidas.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-104">The workflow using the Survey activity schedules the Survey with a list of questions, and then outputs the responses received.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="8ebdf-105">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ebdf-105">Sample Details</span></span>  
 <span data-ttu-id="8ebdf-106">Este ejemplo usa tres actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-106">This sample uses three custom activities.</span></span> <span data-ttu-id="8ebdf-107">`ReadLine`es una sencilla <xref:System.Activities.NativeActivity> \<cadena > que crea un <xref:System.Activities.Bookmark> cuando se programa y, a continuación, Establece la `Return` <xref:System.Activities.OutArgument%601> en el valor con el que el <xref:System.Activities.Bookmark> se reanuda.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-107">`ReadLine` is a simple <xref:System.Activities.NativeActivity>\<string> that creates a <xref:System.Activities.Bookmark> when scheduled, and then sets the `Return`<xref:System.Activities.OutArgument%601> to the value with which the <xref:System.Activities.Bookmark> is resumed.</span></span> <span data-ttu-id="8ebdf-108">`Prompt`es un <xref:System.Activities.Activity%601> \<cadena > que toma un <xref:System.Activities.InArgument%601>< cadena\> denominado `Text` y devuelve los usuarios de respuesta en el `Result` <xref:System.Activities.OutArgument%601> \<cadena >.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-108">`Prompt` is an <xref:System.Activities.Activity%601>\<string> that takes an <xref:System.Activities.InArgument%601><string\> named `Text` and returns the users response in the `Result`<xref:System.Activities.OutArgument%601>\<string>.</span></span> <span data-ttu-id="8ebdf-109">La actividad `Prompt` utiliza las actividades <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.WriteLine> que se distribuyen como parte de .NET Framework y también incorpora la actividad `ReadLine` personalizada para obtener los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-109">The `Prompt` activity uses the <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.WriteLine> activities that ship as part of the .NET Framework, and also incorporates the custom `ReadLine` activity for getting user input.</span></span> <span data-ttu-id="8ebdf-110">La última actividad personalizada es la actividad `Survey`.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-110">The last custom activity is the `Survey` activity.</span></span> <span data-ttu-id="8ebdf-111">Es un <xref:System.Activities.Activity>< ICollection\<cadena >>.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-111">It is an <xref:System.Activities.Activity><ICollection\<string>>.</span></span>  <span data-ttu-id="8ebdf-112">Esta actividad toma un <xref:System.Activities.InArgument%601>< IEnumerable < cadena\>> denominado `Questions` y rellena el `Result` argumento con las respuestas de salida.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-112">This activity takes an <xref:System.Activities.InArgument%601><IEnumerable<string\>> named `Questions` and populates the `Result` out argument with the responses.</span></span> <span data-ttu-id="8ebdf-113">La actividad `Survey` utiliza los objetos <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> y <xref:System.Activities.Statements.AddToCollection%601> de .NET Framework y emplea la actividad `Prompt` para realizar las preguntas del estudio y obtener las respuestas.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-113">The `Survey` activity uses <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.AddToCollection%601> from the .NET Framework and employs the `Prompt` activity for asking the survey questions and getting responses.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8ebdf-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ebdf-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8ebdf-115">Abra la **BasicActivityComposition.sln** solución en de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ebdf-115">Open the **BasicActivityComposition.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="8ebdf-116">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-116">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ebdf-117">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8ebdf-118">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8ebdf-119">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ebdf-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8ebdf-120">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8ebdf-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`