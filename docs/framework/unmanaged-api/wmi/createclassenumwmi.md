---
title: Función CreateClassEnumWmi (referencia de la API no administrada)
description: La función CreateClassEnumWmi devuelve un enumerador para todas las clases que satisfacen los criterios especificados.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b80954e288f6720c75d0af0b8af083fa4856754
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719741"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="416dd-103">Función CreateClassEnumWmi</span><span class="sxs-lookup"><span data-stu-id="416dd-103">CreateClassEnumWmi function</span></span>

<span data-ttu-id="416dd-104">Devuelve un enumerador para todas las clases que cumplan los criterios de selección especificados.</span><span class="sxs-lookup"><span data-stu-id="416dd-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="416dd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="416dd-105">Syntax</span></span>

```cpp
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

## <a name="parameters"></a><span data-ttu-id="416dd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="416dd-106">Parameters</span></span>

`strSuperclass`\
<span data-ttu-id="416dd-107">de Si no es `null` o está en blanco, especifica el nombre de una clase primaria; el enumerador devuelve solo las subclases de esta clase.</span><span class="sxs-lookup"><span data-stu-id="416dd-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="416dd-108">Si está `null` en blanco y `lFlags` está WBEM_FLAG_SHALLOW, solo devuelve clases de nivel superior (clases sin clase primaria).</span><span class="sxs-lookup"><span data-stu-id="416dd-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="416dd-109">Si es `null` o está en blanco y `lFlags` es `WBEM_FLAG_DEEP` , devuelve todas las clases del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="416dd-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`\
<span data-ttu-id="416dd-110">de Combinación de marcas que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="416dd-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="416dd-111">Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="416dd-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="416dd-112">Constante</span><span class="sxs-lookup"><span data-stu-id="416dd-112">Constant</span></span>  |<span data-ttu-id="416dd-113">Value</span><span class="sxs-lookup"><span data-stu-id="416dd-113">Value</span></span>  |<span data-ttu-id="416dd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="416dd-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="416dd-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="416dd-115">0x20000</span></span> | <span data-ttu-id="416dd-116">Si se establece, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="416dd-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="416dd-117">Si no se establece, la función solo recupera los calificadores almacenados en el espacio de nombres inmediato.</span><span class="sxs-lookup"><span data-stu-id="416dd-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="416dd-118">0</span><span class="sxs-lookup"><span data-stu-id="416dd-118">0</span></span> | <span data-ttu-id="416dd-119">La enumeración incluye todas las subclases de la jerarquía, pero no esta clase.</span><span class="sxs-lookup"><span data-stu-id="416dd-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="416dd-120">1</span><span class="sxs-lookup"><span data-stu-id="416dd-120">1</span></span> | <span data-ttu-id="416dd-121">La enumeración solo incluye instancias puras de esta clase y excluye todas las instancias de subclases que suministran propiedades que no se encuentran en esta clase.</span><span class="sxs-lookup"><span data-stu-id="416dd-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="416dd-122">0x10</span><span class="sxs-lookup"><span data-stu-id="416dd-122">0x10</span></span> | <span data-ttu-id="416dd-123">La marca produce una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="416dd-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="416dd-124">0x20</span><span class="sxs-lookup"><span data-stu-id="416dd-124">0x20</span></span> | <span data-ttu-id="416dd-125">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="416dd-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="416dd-126">Normalmente, los enumeradores de solo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten que las llamadas se [clonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="416dd-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="416dd-127">0</span><span class="sxs-lookup"><span data-stu-id="416dd-127">0</span></span> | <span data-ttu-id="416dd-128">WMI conserva los punteros a objetos en la enumeración hasta que se liberan.</span><span class="sxs-lookup"><span data-stu-id="416dd-128">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="416dd-129">Las marcas recomendadas son `WBEM_FLAG_RETURN_IMMEDIATELY` y `WBEM_FLAG_FORWARD_ONLY` para obtener el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="416dd-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="416dd-130">de Normalmente, este valor es `null` .</span><span class="sxs-lookup"><span data-stu-id="416dd-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="416dd-131">De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="416dd-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="416dd-132">enuncia Recibe el puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="416dd-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="416dd-133">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="416dd-133">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="416dd-134">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="416dd-134">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="416dd-135">de Un puntero a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="416dd-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="416dd-136">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="416dd-136">[in] The user name.</span></span> <span data-ttu-id="416dd-137">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="416dd-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="416dd-138">de La contraseña.</span><span class="sxs-lookup"><span data-stu-id="416dd-138">[in] The password.</span></span> <span data-ttu-id="416dd-139">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="416dd-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="416dd-140">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="416dd-140">[in] The domain name of the user.</span></span> <span data-ttu-id="416dd-141">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="416dd-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="416dd-142">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="416dd-142">Return value</span></span>

<span data-ttu-id="416dd-143">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="416dd-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="416dd-144">Constante</span><span class="sxs-lookup"><span data-stu-id="416dd-144">Constant</span></span>  |<span data-ttu-id="416dd-145">Value</span><span class="sxs-lookup"><span data-stu-id="416dd-145">Value</span></span>  |<span data-ttu-id="416dd-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="416dd-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="416dd-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="416dd-147">0x80041003</span></span> | <span data-ttu-id="416dd-148">El usuario no tiene permiso para ver una o varias de las clases que la función puede devolver.</span><span class="sxs-lookup"><span data-stu-id="416dd-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="416dd-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="416dd-149">0x80041001</span></span> | <span data-ttu-id="416dd-150">Error no especificado.</span><span class="sxs-lookup"><span data-stu-id="416dd-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="416dd-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="416dd-151">0x80041010</span></span> | <span data-ttu-id="416dd-152">`strSuperClass` no existe.</span><span class="sxs-lookup"><span data-stu-id="416dd-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="416dd-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="416dd-153">0x80041008</span></span> | <span data-ttu-id="416dd-154">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="416dd-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="416dd-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="416dd-155">0x80041006</span></span> | <span data-ttu-id="416dd-156">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="416dd-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="416dd-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="416dd-157">0x80041033</span></span> | <span data-ttu-id="416dd-158">Es posible que WMI se haya detenido y reiniciado.</span><span class="sxs-lookup"><span data-stu-id="416dd-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="416dd-159">Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="416dd-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="416dd-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="416dd-160">0x80041015</span></span> | <span data-ttu-id="416dd-161">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="416dd-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="416dd-162">0</span><span class="sxs-lookup"><span data-stu-id="416dd-162">0</span></span> | <span data-ttu-id="416dd-163">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="416dd-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="416dd-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="416dd-164">Remarks</span></span>

<span data-ttu-id="416dd-165">Esta función contiene una llamada al método [IWbemServices:: CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) .</span><span class="sxs-lookup"><span data-stu-id="416dd-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="416dd-166">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="416dd-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="416dd-167">Requisitos</span><span class="sxs-lookup"><span data-stu-id="416dd-167">Requirements</span></span>

<span data-ttu-id="416dd-168">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="416dd-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="416dd-169">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="416dd-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="416dd-170">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="416dd-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="416dd-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="416dd-171">See also</span></span>

- [<span data-ttu-id="416dd-172">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="416dd-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
