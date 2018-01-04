---
title: "Usar actividades de colección"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57c4c720e910762a303fc4987166f22960c2f03b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-collection-activities"></a><span data-ttu-id="a984d-102">Usar actividades de colección</span><span class="sxs-lookup"><span data-stu-id="a984d-102">Using Collection Activities</span></span>
<span data-ttu-id="a984d-103">En este ejemplo se muestra cómo utilizar las actividades de colección (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>y <xref:System.Activities.Statements.RemoveFromCollection%601>) con una clase que implementa la interfaz <xref:System.Collections.ICollection> y cómo crear una actividad personalizada que recorra en iteración la colección para imprimir el contenido de cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-103">This sample demonstrates how to use the collection activities (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, and <xref:System.Activities.Statements.RemoveFromCollection%601>) with a class that implements the <xref:System.Collections.ICollection> interface and how to create a custom activity that iterates over a collection to print out the contents of each element in the collection.</span></span> <span data-ttu-id="a984d-104">La actividad personalizada, que se denomina `PrintCollection`, imprime en la consola los miembros de elemento de una colección llamada `Numbers`.</span><span class="sxs-lookup"><span data-stu-id="a984d-104">The custom activity, which is named `PrintCollection`, prints to the console the item members of a collection named `Numbers`.</span></span>  
  
 <span data-ttu-id="a984d-105">En la siguiente tabla se describen las cuatro actividades que ofrecen a los flujos de trabajo manipulación de colecciones.</span><span class="sxs-lookup"><span data-stu-id="a984d-105">The following table describes the four activities that provide collection manipulation for workflows.</span></span>  
  
|<span data-ttu-id="a984d-106">Nombre de actividad</span><span class="sxs-lookup"><span data-stu-id="a984d-106">Activity name</span></span>|<span data-ttu-id="a984d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a984d-107">Description</span></span>|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|<span data-ttu-id="a984d-108">Agrega un elemento a una colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-108">Adds an item to a collection.</span></span>|  
|<xref:System.Activities.Statements.ClearCollection%601>|<span data-ttu-id="a984d-109">Borra todos los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-109">Clears all items in a collection</span></span>|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|<span data-ttu-id="a984d-110">Devuelve `true` si el elemento especificado ya existe en la colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-110">Returns `true` if specified item exists in collection.</span></span>|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|<span data-ttu-id="a984d-111">Quita un elemento de una colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-111">Removes an item from a collection.</span></span>|  
  
 <span data-ttu-id="a984d-112">El ejemplo se compone de dos soluciones, una bajo el directorio CodedWorkflow y la otra bajo el directorio DesignerWorkflow.</span><span class="sxs-lookup"><span data-stu-id="a984d-112">The sample consists of two solutions, one under the CodedWorkflow directory and the other under the DesignerWorkflow directory.</span></span> <span data-ttu-id="a984d-113">Muestran dos maneras diferentes de utilizar las actividades para conseguir los mismos fines.</span><span class="sxs-lookup"><span data-stu-id="a984d-113">They demonstrate two different ways of using the activities for the same purposes.</span></span>  
  
|<span data-ttu-id="a984d-114">Soluciones</span><span class="sxs-lookup"><span data-stu-id="a984d-114">Solution</span></span>|<span data-ttu-id="a984d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a984d-115">Description</span></span>|<span data-ttu-id="a984d-116">Archivos principales</span><span class="sxs-lookup"><span data-stu-id="a984d-116">Main Files</span></span>|  
|-|-|-|  
|<span data-ttu-id="a984d-117">CodedWorkflow</span><span class="sxs-lookup"><span data-stu-id="a984d-117">CodedWorkflow</span></span>|<span data-ttu-id="a984d-118">Aplicación cliente de ejemplo que muestra cómo invocar las actividades de colección mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a984d-118">Sample client application that demonstrates how to invoke the collection activities programmatically.</span></span>|<span data-ttu-id="a984d-119">**PrintCollection.cs**: actividad de aplicación auxiliar para imprimir en la consola de todos los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-119">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="a984d-120">**Program.cs**: compila mediante programación una actividad de secuencia que contiene una serie de actividades de colección y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="a984d-120">**Program.cs**: programmatically builds a sequence activity that contains a series of collection activities, and executes it.</span></span>|  
|<span data-ttu-id="a984d-121">DesignerWorkflow</span><span class="sxs-lookup"><span data-stu-id="a984d-121">DesignerWorkflow</span></span>|<span data-ttu-id="a984d-122">Aplicación cliente de ejemplo que muestra cómo utilizar las actividades de colección en el diseñador de flujo de trabajo mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="a984d-122">Sample client application that demonstrates how to use the collection activities declaratively in the workflow designer.</span></span>|<span data-ttu-id="a984d-123">**CollectionWorkflow.xaml**: un flujo de trabajo creado mediante declaración con el diseñador que utiliza las actividades de colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-123">**CollectionWorkflow.xaml**: a workflow created declaratively with the designer that uses the collection activities.</span></span><br /><br /> <span data-ttu-id="a984d-124">**PrintCollection.cs**: actividad de aplicación auxiliar para imprimir en la consola de todos los elementos de una colección.</span><span class="sxs-lookup"><span data-stu-id="a984d-124">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="a984d-125">**Program.cs**: invoca el flujo de trabajo descrito en CollectionWorkflow.xaml.</span><span class="sxs-lookup"><span data-stu-id="a984d-125">**Program.cs**: invokes the workflow described in CollectionWorkflow.xaml.</span></span>|  
  
 <span data-ttu-id="a984d-126">En la demostración, los miembros de elemento de la colección `Numbers` se imprimen en la consola mediante una actividad definida de forma personalizada denominada `PrintCollection`.</span><span class="sxs-lookup"><span data-stu-id="a984d-126">In the demonstration, the item members of collection `Numbers` are printed on the console using a custom-defined activity called `PrintCollection`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a984d-127">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a984d-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="a984d-128">Abra el archivo de solución Collection.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a984d-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Collection.sln solution file.</span></span>  
  
2.  <span data-ttu-id="a984d-129">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="a984d-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a984d-130">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="a984d-130">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a984d-131">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a984d-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a984d-132">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a984d-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a984d-133">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a984d-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a984d-134">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a984d-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`