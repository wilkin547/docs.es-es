---
description: 'Más información acerca de: CallbackBehavior'
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: fa9e403324afe818e247d1f751cce0ce7d5a6fb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757766"
---
# <a name="callbackbehavior"></a><span data-ttu-id="d38ae-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="d38ae-103">CallbackBehavior</span></span>

<span data-ttu-id="d38ae-104">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="d38ae-104">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d38ae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d38ae-105">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="d38ae-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="d38ae-106">Methods</span></span>  

 <span data-ttu-id="d38ae-107">La clase CallbackBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d38ae-107">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d38ae-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d38ae-108">Properties</span></span>  

 <span data-ttu-id="d38ae-109">La clase CallbackBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="d38ae-109">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="d38ae-110">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="d38ae-110">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="d38ae-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d38ae-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="d38ae-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d38ae-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d38ae-113">Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.</span><span class="sxs-lookup"><span data-stu-id="d38ae-113">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="d38ae-114">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="d38ae-114">ConcurrencyMode</span></span>  

 <span data-ttu-id="d38ae-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="d38ae-115">Data type: string</span></span>  
<span data-ttu-id="d38ae-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d38ae-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d38ae-117">Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="d38ae-117">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="d38ae-118">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="d38ae-118">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="d38ae-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d38ae-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="d38ae-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d38ae-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d38ae-121">Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.</span><span class="sxs-lookup"><span data-stu-id="d38ae-121">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="d38ae-122">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="d38ae-122">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="d38ae-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d38ae-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="d38ae-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d38ae-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d38ae-125">Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.</span><span class="sxs-lookup"><span data-stu-id="d38ae-125">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="d38ae-126">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="d38ae-126">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="d38ae-127">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d38ae-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="d38ae-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d38ae-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d38ae-129">El número máximo de elementos permitido en un objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="d38ae-129">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="d38ae-130">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="d38ae-130">UseSynchronizationContext</span></span>  

 <span data-ttu-id="d38ae-131">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d38ae-131">Data type: boolean</span></span>  
  
 <span data-ttu-id="d38ae-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d38ae-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d38ae-133">Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d38ae-133">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="d38ae-134">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="d38ae-134">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="d38ae-135">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="d38ae-135">Data type: boolean</span></span>  
  
 <span data-ttu-id="d38ae-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d38ae-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d38ae-137">Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .</span><span class="sxs-lookup"><span data-stu-id="d38ae-137">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d38ae-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d38ae-138">Requirements</span></span>  
  
|<span data-ttu-id="d38ae-139">MOF</span><span class="sxs-lookup"><span data-stu-id="d38ae-139">MOF</span></span>|<span data-ttu-id="d38ae-140">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d38ae-140">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d38ae-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d38ae-141">Namespace</span></span>|<span data-ttu-id="d38ae-142">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d38ae-142">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d38ae-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="d38ae-143">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
