---
title: Función PutInstanceWmi (referencia de la API no administrada)
description: La función PutInstanceWmi crea o actualiza una instancia de una clase existente.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798373"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="93e21-103">PutInstanceWmi función)</span><span class="sxs-lookup"><span data-stu-id="93e21-103">PutInstanceWmi function</span></span>

<span data-ttu-id="93e21-104">Crea o actualiza una instancia de una clase existente.</span><span class="sxs-lookup"><span data-stu-id="93e21-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="93e21-105">La instancia se escribe en el repositorio de la WMI.</span><span class="sxs-lookup"><span data-stu-id="93e21-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="93e21-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93e21-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="93e21-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93e21-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="93e21-108">de Puntero a la instancia de que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="93e21-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="93e21-109">de Combinación de marcas que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="93e21-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="93e21-110">Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="93e21-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="93e21-111">Constante</span><span class="sxs-lookup"><span data-stu-id="93e21-111">Constant</span></span>  |<span data-ttu-id="93e21-112">Value</span><span class="sxs-lookup"><span data-stu-id="93e21-112">Value</span></span>  |<span data-ttu-id="93e21-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="93e21-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="93e21-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="93e21-114">0x20000</span></span> | <span data-ttu-id="93e21-115">Si se establece, WMI no almacena ningún calificador con el tipo **modificado** .</span><span class="sxs-lookup"><span data-stu-id="93e21-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="93e21-116">Si no se establece, se supone que este objeto no está localizado y que todos los calificadores se almacenan con esta instancia.</span><span class="sxs-lookup"><span data-stu-id="93e21-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="93e21-117">0</span><span class="sxs-lookup"><span data-stu-id="93e21-117">0</span></span> | <span data-ttu-id="93e21-118">Cree la instancia si no existe, o bien sobrescriba si ya existe.</span><span class="sxs-lookup"><span data-stu-id="93e21-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="93e21-119">1</span><span class="sxs-lookup"><span data-stu-id="93e21-119">1</span></span> | <span data-ttu-id="93e21-120">Actualice la instancia de.</span><span class="sxs-lookup"><span data-stu-id="93e21-120">Update the instance.</span></span> <span data-ttu-id="93e21-121">La instancia debe existir para que la llamada se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="93e21-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="93e21-122">2</span><span class="sxs-lookup"><span data-stu-id="93e21-122">2</span></span> | <span data-ttu-id="93e21-123">Cree la instancia.</span><span class="sxs-lookup"><span data-stu-id="93e21-123">Create the instance.</span></span> <span data-ttu-id="93e21-124">Se produce un error en la llamada si la instancia ya existe.</span><span class="sxs-lookup"><span data-stu-id="93e21-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="93e21-125">0x10</span><span class="sxs-lookup"><span data-stu-id="93e21-125">0x10</span></span> | <span data-ttu-id="93e21-126">La marca produce una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="93e21-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="93e21-127">de Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="93e21-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="93e21-128">De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="93e21-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="93e21-129">enuncia Si `null`es, este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="93e21-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="93e21-130">Si `lFlags` `WBEM_S_NO_ERROR`contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función vuelve inmediatamente a.</span><span class="sxs-lookup"><span data-stu-id="93e21-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="93e21-131">El `ppCallResult` parámetro recibe un puntero a un nuevo objeto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .</span><span class="sxs-lookup"><span data-stu-id="93e21-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="93e21-132">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="93e21-132">Return value</span></span>

<span data-ttu-id="93e21-133">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="93e21-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="93e21-134">Constante</span><span class="sxs-lookup"><span data-stu-id="93e21-134">Constant</span></span>  |<span data-ttu-id="93e21-135">Value</span><span class="sxs-lookup"><span data-stu-id="93e21-135">Value</span></span>  |<span data-ttu-id="93e21-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="93e21-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="93e21-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="93e21-137">0x80041003</span></span> | <span data-ttu-id="93e21-138">El usuario no tiene permiso para actualizar una instancia de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="93e21-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="93e21-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="93e21-139">0x80041001</span></span> | <span data-ttu-id="93e21-140">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="93e21-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="93e21-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="93e21-141">0x80041010</span></span> | <span data-ttu-id="93e21-142">La clase que admite esta instancia no es válida.</span><span class="sxs-lookup"><span data-stu-id="93e21-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="93e21-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="93e21-143">0x80041028</span></span> | <span data-ttu-id="93e21-144">se `null` ha especificado un para una propiedad que no `null`puede ser, como una marcada por un calificador **indexado** o **Not_Null** .</span><span class="sxs-lookup"><span data-stu-id="93e21-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="93e21-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="93e21-145">0x8004100f</span></span> | <span data-ttu-id="93e21-146">La instancia especificada no es válida.</span><span class="sxs-lookup"><span data-stu-id="93e21-146">The specified instance is not valid.</span></span> <span data-ttu-id="93e21-147">(Por ejemplo, llamar `PutInstanceWmi` a con una clase devuelve este valor).</span><span class="sxs-lookup"><span data-stu-id="93e21-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="93e21-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="93e21-148">0x80041008</span></span> | <span data-ttu-id="93e21-149">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="93e21-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="93e21-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="93e21-150">0x80041019</span></span> | <span data-ttu-id="93e21-151">Se `WBEM_FLAG_CREATE_ONLY` especificó la marca, pero la instancia ya existe.</span><span class="sxs-lookup"><span data-stu-id="93e21-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="93e21-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="93e21-152">0x80041002</span></span> | <span data-ttu-id="93e21-153">`WBEM_FLAG_UPDATE_ONLY`se especificó `lFlags`en, pero la instancia no existe.</span><span class="sxs-lookup"><span data-stu-id="93e21-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="93e21-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="93e21-154">0x80041006</span></span> | <span data-ttu-id="93e21-155">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="93e21-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="93e21-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="93e21-156">0x80041033</span></span> | <span data-ttu-id="93e21-157">Es posible que WMI se haya detenido y reiniciado.</span><span class="sxs-lookup"><span data-stu-id="93e21-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="93e21-158">Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="93e21-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="93e21-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="93e21-159">0x80041015</span></span> | <span data-ttu-id="93e21-160">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="93e21-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="93e21-161">0</span><span class="sxs-lookup"><span data-stu-id="93e21-161">0</span></span> | <span data-ttu-id="93e21-162">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="93e21-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="93e21-163">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93e21-163">Remarks</span></span>

<span data-ttu-id="93e21-164">Esta función contiene una llamada al método [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .</span><span class="sxs-lookup"><span data-stu-id="93e21-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="93e21-165">La `PutInstanceWmi` función solo admite la creación de instancias y la actualización de instancias de clases existentes.</span><span class="sxs-lookup"><span data-stu-id="93e21-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="93e21-166">Dependiendo de cómo se establezca `pCtx` el parámetro, se actualizan algunas o todas las propiedades de la instancia.</span><span class="sxs-lookup"><span data-stu-id="93e21-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="93e21-167">Cuando la instancia de a la `pInst` que apunta pertenece a una subclase, la administración de Windows llama a todos los proveedores responsables de las clases de las que deriva la subclase.</span><span class="sxs-lookup"><span data-stu-id="93e21-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="93e21-168">Todos estos proveedores deben realizarse correctamente para que `PutInstanceWmi` la solicitud original se lleve a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="93e21-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="93e21-169">Se llama primero al proveedor que admite la clase de nivel superior en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="93e21-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="93e21-170">El orden de llamada continúa con la subclase de la clase de nivel superior y continúa desde la parte superior a la inferior hasta que la administración de Windows llega al proveedor de la `pInst`clase propietaria de la instancia a la que apunta.</span><span class="sxs-lookup"><span data-stu-id="93e21-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="93e21-171">La administración de Windows no llama a los proveedores de ninguna de las clases secundarias de una instancia.</span><span class="sxs-lookup"><span data-stu-id="93e21-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="93e21-172">Cuando una aplicación debe actualizar una instancia que pertenece a una jerarquía de clases, `pInst` el parámetro debe apuntar a la instancia que contiene las propiedades que se van a modificar.</span><span class="sxs-lookup"><span data-stu-id="93e21-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="93e21-173">Es decir, considere una instancia de destino que pertenece a **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="93e21-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="93e21-174">La instancia de **ClassB** se deriva de **ClassA**y **ClassA** define la propiedad **PROPA**.</span><span class="sxs-lookup"><span data-stu-id="93e21-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="93e21-175">Si una aplicación desea hacer un cambio en el valor de **PROPA** en la instancia de **ClassB** , debe establecerse `pInst` en esa instancia en lugar de en una instancia de **ClassA**.</span><span class="sxs-lookup"><span data-stu-id="93e21-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="93e21-176">No `PutInstanceWmi` se permite llamar a en una instancia de una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="93e21-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="93e21-177">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="93e21-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="93e21-178">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93e21-178">Requirements</span></span>

<span data-ttu-id="93e21-179">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93e21-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="93e21-180">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="93e21-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="93e21-181">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="93e21-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="93e21-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="93e21-182">See also</span></span>

- [<span data-ttu-id="93e21-183">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="93e21-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
