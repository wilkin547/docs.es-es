---
title: Soporte técnico para consultas
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: e281b5ae7a41bd282f8e7c7eb9db6f99ef5487f3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948936"
---
# <a name="support-for-queries"></a><span data-ttu-id="0864a-102">Soporte técnico para consultas</span><span class="sxs-lookup"><span data-stu-id="0864a-102">Support for Queries</span></span>
<span data-ttu-id="0864a-103">El almacén de instancias de flujo de trabajo de SQL graba un conjunto de propiedades conocidas en el almacén.</span><span class="sxs-lookup"><span data-stu-id="0864a-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="0864a-104">Los usuarios pueden consultar instancias basadas en estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="0864a-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="0864a-105">La siguiente lista contiene algunas de estas propiedades conocidas:</span><span class="sxs-lookup"><span data-stu-id="0864a-105">The following list contains some of these well-known properties:</span></span>  
  
- <span data-ttu-id="0864a-106">**Nombre del sitio.**</span><span class="sxs-lookup"><span data-stu-id="0864a-106">**Site Name.**</span></span> <span data-ttu-id="0864a-107">Nombre del sitio web que contiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="0864a-107">Name of the Web site that contains the service.</span></span>  
  
- <span data-ttu-id="0864a-108">**Ruta de acceso de la aplicación relativa.**</span><span class="sxs-lookup"><span data-stu-id="0864a-108">**Relative Application Path.**</span></span> <span data-ttu-id="0864a-109">Ruta de acceso de la aplicación relativa al sitio web.</span><span class="sxs-lookup"><span data-stu-id="0864a-109">Path of the application relative to the Web site.</span></span>  
  
- <span data-ttu-id="0864a-110">**Ruta de acceso relativa al servicio.**</span><span class="sxs-lookup"><span data-stu-id="0864a-110">**Relative Service Path.**</span></span> <span data-ttu-id="0864a-111">Ruta de acceso del servicio relativa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0864a-111">Path of the service relative to the application.</span></span>  
  
- <span data-ttu-id="0864a-112">**Nombre del servicio.**</span><span class="sxs-lookup"><span data-stu-id="0864a-112">**Service Name.**</span></span> <span data-ttu-id="0864a-113">Nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="0864a-113">Name of the service.</span></span>  
  
- <span data-ttu-id="0864a-114">**Espacio de nombres de servicio.**</span><span class="sxs-lookup"><span data-stu-id="0864a-114">**Service Namespace.**</span></span> <span data-ttu-id="0864a-115">Nombre del espacio de nombres que usa el servicio.</span><span class="sxs-lookup"><span data-stu-id="0864a-115">Name of the namespace that the service uses.</span></span>  
  
- <span data-ttu-id="0864a-116">**Máquina actual.**</span><span class="sxs-lookup"><span data-stu-id="0864a-116">**Current Machine.**</span></span>  
  
- <span data-ttu-id="0864a-117">**Última máquina**.</span><span class="sxs-lookup"><span data-stu-id="0864a-117">**Last Machine**.</span></span> <span data-ttu-id="0864a-118">El equipo en el que la instancia de servicio del flujo de trabajo se ejecutó la última vez.</span><span class="sxs-lookup"><span data-stu-id="0864a-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0864a-119">En el caso de los escenarios auto-hospedados con el host de servicio de flujo de trabajo, sólo se rellenan las últimas cuatro propiedades.</span><span class="sxs-lookup"><span data-stu-id="0864a-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="0864a-120">En el caso de escenarios de aplicación de flujo de trabajo, solo se rellena la última propiedad.</span><span class="sxs-lookup"><span data-stu-id="0864a-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="0864a-121">El tiempo de ejecución del flujo de trabajo proporciona los valores para las primeras tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="0864a-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="0864a-122">El host de servicio de flujo de trabajo proporciona el valor para la propiedad **motivo de suspensión** .</span><span class="sxs-lookup"><span data-stu-id="0864a-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="0864a-123">El propio almacén de instancias de flujo de trabajo de SQL proporciona valores para la propiedad del **último equipo actualizado** .</span><span class="sxs-lookup"><span data-stu-id="0864a-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="0864a-124">La característica Almacén de instancias de flujo de trabajo SQL también le permite especificar las propiedades personalizadas para las que desea almacenar los valores en la base de datos de persistencia y que desea usar en consultas.</span><span class="sxs-lookup"><span data-stu-id="0864a-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="0864a-125">Para obtener más información acerca de las promociones personalizadas, consulte extensibilidad del [almacén](store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="0864a-125">For more information about custom promotions, see [Store Extensibility](store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="0864a-126">Vistas</span><span class="sxs-lookup"><span data-stu-id="0864a-126">Views</span></span>  
 <span data-ttu-id="0864a-127">El almacén de instancias contiene las siguientes vistas.</span><span class="sxs-lookup"><span data-stu-id="0864a-127">The instance store contains the following views.</span></span> <span data-ttu-id="0864a-128">Consulte el esquema de la [base de datos de persistencia](persistence-database-schema.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="0864a-128">See [Persistence Database Schema](persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="0864a-129">Vista Instances</span><span class="sxs-lookup"><span data-stu-id="0864a-129">The Instances View</span></span>  
 <span data-ttu-id="0864a-130">La vista Instances contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="0864a-130">The Instances view contains the following fields:</span></span>  
  
1. <span data-ttu-id="0864a-131">**Id**</span><span class="sxs-lookup"><span data-stu-id="0864a-131">**Id**</span></span>  
  
2. <span data-ttu-id="0864a-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="0864a-132">**PendingTimer**</span></span>  
  
3. <span data-ttu-id="0864a-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="0864a-133">**CreationTime**</span></span>  
  
4. <span data-ttu-id="0864a-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="0864a-134">**LastUpdatedTime**</span></span>  
  
5. <span data-ttu-id="0864a-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="0864a-135">**ServiceDeploymentId**</span></span>  
  
6. <span data-ttu-id="0864a-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="0864a-136">**SuspensionExceptionName**</span></span>  
  
7. <span data-ttu-id="0864a-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="0864a-137">**SuspensionReason**</span></span>  
  
8. <span data-ttu-id="0864a-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="0864a-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="0864a-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="0864a-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="0864a-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="0864a-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="0864a-141">**ExecutionStatus**</span><span class="sxs-lookup"><span data-stu-id="0864a-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="0864a-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="0864a-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="0864a-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="0864a-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="0864a-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="0864a-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="0864a-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="0864a-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="0864a-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="0864a-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="0864a-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="0864a-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="0864a-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="0864a-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="0864a-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="0864a-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="0864a-150">Vista ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="0864a-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="0864a-151">La vista ServiceDeployments contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="0864a-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1. <span data-ttu-id="0864a-152">**SiteName**</span><span class="sxs-lookup"><span data-stu-id="0864a-152">**SiteName**</span></span>  
  
2. <span data-ttu-id="0864a-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="0864a-153">**RelativeServicePath**</span></span>  
  
3. <span data-ttu-id="0864a-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="0864a-154">**RelativeApplicationPath**</span></span>  
  
4. <span data-ttu-id="0864a-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="0864a-155">**ServiceName**</span></span>  
  
5. <span data-ttu-id="0864a-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="0864a-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="0864a-157">Vista InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="0864a-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="0864a-158">La vista InstancePromotedProperties contiene los siguientes campos.</span><span class="sxs-lookup"><span data-stu-id="0864a-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="0864a-159">Para obtener más información sobre las propiedades promocionadas, consulte el tema extensibilidad de [almacén](store-extensibility.md) .</span><span class="sxs-lookup"><span data-stu-id="0864a-159">For details on promoted properties, see the [Store Extensibility](store-extensibility.md) topic.</span></span>  
  
1. <span data-ttu-id="0864a-160">**InstanceId**</span><span class="sxs-lookup"><span data-stu-id="0864a-160">**InstanceId**</span></span>  
  
2. <span data-ttu-id="0864a-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="0864a-161">**EncodingOption**</span></span>  
  
3. <span data-ttu-id="0864a-162">**PromotionName**</span><span class="sxs-lookup"><span data-stu-id="0864a-162">**PromotionName**</span></span>  
  
4. <span data-ttu-id="0864a-163">**Valor n.º** (un intervalo de campos de **Value1** a **Value64**).</span><span class="sxs-lookup"><span data-stu-id="0864a-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
