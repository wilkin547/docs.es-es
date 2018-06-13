---
title: Soporte técnico para consultas
ms.date: 03/30/2017
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
ms.openlocfilehash: 5c46ed5ae2fc2cc2275bfa7251fe5f8fa346c1f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517996"
---
# <a name="support-for-queries"></a><span data-ttu-id="3908d-102">Soporte técnico para consultas</span><span class="sxs-lookup"><span data-stu-id="3908d-102">Support for Queries</span></span>
<span data-ttu-id="3908d-103">El almacén de instancias de flujo de trabajo de SQL graba un conjunto de propiedades conocidas en el almacén.</span><span class="sxs-lookup"><span data-stu-id="3908d-103">The SQL Workflow Instance Store records a set of well-known properties in the store.</span></span> <span data-ttu-id="3908d-104">Los usuarios pueden consultar instancias basadas en estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="3908d-104">Users can query for instances based on these properties.</span></span> <span data-ttu-id="3908d-105">La siguiente lista contiene algunas de estas propiedades conocidas:</span><span class="sxs-lookup"><span data-stu-id="3908d-105">The following list contains some of these well-known properties:</span></span>  
  
-   <span data-ttu-id="3908d-106">**Nombre del sitio.**</span><span class="sxs-lookup"><span data-stu-id="3908d-106">**Site Name.**</span></span> <span data-ttu-id="3908d-107">Nombre del sitio web que contiene el servicio.</span><span class="sxs-lookup"><span data-stu-id="3908d-107">Name of the Web site that contains the service.</span></span>  
  
-   <span data-ttu-id="3908d-108">**Ruta de acceso relativa.**</span><span class="sxs-lookup"><span data-stu-id="3908d-108">**Relative Application Path.**</span></span> <span data-ttu-id="3908d-109">Ruta de acceso de la aplicación relativa al sitio web.</span><span class="sxs-lookup"><span data-stu-id="3908d-109">Path of the application relative to the Web site.</span></span>  
  
-   <span data-ttu-id="3908d-110">**Ruta de acceso relativa del servicio.**</span><span class="sxs-lookup"><span data-stu-id="3908d-110">**Relative Service Path.**</span></span> <span data-ttu-id="3908d-111">Ruta de acceso del servicio relativa a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3908d-111">Path of the service relative to the application.</span></span>  
  
-   <span data-ttu-id="3908d-112">**Nombre de servicio.**</span><span class="sxs-lookup"><span data-stu-id="3908d-112">**Service Name.**</span></span> <span data-ttu-id="3908d-113">Nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="3908d-113">Name of the service.</span></span>  
  
-   <span data-ttu-id="3908d-114">**Namespace de servicio.**</span><span class="sxs-lookup"><span data-stu-id="3908d-114">**Service Namespace.**</span></span> <span data-ttu-id="3908d-115">Nombre del espacio de nombres que usa el servicio.</span><span class="sxs-lookup"><span data-stu-id="3908d-115">Name of the namespace that the service uses.</span></span>  
  
-   <span data-ttu-id="3908d-116">**Máquina actual.**</span><span class="sxs-lookup"><span data-stu-id="3908d-116">**Current Machine.**</span></span>  
  
-   <span data-ttu-id="3908d-117">**Último equipo**.</span><span class="sxs-lookup"><span data-stu-id="3908d-117">**Last Machine**.</span></span> <span data-ttu-id="3908d-118">El equipo en el que la instancia de servicio del flujo de trabajo se ejecutó la última vez.</span><span class="sxs-lookup"><span data-stu-id="3908d-118">The computer on which the workflow service instance ran the last time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3908d-119">En el caso de los escenarios auto-hospedados con el host de servicio de flujo de trabajo, sólo se rellenan las últimas cuatro propiedades.</span><span class="sxs-lookup"><span data-stu-id="3908d-119">For self-hosted scenarios using Workflow Service Host, only the last four properties are populated.</span></span> <span data-ttu-id="3908d-120">En el caso de escenarios de aplicación de flujo de trabajo, solo se rellena la última propiedad.</span><span class="sxs-lookup"><span data-stu-id="3908d-120">For Workflow Application scenarios, only the last property is populated.</span></span>  
  
 <span data-ttu-id="3908d-121">El tiempo de ejecución del flujo de trabajo proporciona los valores para las primeras tres propiedades.</span><span class="sxs-lookup"><span data-stu-id="3908d-121">The workflow runtime supplies values for the first three properties.</span></span> <span data-ttu-id="3908d-122">El host de servicio de flujo de trabajo proporciona el valor de la **motivo de la suspensión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="3908d-122">The workflow service host supplies the value for the **Suspend Reason** property.</span></span> <span data-ttu-id="3908d-123">El propio almacén de instancia de flujo de trabajo SQL proporciona los valores para la **último equipo actualizado** propiedad.</span><span class="sxs-lookup"><span data-stu-id="3908d-123">The SQL Workflow Instance Store itself supplies values for the **Last Updated Machine** property.</span></span>  
  
 <span data-ttu-id="3908d-124">La característica Almacén de instancias de flujo de trabajo SQL también le permite especificar las propiedades personalizadas para las que desea almacenar los valores en la base de datos de persistencia y que desea usar en consultas.</span><span class="sxs-lookup"><span data-stu-id="3908d-124">The SQL Workflow Instance Store feature also lets you specify the custom properties for which you want to store the values in the persistence database and that you want to use in queries.</span></span> <span data-ttu-id="3908d-125">Para obtener más información acerca de las promociones personalizadas, consulte [extensibilidad del almacén de](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="3908d-125">For more information about custom promotions, see [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md).</span></span>  
  
## <a name="views"></a><span data-ttu-id="3908d-126">Vistas</span><span class="sxs-lookup"><span data-stu-id="3908d-126">Views</span></span>  
 <span data-ttu-id="3908d-127">El almacén de instancias contiene las siguientes vistas.</span><span class="sxs-lookup"><span data-stu-id="3908d-127">The instance store contains the following views.</span></span> <span data-ttu-id="3908d-128">Vea [esquema de base de datos de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="3908d-128">See [Persistence Database Schema](../../../docs/framework/windows-workflow-foundation/persistence-database-schema.md) for further details.</span></span>  
  
### <a name="the-instances-view"></a><span data-ttu-id="3908d-129">Vista Instances</span><span class="sxs-lookup"><span data-stu-id="3908d-129">The Instances View</span></span>  
 <span data-ttu-id="3908d-130">La vista Instances contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="3908d-130">The Instances view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="3908d-131">**Id.**</span><span class="sxs-lookup"><span data-stu-id="3908d-131">**Id**</span></span>  
  
2.  <span data-ttu-id="3908d-132">**PendingTimer**</span><span class="sxs-lookup"><span data-stu-id="3908d-132">**PendingTimer**</span></span>  
  
3.  <span data-ttu-id="3908d-133">**CreationTime**</span><span class="sxs-lookup"><span data-stu-id="3908d-133">**CreationTime**</span></span>  
  
4.  <span data-ttu-id="3908d-134">**LastUpdatedTime**</span><span class="sxs-lookup"><span data-stu-id="3908d-134">**LastUpdatedTime**</span></span>  
  
5.  <span data-ttu-id="3908d-135">**ServiceDeploymentId**</span><span class="sxs-lookup"><span data-stu-id="3908d-135">**ServiceDeploymentId**</span></span>  
  
6.  <span data-ttu-id="3908d-136">**SuspensionExceptionName**</span><span class="sxs-lookup"><span data-stu-id="3908d-136">**SuspensionExceptionName**</span></span>  
  
7.  <span data-ttu-id="3908d-137">**SuspensionReason**</span><span class="sxs-lookup"><span data-stu-id="3908d-137">**SuspensionReason**</span></span>  
  
8.  <span data-ttu-id="3908d-138">**ActiveBookmarks**</span><span class="sxs-lookup"><span data-stu-id="3908d-138">**ActiveBookmarks**</span></span>  
  
9. <span data-ttu-id="3908d-139">**CurrentMachine**</span><span class="sxs-lookup"><span data-stu-id="3908d-139">**CurrentMachine**</span></span>  
  
10. <span data-ttu-id="3908d-140">**LastMachine**</span><span class="sxs-lookup"><span data-stu-id="3908d-140">**LastMachine**</span></span>  
  
11. <span data-ttu-id="3908d-141">**Estado de ejecución**</span><span class="sxs-lookup"><span data-stu-id="3908d-141">**ExecutionStatus**</span></span>  
  
12. <span data-ttu-id="3908d-142">**IsInitialized**</span><span class="sxs-lookup"><span data-stu-id="3908d-142">**IsInitialized**</span></span>  
  
13. <span data-ttu-id="3908d-143">**IsSuspended**</span><span class="sxs-lookup"><span data-stu-id="3908d-143">**IsSuspended**</span></span>  
  
14. <span data-ttu-id="3908d-144">**IsCompleted**</span><span class="sxs-lookup"><span data-stu-id="3908d-144">**IsCompleted**</span></span>  
  
15. <span data-ttu-id="3908d-145">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="3908d-145">**EncodingOption**</span></span>  
  
16. <span data-ttu-id="3908d-146">**ReadWritePrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="3908d-146">**ReadWritePrimitiveDataProperties**</span></span>  
  
17. <span data-ttu-id="3908d-147">**WriteOnlyPrimitiveDataProperties**</span><span class="sxs-lookup"><span data-stu-id="3908d-147">**WriteOnlyPrimitiveDataProperties**</span></span>  
  
18. <span data-ttu-id="3908d-148">**ReadWriteComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="3908d-148">**ReadWriteComplexDataProperties**</span></span>  
  
19. <span data-ttu-id="3908d-149">**WriteOnlyComplexDataProperties**</span><span class="sxs-lookup"><span data-stu-id="3908d-149">**WriteOnlyComplexDataProperties**</span></span>  
  
### <a name="the-servicedeployments-view"></a><span data-ttu-id="3908d-150">Vista ServiceDeployments</span><span class="sxs-lookup"><span data-stu-id="3908d-150">The ServiceDeployments view</span></span>  
 <span data-ttu-id="3908d-151">La vista ServiceDeployments contiene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="3908d-151">The ServiceDeployments view contains the following fields:</span></span>  
  
1.  <span data-ttu-id="3908d-152">**Nombre del sitio**</span><span class="sxs-lookup"><span data-stu-id="3908d-152">**SiteName**</span></span>  
  
2.  <span data-ttu-id="3908d-153">**RelativeServicePath**</span><span class="sxs-lookup"><span data-stu-id="3908d-153">**RelativeServicePath**</span></span>  
  
3.  <span data-ttu-id="3908d-154">**RelativeApplicationPath**</span><span class="sxs-lookup"><span data-stu-id="3908d-154">**RelativeApplicationPath**</span></span>  
  
4.  <span data-ttu-id="3908d-155">**ServiceName**</span><span class="sxs-lookup"><span data-stu-id="3908d-155">**ServiceName**</span></span>  
  
5.  <span data-ttu-id="3908d-156">**ServiceNamespace**</span><span class="sxs-lookup"><span data-stu-id="3908d-156">**ServiceNamespace**</span></span>  
  
### <a name="the-instancepromotedproperties-view"></a><span data-ttu-id="3908d-157">Vista InstancePromotedProperties</span><span class="sxs-lookup"><span data-stu-id="3908d-157">The InstancePromotedProperties view</span></span>  
 <span data-ttu-id="3908d-158">La vista InstancePromotedProperties contiene los siguientes campos.</span><span class="sxs-lookup"><span data-stu-id="3908d-158">The InstancePromotedProperties view contains the following fields.</span></span> <span data-ttu-id="3908d-159">Para obtener información detallada sobre las propiedades promocionadas, consulte el [extensibilidad del almacén](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) tema.</span><span class="sxs-lookup"><span data-stu-id="3908d-159">For details on promoted properties, see the [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) topic.</span></span>  
  
1.  <span data-ttu-id="3908d-160">**instanceId**</span><span class="sxs-lookup"><span data-stu-id="3908d-160">**InstanceId**</span></span>  
  
2.  <span data-ttu-id="3908d-161">**EncodingOption**</span><span class="sxs-lookup"><span data-stu-id="3908d-161">**EncodingOption**</span></span>  
  
3.  <span data-ttu-id="3908d-162">**Valor de PromotionName**</span><span class="sxs-lookup"><span data-stu-id="3908d-162">**PromotionName**</span></span>  
  
4.  <span data-ttu-id="3908d-163">**Value #** (un intervalo de campos de **Value1** a **Value64**).</span><span class="sxs-lookup"><span data-stu-id="3908d-163">**Value#** (a range of fields from **Value1** to **Value64**).</span></span>
