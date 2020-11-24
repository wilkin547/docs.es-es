---
title: Función GetNames (referencia de la API no administrada)
description: La función GetNames recupera los nombres de las propiedades de un objeto.
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
ms.openlocfilehash: fd889158e61b86f42d88bcf86eda7d816277e6ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687663"
---
# <a name="getnames-function"></a><span data-ttu-id="7a2ca-103">Función GetNames</span><span class="sxs-lookup"><span data-stu-id="7a2ca-103">GetNames function</span></span>

<span data-ttu-id="7a2ca-104">Recupera un subconjunto o todos los nombres de las propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7a2ca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a2ca-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a><span data-ttu-id="7a2ca-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a2ca-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7a2ca-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7a2ca-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="7a2ca-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="7a2ca-109">de Un puntero a un válido `LPCWSTR` que especifica un nombre de calificador que funciona como parte de un filtro.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="7a2ca-110">Para más información, vea la sección [Comentarios](#remarks).</span><span class="sxs-lookup"><span data-stu-id="7a2ca-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="7a2ca-111">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="7a2ca-112">de Combinación de campos de bits.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="7a2ca-113">Para más información, vea la sección [Comentarios](#remarks).</span><span class="sxs-lookup"><span data-stu-id="7a2ca-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="7a2ca-114">`pQualifierValue` de Puntero a una estructura válida `VARIANT` inicializada en un valor de filtro.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="7a2ca-115">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="7a2ca-116">enuncia `SAFEARRAY` Estructura que contiene los nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="7a2ca-117">En la entrada, este parámetro siempre debe ser un puntero a `null` .</span><span class="sxs-lookup"><span data-stu-id="7a2ca-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="7a2ca-118">Vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="7a2ca-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7a2ca-119">Return value</span></span>

<span data-ttu-id="7a2ca-120">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="7a2ca-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7a2ca-121">Constante</span><span class="sxs-lookup"><span data-stu-id="7a2ca-121">Constant</span></span>  |<span data-ttu-id="7a2ca-122">Value</span><span class="sxs-lookup"><span data-stu-id="7a2ca-122">Value</span></span>  |<span data-ttu-id="7a2ca-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a2ca-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="7a2ca-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7a2ca-124">0x80041001</span></span> | <span data-ttu-id="7a2ca-125">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7a2ca-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7a2ca-126">0x80041008</span></span> | <span data-ttu-id="7a2ca-127">Uno o más parámetros no son válidos o se ha especificado una combinación incorrecta de marcas y parámetros.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7a2ca-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7a2ca-128">0x80041006</span></span> | <span data-ttu-id="7a2ca-129">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7a2ca-130">0</span><span class="sxs-lookup"><span data-stu-id="7a2ca-130">0</span></span> | <span data-ttu-id="7a2ca-131">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7a2ca-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7a2ca-132">Remarks</span></span>

<span data-ttu-id="7a2ca-133">Esta función contiene una llamada al método [IWbemClassObject:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) .</span><span class="sxs-lookup"><span data-stu-id="7a2ca-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="7a2ca-134">El nombre devuelto se controla mediante una combinación de marcas y parámetros.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="7a2ca-135">Por ejemplo, la función puede devolver los nombres de todas las propiedades o solo los nombres de las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="7a2ca-136">El filtro principal se especifica en el `lFlags` parámetro y los demás parámetros varían en función de él.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="7a2ca-137">Los valores de marca de `lFlags` son campos de bits</span><span class="sxs-lookup"><span data-stu-id="7a2ca-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="7a2ca-138">Las marcas que se pueden pasar como `lEnumFlags` argumento son campos de bits que se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="7a2ca-139">Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="7a2ca-140">Sin embargo, las marcas del mismo grupo se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="7a2ca-141">Marcas de grupo 1</span><span class="sxs-lookup"><span data-stu-id="7a2ca-141">Group 1 flags</span></span> |<span data-ttu-id="7a2ca-142">Value</span><span class="sxs-lookup"><span data-stu-id="7a2ca-142">Value</span></span>  |<span data-ttu-id="7a2ca-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a2ca-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="7a2ca-144">0</span><span class="sxs-lookup"><span data-stu-id="7a2ca-144">0</span></span> | <span data-ttu-id="7a2ca-145">Devuelve todos los nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-145">Return all property names.</span></span> <span data-ttu-id="7a2ca-146">`strQualifierName` y `pQualifierVal` no se utilizan.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="7a2ca-147">1</span><span class="sxs-lookup"><span data-stu-id="7a2ca-147">1</span></span> | <span data-ttu-id="7a2ca-148">Solo devuelve las propiedades que tienen un calificador del nombre especificado por el `strQualifierName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7a2ca-149">Si se usa esta marca, debe especificar `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="7a2ca-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="7a2ca-150">2</span><span class="sxs-lookup"><span data-stu-id="7a2ca-150">2</span></span> |  <span data-ttu-id="7a2ca-151">Solo devuelve las propiedades que no tienen un calificador del nombre especificado por el `strQualifierName` parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7a2ca-152">Si se usa esta marca, debe especificar `strQualifierName` .</span><span class="sxs-lookup"><span data-stu-id="7a2ca-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="7a2ca-153">3</span><span class="sxs-lookup"><span data-stu-id="7a2ca-153">3</span></span> | <span data-ttu-id="7a2ca-154">Solo devuelve las propiedades que tienen un calificador del nombre especificado por el `wszQualifierName` parámetro y que también tienen un valor idéntico al especificado por la `pQualifierVal` estructura.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="7a2ca-155">Si se usa esta marca, debe especificar tanto un `wszQualifierName` como un `pQualifierValue` .</span><span class="sxs-lookup"><span data-stu-id="7a2ca-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="7a2ca-156">Marcas de grupo 2</span><span class="sxs-lookup"><span data-stu-id="7a2ca-156">Group 2 flags</span></span> |<span data-ttu-id="7a2ca-157">Value</span><span class="sxs-lookup"><span data-stu-id="7a2ca-157">Value</span></span>  |<span data-ttu-id="7a2ca-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a2ca-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="7a2ca-159">0x4</span><span class="sxs-lookup"><span data-stu-id="7a2ca-159">0x4</span></span> | <span data-ttu-id="7a2ca-160">Devuelve solo los nombres de las propiedades que definen las claves.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="7a2ca-161">0x8</span><span class="sxs-lookup"><span data-stu-id="7a2ca-161">0x8</span></span> | <span data-ttu-id="7a2ca-162">Devuelve solo los nombres de propiedad que son referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="7a2ca-163">Marcas de grupo 3</span><span class="sxs-lookup"><span data-stu-id="7a2ca-163">Group 3 flags</span></span> |<span data-ttu-id="7a2ca-164">Value</span><span class="sxs-lookup"><span data-stu-id="7a2ca-164">Value</span></span>  |<span data-ttu-id="7a2ca-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a2ca-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7a2ca-166">0x10</span><span class="sxs-lookup"><span data-stu-id="7a2ca-166">0x10</span></span> | <span data-ttu-id="7a2ca-167">Devuelva solo los nombres de propiedad que pertenezcan a la clase más derivada.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="7a2ca-168">Excluya las propiedades de las clases primarias.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7a2ca-169">0x20</span><span class="sxs-lookup"><span data-stu-id="7a2ca-169">0x20</span></span> | <span data-ttu-id="7a2ca-170">Solo se devuelven los nombres de propiedad que pertenezcan a las clases primarias.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="7a2ca-171">0x30</span><span class="sxs-lookup"><span data-stu-id="7a2ca-171">0x30</span></span> | <span data-ttu-id="7a2ca-172">Devuelve solo los nombres de las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="7a2ca-173">0x40</span><span class="sxs-lookup"><span data-stu-id="7a2ca-173">0x40</span></span> | <span data-ttu-id="7a2ca-174">Devuelve solo los nombres de las propiedades que no son del sistema.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="7a2ca-175">La función siempre asigna un nuevo `SAFEARRAY` si devuelve `WBEM_S_NO_ERROR` y `pstrNames` siempre se establece para que apunte a él.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="7a2ca-176">La matriz devuelta puede tener 0 elementos si ninguna propiedad coincide con los filtros especificados.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="7a2ca-177">Si la función devuelve un valor distinto de `WBM_S_NO_ERROR` , `SAFEARRAY` no se devuelve una nueva estructura.</span><span class="sxs-lookup"><span data-stu-id="7a2ca-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a2ca-178">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a2ca-178">Requirements</span></span>  

 <span data-ttu-id="7a2ca-179">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a2ca-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a2ca-180">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="7a2ca-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7a2ca-181">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7a2ca-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2ca-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a2ca-182">See also</span></span>

- [<span data-ttu-id="7a2ca-183">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="7a2ca-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
