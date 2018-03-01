---
title: "Función siguiente (referencia de API no administrada)"
description: "La siguiente función retireves la siguiente propiedad en una enumeración."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a><span data-ttu-id="2d741-103">Función siguiente</span><span class="sxs-lookup"><span data-stu-id="2d741-103">Next function</span></span>
<span data-ttu-id="2d741-104">Recupera la siguiente propiedad en una enumeración que comienza con una llamada a [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="2d741-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2d741-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d741-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="2d741-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d741-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2d741-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="2d741-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2d741-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="2d741-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="2d741-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="2d741-109">[in] Reserved.</span></span> <span data-ttu-id="2d741-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="2d741-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="2d741-111">[out] Un nuevo `BSTR` que contiene el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d741-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="2d741-112">Puede establecer este parámetro en `null` si el nombre no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="2d741-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="2d741-113">[out] Un `VARIANT` rellena con el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d741-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="2d741-114">Puede establecer este parámetro en `null` si el valor no es necesario.</span><span class="sxs-lookup"><span data-stu-id="2d741-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="2d741-115">Si la función devuelve un código de error, el `VARIANT` pasado a `pVal` es izquierda sin modificar.</span><span class="sxs-lookup"><span data-stu-id="2d741-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="2d741-116">[out] Un puntero a un `CIMTYPE` variable (una `LONG` en que se coloca el tipo de la propiedad).</span><span class="sxs-lookup"><span data-stu-id="2d741-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="2d741-117">El valor de esta propiedad puede ser un `VT_NULL_VARIANT`, en cuyo caso es necesario determinar el tipo real de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d741-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="2d741-118">Este parámetro también puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="2d741-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="2d741-119">[out] `null`, o un valor que recibe información sobre el origen de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="2d741-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="2d741-120">Consulte la sección [comentarios] para los valores posibles.</span><span class="sxs-lookup"><span data-stu-id="2d741-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="2d741-121">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d741-121">Return value</span></span>

<span data-ttu-id="2d741-122">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="2d741-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2d741-123">Constante</span><span class="sxs-lookup"><span data-stu-id="2d741-123">Constant</span></span>  |<span data-ttu-id="2d741-124">Valor</span><span class="sxs-lookup"><span data-stu-id="2d741-124">Value</span></span>  |<span data-ttu-id="2d741-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d741-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2d741-126">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="2d741-126">0x80041001</span></span> | <span data-ttu-id="2d741-127">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="2d741-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2d741-128">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="2d741-128">0x80041008</span></span> | <span data-ttu-id="2d741-129">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="2d741-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="2d741-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="2d741-130">0x8004101d</span></span> | <span data-ttu-id="2d741-131">Se ha producido ninguna llamada a la [ `BeginEnumeration` ](beginenumeration.md) (función).</span><span class="sxs-lookup"><span data-stu-id="2d741-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2d741-132">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="2d741-132">0x80041006</span></span> | <span data-ttu-id="2d741-133">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="2d741-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="2d741-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="2d741-134">0x80041015</span></span> | <span data-ttu-id="2d741-135">Llamada a procedimiento remoto entre el proceso actual y la administración de Windows no se pudo.</span><span class="sxs-lookup"><span data-stu-id="2d741-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2d741-136">0</span><span class="sxs-lookup"><span data-stu-id="2d741-136">0</span></span> | <span data-ttu-id="2d741-137">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="2d741-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="2d741-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="2d741-138">0x40005</span></span> | <span data-ttu-id="2d741-139">No hay ninguna propiedad más en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2d741-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="2d741-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d741-140">Remarks</span></span>

<span data-ttu-id="2d741-141">Esta función contiene una llamada a la [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="2d741-141">This function wraps a call to the [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="2d741-142">Este método también devuelve las propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d741-142">This method also returns system properties.</span></span>

<span data-ttu-id="2d741-143">Si el tipo subyacente de la propiedad es una ruta de acceso del objeto, una fecha o tiempo u otro tipo especial, el tipo de valor devuelto no contiene suficiente información.</span><span class="sxs-lookup"><span data-stu-id="2d741-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="2d741-144">El llamador debe examinar la `CIMTYPE` para la propiedad especificada determinar si la propiedad es una referencia de objeto, una fecha o tiempo u otro tipo especial.</span><span class="sxs-lookup"><span data-stu-id="2d741-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="2d741-145">Si `plFlavor` no `null`, el `LONG` valor recibe información sobre el origen de la propiedad, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2d741-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="2d741-146">Constante</span><span class="sxs-lookup"><span data-stu-id="2d741-146">Constant</span></span>  |<span data-ttu-id="2d741-147">Valor</span><span class="sxs-lookup"><span data-stu-id="2d741-147">Value</span></span>  |<span data-ttu-id="2d741-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d741-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="2d741-149">0 x 40</span><span class="sxs-lookup"><span data-stu-id="2d741-149">0x40</span></span> | <span data-ttu-id="2d741-150">La propiedad es una propiedad estándar del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d741-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="2d741-151">0 x 20</span><span class="sxs-lookup"><span data-stu-id="2d741-151">0x20</span></span> | <span data-ttu-id="2d741-152">Para una clase: la propiedad se hereda de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="2d741-152">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="2d741-153">Para una instancia: la propiedad, mientras que se hereda de la clase primaria, no ha sido modificada por la instancia.</span><span class="sxs-lookup"><span data-stu-id="2d741-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="2d741-154">0</span><span class="sxs-lookup"><span data-stu-id="2d741-154">0</span></span> | <span data-ttu-id="2d741-155">Para una clase: la propiedad pertenece a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="2d741-155">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="2d741-156">Para una instancia: la propiedad se modifica la instancia; es decir, se proporcionó un valor o un calificador se ha agregado o modificado.</span><span class="sxs-lookup"><span data-stu-id="2d741-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="2d741-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d741-157">Requirements</span></span>  
 <span data-ttu-id="2d741-158">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d741-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d741-159">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2d741-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2d741-160">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d741-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d741-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d741-161">See also</span></span>  
[<span data-ttu-id="2d741-162">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="2d741-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
