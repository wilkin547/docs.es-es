---
title: Función QualifierSet_GetNames (referencia de la API no administrada)
description: La función QualifierSet_GetNames recupera los nombres de los calificadores de un objeto o propiedad.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266462a5393c8e26aa2bc3f2ec8ab72d4410a431
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798297"
---
# <a name="qualifierset_getnames-function"></a><span data-ttu-id="7bf2a-103">QualifierSet_GetNames función)</span><span class="sxs-lookup"><span data-stu-id="7bf2a-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="7bf2a-104">Recupera los nombres de todos los calificadores o de determinados calificadores que están disponibles en el objeto o propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7bf2a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bf2a-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="7bf2a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bf2a-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="7bf2a-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="7bf2a-108">de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="7bf2a-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="7bf2a-109">de Uno de los siguientes marcadores o valores que especifica los nombres que se van a incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="7bf2a-110">Constante</span><span class="sxs-lookup"><span data-stu-id="7bf2a-110">Constant</span></span>  |<span data-ttu-id="7bf2a-111">Value</span><span class="sxs-lookup"><span data-stu-id="7bf2a-111">Value</span></span>  |<span data-ttu-id="7bf2a-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7bf2a-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="7bf2a-113">0</span><span class="sxs-lookup"><span data-stu-id="7bf2a-113">0</span></span> | <span data-ttu-id="7bf2a-114">Devuelve los nombres de todos los calificadores.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7bf2a-115">0x10</span><span class="sxs-lookup"><span data-stu-id="7bf2a-115">0x10</span></span> | <span data-ttu-id="7bf2a-116">Devuelve solo los nombres de calificadores específicos de la propiedad o el objeto actual.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="7bf2a-117">Para una propiedad: Solo se devuelven los calificadores específicos de la propiedad (incluidas las invalidaciones), y no los calificadores propagados a partir de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="7bf2a-118">Para una instancia de: Devuelve solo los nombres de calificador específicos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="7bf2a-119">Para una clase: Solo devuelve calificadores específicos de la clase que se va a derivar.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="7bf2a-120">0x20</span><span class="sxs-lookup"><span data-stu-id="7bf2a-120">0x20</span></span> | <span data-ttu-id="7bf2a-121">Devuelve solo los nombres de los calificadores propagados desde otro objeto.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="7bf2a-122">Para una propiedad: Devuelve solo los calificadores propagados a esta propiedad desde la definición de clase, y no los de la propia propiedad.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="7bf2a-123">Para una instancia de: Devuelve solo los calificadores propagados desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="7bf2a-124">Para una clase: Solo se devuelven los nombres de calificador heredados de las clases primarias.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="7bf2a-125">enuncia Un nuevo `SAFEARRAY` que contiene los nombres solicitados.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="7bf2a-126">La matriz puede tener 0 elementos.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-126">The array can have 0 elements.</span></span> <span data-ttu-id="7bf2a-127">Si se produce un error, no `SAFEARRAY` se devuelve un nuevo.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="7bf2a-128">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7bf2a-128">Return value</span></span>

<span data-ttu-id="7bf2a-129">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="7bf2a-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7bf2a-130">Constante</span><span class="sxs-lookup"><span data-stu-id="7bf2a-130">Constant</span></span>  |<span data-ttu-id="7bf2a-131">Valor</span><span class="sxs-lookup"><span data-stu-id="7bf2a-131">Value</span></span>  |<span data-ttu-id="7bf2a-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7bf2a-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7bf2a-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7bf2a-133">0x80041008</span></span> | <span data-ttu-id="7bf2a-134">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7bf2a-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7bf2a-135">0x80041006</span></span> | <span data-ttu-id="7bf2a-136">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7bf2a-137">0</span><span class="sxs-lookup"><span data-stu-id="7bf2a-137">0</span></span> | <span data-ttu-id="7bf2a-138">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="7bf2a-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7bf2a-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7bf2a-139">Remarks</span></span>

<span data-ttu-id="7bf2a-140">Esta función contiene una llamada al método [IWbemQualifierSet:: GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) .</span><span class="sxs-lookup"><span data-stu-id="7bf2a-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="7bf2a-141">Una vez que haya recuperado los nombres de calificador, puede tener acceso a cada calificador por nombre llamando a la función [QualifierSet_Get](qualifierset-get.md) .</span><span class="sxs-lookup"><span data-stu-id="7bf2a-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="7bf2a-142">No es un error que un objeto dado tenga calificadores cero, por lo que el número de cadenas de `pstrNames` en la devolución puede ser 0, aunque la función devuelva. `WBEM_S_NO_ERROR`</span><span class="sxs-lookup"><span data-stu-id="7bf2a-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="7bf2a-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bf2a-143">Requirements</span></span>

<span data-ttu-id="7bf2a-144">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bf2a-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7bf2a-145">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7bf2a-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7bf2a-146">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7bf2a-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7bf2a-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bf2a-147">See also</span></span>

- [<span data-ttu-id="7bf2a-148">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="7bf2a-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
