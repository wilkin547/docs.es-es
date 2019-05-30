---
title: Función QualifierSet_Put (referencia de API no administrada)
description: La función QualifierSet_Put escribe el calificador con nombre y su valor.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a11f19a9b5ebdf491b79c250da7fc5ac3d980b64
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377868"
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="1eef0-103">Función QualifierSet_Put</span><span class="sxs-lookup"><span data-stu-id="1eef0-103">QualifierSet_Put function</span></span>

<span data-ttu-id="1eef0-104">Escribe el calificador y el valor con nombre.</span><span class="sxs-lookup"><span data-stu-id="1eef0-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="1eef0-105">El nuevo calificador sobrescribe el valor anterior del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1eef0-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="1eef0-106">Si el calificador no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="1eef0-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1eef0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1eef0-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="1eef0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1eef0-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="1eef0-109">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="1eef0-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="1eef0-110">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="1eef0-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="1eef0-111">[in] El nombre del calificador que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="1eef0-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="1eef0-112">[in] Un puntero a una `VARIANT` que contiene el calificador a escribir.</span><span class="sxs-lookup"><span data-stu-id="1eef0-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="1eef0-113">Este parámetro no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="1eef0-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="1eef0-114">[in] Una de las constantes siguientes que define los tipos de calificador deseado para este calificador.</span><span class="sxs-lookup"><span data-stu-id="1eef0-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="1eef0-115">El valor predeterminado es `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="1eef0-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="1eef0-116">Constante</span><span class="sxs-lookup"><span data-stu-id="1eef0-116">Constant</span></span>  |<span data-ttu-id="1eef0-117">Valor</span><span class="sxs-lookup"><span data-stu-id="1eef0-117">Value</span></span>  |<span data-ttu-id="1eef0-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eef0-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="1eef0-119">0</span><span class="sxs-lookup"><span data-stu-id="1eef0-119">0</span></span> | <span data-ttu-id="1eef0-120">El calificador se puede invalidar en una clase derivada o una instancia.</span><span class="sxs-lookup"><span data-stu-id="1eef0-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="1eef0-121">**Este es el valor predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="1eef0-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="1eef0-122">1</span><span class="sxs-lookup"><span data-stu-id="1eef0-122">1</span></span> | <span data-ttu-id="1eef0-123">El calificador se propaga a las instancias.</span><span class="sxs-lookup"><span data-stu-id="1eef0-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="1eef0-124">2</span><span class="sxs-lookup"><span data-stu-id="1eef0-124">2</span></span> | <span data-ttu-id="1eef0-125">El calificador se propaga a las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="1eef0-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="1eef0-126">0x10</span><span class="sxs-lookup"><span data-stu-id="1eef0-126">0x10</span></span> | <span data-ttu-id="1eef0-127">El calificador no puede invalidarse en una clase o instancia derivada.</span><span class="sxs-lookup"><span data-stu-id="1eef0-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="1eef0-128">0x80</span><span class="sxs-lookup"><span data-stu-id="1eef0-128">0x80</span></span> | <span data-ttu-id="1eef0-129">El calificador está localizado.</span><span class="sxs-lookup"><span data-stu-id="1eef0-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="1eef0-130">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1eef0-130">Return value</span></span>

<span data-ttu-id="1eef0-131">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="1eef0-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1eef0-132">Constante</span><span class="sxs-lookup"><span data-stu-id="1eef0-132">Constant</span></span>  |<span data-ttu-id="1eef0-133">Valor</span><span class="sxs-lookup"><span data-stu-id="1eef0-133">Value</span></span>  |<span data-ttu-id="1eef0-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="1eef0-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="1eef0-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="1eef0-135">0x8004101f</span></span> | <span data-ttu-id="1eef0-136">Se produjo un intento no válido para especificar el **clave** calificador en una propiedad que no puede ser una clave.</span><span class="sxs-lookup"><span data-stu-id="1eef0-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="1eef0-137">Las claves se especifican en la definición de clase para un objeto y no se pueden modificar por instancia.</span><span class="sxs-lookup"><span data-stu-id="1eef0-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1eef0-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1eef0-138">0x80041008</span></span> | <span data-ttu-id="1eef0-139">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="1eef0-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="1eef0-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="1eef0-140">0x80041029</span></span> | <span data-ttu-id="1eef0-141">El `pVal` parámetro no es de un tipo de calificador válido.</span><span class="sxs-lookup"><span data-stu-id="1eef0-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="1eef0-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="1eef0-142">0x8004101a</span></span> | <span data-ttu-id="1eef0-143">No es posible llamar a la `QualifierSet_Put` invalida el método en el calificador porque el objeto propietario no permite.</span><span class="sxs-lookup"><span data-stu-id="1eef0-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1eef0-144">0</span><span class="sxs-lookup"><span data-stu-id="1eef0-144">0</span></span> | <span data-ttu-id="1eef0-145">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="1eef0-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="1eef0-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1eef0-146">Remarks</span></span>

<span data-ttu-id="1eef0-147">Esta función contiene una llamada a la [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) método.</span><span class="sxs-lookup"><span data-stu-id="1eef0-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1eef0-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1eef0-148">Requirements</span></span>

<span data-ttu-id="1eef0-149">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eef0-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="1eef0-150">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1eef0-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="1eef0-151">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1eef0-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1eef0-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="1eef0-152">See also</span></span>

- [<span data-ttu-id="1eef0-153">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="1eef0-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
