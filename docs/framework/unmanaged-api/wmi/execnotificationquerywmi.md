---
title: Función ExecNotificationQueryWmi (referencia de la API no administrada)
description: La función ExecNotificationQueryWmi ejecuta una consulta para recibir eventos.
ms.date: 11/06/2017
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
ms.openlocfilehash: 5cfe54c7c9b7ae707b2d3591afbd830bac171f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798646"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="b2e31-103">Función ExecNotificationQueryWmi</span><span class="sxs-lookup"><span data-stu-id="b2e31-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="b2e31-104">Ejecuta una consulta para recibir eventos.</span><span class="sxs-lookup"><span data-stu-id="b2e31-104">Executes a query to receive events.</span></span> <span data-ttu-id="b2e31-105">La llamada se devuelve inmediatamente y el autor de la llamada puede sondear el enumerador devuelto para los eventos a medida que llegan.</span><span class="sxs-lookup"><span data-stu-id="b2e31-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="b2e31-106">Al liberar el enumerador devuelto se cancela la consulta.</span><span class="sxs-lookup"><span data-stu-id="b2e31-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b2e31-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2e31-107">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="b2e31-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2e31-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="b2e31-109">de Cadena con el lenguaje de consulta válido compatible con la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="b2e31-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="b2e31-110">Debe ser "WQL", el acrónimo de lenguaje de consulta de WMI.</span><span class="sxs-lookup"><span data-stu-id="b2e31-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="b2e31-111">de Texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b2e31-111">[in] The text of the query.</span></span> <span data-ttu-id="b2e31-112">Este parámetro no puede `null`ser.</span><span class="sxs-lookup"><span data-stu-id="b2e31-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="b2e31-113">de Combinación de las dos marcas siguientes que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="b2e31-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="b2e31-114">Estos valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="b2e31-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="b2e31-115">Constante</span><span class="sxs-lookup"><span data-stu-id="b2e31-115">Constant</span></span> | <span data-ttu-id="b2e31-116">Valor</span><span class="sxs-lookup"><span data-stu-id="b2e31-116">Value</span></span>  | <span data-ttu-id="b2e31-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b2e31-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="b2e31-118">0x10</span><span class="sxs-lookup"><span data-stu-id="b2e31-118">0x10</span></span> | <span data-ttu-id="b2e31-119">La marca produce una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="b2e31-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="b2e31-120">Si no se establece esta marca, se produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="b2e31-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="b2e31-121">Esto se debe a que los eventos se reciben continuamente, lo que significa que el usuario debe sondear el enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="b2e31-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="b2e31-122">El bloqueo de esta llamada indefinidamente hace que sea imposible.</span><span class="sxs-lookup"><span data-stu-id="b2e31-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="b2e31-123">0x20</span><span class="sxs-lookup"><span data-stu-id="b2e31-123">0x20</span></span> | <span data-ttu-id="b2e31-124">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="b2e31-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="b2e31-125">Normalmente, los enumeradores de solo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten que las llamadas se [clonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="b2e31-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="b2e31-126">de Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="b2e31-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="b2e31-127">De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona los eventos solicitados.</span><span class="sxs-lookup"><span data-stu-id="b2e31-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="b2e31-128">enuncia Si no se produce ningún error, recibe el puntero al enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b2e31-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="b2e31-129">Vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b2e31-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="b2e31-130">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="b2e31-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="b2e31-131">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="b2e31-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="b2e31-132">de Un puntero a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="b2e31-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="b2e31-133">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="b2e31-133">[in] The user name.</span></span> <span data-ttu-id="b2e31-134">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b2e31-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="b2e31-135">de La contraseña.</span><span class="sxs-lookup"><span data-stu-id="b2e31-135">[in] The password.</span></span> <span data-ttu-id="b2e31-136">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b2e31-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="b2e31-137">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="b2e31-137">[in] The domain name of the user.</span></span> <span data-ttu-id="b2e31-138">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b2e31-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="b2e31-139">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2e31-139">Return value</span></span>

<span data-ttu-id="b2e31-140">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b2e31-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b2e31-141">Constante</span><span class="sxs-lookup"><span data-stu-id="b2e31-141">Constant</span></span>  |<span data-ttu-id="b2e31-142">Valor</span><span class="sxs-lookup"><span data-stu-id="b2e31-142">Value</span></span>  |<span data-ttu-id="b2e31-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b2e31-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="b2e31-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="b2e31-144">0x80041003</span></span> | <span data-ttu-id="b2e31-145">El usuario no tiene permiso para ver una o varias de las clases que la función puede devolver.</span><span class="sxs-lookup"><span data-stu-id="b2e31-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="b2e31-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b2e31-146">0x80041001</span></span> | <span data-ttu-id="b2e31-147">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="b2e31-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b2e31-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b2e31-148">0x80041008</span></span> | <span data-ttu-id="b2e31-149">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="b2e31-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="b2e31-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="b2e31-150">0x80041010</span></span> | <span data-ttu-id="b2e31-151">La consulta especifica una clase que no existe.</span><span class="sxs-lookup"><span data-stu-id="b2e31-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="b2e31-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="b2e31-152">0x80042002</span></span> | <span data-ttu-id="b2e31-153">Se ha solicitado demasiada precisión en la entrega de eventos.</span><span class="sxs-lookup"><span data-stu-id="b2e31-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="b2e31-154">Se debe especificar una tolerancia de sondeo mayor.</span><span class="sxs-lookup"><span data-stu-id="b2e31-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="b2e31-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="b2e31-155">0x80042001</span></span> | <span data-ttu-id="b2e31-156">La consulta solicita más información de la que puede proporcionar la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="b2e31-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="b2e31-157">`HRESULT` Se devuelve cuando una consulta de evento produce una solicitud para sondear todos los objetos de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b2e31-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="b2e31-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="b2e31-158">0x80041017</span></span> | <span data-ttu-id="b2e31-159">La consulta tenía un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="b2e31-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="b2e31-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="b2e31-160">0x80041018</span></span> | <span data-ttu-id="b2e31-161">No se admite el lenguaje de consulta solicitado.</span><span class="sxs-lookup"><span data-stu-id="b2e31-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="b2e31-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="b2e31-162">0x8004106c</span></span> | <span data-ttu-id="b2e31-163">La consulta es demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="b2e31-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b2e31-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b2e31-164">0x80041006</span></span> | <span data-ttu-id="b2e31-165">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b2e31-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="b2e31-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="b2e31-166">0x80041033</span></span> | <span data-ttu-id="b2e31-167">Es posible que WMI se haya detenido y reiniciado.</span><span class="sxs-lookup"><span data-stu-id="b2e31-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="b2e31-168">Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="b2e31-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="b2e31-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="b2e31-169">0x80041015</span></span> | <span data-ttu-id="b2e31-170">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="b2e31-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="b2e31-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="b2e31-171">0x80041058</span></span> | <span data-ttu-id="b2e31-172">No se puede analizar la consulta.</span><span class="sxs-lookup"><span data-stu-id="b2e31-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b2e31-173">0</span><span class="sxs-lookup"><span data-stu-id="b2e31-173">0</span></span> | <span data-ttu-id="b2e31-174">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b2e31-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="b2e31-175">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2e31-175">Remarks</span></span>

<span data-ttu-id="b2e31-176">Esta función contiene una llamada al método [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) .</span><span class="sxs-lookup"><span data-stu-id="b2e31-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="b2e31-177">Una vez que la función devuelve un resultado, el llamador `ppEnum` pasa periódicamente el objeto devuelto a la función [siguiente](next.md) para ver si hay algún evento disponible.</span><span class="sxs-lookup"><span data-stu-id="b2e31-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="b2e31-178">Hay límites en el número de `AND` palabras clave y `OR` que se pueden usar en las consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="b2e31-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="b2e31-179">Un gran número de palabras clave WQL usadas en una consulta compleja puede hacer que WMI `WBEM_E_QUOTA_VIOLATION` devuelva el código de error (o `HRESULT` 0x8004106c) como un valor.</span><span class="sxs-lookup"><span data-stu-id="b2e31-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="b2e31-180">El límite de palabras clave de WQL depende de la complejidad de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b2e31-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="b2e31-181">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="b2e31-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2e31-182">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2e31-182">Requirements</span></span>

<span data-ttu-id="b2e31-183">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2e31-183">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b2e31-184">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b2e31-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="b2e31-185">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b2e31-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b2e31-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2e31-186">See also</span></span>

- [<span data-ttu-id="b2e31-187">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b2e31-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
