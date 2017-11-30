---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9df9629e280a2aec6acf93773e09384e763280ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="callbackbehavior"></a><span data-ttu-id="e161d-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="e161d-102">CallbackBehavior</span></span>
<span data-ttu-id="e161d-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="e161d-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e161d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e161d-104">Syntax</span></span>  
  
```  
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e161d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e161d-105">Methods</span></span>  
 <span data-ttu-id="e161d-106">La clase CallbackBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="e161d-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e161d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e161d-107">Properties</span></span>  
 <span data-ttu-id="e161d-108">La clase CallbackBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="e161d-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="e161d-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="e161d-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="e161d-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e161d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="e161d-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e161d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e161d-112">Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.</span><span class="sxs-lookup"><span data-stu-id="e161d-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="e161d-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="e161d-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="e161d-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="e161d-114">Data type: string</span></span>  
<span data-ttu-id="e161d-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e161d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e161d-116">Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="e161d-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="e161d-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="e161d-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="e161d-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e161d-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="e161d-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e161d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e161d-120">Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.</span><span class="sxs-lookup"><span data-stu-id="e161d-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="e161d-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="e161d-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="e161d-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e161d-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e161d-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e161d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e161d-124">Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.</span><span class="sxs-lookup"><span data-stu-id="e161d-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="e161d-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="e161d-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="e161d-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e161d-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="e161d-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e161d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e161d-128">El número máximo de elementos permitido en un objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="e161d-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="e161d-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="e161d-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="e161d-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e161d-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="e161d-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e161d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e161d-132">Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e161d-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="e161d-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="e161d-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="e161d-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="e161d-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="e161d-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="e161d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e161d-136">Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .</span><span class="sxs-lookup"><span data-stu-id="e161d-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e161d-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e161d-137">Requirements</span></span>  
  
|<span data-ttu-id="e161d-138">MOF</span><span class="sxs-lookup"><span data-stu-id="e161d-138">MOF</span></span>|<span data-ttu-id="e161d-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e161d-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e161d-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e161d-140">Namespace</span></span>|<span data-ttu-id="e161d-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e161d-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e161d-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="e161d-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
