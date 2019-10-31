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
ms.openlocfilehash: b33f31d69c64ce520580c29f1014c058c78d0953
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127349"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="3c939-103">PutInstanceWmi función)</span><span class="sxs-lookup"><span data-stu-id="3c939-103">PutInstanceWmi function</span></span>

<span data-ttu-id="3c939-104">Crea o actualiza una instancia de una clase existente.</span><span class="sxs-lookup"><span data-stu-id="3c939-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="3c939-105">La instancia se escribe en el repositorio de la WMI.</span><span class="sxs-lookup"><span data-stu-id="3c939-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3c939-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c939-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="3c939-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c939-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="3c939-108">de Puntero a la instancia de que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="3c939-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="3c939-109">de Combinación de marcas que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="3c939-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="3c939-110">Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="3c939-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3c939-111">Constante</span><span class="sxs-lookup"><span data-stu-id="3c939-111">Constant</span></span>  |<span data-ttu-id="3c939-112">Valor</span><span class="sxs-lookup"><span data-stu-id="3c939-112">Value</span></span>  |<span data-ttu-id="3c939-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c939-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="3c939-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="3c939-114">0x20000</span></span> | <span data-ttu-id="3c939-115">Si se establece, WMI no almacena ningún calificador con el tipo **modificado** .</span><span class="sxs-lookup"><span data-stu-id="3c939-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="3c939-116">Si no se establece, se supone que este objeto no está localizado y que todos los calificadores se almacenan con esta instancia.</span><span class="sxs-lookup"><span data-stu-id="3c939-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="3c939-117">0</span><span class="sxs-lookup"><span data-stu-id="3c939-117">0</span></span> | <span data-ttu-id="3c939-118">Cree la instancia si no existe, o bien sobrescriba si ya existe.</span><span class="sxs-lookup"><span data-stu-id="3c939-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="3c939-119">1</span><span class="sxs-lookup"><span data-stu-id="3c939-119">1</span></span> | <span data-ttu-id="3c939-120">Actualice la instancia de.</span><span class="sxs-lookup"><span data-stu-id="3c939-120">Update the instance.</span></span> <span data-ttu-id="3c939-121">La instancia debe existir para que la llamada se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="3c939-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="3c939-122">2</span><span class="sxs-lookup"><span data-stu-id="3c939-122">2</span></span> | <span data-ttu-id="3c939-123">Cree la instancia.</span><span class="sxs-lookup"><span data-stu-id="3c939-123">Create the instance.</span></span> <span data-ttu-id="3c939-124">Se produce un error en la llamada si la instancia ya existe.</span><span class="sxs-lookup"><span data-stu-id="3c939-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="3c939-125">0x10</span><span class="sxs-lookup"><span data-stu-id="3c939-125">0x10</span></span> | <span data-ttu-id="3c939-126">La marca produce una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="3c939-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="3c939-127">de Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="3c939-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="3c939-128">De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="3c939-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="3c939-129">enuncia Si `null`, este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3c939-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="3c939-130">Si `lFlags` contiene `WBEM_FLAG_RETURN_IMMEDIATELY`, la función vuelve inmediatamente a `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="3c939-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="3c939-131">El parámetro `ppCallResult` recibe un puntero a un nuevo objeto [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) .</span><span class="sxs-lookup"><span data-stu-id="3c939-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="3c939-132">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c939-132">Return value</span></span>

<span data-ttu-id="3c939-133">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="3c939-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3c939-134">Constante</span><span class="sxs-lookup"><span data-stu-id="3c939-134">Constant</span></span>  |<span data-ttu-id="3c939-135">Valor</span><span class="sxs-lookup"><span data-stu-id="3c939-135">Value</span></span>  |<span data-ttu-id="3c939-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c939-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="3c939-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="3c939-137">0x80041003</span></span> | <span data-ttu-id="3c939-138">El usuario no tiene permiso para actualizar una instancia de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="3c939-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="3c939-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3c939-139">0x80041001</span></span> | <span data-ttu-id="3c939-140">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="3c939-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="3c939-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="3c939-141">0x80041010</span></span> | <span data-ttu-id="3c939-142">La clase que admite esta instancia no es válida.</span><span class="sxs-lookup"><span data-stu-id="3c939-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="3c939-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="3c939-143">0x80041028</span></span> | <span data-ttu-id="3c939-144">se especificó una `null` para una propiedad que no se puede `null`, como una marcada por un calificador **indexado** o **Not_Null** .</span><span class="sxs-lookup"><span data-stu-id="3c939-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="3c939-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="3c939-145">0x8004100f</span></span> | <span data-ttu-id="3c939-146">La instancia especificada no es válida.</span><span class="sxs-lookup"><span data-stu-id="3c939-146">The specified instance is not valid.</span></span> <span data-ttu-id="3c939-147">(Por ejemplo, al llamar a `PutInstanceWmi` con una clase se devuelve este valor).</span><span class="sxs-lookup"><span data-stu-id="3c939-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3c939-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3c939-148">0x80041008</span></span> | <span data-ttu-id="3c939-149">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="3c939-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="3c939-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="3c939-150">0x80041019</span></span> | <span data-ttu-id="3c939-151">Se especificó la marca `WBEM_FLAG_CREATE_ONLY`, pero la instancia ya existe.</span><span class="sxs-lookup"><span data-stu-id="3c939-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="3c939-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3c939-152">0x80041002</span></span> | <span data-ttu-id="3c939-153">se especificó `WBEM_FLAG_UPDATE_ONLY` en `lFlags`, pero la instancia no existe.</span><span class="sxs-lookup"><span data-stu-id="3c939-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3c939-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3c939-154">0x80041006</span></span> | <span data-ttu-id="3c939-155">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="3c939-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="3c939-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="3c939-156">0x80041033</span></span> | <span data-ttu-id="3c939-157">Es posible que WMI se haya detenido y reiniciado.</span><span class="sxs-lookup"><span data-stu-id="3c939-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="3c939-158">Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="3c939-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="3c939-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="3c939-159">0x80041015</span></span> | <span data-ttu-id="3c939-160">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="3c939-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3c939-161">0</span><span class="sxs-lookup"><span data-stu-id="3c939-161">0</span></span> | <span data-ttu-id="3c939-162">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3c939-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="3c939-163">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c939-163">Remarks</span></span>

<span data-ttu-id="3c939-164">Esta función contiene una llamada al método [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) .</span><span class="sxs-lookup"><span data-stu-id="3c939-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="3c939-165">La función `PutInstanceWmi` admite la creación de instancias y la actualización de instancias de clases existentes.</span><span class="sxs-lookup"><span data-stu-id="3c939-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="3c939-166">Dependiendo de cómo se establezca el parámetro `pCtx`, se actualizan algunas o todas las propiedades de la instancia.</span><span class="sxs-lookup"><span data-stu-id="3c939-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="3c939-167">Cuando la instancia a la que apunta `pInst` pertenece a una subclase, la administración de Windows llama a todos los proveedores responsables de las clases de las que deriva la subclase.</span><span class="sxs-lookup"><span data-stu-id="3c939-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="3c939-168">Todos estos proveedores deben ejecutarse correctamente para que la solicitud de `PutInstanceWmi` original se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="3c939-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="3c939-169">Se llama primero al proveedor que admite la clase de nivel superior en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="3c939-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="3c939-170">El orden de llamada continúa con la subclase de la clase de nivel superior y continúa desde la parte superior a la inferior hasta que la administración de Windows llega al proveedor de la clase propietaria de la instancia a la que apunta `pInst`.</span><span class="sxs-lookup"><span data-stu-id="3c939-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="3c939-171">La administración de Windows no llama a los proveedores de ninguna de las clases secundarias de una instancia.</span><span class="sxs-lookup"><span data-stu-id="3c939-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="3c939-172">Cuando una aplicación debe actualizar una instancia que pertenece a una jerarquía de clases, el parámetro `pInst` debe apuntar a la instancia que contiene las propiedades que se van a modificar.</span><span class="sxs-lookup"><span data-stu-id="3c939-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="3c939-173">Es decir, considere una instancia de destino que pertenece a **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="3c939-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="3c939-174">La instancia de **ClassB** se deriva de **ClassA**y **ClassA** define la propiedad **PROPA**.</span><span class="sxs-lookup"><span data-stu-id="3c939-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="3c939-175">Si una aplicación desea hacer un cambio en el valor de **PROPA** en la instancia de **ClassB** , debe establecer `pInst` en esa instancia en lugar de en una instancia de **ClassA**.</span><span class="sxs-lookup"><span data-stu-id="3c939-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="3c939-176">No se permite llamar a `PutInstanceWmi` en una instancia de una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="3c939-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="3c939-177">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="3c939-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="3c939-178">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c939-178">Requirements</span></span>

<span data-ttu-id="3c939-179">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c939-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3c939-180">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="3c939-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3c939-181">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3c939-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3c939-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c939-182">See also</span></span>

- [<span data-ttu-id="3c939-183">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="3c939-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
