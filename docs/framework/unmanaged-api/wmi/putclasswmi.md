---
title: Función PutClassWmi (referencia de la API no administrada)
description: La función PutClassWmi crea una nueva clase o actualiza una existente.
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
ms.openlocfilehash: 7fcf879705135e0093868b48580a37f9d46aa594
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798383"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="9b350-103">PutClassWmi función)</span><span class="sxs-lookup"><span data-stu-id="9b350-103">PutClassWmi function</span></span>

<span data-ttu-id="9b350-104">Crea una imagen o actualiza una existente.</span><span class="sxs-lookup"><span data-stu-id="9b350-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9b350-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b350-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="9b350-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b350-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="9b350-107">de Puntero a una definición de clase válida.</span><span class="sxs-lookup"><span data-stu-id="9b350-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="9b350-108">Debe inicializarse correctamente con todos los valores de propiedad necesarios.</span><span class="sxs-lookup"><span data-stu-id="9b350-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="9b350-109">de Combinación de marcas que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="9b350-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="9b350-110">Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="9b350-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9b350-111">Constante</span><span class="sxs-lookup"><span data-stu-id="9b350-111">Constant</span></span>  |<span data-ttu-id="9b350-112">Value</span><span class="sxs-lookup"><span data-stu-id="9b350-112">Value</span></span>  |<span data-ttu-id="9b350-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9b350-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="9b350-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="9b350-114">0x20000</span></span> | <span data-ttu-id="9b350-115">Si se establece, WMI no almacena ningún calificador con el tipo modificado.</span><span class="sxs-lookup"><span data-stu-id="9b350-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="9b350-116">Si no se establece, se supone que este objeto no está localizado y que todos los calificadores se almacenan con esta instancia.</span><span class="sxs-lookup"><span data-stu-id="9b350-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="9b350-117">0</span><span class="sxs-lookup"><span data-stu-id="9b350-117">0</span></span> | <span data-ttu-id="9b350-118">Cree la clase si no existe o subscribirá si ya existe.</span><span class="sxs-lookup"><span data-stu-id="9b350-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="9b350-119">1</span><span class="sxs-lookup"><span data-stu-id="9b350-119">1</span></span> | <span data-ttu-id="9b350-120">Actualice la clase.</span><span class="sxs-lookup"><span data-stu-id="9b350-120">Update the class.</span></span> <span data-ttu-id="9b350-121">La clase debe existir para que la llamada sea correcta.</span><span class="sxs-lookup"><span data-stu-id="9b350-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="9b350-122">2</span><span class="sxs-lookup"><span data-stu-id="9b350-122">2</span></span> | <span data-ttu-id="9b350-123">Cree la clase.</span><span class="sxs-lookup"><span data-stu-id="9b350-123">Create the class.</span></span> <span data-ttu-id="9b350-124">Se produce un error en la llamada si la clase ya existe.</span><span class="sxs-lookup"><span data-stu-id="9b350-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="9b350-125">0x10</span><span class="sxs-lookup"><span data-stu-id="9b350-125">0x10</span></span> | <span data-ttu-id="9b350-126">La marca produce una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="9b350-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="9b350-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="9b350-127">0x10000</span></span> | <span data-ttu-id="9b350-128">Los proveedores de inserciones deben especificar esta `PutClassWmi` marca cuando se llama a para indicar que esta clase ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="9b350-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="9b350-129">0</span><span class="sxs-lookup"><span data-stu-id="9b350-129">0</span></span> | <span data-ttu-id="9b350-130">Permite actualizar una clase si no hay clases derivadas ni instancias de esa clase.</span><span class="sxs-lookup"><span data-stu-id="9b350-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="9b350-131">También permite las actualizaciones en todos los casos si el cambio es solo para calificadores no importantes, como el calificador de descripción.</span><span class="sxs-lookup"><span data-stu-id="9b350-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="9b350-132">Si la clase tiene instancias o los cambios se producen en calificadores importantes, se produce un error en la actualización.</span><span class="sxs-lookup"><span data-stu-id="9b350-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="9b350-133">0x20</span><span class="sxs-lookup"><span data-stu-id="9b350-133">0x20</span></span> | <span data-ttu-id="9b350-134">Permite actualizaciones de clases aunque haya clases secundarias, siempre y cuando el cambio no cause conflictos con las clases secundarias.</span><span class="sxs-lookup"><span data-stu-id="9b350-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="9b350-135">Por ejemplo, esta marca permite agregar una nueva propiedad a la clase base que no se mencionó anteriormente en ninguna de las clases secundarias.</span><span class="sxs-lookup"><span data-stu-id="9b350-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="9b350-136">Si la clase tiene instancias, se produce un error en la actualización.</span><span class="sxs-lookup"><span data-stu-id="9b350-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="9b350-137">0x40</span><span class="sxs-lookup"><span data-stu-id="9b350-137">0x40</span></span> | <span data-ttu-id="9b350-138">fuerza la actualización de las clases cuando existen clases secundarias en conflicto.</span><span class="sxs-lookup"><span data-stu-id="9b350-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="9b350-139">Por ejemplo, esta marca fuerza una actualización si se define un calificador de clase en una clase secundaria y la clase base intenta agregar el mismo calificador que entra en conflicto con el existente.</span><span class="sxs-lookup"><span data-stu-id="9b350-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="9b350-140">En el modo Force, el conflicto de TIS se resuelve eliminando el calificador en conflicto de la clase secundaria.</span><span class="sxs-lookup"><span data-stu-id="9b350-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="9b350-141">de Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="9b350-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="9b350-142">De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="9b350-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="9b350-143">enuncia Si `null`es, este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="9b350-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="9b350-144">Si `lFlags` `WBEM_S_NO_ERROR`contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función vuelve inmediatamente a.</span><span class="sxs-lookup"><span data-stu-id="9b350-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="9b350-145">El `ppCallResult` parámetro recibe un puntero a un nuevo objeto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .</span><span class="sxs-lookup"><span data-stu-id="9b350-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="9b350-146">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9b350-146">Return value</span></span>

<span data-ttu-id="9b350-147">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="9b350-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9b350-148">Constante</span><span class="sxs-lookup"><span data-stu-id="9b350-148">Constant</span></span>  |<span data-ttu-id="9b350-149">Value</span><span class="sxs-lookup"><span data-stu-id="9b350-149">Value</span></span>  |<span data-ttu-id="9b350-150">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9b350-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="9b350-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="9b350-151">0x80041003</span></span> | <span data-ttu-id="9b350-152">El usuario no tiene permiso para crear o modificar clases.</span><span class="sxs-lookup"><span data-stu-id="9b350-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="9b350-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="9b350-153">0x80041001</span></span> | <span data-ttu-id="9b350-154">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="9b350-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="9b350-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="9b350-155">0x80041010</span></span> | <span data-ttu-id="9b350-156">La clase especificada no es válida.</span><span class="sxs-lookup"><span data-stu-id="9b350-156">The specified class is not valid.</span></span> <span data-ttu-id="9b350-157">Normalmente, esto indica que `pObject` especifica un objeto de instancia.</span><span class="sxs-lookup"><span data-stu-id="9b350-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9b350-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9b350-158">0x80041008</span></span> | <span data-ttu-id="9b350-159">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="9b350-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="9b350-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="9b350-160">0x80041016</span></span> | <span data-ttu-id="9b350-161">El nombre de clase especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="9b350-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="9b350-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="9b350-162">0x80041025</span></span> | <span data-ttu-id="9b350-163">Se intentó realizar un cambio que invalidaría una subclase.</span><span class="sxs-lookup"><span data-stu-id="9b350-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="9b350-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="9b350-164">0x80041019</span></span> | <span data-ttu-id="9b350-165">Se `WBEM_FLAG_CREATE_ONLY` especificó la marca, pero la clase ya existe.</span><span class="sxs-lookup"><span data-stu-id="9b350-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="9b350-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="9b350-166">0x80041002</span></span> | <span data-ttu-id="9b350-167">`WBEM_FLAG_UPDATE_ONLY`se especificó `lFlags`en y no se encontró la clase.</span><span class="sxs-lookup"><span data-stu-id="9b350-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="9b350-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="9b350-168">0x80041020</span></span> | <span data-ttu-id="9b350-169">No se han establecido todas las propiedades necesarias para las clases.</span><span class="sxs-lookup"><span data-stu-id="9b350-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9b350-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9b350-170">0x80041006</span></span> | <span data-ttu-id="9b350-171">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="9b350-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="9b350-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="9b350-172">0x80041033</span></span> | <span data-ttu-id="9b350-173">Es posible que WMI se haya detenido y reiniciado.</span><span class="sxs-lookup"><span data-stu-id="9b350-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="9b350-174">Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="9b350-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="9b350-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="9b350-175">0x80041015</span></span> | <span data-ttu-id="9b350-176">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="9b350-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9b350-177">0</span><span class="sxs-lookup"><span data-stu-id="9b350-177">0</span></span> | <span data-ttu-id="9b350-178">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b350-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="9b350-179">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9b350-179">Remarks</span></span>

<span data-ttu-id="9b350-180">Esta función contiene una llamada al método [IWbemServices::P utclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) .</span><span class="sxs-lookup"><span data-stu-id="9b350-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="9b350-181">El usuario no puede crear clases con nombres que comiencen o terminen por un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="9b350-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="9b350-182">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="9b350-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b350-183">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b350-183">Requirements</span></span>

<span data-ttu-id="9b350-184">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b350-184">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="9b350-185">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9b350-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="9b350-186">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b350-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9b350-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b350-187">See also</span></span>

- [<span data-ttu-id="9b350-188">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="9b350-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
