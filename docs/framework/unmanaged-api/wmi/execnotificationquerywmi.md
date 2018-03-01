---
title: "Función ExecNotificationQueryWmi (referencia de API no administrada)"
description: "La función ExecNotificationQueryWmi ejecuta una consulta para recibir eventos."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6dd0926d2262f8d0aa125b86755017a65a95a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="b1d9a-103">ExecNotificationQueryWmi (función)</span><span class="sxs-lookup"><span data-stu-id="b1d9a-103">ExecNotificationQueryWmi function</span></span>
<span data-ttu-id="b1d9a-104">Ejecuta una consulta para recibir eventos.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-104">Executes a query to receive events.</span></span> <span data-ttu-id="b1d9a-105">La llamada devuelve inmediatamente, y el llamador puede sondear el enumerador devuelto para los eventos que llegan.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="b1d9a-106">Liberar el enumerador devuelto, cancela la consulta.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-106">Releasing the returned enumerator cancels the query.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b1d9a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1d9a-107">Syntax</span></span>  
  
```  
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
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

## <a name="parameters"></a><span data-ttu-id="b1d9a-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1d9a-108">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="b1d9a-109">[in] Una cadena con el lenguaje de consulta válida compatible con la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="b1d9a-110">Debe ser "WQL", que es el acrónimo de lenguaje de consulta de WMI.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="b1d9a-111">[in] El texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-111">[in] The text of the query.</span></span> <span data-ttu-id="b1d9a-112">Este parámetro no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-112">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="b1d9a-113">[in] Una combinación de los dos indicadores siguientes que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="b1d9a-114">Estos valores se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> 

| <span data-ttu-id="b1d9a-115">Constante</span><span class="sxs-lookup"><span data-stu-id="b1d9a-115">Constant</span></span> | <span data-ttu-id="b1d9a-116">Valor</span><span class="sxs-lookup"><span data-stu-id="b1d9a-116">Value</span></span>  | <span data-ttu-id="b1d9a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1d9a-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="b1d9a-118">0 x 10</span><span class="sxs-lookup"><span data-stu-id="b1d9a-118">0x10</span></span> | <span data-ttu-id="b1d9a-119">La marca hace una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="b1d9a-120">Si no se establece esta marca, se produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="b1d9a-121">Esto es porque los eventos se reciben de forma continua, lo que significa que el usuario debe sondear el enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="b1d9a-122">Esta llamada de bloqueo indefinidamente hace sea imposible.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="b1d9a-123">0 x 20</span><span class="sxs-lookup"><span data-stu-id="b1d9a-123">0x20</span></span> | <span data-ttu-id="b1d9a-124">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="b1d9a-125">Normalmente, los enumeradores de sólo avance son más rápidos y utilizan menos memoria que los enumeradores convencionales, pero no permiten las llamadas a [clon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="b1d9a-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`  
<span data-ttu-id="b1d9a-126">[in] Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="b1d9a-127">En caso contrario, es un puntero a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instancia que se puede usar el proveedor que está proporcionando los eventos solicitados.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-127">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested events.</span></span> 

`ppEnum`  
<span data-ttu-id="b1d9a-128">[out] Si se produce ningún error, recibe el puntero para el enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="b1d9a-129">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="b1d9a-130">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-130">[in] The authorization level.</span></span>

<span data-ttu-id="b1d9a-131">`impLevel`[in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-131">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="b1d9a-132">[in] Un puntero a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objeto que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-132">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="b1d9a-133">[in] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-133">[in] The user name.</span></span> <span data-ttu-id="b1d9a-134">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="b1d9a-135">[in] La contraseña.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-135">[in] The password.</span></span> <span data-ttu-id="b1d9a-136">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="b1d9a-137">[in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-137">[in] The domain name of the user.</span></span> <span data-ttu-id="b1d9a-138">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="b1d9a-139">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b1d9a-139">Return value</span></span>

<span data-ttu-id="b1d9a-140">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b1d9a-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b1d9a-141">Constante</span><span class="sxs-lookup"><span data-stu-id="b1d9a-141">Constant</span></span>  |<span data-ttu-id="b1d9a-142">Valor</span><span class="sxs-lookup"><span data-stu-id="b1d9a-142">Value</span></span>  |<span data-ttu-id="b1d9a-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1d9a-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="b1d9a-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="b1d9a-144">0x80041003</span></span> | <span data-ttu-id="b1d9a-145">El usuario no tiene permiso para ver una o varias de las clases que puede devolver la función.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="b1d9a-146">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="b1d9a-146">0x80041001</span></span> | <span data-ttu-id="b1d9a-147">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b1d9a-148">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="b1d9a-148">0x80041008</span></span> | <span data-ttu-id="b1d9a-149">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="b1d9a-150">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="b1d9a-150">0x80041010</span></span> | <span data-ttu-id="b1d9a-151">La consulta especifica una clase que no existe.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="b1d9a-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="b1d9a-152">0x80042002</span></span> | <span data-ttu-id="b1d9a-153">Se ha solicitado demasiada precisión en la entrega de eventos.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="b1d9a-154">Debe especificarse una mayor tolerancia de sondeo.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="b1d9a-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="b1d9a-155">0x80042001</span></span> | <span data-ttu-id="b1d9a-156">La consulta requess puede proporcionar más información que la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-156">The query requess more information than Windows Management can provide.</span></span> <span data-ttu-id="b1d9a-157">Esto `HRESULT` se devuelve cuando una consulta de evento da como resultado una solicitud para sondear todos los objetos en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="b1d9a-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="b1d9a-158">0x80041017</span></span> | <span data-ttu-id="b1d9a-159">La consulta tenía un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="b1d9a-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="b1d9a-160">0x80041018</span></span> | <span data-ttu-id="b1d9a-161">No se admite el lenguaje de consulta solicitado.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="b1d9a-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="b1d9a-162">0x8004106c</span></span> | <span data-ttu-id="b1d9a-163">La consulta es demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b1d9a-164">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="b1d9a-164">0x80041006</span></span> | <span data-ttu-id="b1d9a-165">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="b1d9a-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="b1d9a-166">0x80041033</span></span> | <span data-ttu-id="b1d9a-167">WMI se ha detenido probablemente y reiniciar.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="b1d9a-168">Llame a [ConnectServerWmi](connectserverwmi.md) nuevo.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="b1d9a-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="b1d9a-169">0x80041015</span></span> | <span data-ttu-id="b1d9a-170">Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="b1d9a-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="b1d9a-171">0x80041058</span></span> | <span data-ttu-id="b1d9a-172">No se puede analizar la consulta.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b1d9a-173">0</span><span class="sxs-lookup"><span data-stu-id="b1d9a-173">0</span></span> | <span data-ttu-id="b1d9a-174">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-174">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b1d9a-175">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1d9a-175">Remarks</span></span>

<span data-ttu-id="b1d9a-176">Esta función contiene una llamada a la [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b1d9a-177">Una vez que regresa la función y el llamador pasa periódicamente el valor devuelto `ppEnum` el objeto a la [siguiente](next.md) función para ver si los eventos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="b1d9a-178">No hay límite al número de `AND` y `OR` palabras clave que se puede usar en las consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="b1d9a-179">Gran número de palabras clave WQL usadas en una consulta compleja puede hacer WMI devolver el `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) código de error como un `HRESULT` valor.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="b1d9a-180">El límite de palabras clave WQL depende de su complejidad es de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="b1d9a-181">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="b1d9a-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="b1d9a-182">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1d9a-182">Requirements</span></span>  
 <span data-ttu-id="b1d9a-183">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1d9a-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1d9a-184">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b1d9a-184">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b1d9a-185">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b1d9a-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d9a-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1d9a-186">See also</span></span>  
[<span data-ttu-id="b1d9a-187">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b1d9a-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
