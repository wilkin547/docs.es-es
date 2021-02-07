---
description: 'Más información acerca de: ServiceBehaviorAttribute'
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: 57ffa9103523618db752b3be6d43bb16603d1728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715579"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="08885-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="08885-103">ServiceBehaviorAttribute</span></span>

<span data-ttu-id="08885-104">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="08885-104">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08885-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08885-105">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="08885-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="08885-106">Methods</span></span>  

 <span data-ttu-id="08885-107">La clase ServiceBehaviorAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="08885-107">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="08885-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="08885-108">Properties</span></span>  

 <span data-ttu-id="08885-109">La clase ServiceBehaviorAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="08885-109">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="08885-110">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="08885-110">AutomaticSessionShutdown</span></span>  

 <span data-ttu-id="08885-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08885-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="08885-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-113">Indica si cerrar automáticamente una sesión cuando un cliente cierra una sesión de salida.</span><span class="sxs-lookup"><span data-stu-id="08885-113">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="08885-114">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="08885-114">ConcurrencyMode</span></span>  

 <span data-ttu-id="08885-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="08885-115">Data type: string</span></span>  
<span data-ttu-id="08885-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-117">Indica si un servicio admite un subproceso, varios subprocesos o las llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="08885-117">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="08885-118">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="08885-118">ConfigurationName</span></span>  

 <span data-ttu-id="08885-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="08885-119">Data type: string</span></span>  
  
 <span data-ttu-id="08885-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-121">El nombre de la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="08885-121">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="08885-122">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="08885-122">IgnoreExtensionDataObject</span></span>  

 <span data-ttu-id="08885-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08885-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="08885-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-125">Especifica si enviar datos de la serialización desconocidos hacia la conexión.</span><span class="sxs-lookup"><span data-stu-id="08885-125">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="08885-126">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="08885-126">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="08885-127">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08885-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="08885-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-129">Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.</span><span class="sxs-lookup"><span data-stu-id="08885-129">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="08885-130">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="08885-130">InstanceContextMode</span></span>  

 <span data-ttu-id="08885-131">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="08885-131">Data type: string</span></span>  
  
 <span data-ttu-id="08885-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-133">Especifica cuándo se crea un nuevo objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="08885-133">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="08885-134">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="08885-134">MaxItemsInObjectGraph</span></span>  

 <span data-ttu-id="08885-135">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="08885-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="08885-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-137">El número máximo de elementos permitido en un objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="08885-137">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="08885-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="08885-138">Name</span></span>  

 <span data-ttu-id="08885-139">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="08885-139">Data type: string</span></span>  
  
 <span data-ttu-id="08885-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-141">El atributo de nombre del servicio en WSDL.</span><span class="sxs-lookup"><span data-stu-id="08885-141">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="08885-142">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="08885-142">Namespace</span></span>  

 <span data-ttu-id="08885-143">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="08885-143">Data type: string</span></span>  
  
 <span data-ttu-id="08885-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-145">El espacio de nombres de destino del servicio en WSDL.</span><span class="sxs-lookup"><span data-stu-id="08885-145">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="08885-146">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="08885-146">ReleaseServiceInstanceOnTransactionComplete</span></span>  

 <span data-ttu-id="08885-147">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08885-147">Data type: boolean</span></span>  
  
 <span data-ttu-id="08885-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-149">Especifica si el objeto de servicio se recicla cuando la transacción actual completa.</span><span class="sxs-lookup"><span data-stu-id="08885-149">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="08885-150">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="08885-150">TransactionAutoCompleteOnSessionClose</span></span>  

 <span data-ttu-id="08885-151">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08885-151">Data type: boolean</span></span>  
  
 <span data-ttu-id="08885-152">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-153">Especifica si las transacciones pendientes se completan cuando la sesión actual se cierra.</span><span class="sxs-lookup"><span data-stu-id="08885-153">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="08885-154">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="08885-154">TransactionIsolationLevel</span></span>  

 <span data-ttu-id="08885-155">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="08885-155">Data type: string</span></span>  
  
 <span data-ttu-id="08885-156">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-156">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-157">Especifica el nivel de aislamiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="08885-157">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="08885-158">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="08885-158">TransactionTimeout</span></span>  

 <span data-ttu-id="08885-159">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="08885-159">Data type: datetime</span></span>  
  
 <span data-ttu-id="08885-160">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-160">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-161">El período dentro del que una transacción se debe completar.</span><span class="sxs-lookup"><span data-stu-id="08885-161">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="08885-162">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="08885-162">UseSynchronizationContext</span></span>  

 <span data-ttu-id="08885-163">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08885-163">Data type: boolean</span></span>  
  
 <span data-ttu-id="08885-164">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-164">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-165">Especifica si utilizar el contexto de sincronización actual para elegir la ejecución del subproceso.</span><span class="sxs-lookup"><span data-stu-id="08885-165">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="08885-166">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="08885-166">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="08885-167">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="08885-167">Data type: boolean</span></span>  
  
 <span data-ttu-id="08885-168">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="08885-168">Access type: Read-only</span></span>  
  
 <span data-ttu-id="08885-169">Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .</span><span class="sxs-lookup"><span data-stu-id="08885-169">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08885-170">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08885-170">Requirements</span></span>  
  
|<span data-ttu-id="08885-171">MOF</span><span class="sxs-lookup"><span data-stu-id="08885-171">MOF</span></span>|<span data-ttu-id="08885-172">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="08885-172">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="08885-173">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="08885-173">Namespace</span></span>|<span data-ttu-id="08885-174">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="08885-174">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08885-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="08885-175">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
