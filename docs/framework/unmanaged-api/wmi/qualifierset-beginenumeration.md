---
title: Función QualifierSet_BeginEnumeration (referencia de la API no administrada)
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
ms.openlocfilehash: 3b75c51ebddd78e447fed57b22a96c2d5c35004e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798344"
---
# <a name="qualifierset_beginenumeration-function"></a><span data-ttu-id="889a9-103">QualifierSet_BeginEnumeration función)</span><span class="sxs-lookup"><span data-stu-id="889a9-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="889a9-104">Restablece un enumerador de los calificadores de un objeto al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="889a9-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="889a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="889a9-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="889a9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="889a9-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="889a9-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="889a9-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="889a9-108">de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="889a9-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="889a9-109">de Combinación bit a bit de las marcas o valores descritos en la sección [comentarios](#remarks) que especifica los calificadores que se van a incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="889a9-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="889a9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="889a9-110">Return value</span></span>

<span data-ttu-id="889a9-111">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="889a9-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="889a9-112">Constante</span><span class="sxs-lookup"><span data-stu-id="889a9-112">Constant</span></span>  |<span data-ttu-id="889a9-113">Value</span><span class="sxs-lookup"><span data-stu-id="889a9-113">Value</span></span>  |<span data-ttu-id="889a9-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="889a9-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="889a9-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="889a9-115">0x80041008</span></span> | <span data-ttu-id="889a9-116">El parámetro `lFlags` no es válido.</span><span class="sxs-lookup"><span data-stu-id="889a9-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="889a9-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="889a9-117">0x8004101d</span></span> | <span data-ttu-id="889a9-118">Se realizó una segunda `QualifierSet_BeginEnumeration` llamada a sin una llamada intermedia a. [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="889a9-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="889a9-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="889a9-119">0x80041006</span></span> | <span data-ttu-id="889a9-120">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="889a9-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="889a9-121">0</span><span class="sxs-lookup"><span data-stu-id="889a9-121">0</span></span> | <span data-ttu-id="889a9-122">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="889a9-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="889a9-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="889a9-123">Remarks</span></span>

<span data-ttu-id="889a9-124">Esta función contiene una llamada al método [IWbemQualifierSet:: BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) .</span><span class="sxs-lookup"><span data-stu-id="889a9-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="889a9-125">Para enumerar todos los calificadores de un objeto, se debe llamar a este método antes de la primera llamada a [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="889a9-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="889a9-126">Se garantiza que el orden en el que se enumeran los calificadores es invariable para una enumeración determinada.</span><span class="sxs-lookup"><span data-stu-id="889a9-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="889a9-127">Las marcas que se pueden pasar como `lEnumFlags` argumento se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="889a9-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="889a9-128">Constante</span><span class="sxs-lookup"><span data-stu-id="889a9-128">Constant</span></span>  |<span data-ttu-id="889a9-129">Value</span><span class="sxs-lookup"><span data-stu-id="889a9-129">Value</span></span>  |<span data-ttu-id="889a9-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="889a9-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="889a9-131">0</span><span class="sxs-lookup"><span data-stu-id="889a9-131">0</span></span> | <span data-ttu-id="889a9-132">Devuelve los nombres de todos los calificadores.</span><span class="sxs-lookup"><span data-stu-id="889a9-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="889a9-133">0x10</span><span class="sxs-lookup"><span data-stu-id="889a9-133">0x10</span></span> | <span data-ttu-id="889a9-134">Devuelve solo los nombres de calificadores específicos de la propiedad o el objeto actual.</span><span class="sxs-lookup"><span data-stu-id="889a9-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="889a9-135">Para una propiedad: Solo se devuelven los calificadores específicos de la propiedad (incluidas las invalidaciones), y no los calificadores propagados a partir de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="889a9-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="889a9-136">Para una instancia de: Devuelve solo los nombres de calificador específicos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="889a9-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="889a9-137">Para una clase: Solo devuelve calificadores específicos de la clase que se va a derivar.</span><span class="sxs-lookup"><span data-stu-id="889a9-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="889a9-138">0x20</span><span class="sxs-lookup"><span data-stu-id="889a9-138">0x20</span></span> | <span data-ttu-id="889a9-139">Devuelve solo los nombres de los calificadores propagados desde otro objeto.</span><span class="sxs-lookup"><span data-stu-id="889a9-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="889a9-140">Para una propiedad: Devuelve solo los calificadores propagados a esta propiedad desde la definición de clase, y no los de la propia propiedad.</span><span class="sxs-lookup"><span data-stu-id="889a9-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="889a9-141">Para una instancia de: Devuelve solo los calificadores propagados desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="889a9-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="889a9-142">Para una clase: Solo se devuelven los nombres de calificador heredados de las clases primarias.</span><span class="sxs-lookup"><span data-stu-id="889a9-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="889a9-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="889a9-143">Requirements</span></span>

<span data-ttu-id="889a9-144">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="889a9-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="889a9-145">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="889a9-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="889a9-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="889a9-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="889a9-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="889a9-147">See also</span></span>

- [<span data-ttu-id="889a9-148">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="889a9-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
