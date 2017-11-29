---
title: ServiceBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f7401acd5aefcb7a8c02ea6c05a94374e41d9b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="56f35-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="56f35-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="56f35-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="56f35-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56f35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56f35-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="56f35-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="56f35-105">Methods</span></span>  
 <span data-ttu-id="56f35-106">La clase ServiceBehaviorAttribute no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="56f35-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="56f35-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="56f35-107">Properties</span></span>  
 <span data-ttu-id="56f35-108">La clase ServiceBehaviorAttribute tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="56f35-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="56f35-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="56f35-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="56f35-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="56f35-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="56f35-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-112">Indica si cerrar automáticamente una sesión cuando un cliente cierra una sesión de salida.</span><span class="sxs-lookup"><span data-stu-id="56f35-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="56f35-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="56f35-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="56f35-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="56f35-114">Data type: string</span></span>  
<span data-ttu-id="56f35-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-116">Indica si un servicio admite un subproceso, varios subprocesos o las llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="56f35-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="56f35-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="56f35-117">ConfigurationName</span></span>  
 <span data-ttu-id="56f35-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="56f35-118">Data type: string</span></span>  
  
 <span data-ttu-id="56f35-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-120">El nombre de la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="56f35-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="56f35-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="56f35-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="56f35-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="56f35-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="56f35-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-124">Especifica si enviar datos de la serialización desconocidos hacia la conexión.</span><span class="sxs-lookup"><span data-stu-id="56f35-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="56f35-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="56f35-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="56f35-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="56f35-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="56f35-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-128">Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.</span><span class="sxs-lookup"><span data-stu-id="56f35-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="56f35-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="56f35-129">InstanceContextMode</span></span>  
 <span data-ttu-id="56f35-130">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="56f35-130">Data type: string</span></span>  
  
 <span data-ttu-id="56f35-131">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-132">Especifica cuándo se crea un nuevo objeto de servicio.</span><span class="sxs-lookup"><span data-stu-id="56f35-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="56f35-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="56f35-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="56f35-134">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="56f35-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="56f35-135">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-136">El número máximo de elementos permitido en un objeto serializado.</span><span class="sxs-lookup"><span data-stu-id="56f35-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="56f35-137">Nombre</span><span class="sxs-lookup"><span data-stu-id="56f35-137">Name</span></span>  
 <span data-ttu-id="56f35-138">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="56f35-138">Data type: string</span></span>  
  
 <span data-ttu-id="56f35-139">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-140">El atributo de nombre del servicio en WSDL.</span><span class="sxs-lookup"><span data-stu-id="56f35-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="56f35-141">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="56f35-141">Namespace</span></span>  
 <span data-ttu-id="56f35-142">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="56f35-142">Data type: string</span></span>  
  
 <span data-ttu-id="56f35-143">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-144">El espacio de nombres de destino del servicio en WSDL.</span><span class="sxs-lookup"><span data-stu-id="56f35-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="56f35-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="56f35-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="56f35-146">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="56f35-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="56f35-147">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-148">Especifica si el objeto de servicio se recicla cuando la transacción actual completa.</span><span class="sxs-lookup"><span data-stu-id="56f35-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="56f35-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="56f35-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="56f35-150">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="56f35-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="56f35-151">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-152">Especifica si las transacciones pendientes se completan cuando la sesión actual se cierra.</span><span class="sxs-lookup"><span data-stu-id="56f35-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="56f35-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="56f35-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="56f35-154">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="56f35-154">Data type: string</span></span>  
  
 <span data-ttu-id="56f35-155">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-156">Especifica el nivel de aislamiento de la transacción.</span><span class="sxs-lookup"><span data-stu-id="56f35-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="56f35-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="56f35-157">TransactionTimeout</span></span>  
 <span data-ttu-id="56f35-158">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="56f35-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="56f35-159">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-160">El período dentro del que una transacción se debe completar.</span><span class="sxs-lookup"><span data-stu-id="56f35-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="56f35-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="56f35-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="56f35-162">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="56f35-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="56f35-163">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-164">Especifica si utilizar el contexto de sincronización actual para elegir la ejecución del subproceso.</span><span class="sxs-lookup"><span data-stu-id="56f35-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="56f35-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="56f35-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="56f35-166">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="56f35-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="56f35-167">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56f35-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="56f35-168">Especifica si el sistema o la aplicación exigen procesamiento de encabezados MustUnderstand de SOAP .</span><span class="sxs-lookup"><span data-stu-id="56f35-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56f35-169">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56f35-169">Requirements</span></span>  
  
|<span data-ttu-id="56f35-170">MOF</span><span class="sxs-lookup"><span data-stu-id="56f35-170">MOF</span></span>|<span data-ttu-id="56f35-171">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="56f35-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="56f35-172">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="56f35-172">Namespace</span></span>|<span data-ttu-id="56f35-173">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="56f35-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="56f35-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="56f35-174">See Also</span></span>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>
