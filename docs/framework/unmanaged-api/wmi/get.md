---
title: Get (función) (referencia de API no administrada)
description: La función Get recupera el valor de propiedad especificado.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7534d760f902f80d42c6c20c57a34d52012997a7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369661"
---
# <a name="get-function"></a><span data-ttu-id="f8dcc-103">Get (función)</span><span class="sxs-lookup"><span data-stu-id="f8dcc-103">Get function</span></span>

<span data-ttu-id="f8dcc-104">Recupera el valor de propiedad especificado si existe.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f8dcc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8dcc-105">Syntax</span></span>

```
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

## <a name="parameters"></a><span data-ttu-id="f8dcc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8dcc-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="f8dcc-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="f8dcc-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="f8dcc-109">[in] El nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="f8dcc-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-110">[in] Reserved.</span></span> <span data-ttu-id="f8dcc-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="f8dcc-112">[out] Si la función devuelve correctamente, contiene el valor de la `wszName` propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="f8dcc-113">El `pval` argumento se asigna el tipo correcto y el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="f8dcc-114">[out] Si la función devuelve correctamente, contiene un [constante de tipo de CIM](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) que indica el tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="f8dcc-115">Su valor puede ser también `null`.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-115">Its value can also be `null`.</span></span> 

`plFlavor`\
<span data-ttu-id="f8dcc-116">[out] Si la función devuelve correctamente, recibe información acerca del origen de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="f8dcc-117">Su valor puede ser `null`, o una de las siguientes constantes WBEM_FLAVOR_TYPE definidas en el *WbemCli.h* archivo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="f8dcc-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="f8dcc-118">Constante</span><span class="sxs-lookup"><span data-stu-id="f8dcc-118">Constant</span></span>  |<span data-ttu-id="f8dcc-119">Valor</span><span class="sxs-lookup"><span data-stu-id="f8dcc-119">Value</span></span>  |<span data-ttu-id="f8dcc-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8dcc-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="f8dcc-121">0x40</span><span class="sxs-lookup"><span data-stu-id="f8dcc-121">0x40</span></span> | <span data-ttu-id="f8dcc-122">La propiedad es una propiedad estándar del sistema.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="f8dcc-123">0x20</span><span class="sxs-lookup"><span data-stu-id="f8dcc-123">0x20</span></span> | <span data-ttu-id="f8dcc-124">Para una clase: La propiedad se hereda de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="f8dcc-125">Para una instancia: La propiedad, mientras se hereda de la clase primaria, no se ha modificado por la instancia.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="f8dcc-126">0</span><span class="sxs-lookup"><span data-stu-id="f8dcc-126">0</span></span> | <span data-ttu-id="f8dcc-127">Para una clase: La propiedad pertenece a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="f8dcc-128">Para una instancia: Se modifica la propiedad por la instancia; es decir, se proporcionó un valor o un calificador se ha agregado o modificado.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="f8dcc-129">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f8dcc-129">Return value</span></span>

<span data-ttu-id="f8dcc-130">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="f8dcc-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f8dcc-131">Constante</span><span class="sxs-lookup"><span data-stu-id="f8dcc-131">Constant</span></span>  |<span data-ttu-id="f8dcc-132">Valor</span><span class="sxs-lookup"><span data-stu-id="f8dcc-132">Value</span></span>  |<span data-ttu-id="f8dcc-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8dcc-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="f8dcc-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f8dcc-134">0x80041001</span></span> | <span data-ttu-id="f8dcc-135">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f8dcc-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f8dcc-136">0x80041008</span></span> | <span data-ttu-id="f8dcc-137">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="f8dcc-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f8dcc-138">0x80041002</span></span> | <span data-ttu-id="f8dcc-139">No se encontró la propiedad especificada.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f8dcc-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f8dcc-140">0x80041006</span></span> | <span data-ttu-id="f8dcc-141">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f8dcc-142">0</span><span class="sxs-lookup"><span data-stu-id="f8dcc-142">0</span></span> | <span data-ttu-id="f8dcc-143">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="f8dcc-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8dcc-144">Remarks</span></span>

<span data-ttu-id="f8dcc-145">Esta función contiene una llamada a la [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) método.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="f8dcc-146">El `Get` función también puede devolver las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="f8dcc-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="f8dcc-147">El `pVal` argumento se asigna el tipo correcto y el valor para el calificador y el COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) (función)</span><span class="sxs-lookup"><span data-stu-id="f8dcc-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="f8dcc-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8dcc-148">Requirements</span></span>

 <span data-ttu-id="f8dcc-149">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8dcc-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="f8dcc-150">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f8dcc-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="f8dcc-151">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8dcc-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f8dcc-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8dcc-152">See also</span></span>

- [<span data-ttu-id="f8dcc-153">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="f8dcc-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)