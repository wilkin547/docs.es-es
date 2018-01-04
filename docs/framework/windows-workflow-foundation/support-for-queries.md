---
title: "Soporte técnico para consultas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f20e9fbcad31a3924474793d9107d6a3c4aeef27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="support-for-queries"></a><span data-ttu-id="f65b7-102">Soporte técnico para consultas</span><span class="sxs-lookup"><span data-stu-id="f65b7-102">Support for Queries</span></span>
<span data-ttu-id="f65b7-103">El almacén de instancias de flujo de trabajo de SQL graba un conjunto de propiedades conocidas en el almacén.</span><span class="sxs-lookup"><span data-stu-id="f65b7-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="f65b7-104">Los usuarios pueden consultar instancias basadas en estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="f65b7-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="f65b7-105">La siguiente lista contiene algunas de estas propiedades conocidas:</span><span class="sxs-lookup"><span data-stu-id="f65b7-105">The following list contains some of these well-known properties:</span></span>  
  
-   <span data-ttu-id="f65b7-106">**Nombre del sitio.**</span><span class="sxs-lookup"><span data-stu-id="f65b7-106">**Site Name.**</span></span> <span data-ttu-id="f65b7-107">Nombre del sitio web que contiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="f65b7-107">Name of the Web site that contains the service.</span></span>  
  
-   <span data-ttu-id="f65b7-108">**Ruta de acceso relativa.**</span><span class="sxs-lookup"><span data-stu-id="f65b7-108">**Relative Application Path.**</span></span> <span data-ttu-id="f65b7-109">Ruta de acceso de la aplicación relativa al sitio web.</span><span class="sxs-lookup"><span data-stu-id="f65b7-109">Path of the application relative to the Web site.</span></span>  
  
-   <span data-ttu-id="f65b7-110">**Ruta de acceso relativa del servicio.**</span><span class="sxs-lookup"><span data-stu-id="f65b7-110">**Relative Service Path.**</span></span> <span data-ttu-id="f65b7-111">Ruta de acceso del servicio relativa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f65b7-111">Path of the service relative to the application.</span></span>  
  
-   <span data-ttu-id="f65b7-112">**Nombre de servicio.**</span><span class="sxs-lookup"><span data-stu-id="f65b7-112">**Service Name.**</span></span> <span data-ttu-id="f65b7-113">Nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="f65b7-113">Name of the service.</span></span>  
  
-   <span data-ttu-id="f65b7-114">**Namespace de servicio.**</span><span class="sxs-lookup"><span data-stu-id="f65b7-114">**Service Namespace.**</span></span> <span data-ttu-id="f65b7-115">Nombre del espacio de nombres que usa el servicio.</span><span class="sxs-lookup"><span data-stu-id="f65b7-115">Name of the namespace that the service uses.</span></span>  
  
-   <span data-ttu-id="f65b7-116">**Máquina actual.**</span><span class="sxs-lookup"><span data-stu-id="f65b7-116">**Current Machine.**</span></span>  
  
-   <span data-ttu-id="f65b7-117">**Último equipo**.</span><span class="sxs-lookup"><span data-stu-id="f65b7-117">**Last Machine**.</span></span> <span data-ttu-id="f65b7-118">El equipo en el que la instancia de servicio del flujo de trabajo se ejecutó la última vez.</span><span class="sxs-lookup"><span data-stu-id="f65b7-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f65b7-119">En el caso de los escenarios auto-hospedados con el host de servicio de flujo de trabajo, sólo se rellenan las últimas cuatro propiedades.</span><span class="sxs-lookup"><span data-stu-id="f65b7-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="f65b7-120">En el caso de escenarios de aplicación de flujo de trabajo, solo se rellena la última propiedad.</span><span class="sxs-lookup"><span data-stu-id="f65b7-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="f65b7-121">El tiempo de ejecución del flujo de trabajo proporciona los valores para las primeras tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="f65b7-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="f65b7-122">El host de servicio de flujo de trabajo proporciona el valor de la **motivo de la suspensión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f65b7-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="f65b7-123">El propio almacén de instancia de flujo de trabajo SQL proporciona los valores para la **último equipo actualizado** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f65b7-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="f65b7-124">La característica Almacén de instancias de flujo de trabajo SQL también le permite especificar las propiedades personalizadas para las que desea almacenar los valores en la base de datos de persistencia y que desea usar en consultas.</span><span class="sxs-lookup"><span data-stu-id="f65b7-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="f65b7-125">Para obtener más información acerca de las promociones personalizadas, consulte [extensibilidad del almacén de](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="f65b7-125">For more information about custom promotions, see [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="f65b7-126">Vistas</span><span class="sxs-lookup"><span data-stu-id="f65b7-126">Views</span></span>  
 <span data-ttu-id="f65b7-127">El almacén de instancias contiene las siguientes vistas.</span><span class="sxs-lookup"><span data-stu-id="f65b7-127">The instance store contains the following views.</span></span> <span data-ttu-id="f65b7-128">Vea [esquema de base de datos de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="f65b7-128">See [Persistence Database Schema](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="f65b7-129">Vista Instances</span><span class="sxs-lookup"><span data-stu-id="f65b7-129">The Instances View</span></span>  
 <span data-ttu-id="f65b7-130">La vista Instances contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f65b7-130">The Instances view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="f65b7-131">**Id.**</span><span class="sxs-lookup"><span data-stu-id="f65b7-131">**Id**</span></span>  
  
2.  <span data-ttu-id="f65b7-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="f65b7-132">**PendingTimer**</span></span>  
  
3.  <span data-ttu-id="f65b7-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="f65b7-133">**CreationTime**</span></span>  
  
4.  <span data-ttu-id="f65b7-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="f65b7-134">**LastUpdatedTime**</span></span>  
  
5.  <span data-ttu-id="f65b7-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="f65b7-135">**ServiceDeploymentId**</span></span>  
  
6.  <span data-ttu-id="f65b7-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="f65b7-136">**SuspensionExceptionName**</span></span>  
  
7.  <span data-ttu-id="f65b7-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="f65b7-137">**SuspensionReason**</span></span>  
  
8.  <span data-ttu-id="f65b7-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="f65b7-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="f65b7-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="f65b7-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="f65b7-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="f65b7-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="f65b7-141">**Estado de ejecución**</span><span class="sxs-lookup"><span data-stu-id="f65b7-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="f65b7-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="f65b7-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="f65b7-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="f65b7-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="f65b7-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="f65b7-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="f65b7-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="f65b7-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="f65b7-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="f65b7-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="f65b7-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="f65b7-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="f65b7-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="f65b7-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="f65b7-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="f65b7-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="f65b7-150">Vista ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="f65b7-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="f65b7-151">La vista ServiceDeployments contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f65b7-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="f65b7-152">**Nombre del sitio**</span><span class="sxs-lookup"><span data-stu-id="f65b7-152">**SiteName**</span></span>  
  
2.  <span data-ttu-id="f65b7-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="f65b7-153">**RelativeServicePath**</span></span>  
  
3.  <span data-ttu-id="f65b7-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="f65b7-154">**RelativeApplicationPath**</span></span>  
  
4.  <span data-ttu-id="f65b7-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="f65b7-155">**ServiceName**</span></span>  
  
5.  <span data-ttu-id="f65b7-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="f65b7-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="f65b7-157">Vista InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="f65b7-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="f65b7-158">La vista InstancePromotedProperties contiene los siguientes campos.</span><span class="sxs-lookup"><span data-stu-id="f65b7-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="f65b7-159">Para obtener información detallada sobre las propiedades promocionadas, consulte el [extensibilidad del almacén](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) tema.</span><span class="sxs-lookup"><span data-stu-id="f65b7-159">For details on promoted properties, see the [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) topic.</span></span>  
  
1.  <span data-ttu-id="f65b7-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="f65b7-160">**InstanceId**</span></span>  
  
2.  <span data-ttu-id="f65b7-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="f65b7-161">**EncodingOption**</span></span>  
  
3.  <span data-ttu-id="f65b7-162">**Valor de PromotionName**</span><span class="sxs-lookup"><span data-stu-id="f65b7-162">**PromotionName**</span></span>  
  
4.  <span data-ttu-id="f65b7-163">**Value #** (un intervalo de campos de **Value1** a **Value64**).</span><span class="sxs-lookup"><span data-stu-id="f65b7-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
