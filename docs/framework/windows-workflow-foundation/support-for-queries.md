---
description: 'Más información acerca de: compatibilidad con consultas'
title: Soporte técnico para consultas
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 418e511e8b845653b9f3ec86d90c6cbfb25d5671
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755218"
---
# <a name="support-for-queries"></a><span data-ttu-id="76380-103">Soporte técnico para consultas</span><span class="sxs-lookup"><span data-stu-id="76380-103">Support for Queries</span></span>

<span data-ttu-id="76380-104">El almacén de instancias de flujo de trabajo de SQL graba un conjunto de propiedades conocidas en el almacén.</span><span class="sxs-lookup"><span data-stu-id="76380-104">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="76380-105">Los usuarios pueden consultar instancias basadas en estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="76380-105">Users can query for instances based on these properties.</span></span> <span data-ttu-id="76380-106">La siguiente lista contiene algunas de estas propiedades conocidas:</span><span class="sxs-lookup"><span data-stu-id="76380-106">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="76380-107">**Nombre del sitio.**</span><span class="sxs-lookup"><span data-stu-id="76380-107">**Site Name.**</span></span> <span data-ttu-id="76380-108">Nombre del sitio web que contiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="76380-108">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="76380-109">**Ruta de acceso de aplicación relativa.**</span><span class="sxs-lookup"><span data-stu-id="76380-109">**Relative Application Path.**</span></span> <span data-ttu-id="76380-110">Ruta de acceso de la aplicación relativa al sitio web.</span><span class="sxs-lookup"><span data-stu-id="76380-110">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="76380-111">**Ruta de acceso del servicio relativa.**</span><span class="sxs-lookup"><span data-stu-id="76380-111">**Relative Service Path.**</span></span> <span data-ttu-id="76380-112">Ruta de acceso del servicio relativa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76380-112">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="76380-113">**Nombre del servicio.**</span><span class="sxs-lookup"><span data-stu-id="76380-113">**Service Name.**</span></span> <span data-ttu-id="76380-114">Nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="76380-114">Name of the service.</span></span>  
  
- <span data-ttu-id="76380-115">**Espacio de nombres de servicio.**</span><span class="sxs-lookup"><span data-stu-id="76380-115">**Service Namespace.**</span></span> <span data-ttu-id="76380-116">Nombre del espacio de nombres que usa el servicio.</span><span class="sxs-lookup"><span data-stu-id="76380-116">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="76380-117">**Equipo actual.**</span><span class="sxs-lookup"><span data-stu-id="76380-117">**Current Machine.**</span></span>  
  
- <span data-ttu-id="76380-118">**Última máquina**.</span><span class="sxs-lookup"><span data-stu-id="76380-118">**Last Machine**.</span></span> <span data-ttu-id="76380-119">El equipo en el que la instancia de servicio del flujo de trabajo se ejecutó la última vez.</span><span class="sxs-lookup"><span data-stu-id="76380-119">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76380-120">En el caso de los escenarios auto-hospedados con el host de servicio de flujo de trabajo, sólo se rellenan las últimas cuatro propiedades.</span><span class="sxs-lookup"><span data-stu-id="76380-120">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="76380-121">En el caso de escenarios de aplicación de flujo de trabajo, solo se rellena la última propiedad.</span><span class="sxs-lookup"><span data-stu-id="76380-121">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="76380-122">El tiempo de ejecución del flujo de trabajo proporciona los valores para las primeras tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="76380-122">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="76380-123">El host de servicio de flujo de trabajo proporciona el valor para la propiedad **motivo de suspensión** .</span><span class="sxs-lookup"><span data-stu-id="76380-123">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="76380-124">El propio almacén de instancias de flujo de trabajo de SQL proporciona valores para la propiedad del **último equipo actualizado** .</span><span class="sxs-lookup"><span data-stu-id="76380-124">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="76380-125">La característica Almacén de instancias de flujo de trabajo SQL también le permite especificar las propiedades personalizadas para las que desea almacenar los valores en la base de datos de persistencia y que desea usar en consultas.</span><span class="sxs-lookup"><span data-stu-id="76380-125">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="76380-126">Para obtener más información acerca de las promociones personalizadas, consulte [extensibilidad del almacén](store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="76380-126">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="76380-127">Vistas</span><span class="sxs-lookup"><span data-stu-id="76380-127">Views</span></span>  

 <span data-ttu-id="76380-128">El almacén de instancias contiene las siguientes vistas.</span><span class="sxs-lookup"><span data-stu-id="76380-128">The instance store contains the following views.</span></span> <span data-ttu-id="76380-129">Consulte el esquema de la [base de datos de persistencia](persistence-database-schema.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="76380-129">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="76380-130">Vista Instances</span><span class="sxs-lookup"><span data-stu-id="76380-130">The Instances View</span></span>  

 <span data-ttu-id="76380-131">La vista Instances contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="76380-131">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="76380-132">**Id**</span><span class="sxs-lookup"><span data-stu-id="76380-132">**Id**</span></span>  
  
2. <span data-ttu-id="76380-133">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="76380-133">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="76380-134">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="76380-134">**CreationTime**</span></span>  
  
4. <span data-ttu-id="76380-135">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="76380-135">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="76380-136">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="76380-136">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="76380-137">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="76380-137">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="76380-138">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="76380-138">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="76380-139">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="76380-139">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="76380-140">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="76380-140">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="76380-141">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="76380-141">**LastMachine**</span></span>  
  
11. <span data-ttu-id="76380-142">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="76380-142">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="76380-143">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="76380-143">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="76380-144">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="76380-144">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="76380-145">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="76380-145">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="76380-146">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="76380-146">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="76380-147">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="76380-147">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="76380-148">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="76380-148">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="76380-149">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="76380-149">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="76380-150">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="76380-150">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="76380-151">Vista ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="76380-151">The ServiceDeployments view</span></span>  

 <span data-ttu-id="76380-152">La vista ServiceDeployments contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="76380-152">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="76380-153">**Nombresitio**</span><span class="sxs-lookup"><span data-stu-id="76380-153">**SiteName**</span></span>  
  
2. <span data-ttu-id="76380-154">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="76380-154">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="76380-155">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="76380-155">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="76380-156">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="76380-156">**ServiceName**</span></span>  
  
5. <span data-ttu-id="76380-157">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="76380-157">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="76380-158">Vista InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="76380-158">The InstancePromotedProperties view</span></span>  

 <span data-ttu-id="76380-159">La vista InstancePromotedProperties contiene los siguientes campos.</span><span class="sxs-lookup"><span data-stu-id="76380-159">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="76380-160">Para obtener más información sobre las propiedades promocionadas, consulte el tema [extensibilidad de almacén](store-extensibility.md) .</span><span class="sxs-lookup"><span data-stu-id="76380-160">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="76380-161">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="76380-161">**InstanceId**</span></span>  
  
2. <span data-ttu-id="76380-162">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="76380-162">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="76380-163">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="76380-163">**PromotionName**</span></span>  
  
4. <span data-ttu-id="76380-164">**Valor n.º** (un intervalo de campos de **Value1** a **Value64**).</span><span class="sxs-lookup"><span data-stu-id="76380-164">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
