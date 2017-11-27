---
title: Grupo de actividad condicionado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab8f47601f84267d1ac357b313fa5d2215a586d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="conditioned-activity-group"></a><span data-ttu-id="3c9f3-102">Grupo de actividad condicionado</span><span class="sxs-lookup"><span data-stu-id="3c9f3-102">Conditioned Activity Group</span></span>
<span data-ttu-id="3c9f3-103">En el ejemplo se muestra una aplicación de reservas de viajes.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-103">The sample demonstrates a travel booking application.</span></span> <span data-ttu-id="3c9f3-104">La actividad <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) tiene dos actividades de código: una actividad Car y una actividad Airline.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-104">The <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) has two code activities: a Car activity and an Airline activity.</span></span> <span data-ttu-id="3c9f3-105">En el constructor `SimpleCAGWorkflow`, el objeto de ArrayList "travelNeedType" se rellena con los tipos de reserva de viajes que se requieren.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-105">In the `SimpleCAGWorkflow` constructor, a "travelNeedType" ArrayList object is populated with the types of travel bookings that are required.</span></span> <span data-ttu-id="3c9f3-106">Si se escribe un comentario en una de las instrucciones `travelNeeds.Add`, o en las dos, se modifica el comportamiento de CAG en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-106">By commenting out one or both of the `travelNeeds.Add` statements, you modify the CAG behavior accordingly.</span></span> <span data-ttu-id="3c9f3-107">Las actividades Car y Airline tienen la condición <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> con detalles de <xref:System.Workflow.Activities.CodeCondition>.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-107">Both the Car and Airline activities have their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> condition populated with a <xref:System.Workflow.Activities.CodeCondition>.</span></span> <span data-ttu-id="3c9f3-108">La actividad Car solo se ejecuta si la colección `travelNeeds` tiene una entrada `TravelNeeds.Car`, y la actividad Airline solo se ejecuta si la colección `travelNeeds` tiene una entrada `TravelNeeds.Airline`.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-108">The Car activity executes only if the `travelNeeds` collection has a `TravelNeeds.Car` entry, and the Airline activity executes only if the `travelNeeds` collection has a `TravelNeeds.Airline` entry.</span></span>  
  
 <span data-ttu-id="3c9f3-109">La ejecución de cada actividad quita la entrada correspondiente de la colección.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-109">The execution of each activity removes the corresponding entry from the collection.</span></span> <span data-ttu-id="3c9f3-110">La condición <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> predeterminada especifica que CAG se debe cerrar cuando no se está ejecutando ningún elemento secundario ni están listos para la ejecución (en función de sus condiciones <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>).</span><span class="sxs-lookup"><span data-stu-id="3c9f3-110">The default <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> condition specifies that the CAG should exit when no children are executing or are ready for execution (based on their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> conditions).</span></span> <span data-ttu-id="3c9f3-111">En este ejemplo, esto significa que CAG se cierra cuando la colección `travelNeeds` está vacía.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-111">In this sample, this means that the CAG exits when the `travelNeeds` collection is empty.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="3c9f3-112">Para compilar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c9f3-112">To build the sample</span></span>  
  
1.  <span data-ttu-id="3c9f3-113">Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c9f3-113">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3c9f3-114">Compile la solución presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-114">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="3c9f3-115">Ejecute la solución sin depuración presionando CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-115">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="3c9f3-116">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c9f3-116">To run the sample</span></span>  
  
-   <span data-ttu-id="3c9f3-117">En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta SimpleCAG\bin\debug (o la carpeta SimpleCAG\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-117">In the SDK Command Prompt window, run the .exe file in the SimpleCAG\bin\debug folder (or the SimpleCAG\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c9f3-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3c9f3-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3c9f3-119">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="3c9f3-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3c9f3-120">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c9f3-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3c9f3-121">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="3c9f3-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a><span data-ttu-id="3c9f3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c9f3-122">See Also</span></span>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
