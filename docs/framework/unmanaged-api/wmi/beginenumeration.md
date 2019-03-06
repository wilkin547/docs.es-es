---
title: BeginEnumeration (función) (referencia de API no administrada)
description: BeginEnumeration (función) restablece el enumerador al principio de la enumeración
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11002ac57a37b3c9ab0badfab49bb9049b0dfa79
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369297"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="4d7b5-103">BeginEnumeration (función)</span><span class="sxs-lookup"><span data-stu-id="4d7b5-103">BeginEnumeration function</span></span>
<span data-ttu-id="4d7b5-104">Restablece el enumerador al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4d7b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d7b5-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="4d7b5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d7b5-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="4d7b5-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="4d7b5-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="4d7b5-109">[in] Una combinación bit a bit de los marcadores o los valores descritos en la [comentarios](#remarks) sección que controla las propiedades incluidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="4d7b5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d7b5-110">Return value</span></span>

<span data-ttu-id="4d7b5-111">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="4d7b5-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4d7b5-112">Constante</span><span class="sxs-lookup"><span data-stu-id="4d7b5-112">Constant</span></span>  |<span data-ttu-id="4d7b5-113">Valor</span><span class="sxs-lookup"><span data-stu-id="4d7b5-113">Value</span></span>  |<span data-ttu-id="4d7b5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d7b5-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4d7b5-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4d7b5-115">0x80041008</span></span> | <span data-ttu-id="4d7b5-116">La combinación de marcas en `lEnumFlags` no es válido o no válido se ha especificado el argumento.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4d7b5-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4d7b5-117">0x8004101d</span></span> | <span data-ttu-id="4d7b5-118">Una segunda llamada a `BeginEnumeration` se realizó sin una llamada intermedia a [ `EndEnumeration` ](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4d7b5-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4d7b5-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4d7b5-119">0x80041006</span></span> | <span data-ttu-id="4d7b5-120">No hay suficiente memoria disponible para comenzar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4d7b5-121">0</span><span class="sxs-lookup"><span data-stu-id="4d7b5-121">0</span></span> | <span data-ttu-id="4d7b5-122">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4d7b5-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d7b5-123">Remarks</span></span>

<span data-ttu-id="4d7b5-124">Esta función contiene una llamada a la [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) método.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="4d7b5-125">Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="4d7b5-126">Puede combinar una marca de todos los grupos con cualquier marca de cualquier otro grupo.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="4d7b5-127">Sin embargo, las marcas del mismo grupo se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="4d7b5-128">**Grupo 1**</span><span class="sxs-lookup"><span data-stu-id="4d7b5-128">**Group 1**</span></span>

|<span data-ttu-id="4d7b5-129">Constante</span><span class="sxs-lookup"><span data-stu-id="4d7b5-129">Constant</span></span>  |<span data-ttu-id="4d7b5-130">Valor</span><span class="sxs-lookup"><span data-stu-id="4d7b5-130">Value</span></span>  |<span data-ttu-id="4d7b5-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d7b5-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="4d7b5-132">0x4</span><span class="sxs-lookup"><span data-stu-id="4d7b5-132">0x4</span></span> | <span data-ttu-id="4d7b5-133">Incluyen propiedades que constituyen la clave solo.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="4d7b5-134">0x8</span><span class="sxs-lookup"><span data-stu-id="4d7b5-134">0x8</span></span> | <span data-ttu-id="4d7b5-135">Incluir propiedades que son las referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="4d7b5-136">**Grupo 2**</span><span class="sxs-lookup"><span data-stu-id="4d7b5-136">**Group 2**</span></span>

<span data-ttu-id="4d7b5-137">Constante</span><span class="sxs-lookup"><span data-stu-id="4d7b5-137">Constant</span></span>  |<span data-ttu-id="4d7b5-138">Valor</span><span class="sxs-lookup"><span data-stu-id="4d7b5-138">Value</span></span>  |<span data-ttu-id="4d7b5-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d7b5-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="4d7b5-140">0x30</span><span class="sxs-lookup"><span data-stu-id="4d7b5-140">0x30</span></span> | <span data-ttu-id="4d7b5-141">Limitar la enumeración de propiedades del sistema solo.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="4d7b5-142">0x40</span><span class="sxs-lookup"><span data-stu-id="4d7b5-142">0x40</span></span> | <span data-ttu-id="4d7b5-143">Incluir propiedades locales y propagadas pero excluir propiedades del sistema de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="4d7b5-144">Las clases:</span><span class="sxs-lookup"><span data-stu-id="4d7b5-144">For classes:</span></span>

<span data-ttu-id="4d7b5-145">Constante</span><span class="sxs-lookup"><span data-stu-id="4d7b5-145">Constant</span></span>  |<span data-ttu-id="4d7b5-146">Valor</span><span class="sxs-lookup"><span data-stu-id="4d7b5-146">Value</span></span>  |<span data-ttu-id="4d7b5-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d7b5-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="4d7b5-148">0x100</span><span class="sxs-lookup"><span data-stu-id="4d7b5-148">0x100</span></span> | <span data-ttu-id="4d7b5-149">Limitar la enumeración de propiedades que se reemplaza en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="4d7b5-150">0x100</span><span class="sxs-lookup"><span data-stu-id="4d7b5-150">0x100</span></span> | <span data-ttu-id="4d7b5-151">Limitar la enumeración a las propiedades que se reemplaza en la definición de clase actual y a las nuevas propiedades definidas en la clase.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="4d7b5-152">0x300</span><span class="sxs-lookup"><span data-stu-id="4d7b5-152">0x300</span></span> | <span data-ttu-id="4d7b5-153">Una máscara (en lugar de una marca) se aplican a un `lEnumFlags` valor para comprobar si `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` está establecido.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4d7b5-154">0x10</span><span class="sxs-lookup"><span data-stu-id="4d7b5-154">0x10</span></span> | <span data-ttu-id="4d7b5-155">Limitar la enumeración de las propiedades que se definen o se modifica en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="4d7b5-156">0x20</span><span class="sxs-lookup"><span data-stu-id="4d7b5-156">0x20</span></span> | <span data-ttu-id="4d7b5-157">Limitar la enumeración de propiedades que se heredan de clases base.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="4d7b5-158">Para las instancias:</span><span class="sxs-lookup"><span data-stu-id="4d7b5-158">For instances:</span></span>

<span data-ttu-id="4d7b5-159">Constante</span><span class="sxs-lookup"><span data-stu-id="4d7b5-159">Constant</span></span>  |<span data-ttu-id="4d7b5-160">Valor</span><span class="sxs-lookup"><span data-stu-id="4d7b5-160">Value</span></span>  |<span data-ttu-id="4d7b5-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d7b5-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4d7b5-162">0x10</span><span class="sxs-lookup"><span data-stu-id="4d7b5-162">0x10</span></span> | <span data-ttu-id="4d7b5-163">Limitar la enumeración de las propiedades que se definen o se modifica en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="4d7b5-164">0x20</span><span class="sxs-lookup"><span data-stu-id="4d7b5-164">0x20</span></span> | <span data-ttu-id="4d7b5-165">Limitar la enumeración de propiedades que se heredan de clases base.</span><span class="sxs-lookup"><span data-stu-id="4d7b5-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="4d7b5-166">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d7b5-166">Requirements</span></span>  
 <span data-ttu-id="4d7b5-167">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d7b5-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d7b5-168">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4d7b5-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4d7b5-169">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4d7b5-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7b5-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d7b5-170">See also</span></span>

- [<span data-ttu-id="4d7b5-171">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="4d7b5-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)