---
title: "Función CreateClassEnumWmi (referencia de API no administrada)"
description: "La función CreateClassEnumWmi devuelve un enumerador para todas las clases que cumplen los criterios especificados."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateClassEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateClassEnumWmi
helpviewer_keywords: CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfbfee6f8e98d04a591c58560e6d50044e716a1f
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="756ca-103">CreateClassEnumWmi (función)</span><span class="sxs-lookup"><span data-stu-id="756ca-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="756ca-104">Devuelve un enumerador para todas las clases que cumplen los criterios de selección especificado.</span><span class="sxs-lookup"><span data-stu-id="756ca-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="756ca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="756ca-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="756ca-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="756ca-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="756ca-107">[in] Si no `null` o en blanco, especifica el nombre de una clase principal; el enumerador devuelve solo las subclases de esta clase.</span><span class="sxs-lookup"><span data-stu-id="756ca-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="756ca-108">Si es `null` o en blanco y `lFlags` es WBEM_FLAG_SHALLOW, se devuelve solo clases de nivel superior (clases con ninguna clase de elemento primario).</span><span class="sxs-lookup"><span data-stu-id="756ca-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="756ca-109">Si es `null` o en blanco y `lFlags` es `WBEM_FLAG_DEEP`, devuelve todas las clases del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="756ca-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="756ca-110">[in] Una combinación de indicadores que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="756ca-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="756ca-111">Los valores siguientes se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="756ca-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="756ca-112">Constante</span><span class="sxs-lookup"><span data-stu-id="756ca-112">Constant</span></span>  |<span data-ttu-id="756ca-113">Valor</span><span class="sxs-lookup"><span data-stu-id="756ca-113">Value</span></span>  |<span data-ttu-id="756ca-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="756ca-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="756ca-115">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="756ca-115">0x20000</span></span> | <span data-ttu-id="756ca-116">Si el conjunto, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="756ca-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="756ca-117">Si no recupera de la función de conjunto, solo los calificadores que se almacenan en el espacio de nombres inmediato.</span><span class="sxs-lookup"><span data-stu-id="756ca-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="756ca-118">0</span><span class="sxs-lookup"><span data-stu-id="756ca-118">0</span></span> | <span data-ttu-id="756ca-119">La enumeración incluye todas las subclases de la jerarquía, pero no de esta clase.</span><span class="sxs-lookup"><span data-stu-id="756ca-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="756ca-120">1</span><span class="sxs-lookup"><span data-stu-id="756ca-120">1</span></span> | <span data-ttu-id="756ca-121">La enumeración incluye solo las instancias de esta clase puras y excluye todas las instancias de las subclases que proporcionan las propiedades que no se encuentran en esta clase.</span><span class="sxs-lookup"><span data-stu-id="756ca-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="756ca-122">0 x 10</span><span class="sxs-lookup"><span data-stu-id="756ca-122">0x10</span></span> | <span data-ttu-id="756ca-123">La marca hace una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="756ca-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="756ca-124">0 x 20</span><span class="sxs-lookup"><span data-stu-id="756ca-124">0x20</span></span> | <span data-ttu-id="756ca-125">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="756ca-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="756ca-126">Normalmente, los enumeradores de sólo avance son más rápidos y utilizan menos memoria que los enumeradores convencionales, pero no permiten las llamadas a [clon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="756ca-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="756ca-127">0</span><span class="sxs-lookup"><span data-stu-id="756ca-127">0</span></span> | <span data-ttu-id="756ca-128">WMI conserva punteros a objetos en el enumration hasta que se publican.</span><span class="sxs-lookup"><span data-stu-id="756ca-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="756ca-129">Las marcas recomendadas son `WBEM_FLAG_RETURN_IMMEDIATELY` y `WBEM_FLAG_FORWARD_ONLY` para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="756ca-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="756ca-130">[in] Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="756ca-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="756ca-131">En caso contrario, es un puntero a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instancia que se puede usar el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="756ca-131">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="756ca-132">[out] Recibe el puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="756ca-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="756ca-133">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="756ca-133">[in] The authorization level.</span></span>

<span data-ttu-id="756ca-134">`impLevel`[in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="756ca-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="756ca-135">[in] Un puntero a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objeto que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="756ca-135">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="756ca-136">[in] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="756ca-136">[in] The user name.</span></span> <span data-ttu-id="756ca-137">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="756ca-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="756ca-138">[in] La contraseña.</span><span class="sxs-lookup"><span data-stu-id="756ca-138">[in] The password.</span></span> <span data-ttu-id="756ca-139">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="756ca-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="756ca-140">[in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="756ca-140">[in] The domain name of the user.</span></span> <span data-ttu-id="756ca-141">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="756ca-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="756ca-142">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="756ca-142">Return value</span></span>

<span data-ttu-id="756ca-143">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="756ca-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="756ca-144">Constante</span><span class="sxs-lookup"><span data-stu-id="756ca-144">Constant</span></span>  |<span data-ttu-id="756ca-145">Valor</span><span class="sxs-lookup"><span data-stu-id="756ca-145">Value</span></span>  |<span data-ttu-id="756ca-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="756ca-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="756ca-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="756ca-147">0x80041003</span></span> | <span data-ttu-id="756ca-148">El usuario no tiene permiso para ver una o varias de las clases que puede devolver la función.</span><span class="sxs-lookup"><span data-stu-id="756ca-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="756ca-149">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="756ca-149">0x80041001</span></span> | <span data-ttu-id="756ca-150">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="756ca-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="756ca-151">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="756ca-151">0x80041010</span></span> | <span data-ttu-id="756ca-152">`strSuperClass` no existe.</span><span class="sxs-lookup"><span data-stu-id="756ca-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="756ca-153">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="756ca-153">0x80041008</span></span> | <span data-ttu-id="756ca-154">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="756ca-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="756ca-155">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="756ca-155">0x80041006</span></span> | <span data-ttu-id="756ca-156">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="756ca-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="756ca-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="756ca-157">0x80041033</span></span> | <span data-ttu-id="756ca-158">WMI se ha detenido probablemente y reiniciar.</span><span class="sxs-lookup"><span data-stu-id="756ca-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="756ca-159">Llame a [ConnectServerWmi](connectserverwmi.md) nuevo.</span><span class="sxs-lookup"><span data-stu-id="756ca-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="756ca-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="756ca-160">0x80041015</span></span> | <span data-ttu-id="756ca-161">Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="756ca-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="756ca-162">0</span><span class="sxs-lookup"><span data-stu-id="756ca-162">0</span></span> | <span data-ttu-id="756ca-163">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="756ca-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="756ca-164">Comentarios</span><span class="sxs-lookup"><span data-stu-id="756ca-164">Remarks</span></span>

<span data-ttu-id="756ca-165">Esta función contiene una llamada a la [CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="756ca-165">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="756ca-166">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="756ca-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="756ca-167">Requisitos</span><span class="sxs-lookup"><span data-stu-id="756ca-167">Requirements</span></span>  
 <span data-ttu-id="756ca-168">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="756ca-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="756ca-169">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="756ca-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="756ca-170">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="756ca-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756ca-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="756ca-171">See also</span></span>  
[<span data-ttu-id="756ca-172">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="756ca-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
