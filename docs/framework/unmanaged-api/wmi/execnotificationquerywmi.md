---
title: ExecNotificationQueryWmi (función) (referencia de API no administrada)
description: ExecNotificationQueryWmi (función) ejecuta una consulta para recibir eventos.
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
ms.openlocfilehash: 9cac00ff96d0c7007bdd6135282c3f767217385e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935621"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="75217-103">Función ExecNotificationQueryWmi</span><span class="sxs-lookup"><span data-stu-id="75217-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="75217-104">Ejecuta una consulta para recibir eventos.</span><span class="sxs-lookup"><span data-stu-id="75217-104">Executes a query to receive events.</span></span> <span data-ttu-id="75217-105">La llamada devuelve inmediatamente, y el llamador puede sondear el enumerador devuelto para los eventos cuando llegan.</span><span class="sxs-lookup"><span data-stu-id="75217-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="75217-106">Liberar el enumerador devuelto, cancela la consulta.</span><span class="sxs-lookup"><span data-stu-id="75217-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="75217-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75217-107">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="75217-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75217-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="75217-109">[in] Una cadena con el lenguaje de consulta válido compatible con la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="75217-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="75217-110">Debe ser "WQL", que es el acrónimo de lenguaje de consulta de WMI.</span><span class="sxs-lookup"><span data-stu-id="75217-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="75217-111">[in] El texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="75217-111">[in] The text of the query.</span></span> <span data-ttu-id="75217-112">Este parámetro no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="75217-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="75217-113">[in] Una combinación de los dos indicadores siguientes que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="75217-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="75217-114">Estos valores se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="75217-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="75217-115">Constante</span><span class="sxs-lookup"><span data-stu-id="75217-115">Constant</span></span> | <span data-ttu-id="75217-116">Valor</span><span class="sxs-lookup"><span data-stu-id="75217-116">Value</span></span>  | <span data-ttu-id="75217-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="75217-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="75217-118">0x10</span><span class="sxs-lookup"><span data-stu-id="75217-118">0x10</span></span> | <span data-ttu-id="75217-119">La marca provoca una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="75217-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="75217-120">Si no se establece esta marca, se produce un error en la llamada.</span><span class="sxs-lookup"><span data-stu-id="75217-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="75217-121">Esto es porque se reciben eventos de forma continua, lo que significa que el usuario debe sondear el enumerador devuelto.</span><span class="sxs-lookup"><span data-stu-id="75217-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="75217-122">Esta llamada de bloqueo indefinidamente hace sea imposible.</span><span class="sxs-lookup"><span data-stu-id="75217-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="75217-123">0x20</span><span class="sxs-lookup"><span data-stu-id="75217-123">0x20</span></span> | <span data-ttu-id="75217-124">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="75217-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="75217-125">Normalmente, los enumeradores de sólo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten las llamadas a [clon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="75217-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="75217-126">[in] Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="75217-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="75217-127">En caso contrario, es un puntero a un [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instancia que se puede usar el proveedor que está proporcionando los eventos solicitados.</span><span class="sxs-lookup"><span data-stu-id="75217-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="75217-128">[out] Si se produce ningún error, recibe el puntero en el enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="75217-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="75217-129">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="75217-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="75217-130">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="75217-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="75217-131">[in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="75217-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="75217-132">[in] Un puntero a un [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) objeto que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="75217-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="75217-133">[in] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="75217-133">[in] The user name.</span></span> <span data-ttu-id="75217-134">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="75217-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="75217-135">[in] La contraseña.</span><span class="sxs-lookup"><span data-stu-id="75217-135">[in] The password.</span></span> <span data-ttu-id="75217-136">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="75217-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="75217-137">[in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="75217-137">[in] The domain name of the user.</span></span> <span data-ttu-id="75217-138">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="75217-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="75217-139">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="75217-139">Return value</span></span>

<span data-ttu-id="75217-140">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="75217-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="75217-141">Constante</span><span class="sxs-lookup"><span data-stu-id="75217-141">Constant</span></span>  |<span data-ttu-id="75217-142">Valor</span><span class="sxs-lookup"><span data-stu-id="75217-142">Value</span></span>  |<span data-ttu-id="75217-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="75217-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="75217-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="75217-144">0x80041003</span></span> | <span data-ttu-id="75217-145">El usuario no tiene permiso para ver una o varias de las clases que puede devolver la función.</span><span class="sxs-lookup"><span data-stu-id="75217-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="75217-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="75217-146">0x80041001</span></span> | <span data-ttu-id="75217-147">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="75217-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="75217-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="75217-148">0x80041008</span></span> | <span data-ttu-id="75217-149">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="75217-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="75217-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="75217-150">0x80041010</span></span> | <span data-ttu-id="75217-151">La consulta especifica una clase que no existe.</span><span class="sxs-lookup"><span data-stu-id="75217-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="75217-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="75217-152">0x80042002</span></span> | <span data-ttu-id="75217-153">Se ha solicitado demasiada precisión en la entrega de eventos.</span><span class="sxs-lookup"><span data-stu-id="75217-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="75217-154">Debe especificarse una mayor tolerancia de sondeo.</span><span class="sxs-lookup"><span data-stu-id="75217-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="75217-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="75217-155">0x80042001</span></span> | <span data-ttu-id="75217-156">La consulta solicita más información que puede proporcionar la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="75217-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="75217-157">Esto `HRESULT` se devuelve cuando una consulta de evento da como resultado una solicitud para sondear todos los objetos en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="75217-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="75217-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="75217-158">0x80041017</span></span> | <span data-ttu-id="75217-159">La consulta tuvo un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="75217-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="75217-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="75217-160">0x80041018</span></span> | <span data-ttu-id="75217-161">No se admite el lenguaje de consulta solicitado.</span><span class="sxs-lookup"><span data-stu-id="75217-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="75217-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="75217-162">0x8004106c</span></span> | <span data-ttu-id="75217-163">La consulta es demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="75217-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="75217-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="75217-164">0x80041006</span></span> | <span data-ttu-id="75217-165">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="75217-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="75217-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="75217-166">0x80041033</span></span> | <span data-ttu-id="75217-167">WMI era probablemente detenido y volver a iniciar.</span><span class="sxs-lookup"><span data-stu-id="75217-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="75217-168">Llame a [ConnectServerWmi](connectserverwmi.md) nuevo.</span><span class="sxs-lookup"><span data-stu-id="75217-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="75217-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="75217-169">0x80041015</span></span> | <span data-ttu-id="75217-170">Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="75217-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="75217-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="75217-171">0x80041058</span></span> | <span data-ttu-id="75217-172">No se puede analizar la consulta.</span><span class="sxs-lookup"><span data-stu-id="75217-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="75217-173">0</span><span class="sxs-lookup"><span data-stu-id="75217-173">0</span></span> | <span data-ttu-id="75217-174">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="75217-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="75217-175">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75217-175">Remarks</span></span>

<span data-ttu-id="75217-176">Esta función contiene una llamada a la [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) método.</span><span class="sxs-lookup"><span data-stu-id="75217-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="75217-177">Después de que se devuelva la función, el llamador pasa periódicamente el valor devuelto `ppEnum` de objeto para el [siguiente](next.md) función para ver si los eventos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="75217-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="75217-178">No hay límite al número de `AND` y `OR` palabras clave que se pueden usar en las consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="75217-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="75217-179">Gran número de palabras clave WQL que se usa en una consulta compleja puede hacer que WMI devolver el `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) código de error como un `HRESULT` valor.</span><span class="sxs-lookup"><span data-stu-id="75217-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="75217-180">El límite de palabras clave WQL depende de la complejidad de la consulta es.</span><span class="sxs-lookup"><span data-stu-id="75217-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="75217-181">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="75217-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="75217-182">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75217-182">Requirements</span></span>

<span data-ttu-id="75217-183">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75217-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="75217-184">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="75217-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="75217-185">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="75217-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="75217-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="75217-186">See also</span></span>

- [<span data-ttu-id="75217-187">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="75217-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)