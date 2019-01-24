---
title: Función PutClassWmi (referencia de API no administrada)
description: La función PutClassWmi crea una nueva clase o actualiza una ya existente.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 995c697497876969edc1021350b7bfe28e4018bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614515"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="209e2-103">Función PutClassWmi</span><span class="sxs-lookup"><span data-stu-id="209e2-103">PutClassWmi function</span></span>
<span data-ttu-id="209e2-104">Crea una imagen o actualiza una existente.</span><span class="sxs-lookup"><span data-stu-id="209e2-104">Creates a new class or updates an existing one.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="209e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="209e2-105">Syntax</span></span>  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="209e2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="209e2-106">Parameters</span></span>

`pObject`    
<span data-ttu-id="209e2-107">[in] Un puntero a una definición de clase válido.</span><span class="sxs-lookup"><span data-stu-id="209e2-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="209e2-108">Se debe inicializar correctamente con todos los valores de propiedad necesaria.</span><span class="sxs-lookup"><span data-stu-id="209e2-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`   
<span data-ttu-id="209e2-109">[in] Una combinación de marcas que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="209e2-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="209e2-110">Los siguientes valores se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="209e2-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="209e2-111">Constante</span><span class="sxs-lookup"><span data-stu-id="209e2-111">Constant</span></span>  |<span data-ttu-id="209e2-112">Valor</span><span class="sxs-lookup"><span data-stu-id="209e2-112">Value</span></span>  |<span data-ttu-id="209e2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="209e2-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="209e2-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="209e2-114">0x20000</span></span> | <span data-ttu-id="209e2-115">Si el conjunto, WMI no almacena los calificadores con el tipo modificado.</span><span class="sxs-lookup"><span data-stu-id="209e2-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> </br> <span data-ttu-id="209e2-116">Si no es el conjunto, se supone que este objeto no está localizado y todos los calificadores son storedwith esta instancia.</span><span class="sxs-lookup"><span data-stu-id="209e2-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="209e2-117">0</span><span class="sxs-lookup"><span data-stu-id="209e2-117">0</span></span> | <span data-ttu-id="209e2-118">Cree la clase si no existe, o sobrescribirlo si ya existe.</span><span class="sxs-lookup"><span data-stu-id="209e2-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="209e2-119">1</span><span class="sxs-lookup"><span data-stu-id="209e2-119">1</span></span> | <span data-ttu-id="209e2-120">Actualización de la clase.</span><span class="sxs-lookup"><span data-stu-id="209e2-120">Update the class.</span></span> <span data-ttu-id="209e2-121">La clase debe existir para que la llamada se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="209e2-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="209e2-122">2</span><span class="sxs-lookup"><span data-stu-id="209e2-122">2</span></span> | <span data-ttu-id="209e2-123">Cree la clase.</span><span class="sxs-lookup"><span data-stu-id="209e2-123">Create the class.</span></span> <span data-ttu-id="209e2-124">Se produce un error en la llamada si la clase ya existe.</span><span class="sxs-lookup"><span data-stu-id="209e2-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="209e2-125">0x10</span><span class="sxs-lookup"><span data-stu-id="209e2-125">0x10</span></span> | <span data-ttu-id="209e2-126">La marca provoca una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="209e2-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="209e2-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="209e2-127">0x10000</span></span> | <span data-ttu-id="209e2-128">Proveedores de inserción deben especificar esta marca cuando se llama a `PutClassWmi` para indicar que esta clase ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="209e2-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="209e2-129">0</span><span class="sxs-lookup"><span data-stu-id="209e2-129">0</span></span> | <span data-ttu-id="209e2-130">Permite que una clase actualizarse si no hay ninguna instancia de esa clase y no hay clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="209e2-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="209e2-131">También permite actualizaciones en todos los casos si el cambio es simplemente calificadores sin importancia, por ejemplo, el calificador de descripción.</span><span class="sxs-lookup"><span data-stu-id="209e2-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="209e2-132">Si la clase tiene instancias o los cambios son para los calificadores importantes, se produce un error en la actualización.</span><span class="sxs-lookup"><span data-stu-id="209e2-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="209e2-133">0x20</span><span class="sxs-lookup"><span data-stu-id="209e2-133">0x20</span></span> | <span data-ttu-id="209e2-134">Permite actualizaciones en las clases incluso si hay clases secundarias, siempre que el cambio no provoque conflictos con las clases secundarias.</span><span class="sxs-lookup"><span data-stu-id="209e2-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="209e2-135">Por ejemplo, esta marca permite una nueva propiedad que se agregarán a la clase base que no se ha mencionado anteriormente en cualquiera de las clases secundarias.</span><span class="sxs-lookup"><span data-stu-id="209e2-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="209e2-136">Si la clase tiene instancias, se produce un error en la actualización.</span><span class="sxs-lookup"><span data-stu-id="209e2-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="209e2-137">0x40</span><span class="sxs-lookup"><span data-stu-id="209e2-137">0x40</span></span> | <span data-ttu-id="209e2-138">fuerza actualizaciones en las clases cuando se den conflictos con clases secundarias.</span><span class="sxs-lookup"><span data-stu-id="209e2-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="209e2-139">Por ejemplo, esta marca fuerza una actualización si un calificador de clase se define en una clase secundaria y la clase base intenta agregar el mismo calificador que entra en conflicto con thte uno existente.</span><span class="sxs-lookup"><span data-stu-id="209e2-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with thte existing one.</span></span> <span data-ttu-id="209e2-140">En modo forzado, este conflicto se resuelve al eliminar el calificador en conflicto en la clase secundaria.</span><span class="sxs-lookup"><span data-stu-id="209e2-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`  
<span data-ttu-id="209e2-141">[in] Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="209e2-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="209e2-142">En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instancia que se puede usar el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="209e2-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="209e2-143">[out] Si `null`, este parámetro se utiliza.</span><span class="sxs-lookup"><span data-stu-id="209e2-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="209e2-144">Si `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función devuelve inmediatamente con `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="209e2-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="209e2-145">El `ppCallResult` parámetro recibe un puntero a un nuevo [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) objeto.</span><span class="sxs-lookup"><span data-stu-id="209e2-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="209e2-146">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="209e2-146">Return value</span></span>

<span data-ttu-id="209e2-147">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="209e2-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="209e2-148">Constante</span><span class="sxs-lookup"><span data-stu-id="209e2-148">Constant</span></span>  |<span data-ttu-id="209e2-149">Valor</span><span class="sxs-lookup"><span data-stu-id="209e2-149">Value</span></span>  |<span data-ttu-id="209e2-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="209e2-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="209e2-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="209e2-151">0x80041003</span></span> | <span data-ttu-id="209e2-152">El usuario no tiene permiso para crear o modificar las clases.</span><span class="sxs-lookup"><span data-stu-id="209e2-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="209e2-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="209e2-153">0x80041001</span></span> | <span data-ttu-id="209e2-154">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="209e2-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="209e2-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="209e2-155">0x80041010</span></span> | <span data-ttu-id="209e2-156">La clase especificada no es válida.</span><span class="sxs-lookup"><span data-stu-id="209e2-156">The specified class is not valid.</span></span> <span data-ttu-id="209e2-157">Normalmente, esto indica que `pObject` especifica un objeto de instancia.</span><span class="sxs-lookup"><span data-stu-id="209e2-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="209e2-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="209e2-158">0x80041008</span></span> | <span data-ttu-id="209e2-159">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="209e2-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="209e2-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="209e2-160">0x80041016</span></span> | <span data-ttu-id="209e2-161">El nombre de la clase especificada no es válido.</span><span class="sxs-lookup"><span data-stu-id="209e2-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="209e2-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="209e2-162">0x80041025</span></span> | <span data-ttu-id="209e2-163">Se intentó realizar un cambio que invalidaría una subclase.</span><span class="sxs-lookup"><span data-stu-id="209e2-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="209e2-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="209e2-164">0x80041019</span></span> | <span data-ttu-id="209e2-165">El `WBEM_FLAG_CREATE_ONLY` se especificó la marca, pero la clase ya existe.</span><span class="sxs-lookup"><span data-stu-id="209e2-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="209e2-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="209e2-166">0x80041002</span></span> | <span data-ttu-id="209e2-167">`WBEM_FLAG_UPDATE_ONLY` no se especificó en `lFlags`, y no se encontró la clase.</span><span class="sxs-lookup"><span data-stu-id="209e2-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="209e2-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="209e2-168">0x80041020</span></span> | <span data-ttu-id="209e2-169">Las propiedades necesarias para las clases no todos se han establecido.</span><span class="sxs-lookup"><span data-stu-id="209e2-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="209e2-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="209e2-170">0x80041006</span></span> | <span data-ttu-id="209e2-171">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="209e2-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="209e2-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="209e2-172">0x80041033</span></span> | <span data-ttu-id="209e2-173">WMI era probablemente detenido y volver a iniciar.</span><span class="sxs-lookup"><span data-stu-id="209e2-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="209e2-174">Llame a [ConnectServerWmi](connectserverwmi.md) nuevo.</span><span class="sxs-lookup"><span data-stu-id="209e2-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="209e2-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="209e2-175">0x80041015</span></span> | <span data-ttu-id="209e2-176">Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="209e2-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="209e2-177">0</span><span class="sxs-lookup"><span data-stu-id="209e2-177">0</span></span> | <span data-ttu-id="209e2-178">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="209e2-178">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="209e2-179">Comentarios</span><span class="sxs-lookup"><span data-stu-id="209e2-179">Remarks</span></span>

<span data-ttu-id="209e2-180">Esta función contiene una llamada a la [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) método.</span><span class="sxs-lookup"><span data-stu-id="209e2-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="209e2-181">El usuario no puede crear clases con nombres que empiezan o terminan con un carácter de subrayado chacater</span><span class="sxs-lookup"><span data-stu-id="209e2-181">The user may not create classes with names that begin or end with an underscore chacater</span></span>

<span data-ttu-id="209e2-182">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="209e2-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="209e2-183">Requisitos</span><span class="sxs-lookup"><span data-stu-id="209e2-183">Requirements</span></span>  
 <span data-ttu-id="209e2-184">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="209e2-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="209e2-185">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="209e2-185">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="209e2-186">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="209e2-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="209e2-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="209e2-187">See also</span></span>
- [<span data-ttu-id="209e2-188">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="209e2-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
