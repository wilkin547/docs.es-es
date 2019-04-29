---
title: GetNames (función) (referencia de API no administrada)
description: La función de GetNames recupera los nombres de las propiedades de un objeto.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f664edf29e5d2f9ec4e523aa7f7b204cf999e01b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61724088"
---
# <a name="getnames-function"></a><span data-ttu-id="36326-103">Función GetNames</span><span class="sxs-lookup"><span data-stu-id="36326-103">GetNames function</span></span>
<span data-ttu-id="36326-104">Recupera un subconjunto o todos los nombres de las propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="36326-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="36326-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36326-105">Syntax</span></span>  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="36326-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36326-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="36326-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="36326-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="36326-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="36326-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="36326-109">[in] Un puntero a una `LPCWSTR` que especifica un nombre de calificador que opera como parte de un filtro.</span><span class="sxs-lookup"><span data-stu-id="36326-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="36326-110">Para obtener más información, consulte el [comentarios](#remarks) sección.</span><span class="sxs-lookup"><span data-stu-id="36326-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="36326-111">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="36326-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="36326-112">[in] Una combinación de campos de bits.</span><span class="sxs-lookup"><span data-stu-id="36326-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="36326-113">Para obtener más información, consulte el [comentarios](#remarks) sección.</span><span class="sxs-lookup"><span data-stu-id="36326-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="36326-114">[in] Un puntero a una `VARIANT` estructura inicializada con un valor de filtro.</span><span class="sxs-lookup"><span data-stu-id="36326-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="36326-115">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="36326-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="36326-116">[out] Un `SAFEARRAY` estructura que contiene los nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="36326-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="36326-117">En la entrada, este parámetro siempre debe ser un puntero a `null`.</span><span class="sxs-lookup"><span data-stu-id="36326-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="36326-118">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="36326-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="36326-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36326-119">Return value</span></span>

<span data-ttu-id="36326-120">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="36326-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="36326-121">Constante</span><span class="sxs-lookup"><span data-stu-id="36326-121">Constant</span></span>  |<span data-ttu-id="36326-122">Valor</span><span class="sxs-lookup"><span data-stu-id="36326-122">Value</span></span>  |<span data-ttu-id="36326-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="36326-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="36326-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="36326-124">0x80041001</span></span> | <span data-ttu-id="36326-125">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="36326-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="36326-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="36326-126">0x80041008</span></span> | <span data-ttu-id="36326-127">Uno o más parámetros no son válidos o se especificó una combinación de marcas y los parámetros incorrecta.</span><span class="sxs-lookup"><span data-stu-id="36326-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="36326-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="36326-128">0x80041006</span></span> | <span data-ttu-id="36326-129">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="36326-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="36326-130">0</span><span class="sxs-lookup"><span data-stu-id="36326-130">0</span></span> | <span data-ttu-id="36326-131">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="36326-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="36326-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36326-132">Remarks</span></span>

<span data-ttu-id="36326-133">Esta función contiene una llamada a la [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) método.</span><span class="sxs-lookup"><span data-stu-id="36326-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="36326-134">Con el nombre devuelto se controla mediante una combinación de marcas y los parámetros.</span><span class="sxs-lookup"><span data-stu-id="36326-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="36326-135">Por ejemplo, la función puede devolver los nombres de todas las propiedades o solo los nombres de las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="36326-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="36326-136">El filtro primario se especifica en el `lFlags` parámetro y los demás parámetros varían en función de lo.</span><span class="sxs-lookup"><span data-stu-id="36326-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="36326-137">Valores de la marca de `lFlags` son campos de bits</span><span class="sxs-lookup"><span data-stu-id="36326-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="36326-138">Las marcas que se pueden pasar como el `lEnumFlags` argumento son campos de bits que se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="36326-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="36326-139">Puede combinar una marca de todos los grupos con cualquier marca de cualquier otro grupo.</span><span class="sxs-lookup"><span data-stu-id="36326-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="36326-140">Sin embargo, las marcas del mismo grupo se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="36326-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="36326-141">Marcas de grupo 1</span><span class="sxs-lookup"><span data-stu-id="36326-141">Group 1 flags</span></span> |<span data-ttu-id="36326-142">Valor</span><span class="sxs-lookup"><span data-stu-id="36326-142">Value</span></span>  |<span data-ttu-id="36326-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="36326-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="36326-144">0</span><span class="sxs-lookup"><span data-stu-id="36326-144">0</span></span> | <span data-ttu-id="36326-145">Devolver todos los nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="36326-145">Return all property names.</span></span> <span data-ttu-id="36326-146">`strQualifierName` y `pQualifierVal` no se usan.</span><span class="sxs-lookup"><span data-stu-id="36326-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="36326-147">1</span><span class="sxs-lookup"><span data-stu-id="36326-147">1</span></span> | <span data-ttu-id="36326-148">Devolver solo las propiedades que tienen un calificador del nombre especificado por el `strQualifierName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="36326-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="36326-149">Si se usa esta marca, debe especificar `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="36326-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="36326-150">2</span><span class="sxs-lookup"><span data-stu-id="36326-150">2</span></span> |  <span data-ttu-id="36326-151">Devolver solo las propiedades que no tienen un calificador del nombre especificado por el `strQualifierName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="36326-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="36326-152">Si se usa esta marca, debe especificar `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="36326-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="36326-153">3</span><span class="sxs-lookup"><span data-stu-id="36326-153">3</span></span> | <span data-ttu-id="36326-154">Devolver solo las propiedades que tienen un calificador del nombre especificado por el `wszQualifierName` parámetro y también tiene un valor idéntico al especificado por el `pQualifierVal` estructura.</span><span class="sxs-lookup"><span data-stu-id="36326-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="36326-155">Si se usa esta marca, debe especificar tanto un `wszQualifierName` y un `pQualifierValue`.</span><span class="sxs-lookup"><span data-stu-id="36326-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="36326-156">Marcas de grupo 2</span><span class="sxs-lookup"><span data-stu-id="36326-156">Group 2 flags</span></span> |<span data-ttu-id="36326-157">Valor</span><span class="sxs-lookup"><span data-stu-id="36326-157">Value</span></span>  |<span data-ttu-id="36326-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="36326-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="36326-159">0x4</span><span class="sxs-lookup"><span data-stu-id="36326-159">0x4</span></span> | <span data-ttu-id="36326-160">Devolver solo los nombres de propiedades que definen las claves.</span><span class="sxs-lookup"><span data-stu-id="36326-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="36326-161">0x8</span><span class="sxs-lookup"><span data-stu-id="36326-161">0x8</span></span> | <span data-ttu-id="36326-162">Valor devuelto solo nombres de propiedad que son referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="36326-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="36326-163">Marcas de grupo 3</span><span class="sxs-lookup"><span data-stu-id="36326-163">Group 3 flags</span></span> |<span data-ttu-id="36326-164">Valor</span><span class="sxs-lookup"><span data-stu-id="36326-164">Value</span></span>  |<span data-ttu-id="36326-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="36326-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="36326-166">0x10</span><span class="sxs-lookup"><span data-stu-id="36326-166">0x10</span></span> | <span data-ttu-id="36326-167">Devolver solo los nombres de propiedad que pertenecen a la clase más derivada.</span><span class="sxs-lookup"><span data-stu-id="36326-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="36326-168">Excluir propiedades de las clases principales.</span><span class="sxs-lookup"><span data-stu-id="36326-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="36326-169">0x20</span><span class="sxs-lookup"><span data-stu-id="36326-169">0x20</span></span> | <span data-ttu-id="36326-170">Devolver solo los nombres de propiedad que pertenecen a las clases principales.</span><span class="sxs-lookup"><span data-stu-id="36326-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="36326-171">0x30</span><span class="sxs-lookup"><span data-stu-id="36326-171">0x30</span></span> | <span data-ttu-id="36326-172">Devolver solo los nombres de las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="36326-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="36326-173">0x40</span><span class="sxs-lookup"><span data-stu-id="36326-173">0x40</span></span> | <span data-ttu-id="36326-174">Devolver solo los nombres de propiedades que no son de sistema.</span><span class="sxs-lookup"><span data-stu-id="36326-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="36326-175">La función siempre asigna un nuevo `SAFEARRAY` si devuelve `WBEM_S_NO_ERROR`, y `pstrNames` siempre se establece para que apunte a él.</span><span class="sxs-lookup"><span data-stu-id="36326-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="36326-176">La matriz devuelta puede tener 0 elementos si no hay propiedades coinciden con los filtros especificados.</span><span class="sxs-lookup"><span data-stu-id="36326-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="36326-177">Si la función devuelve un valor distinto de `WBM_S_NO_ERROR`, un nuevo `SAFEARRAY` estructura no se devuelve.</span><span class="sxs-lookup"><span data-stu-id="36326-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="36326-178">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36326-178">Requirements</span></span>  
 <span data-ttu-id="36326-179">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36326-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36326-180">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="36326-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="36326-181">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="36326-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36326-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="36326-182">See also</span></span>

- [<span data-ttu-id="36326-183">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="36326-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
