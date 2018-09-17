---
title: Usar AsyncOperationContext en un ejemplo de actividad
ms.date: 03/30/2017
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
ms.openlocfilehash: 4358a364a3f7ec69b7c1c548fcf82fe494f37505
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45742893"
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a><span data-ttu-id="828ad-102">Usar AsyncOperationContext en un ejemplo de actividad</span><span class="sxs-lookup"><span data-stu-id="828ad-102">Using AsyncOperationContext in an Activity Sample</span></span>
<span data-ttu-id="828ad-103">En este ejemplo se muestra cómo desarrollar una actividad <xref:System.Activities.CodeActivity> personalizada que utiliza <xref:System.Activities.AsyncCodeActivityContext> para realizar trabajo de forma asincrónica fuera del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="828ad-103">This sample demonstrates how to develop a custom <xref:System.Activities.CodeActivity> that uses <xref:System.Activities.AsyncCodeActivityContext> to perform work asynchronously outside of the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="828ad-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="828ad-104">Sample Details</span></span>  
 <span data-ttu-id="828ad-105">La actividad de ejemplo utiliza los métodos <xref:System.IO.FileStream.BeginWrite%2A> y <xref:System.IO.FileStream.EndWrite%2A> de la clase <xref:System.IO.FileStream> para escribir datos en un archivo de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="828ad-105">The sample activity uses the <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.EndWrite%2A> methods on the <xref:System.IO.FileStream> class to asynchronously write data to a file.</span></span> <span data-ttu-id="828ad-106">El patrón introducido aquí se puede adaptar para el uso con otros métodos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="828ad-106">The pattern introduced here can be adapted for use with other asynchronous methods.</span></span> <span data-ttu-id="828ad-107">Mientras se está ejecutando la operación asincrónica, se pueden ejecutar otras actividades del flujo de trabajo, pero este no se puede guardar.</span><span class="sxs-lookup"><span data-stu-id="828ad-107">While the asynchronous operation is executing, other activities in the workflow can execute, but the workflow cannot be persisted.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="828ad-108">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="828ad-108">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="828ad-109">Abra la solución de ejemplo Async.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="828ad-109">Open the Async.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="828ad-110">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="828ad-110">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="828ad-111">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="828ad-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="828ad-112">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="828ad-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="828ad-113">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="828ad-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="828ad-114">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="828ad-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`