---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 9d8f4335c304d164daafeb0ad4de5b4e3bba4590
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973972"
---
# <a name="callbackbehavior"></a><span data-ttu-id="92490-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="92490-102">CallbackBehavior</span></span>
<span data-ttu-id="92490-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="92490-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92490-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92490-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="92490-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="92490-105">Methods</span></span>  
 <span data-ttu-id="92490-106">La clase CallbackBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="92490-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="92490-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="92490-107">Properties</span></span>  
 <span data-ttu-id="92490-108">La clase CallbackBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="92490-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="92490-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="92490-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="92490-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="92490-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="92490-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="92490-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92490-112">Cuando es verdadero, se cierra la sesión automáticamente cuando un servicio cierra una sesión dúplex.</span><span class="sxs-lookup"><span data-stu-id="92490-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="92490-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="92490-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="92490-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="92490-114">Data type: string</span></span>  
<span data-ttu-id="92490-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="92490-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92490-116">Especifica si el servicio admite un subproceso, varios subprocesos o llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="92490-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="92490-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="92490-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="92490-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="92490-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="92490-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="92490-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92490-120">Un valor que especifica si enviar o no datos de la serialización desconocidos hacia la conexión.</span><span class="sxs-lookup"><span data-stu-id="92490-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="92490-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="92490-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="92490-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="92490-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="92490-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="92490-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92490-124">Cuando se habilita, se adjuntan detalles sobre las excepciones de la devolución de llamadas a los errores devueltos al servicio.</span><span class="sxs-lookup"><span data-stu-id="92490-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="92490-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="92490-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="92490-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="92490-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="92490-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="92490-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92490-128">El número máximo de elementos permitido en un objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="92490-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="92490-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="92490-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="92490-130">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="92490-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="92490-131">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="92490-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92490-132">Especifica si utilizar o no el contexto de sincronización actual para elegir la el subproceso de ejecución.</span><span class="sxs-lookup"><span data-stu-id="92490-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="92490-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="92490-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="92490-134">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="92490-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="92490-135">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="92490-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="92490-136">Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .</span><span class="sxs-lookup"><span data-stu-id="92490-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92490-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92490-137">Requirements</span></span>  
  
|<span data-ttu-id="92490-138">MOF</span><span class="sxs-lookup"><span data-stu-id="92490-138">MOF</span></span>|<span data-ttu-id="92490-139">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="92490-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="92490-140">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="92490-140">Namespace</span></span>|<span data-ttu-id="92490-141">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="92490-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92490-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="92490-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
