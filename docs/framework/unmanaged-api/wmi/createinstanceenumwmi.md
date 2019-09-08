---
title: Función CreateInstanceEnumWmi (referencia de la API no administrada)
description: La función CreateInstanceEnumWmi devuelve un enumerador que contiene las instancias de una clase especificada que cumplen los criterios de selección.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7709d9c50a494013ece2f91b3acc213278f0e57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798908"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="33df4-103">CreateInstanceEnumWmi función)</span><span class="sxs-lookup"><span data-stu-id="33df4-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="33df4-104">Devuelve un enumerador que devuelve las instancias de una clase especificada que cumpla los criterios de selección especificados.</span><span class="sxs-lookup"><span data-stu-id="33df4-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="33df4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33df4-105">Syntax</span></span>

```cpp
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
);
```

## <a name="parameters"></a><span data-ttu-id="33df4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33df4-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="33df4-107">de Nombre de la clase para la que se desean instancias.</span><span class="sxs-lookup"><span data-stu-id="33df4-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="33df4-108">Este parámetro no puede `null`ser.</span><span class="sxs-lookup"><span data-stu-id="33df4-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="33df4-109">de Combinación de marcas que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="33df4-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="33df4-110">Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="33df4-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="33df4-111">Constante</span><span class="sxs-lookup"><span data-stu-id="33df4-111">Constant</span></span>  |<span data-ttu-id="33df4-112">Valor</span><span class="sxs-lookup"><span data-stu-id="33df4-112">Value</span></span>  |<span data-ttu-id="33df4-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33df4-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="33df4-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="33df4-114">0x20000</span></span> | <span data-ttu-id="33df4-115">Si se establece, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="33df4-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="33df4-116">Si no se establece, la función solo recupera los calificadores almacenados en el espacio de nombres inmediato.</span><span class="sxs-lookup"><span data-stu-id="33df4-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="33df4-117">0</span><span class="sxs-lookup"><span data-stu-id="33df4-117">0</span></span> | <span data-ttu-id="33df4-118">La enumeración incluye esta y todas las subclases de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="33df4-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="33df4-119">1</span><span class="sxs-lookup"><span data-stu-id="33df4-119">1</span></span> | <span data-ttu-id="33df4-120">La enumeración solo incluye instancias puras de esta clase y excluye todas las instancias de subclases que suministran propiedades que no se encuentran en esta clase.</span><span class="sxs-lookup"><span data-stu-id="33df4-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="33df4-121">0x10</span><span class="sxs-lookup"><span data-stu-id="33df4-121">0x10</span></span> | <span data-ttu-id="33df4-122">La marca produce una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="33df4-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="33df4-123">0x20</span><span class="sxs-lookup"><span data-stu-id="33df4-123">0x20</span></span> | <span data-ttu-id="33df4-124">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="33df4-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="33df4-125">Normalmente, los enumeradores de solo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten que las llamadas se [clonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="33df4-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="33df4-126">0</span><span class="sxs-lookup"><span data-stu-id="33df4-126">0</span></span> | <span data-ttu-id="33df4-127">WMI conserva los punteros a objetos en la enumeración hasta que se liberan.</span><span class="sxs-lookup"><span data-stu-id="33df4-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="33df4-128">Las marcas recomendadas `WBEM_FLAG_RETURN_IMMEDIATELY` son `WBEM_FLAG_FORWARD_ONLY` y para obtener el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="33df4-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="33df4-129">de Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="33df4-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="33df4-130">De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las instancias solicitadas.</span><span class="sxs-lookup"><span data-stu-id="33df4-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="33df4-131">enuncia Recibe el puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="33df4-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="33df4-132">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="33df4-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="33df4-133">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="33df4-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="33df4-134">de Un puntero a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="33df4-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="33df4-135">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="33df4-135">[in] The user name.</span></span> <span data-ttu-id="33df4-136">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33df4-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="33df4-137">de La contraseña.</span><span class="sxs-lookup"><span data-stu-id="33df4-137">[in] The password.</span></span> <span data-ttu-id="33df4-138">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33df4-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="33df4-139">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="33df4-139">[in] The domain name of the user.</span></span> <span data-ttu-id="33df4-140">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="33df4-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="33df4-141">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33df4-141">Return value</span></span>

<span data-ttu-id="33df4-142">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="33df4-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="33df4-143">Constante</span><span class="sxs-lookup"><span data-stu-id="33df4-143">Constant</span></span>  |<span data-ttu-id="33df4-144">Valor</span><span class="sxs-lookup"><span data-stu-id="33df4-144">Value</span></span>  |<span data-ttu-id="33df4-145">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33df4-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="33df4-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="33df4-146">0x80041003</span></span> | <span data-ttu-id="33df4-147">El usuario no tiene permiso para ver las instancias de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="33df4-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="33df4-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="33df4-148">0x80041001</span></span> | <span data-ttu-id="33df4-149">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="33df4-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="33df4-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="33df4-150">0x80041010</span></span> | <span data-ttu-id="33df4-151">`strFilter` no existe.</span><span class="sxs-lookup"><span data-stu-id="33df4-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="33df4-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="33df4-152">0x80041008</span></span> | <span data-ttu-id="33df4-153">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="33df4-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="33df4-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="33df4-154">0x80041006</span></span> | <span data-ttu-id="33df4-155">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="33df4-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="33df4-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="33df4-156">0x80041033</span></span> | <span data-ttu-id="33df4-157">Es posible que WMI se haya detenido y reiniciado.</span><span class="sxs-lookup"><span data-stu-id="33df4-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="33df4-158">Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="33df4-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="33df4-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="33df4-159">0x80041015</span></span> | <span data-ttu-id="33df4-160">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="33df4-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="33df4-161">0</span><span class="sxs-lookup"><span data-stu-id="33df4-161">0</span></span> | <span data-ttu-id="33df4-162">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="33df4-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="33df4-163">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33df4-163">Remarks</span></span>

<span data-ttu-id="33df4-164">Esta función contiene una llamada al método [IWbemServices:: CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) .</span><span class="sxs-lookup"><span data-stu-id="33df4-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="33df4-165">Tenga en cuenta que el enumerador devuelto puede tener cero elementos.</span><span class="sxs-lookup"><span data-stu-id="33df4-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="33df4-166">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="33df4-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="33df4-167">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33df4-167">Requirements</span></span>

<span data-ttu-id="33df4-168">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33df4-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="33df4-169">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="33df4-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="33df4-170">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33df4-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="33df4-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="33df4-171">See also</span></span>

- [<span data-ttu-id="33df4-172">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="33df4-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
