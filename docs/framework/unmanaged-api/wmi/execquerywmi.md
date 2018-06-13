---
title: Función ExecQueryWmi (referencia de API no administrada)
description: La función ExecQueryWmi ejecuta una consulta para recuperar los objetos.
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
ms.openlocfilehash: b482f2ca2e2d5c06e69945adb71aa6c0f5d26465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462096"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="9e550-103">ExecQueryWmi (función)</span><span class="sxs-lookup"><span data-stu-id="9e550-103">ExecQueryWmi function</span></span>
<span data-ttu-id="9e550-104">Ejecuta una consulta para recuperar los objetos.</span><span class="sxs-lookup"><span data-stu-id="9e550-104">Executes a query to retrieve objects.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9e550-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e550-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="9e550-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9e550-106">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="9e550-107">[in] Una cadena con el lenguaje de consulta válida compatible con la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="9e550-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="9e550-108">Debe ser "WQL", que es el acrónimo de lenguaje de consulta de WMI.</span><span class="sxs-lookup"><span data-stu-id="9e550-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="9e550-109">[in] El texto de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e550-109">[in] The text of the query.</span></span> <span data-ttu-id="9e550-110">Este parámetro no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="9e550-110">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="9e550-111">[in] Una combinación de indicadores que afectan al comportamiento de esta función.</span><span class="sxs-lookup"><span data-stu-id="9e550-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="9e550-112">Los valores siguientes se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="9e550-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

| <span data-ttu-id="9e550-113">Constante</span><span class="sxs-lookup"><span data-stu-id="9e550-113">Constant</span></span> | <span data-ttu-id="9e550-114">Valor</span><span class="sxs-lookup"><span data-stu-id="9e550-114">Value</span></span>  | <span data-ttu-id="9e550-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e550-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="9e550-116">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="9e550-116">0x20000</span></span> | <span data-ttu-id="9e550-117">Si el conjunto, la función recupera los calificadores modificados almacenados en el espacio de nombres localizado de la configuración regional de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="9e550-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="9e550-118">Si no recupera de la función de conjunto, solo los calificadores que se almacenan en el espacio de nombres inmediato.</span><span class="sxs-lookup"><span data-stu-id="9e550-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="9e550-119">0 x 10</span><span class="sxs-lookup"><span data-stu-id="9e550-119">0x10</span></span> | <span data-ttu-id="9e550-120">La marca hace una llamada semisincrónica.</span><span class="sxs-lookup"><span data-stu-id="9e550-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="9e550-121">0 x 20</span><span class="sxs-lookup"><span data-stu-id="9e550-121">0x20</span></span> | <span data-ttu-id="9e550-122">La función devuelve un enumerador de solo avance.</span><span class="sxs-lookup"><span data-stu-id="9e550-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="9e550-123">Normalmente, los enumeradores de sólo avance son más rápidos y utilizan menos memoria que los enumeradores convencionales, pero no permiten las llamadas a [clon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="9e550-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="9e550-124">0</span><span class="sxs-lookup"><span data-stu-id="9e550-124">0</span></span> | <span data-ttu-id="9e550-125">WMI conserva punteros a objetos en el enumration hasta que se publican.</span><span class="sxs-lookup"><span data-stu-id="9e550-125">WMI retains pointers to objects in the enumration until they are released.</span></span> | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="9e550-126">0 x 100</span><span class="sxs-lookup"><span data-stu-id="9e550-126">0x100</span></span> | <span data-ttu-id="9e550-127">Garantiza que cualquier devuelven objetos tienen suficiente información en ellos por lo que ese propiedades del sistema, como **__PATH**, **__RELPATH**, y **__SERVER**, no son `null`.</span><span class="sxs-lookup"><span data-stu-id="9e550-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="9e550-128">2</span><span class="sxs-lookup"><span data-stu-id="9e550-128">2</span></span> | <span data-ttu-id="9e550-129">Esta marca se utiliza para la creación de prototipos.</span><span class="sxs-lookup"><span data-stu-id="9e550-129">This flag is used for prototyping.</span></span> <span data-ttu-id="9e550-130">No se ejecuta la consulta y en su lugar, devuelve un objeto que es similar a un objeto de resultado típico.</span><span class="sxs-lookup"><span data-stu-id="9e550-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="9e550-131">0 x 200</span><span class="sxs-lookup"><span data-stu-id="9e550-131">0x200</span></span> | <span data-ttu-id="9e550-132">Causas acceso dirigen al proveedor para la clase especificada sin tener en cuenta su clase primaria o cualquier subclase.</span><span class="sxs-lookup"><span data-stu-id="9e550-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="9e550-133">Las marcas recomendadas son `WBEM_FLAG_RETURN_IMMEDIATELY` y `WBEM_FLAG_FORWARD_ONLY` para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9e550-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="9e550-134">[in] Normalmente, este valor es `null`.</span><span class="sxs-lookup"><span data-stu-id="9e550-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="9e550-135">En caso contrario, es un puntero a un [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instancia que se puede usar el proveedor que proporciona las clases solicitadas.</span><span class="sxs-lookup"><span data-stu-id="9e550-135">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="9e550-136">[out] Si se produce ningún error, recibe el puntero para el enumerador que permite al llamador recuperar las instancias en el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e550-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="9e550-137">La consulta puede tener un conjunto de resultados con cero instancias.</span><span class="sxs-lookup"><span data-stu-id="9e550-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="9e550-138">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9e550-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="9e550-139">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="9e550-139">[in] The authorization level.</span></span>

<span data-ttu-id="9e550-140">`impLevel` [in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="9e550-140">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="9e550-141">[in] Un puntero a un [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) objeto que representa el espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="9e550-141">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="9e550-142">[in] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="9e550-142">[in] The user name.</span></span> <span data-ttu-id="9e550-143">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9e550-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="9e550-144">[in] La contraseña.</span><span class="sxs-lookup"><span data-stu-id="9e550-144">[in] The password.</span></span> <span data-ttu-id="9e550-145">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9e550-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="9e550-146">[in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="9e550-146">[in] The domain name of the user.</span></span> <span data-ttu-id="9e550-147">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9e550-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="9e550-148">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9e550-148">Return value</span></span>

<span data-ttu-id="9e550-149">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="9e550-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9e550-150">Constante</span><span class="sxs-lookup"><span data-stu-id="9e550-150">Constant</span></span>  |<span data-ttu-id="9e550-151">Valor</span><span class="sxs-lookup"><span data-stu-id="9e550-151">Value</span></span>  |<span data-ttu-id="9e550-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e550-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="9e550-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="9e550-153">0x80041003</span></span> | <span data-ttu-id="9e550-154">El usuario no tiene permiso para ver una o varias de las clases que puede devolver la función.</span><span class="sxs-lookup"><span data-stu-id="9e550-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="9e550-155">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="9e550-155">0x80041001</span></span> | <span data-ttu-id="9e550-156">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="9e550-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9e550-157">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="9e550-157">0x80041008</span></span> | <span data-ttu-id="9e550-158">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="9e550-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="9e550-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="9e550-159">0x80041017</span></span> | <span data-ttu-id="9e550-160">La consulta tenía un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="9e550-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="9e550-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="9e550-161">0x80041018</span></span> | <span data-ttu-id="9e550-162">No se admite el lenguaje de consulta solicitado.</span><span class="sxs-lookup"><span data-stu-id="9e550-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="9e550-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="9e550-163">0x8004106c</span></span> | <span data-ttu-id="9e550-164">La consulta es demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="9e550-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9e550-165">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="9e550-165">0x80041006</span></span> | <span data-ttu-id="9e550-166">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="9e550-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="9e550-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="9e550-167">0x80041033</span></span> | <span data-ttu-id="9e550-168">WMI se ha detenido probablemente y reiniciar.</span><span class="sxs-lookup"><span data-stu-id="9e550-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="9e550-169">Llame a [ConnectServerWmi](connectserverwmi.md) nuevo.</span><span class="sxs-lookup"><span data-stu-id="9e550-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="9e550-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="9e550-170">0x80041015</span></span> | <span data-ttu-id="9e550-171">Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="9e550-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="9e550-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="9e550-172">0x80041002</span></span> | <span data-ttu-id="9e550-173">La consulta especifica una clase que no existe.</span><span class="sxs-lookup"><span data-stu-id="9e550-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9e550-174">0</span><span class="sxs-lookup"><span data-stu-id="9e550-174">0</span></span> | <span data-ttu-id="9e550-175">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="9e550-175">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9e550-176">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9e550-176">Remarks</span></span>

<span data-ttu-id="9e550-177">Esta función contiene una llamada a la [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="9e550-177">This function wraps a call to the [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="9e550-178">Esta función procesa la consulta especificada en el `strQuery` parámetro y crea un enumerador a través del cual el autor de llamada puede tener acceso a los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e550-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="9e550-179">El enumerador es un puntero a un [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interfaz; la consulta de resultados son instancias de objetos de clase disponibles a través de la [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interfaz.</span><span class="sxs-lookup"><span data-stu-id="9e550-179">The enumerator is a pointer to an [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interface; the query results are instances of class objects made available through the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interface.</span></span>

<span data-ttu-id="9e550-180">No hay límite al número de `AND` y `OR` palabras clave que se puede usar en las consultas WQL.</span><span class="sxs-lookup"><span data-stu-id="9e550-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="9e550-181">Gran número de palabras clave WQL usadas en una consulta compleja puede hacer WMI devolver el `WBEM_E_QUOTA_VIOLATION` (o 0x8004106c) código de error como un `HRESULT` valor.</span><span class="sxs-lookup"><span data-stu-id="9e550-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="9e550-182">El límite de palabras clave WQL depende de su complejidad es de la consulta.</span><span class="sxs-lookup"><span data-stu-id="9e550-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="9e550-183">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="9e550-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="9e550-184">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e550-184">Requirements</span></span>  
 <span data-ttu-id="9e550-185">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e550-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e550-186">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9e550-186">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9e550-187">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9e550-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e550-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e550-188">See also</span></span>  
[<span data-ttu-id="9e550-189">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="9e550-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
