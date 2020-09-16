---
title: Función get (referencia de la API no administrada)
description: La función get recupera el valor de propiedad especificado.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 7cc0c285f79b2791863fce251e4683aa7b55341b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553693"
---
# <a name="get-function"></a><span data-ttu-id="665ce-103">Función Get</span><span class="sxs-lookup"><span data-stu-id="665ce-103">Get function</span></span>

<span data-ttu-id="665ce-104">Recupera el valor de propiedad especificado si existe.</span><span class="sxs-lookup"><span data-stu-id="665ce-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="665ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="665ce-105">Syntax</span></span>

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="665ce-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="665ce-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="665ce-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="665ce-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="665ce-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="665ce-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="665ce-109">[in] Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="665ce-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="665ce-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="665ce-110">[in] Reserved.</span></span> <span data-ttu-id="665ce-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="665ce-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="665ce-112">enuncia Si la función se devuelve correctamente, contiene el valor de la `wszName` propiedad.</span><span class="sxs-lookup"><span data-stu-id="665ce-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="665ce-113">El `pval` argumento tiene asignado el tipo y el valor correctos para el calificador.</span><span class="sxs-lookup"><span data-stu-id="665ce-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="665ce-114">enuncia Si la función se devuelve correctamente, contiene una [constante de tipo CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) que indica el tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="665ce-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="665ce-115">Su valor también puede ser `null` .</span><span class="sxs-lookup"><span data-stu-id="665ce-115">Its value can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="665ce-116">enuncia Si la función se devuelve correctamente, recibe información sobre el origen de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="665ce-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="665ce-117">Su valor puede ser `null` , o una de las siguientes constantes de WBEM_FLAVOR_TYPE definidas en el archivo de encabezado *WbemCli. h* :</span><span class="sxs-lookup"><span data-stu-id="665ce-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span>

|<span data-ttu-id="665ce-118">Constante</span><span class="sxs-lookup"><span data-stu-id="665ce-118">Constant</span></span>  |<span data-ttu-id="665ce-119">Valor</span><span class="sxs-lookup"><span data-stu-id="665ce-119">Value</span></span>  |<span data-ttu-id="665ce-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="665ce-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="665ce-121">0x40</span><span class="sxs-lookup"><span data-stu-id="665ce-121">0x40</span></span> | <span data-ttu-id="665ce-122">La propiedad es una propiedad estándar del sistema.</span><span class="sxs-lookup"><span data-stu-id="665ce-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="665ce-123">0x20</span><span class="sxs-lookup"><span data-stu-id="665ce-123">0x20</span></span> | <span data-ttu-id="665ce-124">Para una clase: la propiedad se hereda de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="665ce-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="665ce-125">Para una instancia: la propiedad, mientras que se hereda de la clase primaria, no ha sido modificada por la instancia de.</span><span class="sxs-lookup"><span data-stu-id="665ce-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="665ce-126">0</span><span class="sxs-lookup"><span data-stu-id="665ce-126">0</span></span> | <span data-ttu-id="665ce-127">Para una clase: la propiedad pertenece a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="665ce-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="665ce-128">Para una instancia de: la propiedad es modificada por la instancia de; es decir, se ha proporcionado un valor o se ha agregado o modificado un calificador.</span><span class="sxs-lookup"><span data-stu-id="665ce-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="665ce-129">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="665ce-129">Return value</span></span>

<span data-ttu-id="665ce-130">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="665ce-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="665ce-131">Constante</span><span class="sxs-lookup"><span data-stu-id="665ce-131">Constant</span></span>  |<span data-ttu-id="665ce-132">Valor</span><span class="sxs-lookup"><span data-stu-id="665ce-132">Value</span></span>  |<span data-ttu-id="665ce-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="665ce-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="665ce-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="665ce-134">0x80041001</span></span> | <span data-ttu-id="665ce-135">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="665ce-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="665ce-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="665ce-136">0x80041008</span></span> | <span data-ttu-id="665ce-137">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="665ce-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="665ce-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="665ce-138">0x80041002</span></span> | <span data-ttu-id="665ce-139">No se encontró la propiedad especificada.</span><span class="sxs-lookup"><span data-stu-id="665ce-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="665ce-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="665ce-140">0x80041006</span></span> | <span data-ttu-id="665ce-141">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="665ce-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="665ce-142">0</span><span class="sxs-lookup"><span data-stu-id="665ce-142">0</span></span> | <span data-ttu-id="665ce-143">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="665ce-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="665ce-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="665ce-144">Remarks</span></span>

<span data-ttu-id="665ce-145">Esta función contiene una llamada al método [IWbemClassObject:: get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .</span><span class="sxs-lookup"><span data-stu-id="665ce-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="665ce-146">La `Get` función también puede devolver propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="665ce-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="665ce-147">El `pVal` argumento tiene asignado el tipo y el valor correctos para el calificador y la función [VARIANTINIT](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) de com.</span><span class="sxs-lookup"><span data-stu-id="665ce-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="665ce-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="665ce-148">Requirements</span></span>

 <span data-ttu-id="665ce-149">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="665ce-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="665ce-150">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="665ce-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="665ce-151">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="665ce-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="665ce-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="665ce-152">See also</span></span>

- [<span data-ttu-id="665ce-153">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="665ce-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
