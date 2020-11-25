---
title: Función Next (referencia de la API no administrada)
description: La siguiente función recupera la propiedad siguiente en una enumeración.
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
ms.openlocfilehash: c2a7fae32e82caae40a95bfdad10fa78082988ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726795"
---
# <a name="next-function"></a><span data-ttu-id="2bf90-103">Función Next</span><span class="sxs-lookup"><span data-stu-id="2bf90-103">Next function</span></span>

<span data-ttu-id="2bf90-104">Recupera la siguiente propiedad de una enumeración que comienza con una llamada a [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="2bf90-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="2bf90-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bf90-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="2bf90-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bf90-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="2bf90-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="2bf90-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="2bf90-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="2bf90-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="2bf90-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="2bf90-109">[in] Reserved.</span></span> <span data-ttu-id="2bf90-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="2bf90-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="2bf90-111">enuncia Un nuevo `BSTR` que contiene el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bf90-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="2bf90-112">Puede establecer este parámetro en `null` si el nombre no es necesario.</span><span class="sxs-lookup"><span data-stu-id="2bf90-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="2bf90-113">enuncia Un `VARIANT` rellenado con el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bf90-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="2bf90-114">Puede establecer este parámetro en `null` si el valor no es necesario.</span><span class="sxs-lookup"><span data-stu-id="2bf90-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="2bf90-115">Si la función devuelve un código de error, el `VARIANT` que se pasa a `pVal` se deja sin modificar.</span><span class="sxs-lookup"><span data-stu-id="2bf90-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="2bf90-116">enuncia Puntero a una `CIMTYPE` variable ( `LONG` en la que se coloca el tipo de la propiedad).</span><span class="sxs-lookup"><span data-stu-id="2bf90-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="2bf90-117">El valor de esta propiedad puede ser `VT_NULL_VARIANT` , en cuyo caso es necesario determinar el tipo real de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bf90-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="2bf90-118">Este parámetro también puede ser `null` .</span><span class="sxs-lookup"><span data-stu-id="2bf90-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="2bf90-119">[out] `null` o un valor que recibe información sobre el origen de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2bf90-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="2bf90-120">Vea la sección [comentarios] para ver los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="2bf90-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="2bf90-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2bf90-121">Return value</span></span>

<span data-ttu-id="2bf90-122">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="2bf90-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2bf90-123">Constante</span><span class="sxs-lookup"><span data-stu-id="2bf90-123">Constant</span></span>  |<span data-ttu-id="2bf90-124">Value</span><span class="sxs-lookup"><span data-stu-id="2bf90-124">Value</span></span>  |<span data-ttu-id="2bf90-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bf90-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2bf90-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="2bf90-126">0x80041001</span></span> | <span data-ttu-id="2bf90-127">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="2bf90-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2bf90-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2bf90-128">0x80041008</span></span> | <span data-ttu-id="2bf90-129">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="2bf90-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="2bf90-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="2bf90-130">0x8004101d</span></span> | <span data-ttu-id="2bf90-131">No había ninguna llamada a la [`BeginEnumeration`](beginenumeration.md) función.</span><span class="sxs-lookup"><span data-stu-id="2bf90-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2bf90-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2bf90-132">0x80041006</span></span> | <span data-ttu-id="2bf90-133">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="2bf90-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="2bf90-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="2bf90-134">0x80041015</span></span> | <span data-ttu-id="2bf90-135">Error en la llamada a procedimiento remoto entre el proceso actual y la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="2bf90-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2bf90-136">0</span><span class="sxs-lookup"><span data-stu-id="2bf90-136">0</span></span> | <span data-ttu-id="2bf90-137">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bf90-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="2bf90-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="2bf90-138">0x40005</span></span> | <span data-ttu-id="2bf90-139">No hay más propiedades en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2bf90-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2bf90-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2bf90-140">Remarks</span></span>

<span data-ttu-id="2bf90-141">Esta función contiene una llamada al método [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) .</span><span class="sxs-lookup"><span data-stu-id="2bf90-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="2bf90-142">Este método también devuelve propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="2bf90-142">This method also returns system properties.</span></span>

<span data-ttu-id="2bf90-143">Si el tipo subyacente de la propiedad es una ruta de acceso de objeto, una fecha u hora u otro tipo especial, el tipo devuelto no contiene suficiente información.</span><span class="sxs-lookup"><span data-stu-id="2bf90-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="2bf90-144">El autor de la llamada debe examinar el `CIMTYPE` de la propiedad especificada para determinar si la propiedad es una referencia de objeto, una fecha u hora u otro tipo especial.</span><span class="sxs-lookup"><span data-stu-id="2bf90-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="2bf90-145">Si `plFlavor` no es `null` , el `LONG` valor recibe información sobre el origen de la propiedad, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2bf90-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="2bf90-146">Constante</span><span class="sxs-lookup"><span data-stu-id="2bf90-146">Constant</span></span>  |<span data-ttu-id="2bf90-147">Value</span><span class="sxs-lookup"><span data-stu-id="2bf90-147">Value</span></span>  |<span data-ttu-id="2bf90-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bf90-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="2bf90-149">0x40</span><span class="sxs-lookup"><span data-stu-id="2bf90-149">0x40</span></span> | <span data-ttu-id="2bf90-150">La propiedad es una propiedad estándar del sistema.</span><span class="sxs-lookup"><span data-stu-id="2bf90-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="2bf90-151">0x20</span><span class="sxs-lookup"><span data-stu-id="2bf90-151">0x20</span></span> | <span data-ttu-id="2bf90-152">Para una clase: la propiedad se hereda de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="2bf90-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="2bf90-153">Para una instancia: la propiedad, mientras que se hereda de la clase primaria, no ha sido modificada por la instancia de.</span><span class="sxs-lookup"><span data-stu-id="2bf90-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="2bf90-154">0</span><span class="sxs-lookup"><span data-stu-id="2bf90-154">0</span></span> | <span data-ttu-id="2bf90-155">Para una clase: la propiedad pertenece a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="2bf90-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="2bf90-156">Para una instancia de: la propiedad es modificada por la instancia de; es decir, se ha proporcionado un valor o se ha agregado o modificado un calificador.</span><span class="sxs-lookup"><span data-stu-id="2bf90-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="2bf90-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bf90-157">Requirements</span></span>

<span data-ttu-id="2bf90-158">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bf90-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="2bf90-159">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="2bf90-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="2bf90-160">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2bf90-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2bf90-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bf90-161">See also</span></span>

- [<span data-ttu-id="2bf90-162">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="2bf90-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
