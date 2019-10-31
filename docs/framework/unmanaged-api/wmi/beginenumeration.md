---
title: Función BeginEnumeration (referencia de la API no administrada)
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
ms.openlocfilehash: 9e467234a45ae702a5b77a5f0fa8b75d4ff03c52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124128"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="06d2c-103">Función BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="06d2c-103">BeginEnumeration function</span></span>
<span data-ttu-id="06d2c-104">Vuelve a establecer un enumerador al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="06d2c-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="06d2c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06d2c-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="06d2c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06d2c-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="06d2c-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="06d2c-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="06d2c-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="06d2c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="06d2c-109">de Combinación bit a bit de las marcas o valores descritos en la sección [comentarios](#remarks) que controla las propiedades incluidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="06d2c-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="06d2c-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="06d2c-110">Return value</span></span>

<span data-ttu-id="06d2c-111">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="06d2c-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="06d2c-112">Constante</span><span class="sxs-lookup"><span data-stu-id="06d2c-112">Constant</span></span>  |<span data-ttu-id="06d2c-113">Valor</span><span class="sxs-lookup"><span data-stu-id="06d2c-113">Value</span></span>  |<span data-ttu-id="06d2c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="06d2c-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="06d2c-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="06d2c-115">0x80041008</span></span> | <span data-ttu-id="06d2c-116">La combinación de marcas de `lEnumFlags` no es válida o se ha especificado un argumento no válido.</span><span class="sxs-lookup"><span data-stu-id="06d2c-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="06d2c-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="06d2c-117">0x8004101d</span></span> | <span data-ttu-id="06d2c-118">Se realizó una segunda llamada a `BeginEnumeration` sin una llamada intermedia a [`EndEnumeration`](endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="06d2c-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="06d2c-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="06d2c-119">0x80041006</span></span> | <span data-ttu-id="06d2c-120">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="06d2c-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="06d2c-121">0</span><span class="sxs-lookup"><span data-stu-id="06d2c-121">0</span></span> | <span data-ttu-id="06d2c-122">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="06d2c-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="06d2c-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="06d2c-123">Remarks</span></span>

<span data-ttu-id="06d2c-124">Esta función contiene una llamada al método [IWbemClassObject:: BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="06d2c-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="06d2c-125">Las marcas que se pueden pasar como `lEnumFlags` argumento se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="06d2c-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="06d2c-126">Puede combinar una marca de cada grupo con cualquier marca de cualquier otro grupo.</span><span class="sxs-lookup"><span data-stu-id="06d2c-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="06d2c-127">Sin embargo, las marcas del mismo grupo se excluyen mutuamente.</span><span class="sxs-lookup"><span data-stu-id="06d2c-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="06d2c-128">**Grupo 1**</span><span class="sxs-lookup"><span data-stu-id="06d2c-128">**Group 1**</span></span>

|<span data-ttu-id="06d2c-129">Constante</span><span class="sxs-lookup"><span data-stu-id="06d2c-129">Constant</span></span>  |<span data-ttu-id="06d2c-130">Valor</span><span class="sxs-lookup"><span data-stu-id="06d2c-130">Value</span></span>  |<span data-ttu-id="06d2c-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="06d2c-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="06d2c-132">0x4</span><span class="sxs-lookup"><span data-stu-id="06d2c-132">0x4</span></span> | <span data-ttu-id="06d2c-133">Incluye propiedades que solo constituyen la clave.</span><span class="sxs-lookup"><span data-stu-id="06d2c-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="06d2c-134">0x8</span><span class="sxs-lookup"><span data-stu-id="06d2c-134">0x8</span></span> | <span data-ttu-id="06d2c-135">Incluye propiedades que son solo referencias de objeto.</span><span class="sxs-lookup"><span data-stu-id="06d2c-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="06d2c-136">**Grupo 2**</span><span class="sxs-lookup"><span data-stu-id="06d2c-136">**Group 2**</span></span>

<span data-ttu-id="06d2c-137">Constante</span><span class="sxs-lookup"><span data-stu-id="06d2c-137">Constant</span></span>  |<span data-ttu-id="06d2c-138">Valor</span><span class="sxs-lookup"><span data-stu-id="06d2c-138">Value</span></span>  |<span data-ttu-id="06d2c-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="06d2c-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="06d2c-140">0x30</span><span class="sxs-lookup"><span data-stu-id="06d2c-140">0x30</span></span> | <span data-ttu-id="06d2c-141">Limite la enumeración solo a las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="06d2c-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="06d2c-142">0x40</span><span class="sxs-lookup"><span data-stu-id="06d2c-142">0x40</span></span> | <span data-ttu-id="06d2c-143">Incluye propiedades locales y propagadas, pero excluye propiedades del sistema de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="06d2c-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="06d2c-144">Para las clases:</span><span class="sxs-lookup"><span data-stu-id="06d2c-144">For classes:</span></span>

<span data-ttu-id="06d2c-145">Constante</span><span class="sxs-lookup"><span data-stu-id="06d2c-145">Constant</span></span>  |<span data-ttu-id="06d2c-146">Valor</span><span class="sxs-lookup"><span data-stu-id="06d2c-146">Value</span></span>  |<span data-ttu-id="06d2c-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="06d2c-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="06d2c-148">0x100</span><span class="sxs-lookup"><span data-stu-id="06d2c-148">0x100</span></span> | <span data-ttu-id="06d2c-149">Limite la enumeración a propiedades invalidadas en la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="06d2c-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="06d2c-150">0x100</span><span class="sxs-lookup"><span data-stu-id="06d2c-150">0x100</span></span> | <span data-ttu-id="06d2c-151">Limite la enumeración a las propiedades invalidadas en la definición de clase actual y a las nuevas propiedades definidas en la clase.</span><span class="sxs-lookup"><span data-stu-id="06d2c-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="06d2c-152">0x300</span><span class="sxs-lookup"><span data-stu-id="06d2c-152">0x300</span></span> | <span data-ttu-id="06d2c-153">Máscara (en lugar de una marca) que se va a aplicar a un valor de `lEnumFlags` para comprobar si se ha establecido `WBEM_FLAG_CLASS_OVERRIDES_ONLY` o `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`.</span><span class="sxs-lookup"><span data-stu-id="06d2c-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="06d2c-154">0x10</span><span class="sxs-lookup"><span data-stu-id="06d2c-154">0x10</span></span> | <span data-ttu-id="06d2c-155">Limite la enumeración a las propiedades que se definen o modifican en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="06d2c-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="06d2c-156">0x20</span><span class="sxs-lookup"><span data-stu-id="06d2c-156">0x20</span></span> | <span data-ttu-id="06d2c-157">Limite la enumeración a las propiedades que se heredan de las clases base.</span><span class="sxs-lookup"><span data-stu-id="06d2c-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="06d2c-158">Para las instancias:</span><span class="sxs-lookup"><span data-stu-id="06d2c-158">For instances:</span></span>

<span data-ttu-id="06d2c-159">Constante</span><span class="sxs-lookup"><span data-stu-id="06d2c-159">Constant</span></span>  |<span data-ttu-id="06d2c-160">Valor</span><span class="sxs-lookup"><span data-stu-id="06d2c-160">Value</span></span>  |<span data-ttu-id="06d2c-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="06d2c-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="06d2c-162">0x10</span><span class="sxs-lookup"><span data-stu-id="06d2c-162">0x10</span></span> | <span data-ttu-id="06d2c-163">Limite la enumeración a las propiedades que se definen o modifican en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="06d2c-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="06d2c-164">0x20</span><span class="sxs-lookup"><span data-stu-id="06d2c-164">0x20</span></span> | <span data-ttu-id="06d2c-165">Limite la enumeración a las propiedades que se heredan de las clases base.</span><span class="sxs-lookup"><span data-stu-id="06d2c-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="06d2c-166">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06d2c-166">Requirements</span></span>  
 <span data-ttu-id="06d2c-167">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06d2c-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d2c-168">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="06d2c-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="06d2c-169">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="06d2c-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d2c-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="06d2c-170">See also</span></span>

- [<span data-ttu-id="06d2c-171">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="06d2c-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
