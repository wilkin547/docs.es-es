---
title: Función ExecQueryWmi (referencia de la API no administrada)
description: La función ExecQueryWmi ejecuta una consulta para recuperar objetos.
ms.date: 11/06/2017
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8547d306819e85b838f1160d9912dd43e42f2f3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798687"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="7eb05-103">Función ExecQueryWmi</span><span class="sxs-lookup"><span data-stu-id="7eb05-103">ExecQueryWmi function</span></span>

<span data-ttu-id="7eb05-104">Ejecuta una consulta para recuperar objetos.</span><span class="sxs-lookup"><span data-stu-id="7eb05-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7eb05-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7eb05-105">Syntax</span></span>

```cpp
HRESULT ExecQueryWmi (
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

## <a name="parameters"></a><span data-ttu-id="7eb05-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7eb05-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="7eb05-107">de Cadena con el lenguaje de consulta válido compatible con la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="7eb05-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="7eb05-108">Debe ser "WQL", el acrónimo de lenguaje de consulta de WMI.</span><span class="sxs-lookup"><span data-stu-id="7eb05-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="7eb05-109">de Texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="7eb05-109">[in] The text of the query.</span></span> <span data-ttu-id="7eb05-110">Este parámetro no puede `null`ser.</span><span class="sxs-lookup"><span data-stu-id="7eb05-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="7eb05-111">de Combinación de marcas que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="7eb05-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="7eb05-112">Los siguientes valores se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="7eb05-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="7eb05-113">Constante</span><span class="sxs-lookup"><span data-stu-id="7eb05-113">Constant</span></span> | <span data-ttu-id="7eb05-114">Value</span><span class="sxs-lookup"><span data-stu-id="7eb05-114">Value</span></span>  | <span data-ttu-id="7eb05-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7eb05-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="7eb05-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="7eb05-116">0x20000</span></span> | <span data-ttu-id="7eb05-117">Si se establece, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="7eb05-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="7eb05-118">Si no se establece, la función solo recupera los calificadores almacenados en el espacio de nombres inmediato.</span><span class="sxs-lookup"><span data-stu-id="7eb05-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="7eb05-119">0x10</span><span class="sxs-lookup"><span data-stu-id="7eb05-119">0x10</span></span> | <span data-ttu-id="7eb05-120">La marca produce una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="7eb05-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="7eb05-121">0x20</span><span class="sxs-lookup"><span data-stu-id="7eb05-121">0x20</span></span> | <span data-ttu-id="7eb05-122">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="7eb05-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="7eb05-123">Normalmente, los enumeradores de solo avance son más rápidos y usan menos memoria que los enumeradores convencionales, pero no permiten que las llamadas se [clonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="7eb05-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="7eb05-124">0</span><span class="sxs-lookup"><span data-stu-id="7eb05-124">0</span></span> | <span data-ttu-id="7eb05-125">WMI conserva los punteros a objetos en la enumeración hasta que se liberan.</span><span class="sxs-lookup"><span data-stu-id="7eb05-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="7eb05-126">0x100</span><span class="sxs-lookup"><span data-stu-id="7eb05-126">0x100</span></span> | <span data-ttu-id="7eb05-127">Garantiza que los objetos devueltos tienen suficiente información en ellos, de modo que las propiedades del sistema, como **__PATH**, **__RELPATH**y `null` **__SERVER**, no lo son.</span><span class="sxs-lookup"><span data-stu-id="7eb05-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="7eb05-128">2</span><span class="sxs-lookup"><span data-stu-id="7eb05-128">2</span></span> | <span data-ttu-id="7eb05-129">Esta marca se utiliza para la prototipo.</span><span class="sxs-lookup"><span data-stu-id="7eb05-129">This flag is used for prototyping.</span></span> <span data-ttu-id="7eb05-130">No ejecuta la consulta y, en su lugar, devuelve un objeto que es similar a un objeto de resultado típico.</span><span class="sxs-lookup"><span data-stu-id="7eb05-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="7eb05-131">0x200</span><span class="sxs-lookup"><span data-stu-id="7eb05-131">0x200</span></span> | <span data-ttu-id="7eb05-132">Provoca el acceso directo al proveedor para la clase especificada, sin tener en cuenta su clase primaria o cualquier subclase.</span><span class="sxs-lookup"><span data-stu-id="7eb05-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="7eb05-133">Las marcas recomendadas `WBEM_FLAG_RETURN_IMMEDIATELY` son `WBEM_FLAG_FORWARD_ONLY` y para obtener el mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7eb05-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="7eb05-134">de Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="7eb05-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="7eb05-135">De lo contrario, es un puntero a una instancia de [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) que puede ser utilizada por el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="7eb05-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="7eb05-136">enuncia Si no se produce ningún error, recibe el puntero al enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="7eb05-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="7eb05-137">La consulta puede tener un conjunto de resultados con cero instancias.</span><span class="sxs-lookup"><span data-stu-id="7eb05-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="7eb05-138">Vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7eb05-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="7eb05-139">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="7eb05-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="7eb05-140">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="7eb05-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="7eb05-141">de Un puntero a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="7eb05-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="7eb05-142">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="7eb05-142">[in] The user name.</span></span> <span data-ttu-id="7eb05-143">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7eb05-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="7eb05-144">de La contraseña.</span><span class="sxs-lookup"><span data-stu-id="7eb05-144">[in] The password.</span></span> <span data-ttu-id="7eb05-145">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7eb05-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="7eb05-146">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="7eb05-146">[in] The domain name of the user.</span></span> <span data-ttu-id="7eb05-147">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7eb05-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="7eb05-148">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7eb05-148">Return value</span></span>

<span data-ttu-id="7eb05-149">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="7eb05-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7eb05-150">Constante</span><span class="sxs-lookup"><span data-stu-id="7eb05-150">Constant</span></span>  |<span data-ttu-id="7eb05-151">Value</span><span class="sxs-lookup"><span data-stu-id="7eb05-151">Value</span></span>  |<span data-ttu-id="7eb05-152">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7eb05-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="7eb05-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="7eb05-153">0x80041003</span></span> | <span data-ttu-id="7eb05-154">El usuario no tiene permiso para ver una o varias de las clases que la función puede devolver.</span><span class="sxs-lookup"><span data-stu-id="7eb05-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="7eb05-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7eb05-155">0x80041001</span></span> | <span data-ttu-id="7eb05-156">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="7eb05-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7eb05-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7eb05-157">0x80041008</span></span> | <span data-ttu-id="7eb05-158">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="7eb05-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="7eb05-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="7eb05-159">0x80041017</span></span> | <span data-ttu-id="7eb05-160">La consulta tenía un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="7eb05-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="7eb05-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="7eb05-161">0x80041018</span></span> | <span data-ttu-id="7eb05-162">No se admite el lenguaje de consulta solicitado.</span><span class="sxs-lookup"><span data-stu-id="7eb05-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="7eb05-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="7eb05-163">0x8004106c</span></span> | <span data-ttu-id="7eb05-164">La consulta es demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="7eb05-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7eb05-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7eb05-165">0x80041006</span></span> | <span data-ttu-id="7eb05-166">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="7eb05-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="7eb05-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="7eb05-167">0x80041033</span></span> | <span data-ttu-id="7eb05-168">Es posible que WMI se haya detenido y reiniciado.</span><span class="sxs-lookup"><span data-stu-id="7eb05-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="7eb05-169">Vuelva a llamar a [ConnectServerWmi](connectserverwmi.md) .</span><span class="sxs-lookup"><span data-stu-id="7eb05-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="7eb05-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="7eb05-170">0x80041015</span></span> | <span data-ttu-id="7eb05-171">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="7eb05-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="7eb05-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7eb05-172">0x80041002</span></span> | <span data-ttu-id="7eb05-173">La consulta especifica una clase que no existe.</span><span class="sxs-lookup"><span data-stu-id="7eb05-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7eb05-174">0</span><span class="sxs-lookup"><span data-stu-id="7eb05-174">0</span></span> | <span data-ttu-id="7eb05-175">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7eb05-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7eb05-176">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7eb05-176">Remarks</span></span>

<span data-ttu-id="7eb05-177">Esta función contiene una llamada al método [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) .</span><span class="sxs-lookup"><span data-stu-id="7eb05-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="7eb05-178">Esta función procesa la consulta especificada en el `strQuery` parámetro y crea un enumerador a través del que el llamador puede tener acceso a los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="7eb05-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="7eb05-179">El enumerador es un puntero a una interfaz [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) ; los resultados de la consulta son instancias de objetos de clase que se ponen a disposición a través de la interfaz [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="7eb05-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="7eb05-180">Hay límites en el número de `AND` palabras clave y `OR` que se pueden usar en las consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="7eb05-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="7eb05-181">Un gran número de palabras clave WQL usadas en una consulta compleja puede hacer que WMI `WBEM_E_QUOTA_VIOLATION` devuelva el código de error (o `HRESULT` 0x8004106c) como un valor.</span><span class="sxs-lookup"><span data-stu-id="7eb05-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="7eb05-182">El límite de palabras clave de WQL depende de la complejidad de la consulta.</span><span class="sxs-lookup"><span data-stu-id="7eb05-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="7eb05-183">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="7eb05-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="7eb05-184">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7eb05-184">Requirements</span></span>

<span data-ttu-id="7eb05-185">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb05-185">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7eb05-186">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7eb05-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7eb05-187">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb05-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7eb05-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="7eb05-188">See also</span></span>

- [<span data-ttu-id="7eb05-189">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="7eb05-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
