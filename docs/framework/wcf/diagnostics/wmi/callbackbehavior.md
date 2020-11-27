---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: cec9005a099247671dbebaacc0b242ca8d7a0144
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269653"
---
# <a name="callbackbehavior"></a><span data-ttu-id="4be69-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="4be69-102">CallbackBehavior</span></span>

<span data-ttu-id="4be69-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="4be69-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4be69-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="4be69-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4be69-105">Methods</span></span>  

 <span data-ttu-id="4be69-106">La clase CallbackBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="4be69-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4be69-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4be69-107">Properties</span></span>  

 <span data-ttu-id="4be69-108">La clase CallbackBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="4be69-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="4be69-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="4be69-109">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="4be69-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4be69-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be69-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4be69-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be69-112">Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.</span><span class="sxs-lookup"><span data-stu-id="4be69-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="4be69-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="4be69-113">ConcurrencyMode</span></span>  

 <span data-ttu-id="4be69-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="4be69-114">Data type: string</span></span>  
<span data-ttu-id="4be69-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4be69-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be69-116">Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="4be69-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="4be69-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="4be69-117">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="4be69-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4be69-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be69-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4be69-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be69-120">Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.</span><span class="sxs-lookup"><span data-stu-id="4be69-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="4be69-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="4be69-121">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="4be69-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4be69-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be69-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4be69-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be69-124">Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.</span><span class="sxs-lookup"><span data-stu-id="4be69-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="4be69-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="4be69-125">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="4be69-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4be69-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be69-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4be69-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be69-128">El número máximo de elementos permitido en un objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="4be69-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="4be69-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="4be69-129">UseSynchronizationContext</span></span>  

 <span data-ttu-id="4be69-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4be69-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be69-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4be69-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be69-132">Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4be69-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="4be69-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="4be69-133">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="4be69-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4be69-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="4be69-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4be69-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4be69-136">Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .</span><span class="sxs-lookup"><span data-stu-id="4be69-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4be69-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4be69-137">Requirements</span></span>  
  
|<span data-ttu-id="4be69-138">MOF</span><span class="sxs-lookup"><span data-stu-id="4be69-138">MOF</span></span>|<span data-ttu-id="4be69-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4be69-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4be69-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4be69-140">Namespace</span></span>|<span data-ttu-id="4be69-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4be69-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4be69-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="4be69-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
