---
title: Función CompareTo (referencia de la API no administrada)
description: La función CompareTo compara un objeto con otro objeto WMI.
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
ms.openlocfilehash: 0d210795016cd2e0179b902a224ca0c62f4ac01f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128708"
---
# <a name="compareto-function"></a><span data-ttu-id="ed829-103">Función CompareTo</span><span class="sxs-lookup"><span data-stu-id="ed829-103">CompareTo function</span></span>

<span data-ttu-id="ed829-104">Compara un objeto de administración de Windows con otro.</span><span class="sxs-lookup"><span data-stu-id="ed829-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ed829-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed829-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="ed829-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed829-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ed829-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="ed829-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ed829-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="ed829-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="ed829-109">de Combinación bit a bit de las marcas que especifican las características del objeto que se deben tener en cuenta para la comparación.</span><span class="sxs-lookup"><span data-stu-id="ed829-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="ed829-110">Vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ed829-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="ed829-111">de Objeto para la comparación.</span><span class="sxs-lookup"><span data-stu-id="ed829-111">[in] The object for comparison.</span></span> <span data-ttu-id="ed829-112">`pCompareTo` debe ser una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) válida; no se puede `null`.</span><span class="sxs-lookup"><span data-stu-id="ed829-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ed829-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed829-113">Return value</span></span>

<span data-ttu-id="ed829-114">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="ed829-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ed829-115">Constante</span><span class="sxs-lookup"><span data-stu-id="ed829-115">Constant</span></span>  |<span data-ttu-id="ed829-116">Valor</span><span class="sxs-lookup"><span data-stu-id="ed829-116">Value</span></span>  |<span data-ttu-id="ed829-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed829-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ed829-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ed829-118">0x80041001</span></span> | <span data-ttu-id="ed829-119">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="ed829-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ed829-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ed829-120">0x80041008</span></span> | <span data-ttu-id="ed829-121">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="ed829-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="ed829-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ed829-122">0x8004101d</span></span> | <span data-ttu-id="ed829-123">Se realizó una segunda llamada a `BeginEnumeration` sin una llamada intermedia a [`EndEnumeration`](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ed829-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ed829-124">0</span><span class="sxs-lookup"><span data-stu-id="ed829-124">0</span></span> | <span data-ttu-id="ed829-125">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed829-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="ed829-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="ed829-126">0x40003</span></span> | <span data-ttu-id="ed829-127">Los objetos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="ed829-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="ed829-128">0</span><span class="sxs-lookup"><span data-stu-id="ed829-128">0</span></span> | <span data-ttu-id="ed829-129">Los objetos son los mismos en función de las marcas de comparación.</span><span class="sxs-lookup"><span data-stu-id="ed829-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ed829-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed829-130">Remarks</span></span>

<span data-ttu-id="ed829-131">Esta función contiene una llamada al método [IWbemClassObject:: CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) .</span><span class="sxs-lookup"><span data-stu-id="ed829-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="ed829-132">Las marcas que se pueden pasar como `lEnumFlags` argumento se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="ed829-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="ed829-133">Puede especificar las características individuales implicadas en la comparación especificando una combinación bit a bit de las marcas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed829-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="ed829-134">Constante</span><span class="sxs-lookup"><span data-stu-id="ed829-134">Constant</span></span>  |<span data-ttu-id="ed829-135">Valor</span><span class="sxs-lookup"><span data-stu-id="ed829-135">Value</span></span>  |<span data-ttu-id="ed829-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed829-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="ed829-137">2</span><span class="sxs-lookup"><span data-stu-id="ed829-137">2</span></span> | <span data-ttu-id="ed829-138">Omita el origen (el servidor y el espacio de nombres del que proceden).</span><span class="sxs-lookup"><span data-stu-id="ed829-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="ed829-139">1</span><span class="sxs-lookup"><span data-stu-id="ed829-139">1</span></span> | <span data-ttu-id="ed829-140">Omitir todos los calificadores (incluidos **clave** y **dinámico**)</span><span class="sxs-lookup"><span data-stu-id="ed829-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="ed829-141">4</span><span class="sxs-lookup"><span data-stu-id="ed829-141">4</span></span> | <span data-ttu-id="ed829-142">Omitir los valores predeterminados de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="ed829-142">Ignore default values of properties.</span></span> <span data-ttu-id="ed829-143">Esta marca solo se aplica a la comparación de clases.</span><span class="sxs-lookup"><span data-stu-id="ed829-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="ed829-144">0x20</span><span class="sxs-lookup"><span data-stu-id="ed829-144">0x20</span></span> | <span data-ttu-id="ed829-145">Omitir tipos de calificador.</span><span class="sxs-lookup"><span data-stu-id="ed829-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="ed829-146">Esta marca todavía toma los calificadores en cuenta, pero omite las distinciones de sabor, como las reglas de propagación y las restricciones de invalidación.</span><span class="sxs-lookup"><span data-stu-id="ed829-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="ed829-147">0x10</span><span class="sxs-lookup"><span data-stu-id="ed829-147">0x10</span></span> | <span data-ttu-id="ed829-148">Omitir mayúsculas y minúsculas en la comparación de valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="ed829-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="ed829-149">Esto se aplica a las cadenas y los valores de calificador.</span><span class="sxs-lookup"><span data-stu-id="ed829-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="ed829-150">La comparación de nombres de propiedad y calificador siempre distingue entre mayúsculas y minúsculas, independientemente de si esta marca está establecida.</span><span class="sxs-lookup"><span data-stu-id="ed829-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="ed829-151">0x8</span><span class="sxs-lookup"><span data-stu-id="ed829-151">0x8</span></span> | <span data-ttu-id="ed829-152">Supongamos que los objetos que se comparan son instancias de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="ed829-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="ed829-153">Por consiguiente, esta marca solo compara la información relacionada con la instancia.</span><span class="sxs-lookup"><span data-stu-id="ed829-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="ed829-154">Use estas marcas para optimizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ed829-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="ed829-155">Si los objetos no son de la misma clase, los resultados son indefinidos.</span><span class="sxs-lookup"><span data-stu-id="ed829-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="ed829-156">O bien, puede especificar una única marca compuesta como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="ed829-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="ed829-157">Constante</span><span class="sxs-lookup"><span data-stu-id="ed829-157">Constant</span></span>  |<span data-ttu-id="ed829-158">Valor</span><span class="sxs-lookup"><span data-stu-id="ed829-158">Value</span></span>  |<span data-ttu-id="ed829-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed829-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="ed829-160">0</span><span class="sxs-lookup"><span data-stu-id="ed829-160">0</span></span> | <span data-ttu-id="ed829-161">Tenga en cuenta todas las características de la comparación.</span><span class="sxs-lookup"><span data-stu-id="ed829-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="ed829-162">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed829-162">Requirements</span></span>

<span data-ttu-id="ed829-163">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed829-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ed829-164">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ed829-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ed829-165">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ed829-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ed829-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed829-166">See also</span></span>

- [<span data-ttu-id="ed829-167">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="ed829-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
