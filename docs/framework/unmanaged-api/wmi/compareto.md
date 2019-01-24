---
title: Función CompareTo (referencia de API no administrada)
description: La función CompareTo compara un objeto a otro objeto WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa46cf1fde4306af562248b4c12b048e3d8e2a51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717654"
---
# <a name="compareto-function"></a><span data-ttu-id="24206-103">CompareTo (función)</span><span class="sxs-lookup"><span data-stu-id="24206-103">CompareTo function</span></span>
<span data-ttu-id="24206-104">Compara un objeto de administración de Windows con otro.</span><span class="sxs-lookup"><span data-stu-id="24206-104">Compares an object to another Windows management object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="24206-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24206-105">Syntax</span></span>  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a><span data-ttu-id="24206-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24206-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="24206-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="24206-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="24206-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="24206-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`  
<span data-ttu-id="24206-109">[in] Una combinación bit a bit de los marcadores que especifican las características de objeto deben tener en cuenta para la comparación.</span><span class="sxs-lookup"><span data-stu-id="24206-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="24206-110">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="24206-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`  

<span data-ttu-id="24206-111">[in] El objeto para la comparación.</span><span class="sxs-lookup"><span data-stu-id="24206-111">[in] The object for comparison.</span></span> <span data-ttu-id="24206-112">`pcompareTo` debe ser válido [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia; no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="24206-112">`pcompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="24206-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="24206-113">Return value</span></span>

<span data-ttu-id="24206-114">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="24206-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="24206-115">Constante</span><span class="sxs-lookup"><span data-stu-id="24206-115">Constant</span></span>  |<span data-ttu-id="24206-116">Valor</span><span class="sxs-lookup"><span data-stu-id="24206-116">Value</span></span>  |<span data-ttu-id="24206-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="24206-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="24206-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="24206-118">0x80041001</span></span> | <span data-ttu-id="24206-119">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="24206-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="24206-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="24206-120">0x80041008</span></span> | <span data-ttu-id="24206-121">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="24206-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="24206-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="24206-122">0x8004101d</span></span> | <span data-ttu-id="24206-123">Una segunda llamada a `BeginEnumeration` se realizó sin una llamada intermedia a [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="24206-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="24206-124">0</span><span class="sxs-lookup"><span data-stu-id="24206-124">0</span></span> | <span data-ttu-id="24206-125">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="24206-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="24206-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="24206-126">0x40003</span></span> | <span data-ttu-id="24206-127">Los objetos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="24206-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="24206-128">0</span><span class="sxs-lookup"><span data-stu-id="24206-128">0</span></span> | <span data-ttu-id="24206-129">Los objetos son iguales según las marcas de comparación.</span><span class="sxs-lookup"><span data-stu-id="24206-129">The objects are the same based on the comparison flags.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="24206-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24206-130">Remarks</span></span>

<span data-ttu-id="24206-131">Esta función contiene una llamada a la [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) método.</span><span class="sxs-lookup"><span data-stu-id="24206-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="24206-132">Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="24206-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="24206-133">Puede especificar las características individuales implicadas en la comparación mediante la especificación de una combinación bit a bit de los siguientes indicadores:</span><span class="sxs-lookup"><span data-stu-id="24206-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="24206-134">Constante</span><span class="sxs-lookup"><span data-stu-id="24206-134">Constant</span></span>  |<span data-ttu-id="24206-135">Valor</span><span class="sxs-lookup"><span data-stu-id="24206-135">Value</span></span>  |<span data-ttu-id="24206-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="24206-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="24206-137">2</span><span class="sxs-lookup"><span data-stu-id="24206-137">2</span></span> | <span data-ttu-id="24206-138">Omitir el origen (el servidor y el espacio de nombres que proceden).</span><span class="sxs-lookup"><span data-stu-id="24206-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="24206-139">1</span><span class="sxs-lookup"><span data-stu-id="24206-139">1</span></span> | <span data-ttu-id="24206-140">Omitir todos los calificadores (incluidos **clave** y **dinámica**)</span><span class="sxs-lookup"><span data-stu-id="24206-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="24206-141">4</span><span class="sxs-lookup"><span data-stu-id="24206-141">4</span></span> | <span data-ttu-id="24206-142">Pasar por alto los valores predeterminados de propiedades.</span><span class="sxs-lookup"><span data-stu-id="24206-142">Ignore default values of properties.</span></span> <span data-ttu-id="24206-143">Esta marca solo se aplica a la comparación de las clases.</span><span class="sxs-lookup"><span data-stu-id="24206-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="24206-144">0x20</span><span class="sxs-lookup"><span data-stu-id="24206-144">0x20</span></span> | <span data-ttu-id="24206-145">Omitir los tipos de calificador.</span><span class="sxs-lookup"><span data-stu-id="24206-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="24206-146">Esta marca todavía tiene calificadores en cuenta, pero omite las distinciones de modos tales como las reglas de propagación y reemplazar las restricciones.</span><span class="sxs-lookup"><span data-stu-id="24206-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="24206-147">0x10</span><span class="sxs-lookup"><span data-stu-id="24206-147">0x10</span></span> | <span data-ttu-id="24206-148">Omitir mayúsculas y minúsculas al comparar los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="24206-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="24206-149">Esto se aplica tanto a las cadenas y valores del calificador.</span><span class="sxs-lookup"><span data-stu-id="24206-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="24206-150">La comparación de los nombres de propiedades y calificadores siempre distingue mayúsculas de minúsculas, independientemente de si se establece esta marca.</span><span class="sxs-lookup"><span data-stu-id="24206-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="24206-151">0x8</span><span class="sxs-lookup"><span data-stu-id="24206-151">0x8</span></span> | <span data-ttu-id="24206-152">Se supone que los objetos que se comparan son instancias de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="24206-152">Assume that the objects being compared are instanes of the same class.</span></span> <span data-ttu-id="24206-153">Por lo tanto, esta marca compara solo información relacionada con la instancia.</span><span class="sxs-lookup"><span data-stu-id="24206-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="24206-154">Utilice este marcas para optimizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="24206-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="24206-155">Si los objetos no son de la misma clase, los resultados son indefinidos.</span><span class="sxs-lookup"><span data-stu-id="24206-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="24206-156">O bien, puede especificar una única marca compuesta como sigue:</span><span class="sxs-lookup"><span data-stu-id="24206-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="24206-157">Constante</span><span class="sxs-lookup"><span data-stu-id="24206-157">Constant</span></span>  |<span data-ttu-id="24206-158">Valor</span><span class="sxs-lookup"><span data-stu-id="24206-158">Value</span></span>  |<span data-ttu-id="24206-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="24206-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="24206-160">0</span><span class="sxs-lookup"><span data-stu-id="24206-160">0</span></span> | <span data-ttu-id="24206-161">Tenga en cuenta todas las características en la comparación.</span><span class="sxs-lookup"><span data-stu-id="24206-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="24206-162">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24206-162">Requirements</span></span>  
 <span data-ttu-id="24206-163">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24206-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24206-164">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="24206-164">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="24206-165">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="24206-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24206-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="24206-166">See also</span></span>
- [<span data-ttu-id="24206-167">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="24206-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
