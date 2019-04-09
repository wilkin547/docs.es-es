---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 9d8f4335c304d164daafeb0ad4de5b4e3bba4590
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115042"
---
# <a name="callbackbehavior"></a><span data-ttu-id="2c5ca-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="2c5ca-102">CallbackBehavior</span></span>
<span data-ttu-id="2c5ca-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="2c5ca-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c5ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c5ca-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="2c5ca-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2c5ca-105">Methods</span></span>  
 <span data-ttu-id="2c5ca-106">La clase CallbackBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2c5ca-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2c5ca-107">Properties</span></span>  
 <span data-ttu-id="2c5ca-108">La clase CallbackBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c5ca-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="2c5ca-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="2c5ca-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="2c5ca-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="2c5ca-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c5ca-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2c5ca-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c5ca-112">Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="2c5ca-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="2c5ca-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="2c5ca-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="2c5ca-114">Data type: string</span></span>  
<span data-ttu-id="2c5ca-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2c5ca-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c5ca-116">Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="2c5ca-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="2c5ca-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="2c5ca-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="2c5ca-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c5ca-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2c5ca-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c5ca-120">Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="2c5ca-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="2c5ca-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="2c5ca-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="2c5ca-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c5ca-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2c5ca-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c5ca-124">Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="2c5ca-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="2c5ca-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="2c5ca-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="2c5ca-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c5ca-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2c5ca-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c5ca-128">El número máximo de elementos permitido en un objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="2c5ca-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="2c5ca-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="2c5ca-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="2c5ca-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c5ca-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2c5ca-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c5ca-132">Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="2c5ca-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="2c5ca-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="2c5ca-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="2c5ca-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c5ca-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="2c5ca-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c5ca-136">Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .</span><span class="sxs-lookup"><span data-stu-id="2c5ca-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c5ca-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c5ca-137">Requirements</span></span>  
  
|<span data-ttu-id="2c5ca-138">MOF</span><span class="sxs-lookup"><span data-stu-id="2c5ca-138">MOF</span></span>|<span data-ttu-id="2c5ca-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2c5ca-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2c5ca-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="2c5ca-140">Namespace</span></span>|<span data-ttu-id="2c5ca-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2c5ca-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c5ca-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c5ca-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
