---
title: "Función Put (referencia de API no administrada)"
description: "La función Put asigna un nuevo valor a una propiedad con nombre."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Put
helpviewer_keywords: Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c4ad979a3a662618ab62b52d63bda3dbb1e71b9
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="put-function"></a><span data-ttu-id="b7c94-103">Función Put</span><span class="sxs-lookup"><span data-stu-id="b7c94-103">Put function</span></span>
<span data-ttu-id="b7c94-104">Establece una propiedad con nombre en un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="b7c94-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b7c94-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7c94-105">Syntax</span></span>  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a><span data-ttu-id="b7c94-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7c94-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b7c94-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b7c94-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b7c94-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="b7c94-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="b7c94-109">[in] El nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7c94-109">[in] The name of the property.</span></span> <span data-ttu-id="b7c94-110">Este parámetro no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-110">This parameter cannot be `null`.</span></span>

`lFlags`  
<span data-ttu-id="b7c94-111">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="b7c94-111">[in] Reserved.</span></span> <span data-ttu-id="b7c94-112">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="b7c94-112">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="b7c94-113">[in] Un puntero a un válido `VARIANT` que se convierte en el nuevo valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7c94-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="b7c94-114">Si `pVal` es `null` o apunta a un `VARIANT` de tipo `VT_NULL`, la propiedad se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span> 

`vtType`  
<span data-ttu-id="b7c94-115">[in] El tipo de `VARIANT` señalada por `pVal`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="b7c94-116">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b7c94-116">See the [Remarks](#remarks) section for more information.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="b7c94-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7c94-117">Return value</span></span>

<span data-ttu-id="b7c94-118">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b7c94-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b7c94-119">Constante</span><span class="sxs-lookup"><span data-stu-id="b7c94-119">Constant</span></span>  |<span data-ttu-id="b7c94-120">Valor</span><span class="sxs-lookup"><span data-stu-id="b7c94-120">Value</span></span>  |<span data-ttu-id="b7c94-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7c94-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b7c94-122">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="b7c94-122">0x80041001</span></span> | <span data-ttu-id="b7c94-123">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="b7c94-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b7c94-124">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="b7c94-124">0x80041008</span></span> | <span data-ttu-id="b7c94-125">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="b7c94-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="b7c94-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="b7c94-126">0x8004102a</span></span> | <span data-ttu-id="b7c94-127">No se reconoce el tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7c94-127">The property type is not recognized.</span></span> <span data-ttu-id="b7c94-128">Este valor se devuelve cuando se crean instancias de clase si la clase ya existe.</span><span class="sxs-lookup"><span data-stu-id="b7c94-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b7c94-129">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="b7c94-129">0x80041006</span></span> | <span data-ttu-id="b7c94-130">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b7c94-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="b7c94-131">0 x 80041005</span><span class="sxs-lookup"><span data-stu-id="b7c94-131">0x80041005</span></span> | <span data-ttu-id="b7c94-132">Para instancias: indica que `pVal` apunta a un `VARIANT` de un tipo incorrecto para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7c94-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="b7c94-133">Para obtener definiciones de clase: la propiedad ya existe en la clase primaria y el nuevo tipo COM es diferente del tipo COM antiguo.</span><span class="sxs-lookup"><span data-stu-id="b7c94-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b7c94-134">0</span><span class="sxs-lookup"><span data-stu-id="b7c94-134">0</span></span> | <span data-ttu-id="b7c94-135">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="b7c94-135">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b7c94-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7c94-136">Remarks</span></span>

<span data-ttu-id="b7c94-137">Esta función contiene una llamada a la [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="b7c94-137">This function wraps a call to the [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b7c94-138">Esta función siempre sobrescribe el valor de propiedad actual por una nueva.</span><span class="sxs-lookup"><span data-stu-id="b7c94-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="b7c94-139">Si el [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) apunta a una definición de clase `Put` crea o actualiza el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7c94-139">If the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="b7c94-140">Cuando [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) apunta a una instancia CIM, `Put` actualiza el valor de propiedad solo; `Put` no se puede crear un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7c94-140">When [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="b7c94-141">El `__CLASS` propiedad del sistema resulta solo escritura durante la creación de la clase, no pueden dejarse en blanco.</span><span class="sxs-lookup"><span data-stu-id="b7c94-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="b7c94-142">Todas las demás propiedades del sistema son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b7c94-142">All other system properties are read-only.</span></span>

<span data-ttu-id="b7c94-143">Un usuario no puede crear propiedades con nombres que empezarán ni terminan con un carácter de subrayado ("_").</span><span class="sxs-lookup"><span data-stu-id="b7c94-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="b7c94-144">Se reserva para las propiedades y clases del sistema.</span><span class="sxs-lookup"><span data-stu-id="b7c94-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="b7c94-145">Si la propiedad se establece mediante el `Put` función existe en la clase primaria, el valor predeterminado de la propiedad se cambia a menos que el tipo de propiedad no coincide con el tipo de clase principal.</span><span class="sxs-lookup"><span data-stu-id="b7c94-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="b7c94-146">Si la propiedad no existe y no es un tipo no coincidente, la propiedad es ceated.</span><span class="sxs-lookup"><span data-stu-id="b7c94-146">If the property does not exist and it is not a type mismatch, the property is ceated.</span></span>

<span data-ttu-id="b7c94-147">Use la `vtType` parámetro solo cuando se crean nuevas propiedades en una definición de clase CIM y `pVal` es `null` o apunta a un `VARIANT` de tipo `VT_NULL`.</span><span class="sxs-lookup"><span data-stu-id="b7c94-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="b7c94-148">En este caso, el `vType` parámetro especifica el tipo CIM de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b7c94-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="b7c94-149">En los demás casos, `vtType` debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="b7c94-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="b7c94-150">`vtType`También debe ser 0 si el objeto subyacente es una instancia (aunque `Val` es `null`) porque el tipo de la propiedad es fijo y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="b7c94-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>   

## <a name="example"></a><span data-ttu-id="b7c94-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7c94-151">Example</span></span>

<span data-ttu-id="b7c94-152">Para obtener un ejemplo, vea el [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="b7c94-152">For an example, see the [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7c94-153">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7c94-153">Requirements</span></span>  
 <span data-ttu-id="b7c94-154">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7c94-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7c94-155">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b7c94-155">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b7c94-156">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b7c94-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c94-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7c94-157">See also</span></span>  
[<span data-ttu-id="b7c94-158">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b7c94-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
