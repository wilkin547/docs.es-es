---
title: Función BeginEnumeration (Referencia de API no administrada)
description: La función BeginEnumeration restablece un enumerador al principio de la enumeración
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176882"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="c63f2-103">Función BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="c63f2-103">BeginEnumeration function</span></span>
<span data-ttu-id="c63f2-104">Restablece un enumerador al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c63f2-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c63f2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c63f2-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="c63f2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c63f2-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c63f2-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="c63f2-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c63f2-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="c63f2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="c63f2-109">[en] Combinación bit a bit de los indicadores o valores descritos en la sección [Comentarios](#remarks) que controla las propiedades incluidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c63f2-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="c63f2-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c63f2-110">Return value</span></span>

<span data-ttu-id="c63f2-111">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="c63f2-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c63f2-112">Constante</span><span class="sxs-lookup"><span data-stu-id="c63f2-112">Constant</span></span>  |<span data-ttu-id="c63f2-113">Value</span><span class="sxs-lookup"><span data-stu-id="c63f2-113">Value</span></span>  |<span data-ttu-id="c63f2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c63f2-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c63f2-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c63f2-115">0x80041008</span></span> | <span data-ttu-id="c63f2-116">La combinación `lEnumFlags` de marcas en no es válida o se especificó un argumento no válido.</span><span class="sxs-lookup"><span data-stu-id="c63f2-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="c63f2-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c63f2-117">0x8004101d</span></span> | <span data-ttu-id="c63f2-118">Una segunda `BeginEnumeration` llamada a se hizo [`EndEnumeration`](endenumeration.md)sin una llamada interviniente a .</span><span class="sxs-lookup"><span data-stu-id="c63f2-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c63f2-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c63f2-119">0x80041006</span></span> | <span data-ttu-id="c63f2-120">No hay suficiente memoria disponible para comenzar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="c63f2-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c63f2-121">0</span><span class="sxs-lookup"><span data-stu-id="c63f2-121">0</span></span> | <span data-ttu-id="c63f2-122">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c63f2-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c63f2-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c63f2-123">Remarks</span></span>

<span data-ttu-id="c63f2-124">Esta función ajusta una llamada a la [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) método.</span><span class="sxs-lookup"><span data-stu-id="c63f2-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="c63f2-125">Los indicadores que se `lEnumFlags` pueden pasar como argumento se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="c63f2-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="c63f2-126">Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo.</span><span class="sxs-lookup"><span data-stu-id="c63f2-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="c63f2-127">Sin embargo, las marcas del mismo grupo son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="c63f2-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="c63f2-128">**Grupo 1**</span><span class="sxs-lookup"><span data-stu-id="c63f2-128">**Group 1**</span></span>

|<span data-ttu-id="c63f2-129">Constante</span><span class="sxs-lookup"><span data-stu-id="c63f2-129">Constant</span></span>  |<span data-ttu-id="c63f2-130">Value</span><span class="sxs-lookup"><span data-stu-id="c63f2-130">Value</span></span>  |<span data-ttu-id="c63f2-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="c63f2-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="c63f2-132">0x4</span><span class="sxs-lookup"><span data-stu-id="c63f2-132">0x4</span></span> | <span data-ttu-id="c63f2-133">Incluya las propiedades que constituyen solo la clave.</span><span class="sxs-lookup"><span data-stu-id="c63f2-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="c63f2-134">0x8</span><span class="sxs-lookup"><span data-stu-id="c63f2-134">0x8</span></span> | <span data-ttu-id="c63f2-135">Incluya solo propiedades que sean referencias a objetos.</span><span class="sxs-lookup"><span data-stu-id="c63f2-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="c63f2-136">**Grupo 2**</span><span class="sxs-lookup"><span data-stu-id="c63f2-136">**Group 2**</span></span>

<span data-ttu-id="c63f2-137">Constante</span><span class="sxs-lookup"><span data-stu-id="c63f2-137">Constant</span></span>  |<span data-ttu-id="c63f2-138">Value</span><span class="sxs-lookup"><span data-stu-id="c63f2-138">Value</span></span>  |<span data-ttu-id="c63f2-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="c63f2-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="c63f2-140">0x30</span><span class="sxs-lookup"><span data-stu-id="c63f2-140">0x30</span></span> | <span data-ttu-id="c63f2-141">Limite la enumeración solo a las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="c63f2-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="c63f2-142">0x40</span><span class="sxs-lookup"><span data-stu-id="c63f2-142">0x40</span></span> | <span data-ttu-id="c63f2-143">Incluya propiedades locales y propagadas, pero excluya las propiedades del sistema de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c63f2-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="c63f2-144">Para clases:</span><span class="sxs-lookup"><span data-stu-id="c63f2-144">For classes:</span></span>

<span data-ttu-id="c63f2-145">Constante</span><span class="sxs-lookup"><span data-stu-id="c63f2-145">Constant</span></span>  |<span data-ttu-id="c63f2-146">Value</span><span class="sxs-lookup"><span data-stu-id="c63f2-146">Value</span></span>  |<span data-ttu-id="c63f2-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="c63f2-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="c63f2-148">0x100</span><span class="sxs-lookup"><span data-stu-id="c63f2-148">0x100</span></span> | <span data-ttu-id="c63f2-149">Limite la enumeración a las propiedades reemplazadas en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="c63f2-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="c63f2-150">0x100</span><span class="sxs-lookup"><span data-stu-id="c63f2-150">0x100</span></span> | <span data-ttu-id="c63f2-151">Limite la enumeración a las propiedades reemplazadas en la definición de clase actual y a las nuevas propiedades definidas en la clase.</span><span class="sxs-lookup"><span data-stu-id="c63f2-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="c63f2-152">0x300</span><span class="sxs-lookup"><span data-stu-id="c63f2-152">0x300</span></span> | <span data-ttu-id="c63f2-153">Una máscara (en lugar de una `lEnumFlags` marca) para `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` aplicar contra un valor para comprobar si se establece o está establecido.</span><span class="sxs-lookup"><span data-stu-id="c63f2-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="c63f2-154">0x10</span><span class="sxs-lookup"><span data-stu-id="c63f2-154">0x10</span></span> | <span data-ttu-id="c63f2-155">Limite la enumeración a las propiedades que se definen o modifican en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="c63f2-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="c63f2-156">0x20</span><span class="sxs-lookup"><span data-stu-id="c63f2-156">0x20</span></span> | <span data-ttu-id="c63f2-157">Limite la enumeración a las propiedades que se heredan de las clases base.</span><span class="sxs-lookup"><span data-stu-id="c63f2-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="c63f2-158">Para ejemplos:</span><span class="sxs-lookup"><span data-stu-id="c63f2-158">For instances:</span></span>

<span data-ttu-id="c63f2-159">Constante</span><span class="sxs-lookup"><span data-stu-id="c63f2-159">Constant</span></span>  |<span data-ttu-id="c63f2-160">Value</span><span class="sxs-lookup"><span data-stu-id="c63f2-160">Value</span></span>  |<span data-ttu-id="c63f2-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="c63f2-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="c63f2-162">0x10</span><span class="sxs-lookup"><span data-stu-id="c63f2-162">0x10</span></span> | <span data-ttu-id="c63f2-163">Limite la enumeración a las propiedades que se definen o modifican en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="c63f2-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="c63f2-164">0x20</span><span class="sxs-lookup"><span data-stu-id="c63f2-164">0x20</span></span> | <span data-ttu-id="c63f2-165">Limite la enumeración a las propiedades que se heredan de las clases base.</span><span class="sxs-lookup"><span data-stu-id="c63f2-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="c63f2-166">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c63f2-166">Requirements</span></span>  
 <span data-ttu-id="c63f2-167">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c63f2-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c63f2-168">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c63f2-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c63f2-169">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c63f2-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c63f2-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c63f2-170">See also</span></span>

- [<span data-ttu-id="c63f2-171">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c63f2-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
