---
title: Función Next (referencia de API no administrada)
description: La función siguiente recupera la siguiente propiedad en una enumeración.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 240544330fa352cbfdc01944e4be6bcad28dc96f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373206"
---
# <a name="next-function"></a><span data-ttu-id="c66e6-103">Función Next</span><span class="sxs-lookup"><span data-stu-id="c66e6-103">Next function</span></span>
<span data-ttu-id="c66e6-104">Recupera la siguiente propiedad en una enumeración que comienza con una llamada a [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="c66e6-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c66e6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c66e6-105">Syntax</span></span>

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="c66e6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c66e6-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c66e6-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="c66e6-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c66e6-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="c66e6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="c66e6-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="c66e6-109">[in] Reserved.</span></span> <span data-ttu-id="c66e6-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="c66e6-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="c66e6-111">[out] Un nuevo `BSTR` que contiene el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c66e6-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="c66e6-112">Puede establecer este parámetro en `null` si el nombre no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c66e6-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="c66e6-113">[out] Un `VARIANT` rellena con el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c66e6-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="c66e6-114">Puede establecer este parámetro en `null` si el valor no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c66e6-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="c66e6-115">Si la función devuelve un código de error, el `VARIANT` pasado a `pVal` es izquierda sin modificar.</span><span class="sxs-lookup"><span data-stu-id="c66e6-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="c66e6-116">[out] Un puntero a un `CIMTYPE` variable (un `LONG` en que se coloca el tipo de la propiedad).</span><span class="sxs-lookup"><span data-stu-id="c66e6-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="c66e6-117">El valor de esta propiedad puede ser un `VT_NULL_VARIANT`, en cuyo caso es necesario determinar el tipo real de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c66e6-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="c66e6-118">Este parámetro también puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="c66e6-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="c66e6-119">[out] `null`, o un valor que recibe información sobre el origen de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c66e6-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="c66e6-120">Consulte la sección [Nota] los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="c66e6-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="c66e6-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c66e6-121">Return value</span></span>

<span data-ttu-id="c66e6-122">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="c66e6-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c66e6-123">Constante</span><span class="sxs-lookup"><span data-stu-id="c66e6-123">Constant</span></span>  |<span data-ttu-id="c66e6-124">Valor</span><span class="sxs-lookup"><span data-stu-id="c66e6-124">Value</span></span>  |<span data-ttu-id="c66e6-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c66e6-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c66e6-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c66e6-126">0x80041001</span></span> | <span data-ttu-id="c66e6-127">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="c66e6-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c66e6-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c66e6-128">0x80041008</span></span> | <span data-ttu-id="c66e6-129">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="c66e6-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="c66e6-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="c66e6-130">0x8004101d</span></span> | <span data-ttu-id="c66e6-131">Se ha producido ninguna llamada a la [ `BeginEnumeration` ](beginenumeration.md) función.</span><span class="sxs-lookup"><span data-stu-id="c66e6-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c66e6-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c66e6-132">0x80041006</span></span> | <span data-ttu-id="c66e6-133">No hay suficiente memoria disponible para comenzar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="c66e6-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="c66e6-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="c66e6-134">0x80041015</span></span> | <span data-ttu-id="c66e6-135">La llamada a procedimiento remoto entre el proceso actual y la administración de Windows no se pudo.</span><span class="sxs-lookup"><span data-stu-id="c66e6-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c66e6-136">0</span><span class="sxs-lookup"><span data-stu-id="c66e6-136">0</span></span> | <span data-ttu-id="c66e6-137">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="c66e6-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="c66e6-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="c66e6-138">0x40005</span></span> | <span data-ttu-id="c66e6-139">No hay ninguna propiedad más en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c66e6-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c66e6-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c66e6-140">Remarks</span></span>

<span data-ttu-id="c66e6-141">Esta función contiene una llamada a la [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) método.</span><span class="sxs-lookup"><span data-stu-id="c66e6-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="c66e6-142">Este método también devuelve las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="c66e6-142">This method also returns system properties.</span></span>

<span data-ttu-id="c66e6-143">Si el tipo subyacente de la propiedad es una ruta de acceso del objeto, una fecha o tiempo u otro tipo especial, el tipo devuelto no tiene suficiente información.</span><span class="sxs-lookup"><span data-stu-id="c66e6-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="c66e6-144">El llamador debe examinar el `CIMTYPE` para la propiedad especificada determinar si la propiedad es una referencia de objeto, una fecha o tiempo u otro tipo especial.</span><span class="sxs-lookup"><span data-stu-id="c66e6-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="c66e6-145">Si `plFlavor` no `null`, el `LONG` valor recibe información acerca del origen de la propiedad, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c66e6-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="c66e6-146">Constante</span><span class="sxs-lookup"><span data-stu-id="c66e6-146">Constant</span></span>  |<span data-ttu-id="c66e6-147">Valor</span><span class="sxs-lookup"><span data-stu-id="c66e6-147">Value</span></span>  |<span data-ttu-id="c66e6-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="c66e6-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="c66e6-149">0x40</span><span class="sxs-lookup"><span data-stu-id="c66e6-149">0x40</span></span> | <span data-ttu-id="c66e6-150">La propiedad es una propiedad estándar del sistema.</span><span class="sxs-lookup"><span data-stu-id="c66e6-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="c66e6-151">0x20</span><span class="sxs-lookup"><span data-stu-id="c66e6-151">0x20</span></span> | <span data-ttu-id="c66e6-152">Para una clase: La propiedad se hereda de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="c66e6-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="c66e6-153">Para una instancia: La propiedad, mientras se hereda de la clase primaria, no se ha modificado por la instancia.</span><span class="sxs-lookup"><span data-stu-id="c66e6-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="c66e6-154">0</span><span class="sxs-lookup"><span data-stu-id="c66e6-154">0</span></span> | <span data-ttu-id="c66e6-155">Para una clase: La propiedad pertenece a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c66e6-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="c66e6-156">Para una instancia: Se modifica la propiedad por la instancia; es decir, se proporcionó un valor o un calificador se ha agregado o modificado.</span><span class="sxs-lookup"><span data-stu-id="c66e6-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="c66e6-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c66e6-157">Requirements</span></span>

<span data-ttu-id="c66e6-158">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c66e6-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c66e6-159">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c66e6-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="c66e6-160">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c66e6-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c66e6-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="c66e6-161">See also</span></span>

- [<span data-ttu-id="c66e6-162">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c66e6-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)