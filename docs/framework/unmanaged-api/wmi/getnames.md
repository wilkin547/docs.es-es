---
title: Función GetNames (Referencia de API no administrada)
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
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174958"
---
# <a name="getnames-function"></a><span data-ttu-id="b536e-103">Función GetNames</span><span class="sxs-lookup"><span data-stu-id="b536e-103">GetNames function</span></span>
<span data-ttu-id="b536e-104">Recupera un subconjunto o todos los nombres de las propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="b536e-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b536e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b536e-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="b536e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b536e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b536e-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b536e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b536e-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="b536e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="b536e-109">[en] Puntero a un `LPCWSTR` válido que especifica un nombre de calificador que funciona como parte de un filtro.</span><span class="sxs-lookup"><span data-stu-id="b536e-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="b536e-110">Para obtener más información, consulte la sección [Comentarios.](#remarks)</span><span class="sxs-lookup"><span data-stu-id="b536e-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="b536e-111">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b536e-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="b536e-112">[en] Una combinación de campos de bits.</span><span class="sxs-lookup"><span data-stu-id="b536e-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="b536e-113">Para obtener más información, consulte la sección [Comentarios.](#remarks)</span><span class="sxs-lookup"><span data-stu-id="b536e-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="b536e-114">`pQualifierValue`[en] Puntero a una `VARIANT` estructura válida inicializada en un valor de filtro.</span><span class="sxs-lookup"><span data-stu-id="b536e-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="b536e-115">Este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b536e-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="b536e-116">[fuera] Estructura `SAFEARRAY` que contiene nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b536e-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="b536e-117">En la entrada, este parámetro `null`siempre debe ser un puntero a .</span><span class="sxs-lookup"><span data-stu-id="b536e-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="b536e-118">Consulte la sección [Comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b536e-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="b536e-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b536e-119">Return value</span></span>

<span data-ttu-id="b536e-120">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b536e-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b536e-121">Constante</span><span class="sxs-lookup"><span data-stu-id="b536e-121">Constant</span></span>  |<span data-ttu-id="b536e-122">Value</span><span class="sxs-lookup"><span data-stu-id="b536e-122">Value</span></span>  |<span data-ttu-id="b536e-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b536e-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b536e-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b536e-124">0x80041001</span></span> | <span data-ttu-id="b536e-125">Ha habido un fracaso general.</span><span class="sxs-lookup"><span data-stu-id="b536e-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b536e-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b536e-126">0x80041008</span></span> | <span data-ttu-id="b536e-127">Uno o más parámetros no son válidos o se especificó una combinación incorrecta de indicadores y parámetros.</span><span class="sxs-lookup"><span data-stu-id="b536e-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b536e-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b536e-128">0x80041006</span></span> | <span data-ttu-id="b536e-129">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b536e-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b536e-130">0</span><span class="sxs-lookup"><span data-stu-id="b536e-130">0</span></span> | <span data-ttu-id="b536e-131">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b536e-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b536e-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b536e-132">Remarks</span></span>

<span data-ttu-id="b536e-133">Esta función ajusta una llamada a la [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) método.</span><span class="sxs-lookup"><span data-stu-id="b536e-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="b536e-134">El nombre devuelto se controla mediante una combinación de indicadores y parámetros.</span><span class="sxs-lookup"><span data-stu-id="b536e-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="b536e-135">Por ejemplo, la función puede devolver los nombres de todas las propiedades o solo los nombres de las propiedades de clave.</span><span class="sxs-lookup"><span data-stu-id="b536e-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="b536e-136">El filtro principal se `lFlags` especifica en el parámetro y los demás parámetros varían en función de él.</span><span class="sxs-lookup"><span data-stu-id="b536e-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="b536e-137">Los valores `lFlags` de marca en son campos de bits</span><span class="sxs-lookup"><span data-stu-id="b536e-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="b536e-138">Los indicadores que se `lEnumFlags` pueden pasar como argumento son campos de bits que se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="b536e-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="b536e-139">Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo.</span><span class="sxs-lookup"><span data-stu-id="b536e-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="b536e-140">Sin embargo, las marcas del mismo grupo son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="b536e-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="b536e-141">Banderas del Grupo 1</span><span class="sxs-lookup"><span data-stu-id="b536e-141">Group 1 flags</span></span> |<span data-ttu-id="b536e-142">Value</span><span class="sxs-lookup"><span data-stu-id="b536e-142">Value</span></span>  |<span data-ttu-id="b536e-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="b536e-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="b536e-144">0</span><span class="sxs-lookup"><span data-stu-id="b536e-144">0</span></span> | <span data-ttu-id="b536e-145">Devuelve todos los nombres de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b536e-145">Return all property names.</span></span> <span data-ttu-id="b536e-146">`strQualifierName`y `pQualifierVal` no se utilizan.</span><span class="sxs-lookup"><span data-stu-id="b536e-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="b536e-147">1</span><span class="sxs-lookup"><span data-stu-id="b536e-147">1</span></span> | <span data-ttu-id="b536e-148">Devuelve solo las propiedades que tienen un `strQualifierName` calificador del nombre especificado por el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b536e-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="b536e-149">Si se utiliza esta marca, debe especificar `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="b536e-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="b536e-150">2</span><span class="sxs-lookup"><span data-stu-id="b536e-150">2</span></span> |  <span data-ttu-id="b536e-151">Devuelve solo las propiedades que no tienen un `strQualifierName` calificador del nombre especificado por el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b536e-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="b536e-152">Si se utiliza esta marca, debe especificar `strQualifierName`.</span><span class="sxs-lookup"><span data-stu-id="b536e-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="b536e-153">3</span><span class="sxs-lookup"><span data-stu-id="b536e-153">3</span></span> | <span data-ttu-id="b536e-154">Devuelve solo las propiedades que tienen un `wszQualifierName` calificador del nombre especificado por el `pQualifierVal` parámetro y también tienen un valor idéntico al especificado por la estructura.</span><span class="sxs-lookup"><span data-stu-id="b536e-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="b536e-155">Si se utiliza esta marca, `wszQualifierName` debe `pQualifierValue`especificar a y a .</span><span class="sxs-lookup"><span data-stu-id="b536e-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="b536e-156">Banderas del Grupo 2</span><span class="sxs-lookup"><span data-stu-id="b536e-156">Group 2 flags</span></span> |<span data-ttu-id="b536e-157">Value</span><span class="sxs-lookup"><span data-stu-id="b536e-157">Value</span></span>  |<span data-ttu-id="b536e-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="b536e-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="b536e-159">0x4</span><span class="sxs-lookup"><span data-stu-id="b536e-159">0x4</span></span> | <span data-ttu-id="b536e-160">Devuelve solo los nombres de las propiedades que definen las claves.</span><span class="sxs-lookup"><span data-stu-id="b536e-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="b536e-161">0x8</span><span class="sxs-lookup"><span data-stu-id="b536e-161">0x8</span></span> | <span data-ttu-id="b536e-162">Devuelve solo los nombres de propiedad que son referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="b536e-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="b536e-163">Banderas del Grupo 3</span><span class="sxs-lookup"><span data-stu-id="b536e-163">Group 3 flags</span></span> |<span data-ttu-id="b536e-164">Value</span><span class="sxs-lookup"><span data-stu-id="b536e-164">Value</span></span>  |<span data-ttu-id="b536e-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="b536e-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="b536e-166">0x10</span><span class="sxs-lookup"><span data-stu-id="b536e-166">0x10</span></span> | <span data-ttu-id="b536e-167">Devuelve solo los nombres de propiedad que pertenecen a la clase más derivada.</span><span class="sxs-lookup"><span data-stu-id="b536e-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="b536e-168">Excluir propiedades de las clases primarias.</span><span class="sxs-lookup"><span data-stu-id="b536e-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="b536e-169">0x20</span><span class="sxs-lookup"><span data-stu-id="b536e-169">0x20</span></span> | <span data-ttu-id="b536e-170">Devuelve solo los nombres de propiedad que pertenecen a las clases primarias.</span><span class="sxs-lookup"><span data-stu-id="b536e-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="b536e-171">0x30</span><span class="sxs-lookup"><span data-stu-id="b536e-171">0x30</span></span> | <span data-ttu-id="b536e-172">Devuelve solo los nombres de las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="b536e-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="b536e-173">0x40</span><span class="sxs-lookup"><span data-stu-id="b536e-173">0x40</span></span> | <span data-ttu-id="b536e-174">Devuelve solo los nombres de las propiedades que no son del sistema.</span><span class="sxs-lookup"><span data-stu-id="b536e-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="b536e-175">La función siempre `SAFEARRAY` asigna un `WBEM_S_NO_ERROR`nuevo `pstrNames` si devuelve , y siempre se establece para que apunte a ella.</span><span class="sxs-lookup"><span data-stu-id="b536e-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="b536e-176">La matriz devuelta puede tener 0 elementos si ninguna propiedad coincide con los filtros especificados.</span><span class="sxs-lookup"><span data-stu-id="b536e-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="b536e-177">Si la función devuelve `WBM_S_NO_ERROR`un `SAFEARRAY` valor distinto de , no se devuelve una nueva estructura.</span><span class="sxs-lookup"><span data-stu-id="b536e-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="b536e-178">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b536e-178">Requirements</span></span>  
 <span data-ttu-id="b536e-179">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b536e-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b536e-180">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b536e-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b536e-181">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b536e-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b536e-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b536e-182">See also</span></span>

- [<span data-ttu-id="b536e-183">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b536e-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
