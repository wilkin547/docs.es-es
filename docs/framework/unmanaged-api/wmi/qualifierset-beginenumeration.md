---
title: Función QualifierSet_BeginEnumeration (referencia de API no administrada)
description: La función QualifierSet_BeginEnumeration restablece un enumerador de los calificadores de un objeto.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5f3987705486727a591dce1670cd369d909a0d4a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636232"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="56cdb-103">Función QualifierSet_BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="56cdb-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="56cdb-104">Restablece un enumerador de los calificadores de un objeto al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="56cdb-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="56cdb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56cdb-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="56cdb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56cdb-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="56cdb-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="56cdb-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="56cdb-108">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="56cdb-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="56cdb-109">[in] Una combinación bit a bit de los marcadores o los valores descritos en la [comentarios](#remarks) sección que especifica los calificadores que se va a incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="56cdb-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="56cdb-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="56cdb-110">Return value</span></span>

<span data-ttu-id="56cdb-111">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="56cdb-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="56cdb-112">Constante</span><span class="sxs-lookup"><span data-stu-id="56cdb-112">Constant</span></span>  |<span data-ttu-id="56cdb-113">Valor</span><span class="sxs-lookup"><span data-stu-id="56cdb-113">Value</span></span>  |<span data-ttu-id="56cdb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="56cdb-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="56cdb-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="56cdb-115">0x80041008</span></span> | <span data-ttu-id="56cdb-116">El parámetro `lFlags` no es válido.</span><span class="sxs-lookup"><span data-stu-id="56cdb-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="56cdb-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="56cdb-117">0x8004101d</span></span> | <span data-ttu-id="56cdb-118">Una segunda llamada a `QualifierSet_BeginEnumeration` se realizó sin una llamada intermedia a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="56cdb-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="56cdb-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="56cdb-119">0x80041006</span></span> | <span data-ttu-id="56cdb-120">No hay suficiente memoria disponible para comenzar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="56cdb-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="56cdb-121">0</span><span class="sxs-lookup"><span data-stu-id="56cdb-121">0</span></span> | <span data-ttu-id="56cdb-122">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="56cdb-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="56cdb-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="56cdb-123">Remarks</span></span>

<span data-ttu-id="56cdb-124">Esta función contiene una llamada a la [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="56cdb-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="56cdb-125">Para enumerar todos los calificadores en un objeto, este método debe llamarse antes de la primera llamada a [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="56cdb-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="56cdb-126">El orden en el que se enumeran los calificadores se garantiza que todos los idiomas para una enumeración especificada.</span><span class="sxs-lookup"><span data-stu-id="56cdb-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="56cdb-127">Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="56cdb-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="56cdb-128">Constante</span><span class="sxs-lookup"><span data-stu-id="56cdb-128">Constant</span></span>  |<span data-ttu-id="56cdb-129">Valor</span><span class="sxs-lookup"><span data-stu-id="56cdb-129">Value</span></span>  |<span data-ttu-id="56cdb-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="56cdb-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="56cdb-131">0</span><span class="sxs-lookup"><span data-stu-id="56cdb-131">0</span></span> | <span data-ttu-id="56cdb-132">Devuelve los nombres de todos los calificadores.</span><span class="sxs-lookup"><span data-stu-id="56cdb-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="56cdb-133">0x10</span><span class="sxs-lookup"><span data-stu-id="56cdb-133">0x10</span></span> | <span data-ttu-id="56cdb-134">Devolver solo los nombres de los calificadores específicos que el objeto o propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="56cdb-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="56cdb-135">Para una propiedad: Devolver solo los calificadores específicos de la propiedad (incluidas las invalidaciones) y no los calificadores propagados desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="56cdb-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="56cdb-136">Para una instancia: Devolver solo los nombres de calificador específicos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="56cdb-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="56cdb-137">Para una clase: Devolver solo los calificadores específica a la clase que se deriva.</span><span class="sxs-lookup"><span data-stu-id="56cdb-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="56cdb-138">0x20</span><span class="sxs-lookup"><span data-stu-id="56cdb-138">0x20</span></span> | <span data-ttu-id="56cdb-139">Si la devolución propagan los nombres de los calificadores de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="56cdb-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="56cdb-140">Para una propiedad: Si la devolución solo los calificadores se propagan a esta propiedad desde la definición de clase y no los de la propiedad propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="56cdb-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="56cdb-141">Para una instancia: Si la devolución solo esos calificadores se propagan desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="56cdb-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="56cdb-142">Para una clase: Si la devolución solo esos nombres calificador heredados de las clases principales.</span><span class="sxs-lookup"><span data-stu-id="56cdb-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="56cdb-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56cdb-143">Requirements</span></span>

<span data-ttu-id="56cdb-144">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56cdb-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="56cdb-145">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="56cdb-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="56cdb-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="56cdb-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="56cdb-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="56cdb-147">See also</span></span>

- [<span data-ttu-id="56cdb-148">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="56cdb-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
