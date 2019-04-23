---
title: Función PutMethod (referencia de API no administrada)
description: La función PutMethod crea un método.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99bc65b0181a7c0ab7877273b3747ece91544f99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152508"
---
# <a name="putmethod-function"></a><span data-ttu-id="c5d75-103">Función PutMethod</span><span class="sxs-lookup"><span data-stu-id="c5d75-103">PutMethod function</span></span>
<span data-ttu-id="c5d75-104">Crea un método.</span><span class="sxs-lookup"><span data-stu-id="c5d75-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c5d75-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5d75-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="c5d75-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5d75-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c5d75-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="c5d75-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c5d75-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="c5d75-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="c5d75-109">[in] El nombre del método que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c5d75-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="c5d75-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="c5d75-110">[in] Reserved.</span></span> <span data-ttu-id="c5d75-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="c5d75-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="c5d75-112">[in] Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene el `in` parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="c5d75-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="c5d75-113">Este parámetro se omite si establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="c5d75-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="c5d75-114">[in]  Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene el `out` parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="c5d75-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="c5d75-115">Este parámetro se omite si establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="c5d75-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c5d75-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c5d75-116">Return value</span></span>

<span data-ttu-id="c5d75-117">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="c5d75-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c5d75-118">Constante</span><span class="sxs-lookup"><span data-stu-id="c5d75-118">Constant</span></span>  |<span data-ttu-id="c5d75-119">Valor</span><span class="sxs-lookup"><span data-stu-id="c5d75-119">Value</span></span>  |<span data-ttu-id="c5d75-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5d75-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c5d75-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c5d75-121">0x80041008</span></span> | <span data-ttu-id="c5d75-122">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="c5d75-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="c5d75-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="c5d75-123">0x80041043</span></span> | <span data-ttu-id="c5d75-124">El `[in, out]` parámetro del método especificado en ambos el *pInSignature* y *pOutSignature* objetos tienen distintos calificadores.</span><span class="sxs-lookup"><span data-stu-id="c5d75-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="c5d75-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="c5d75-125">0x80041036</span></span> | <span data-ttu-id="c5d75-126">Falta la especificación de un parámetro de método la **ID** calificador.</span><span class="sxs-lookup"><span data-stu-id="c5d75-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="c5d75-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="c5d75-127">0x80041038</span></span> | <span data-ttu-id="c5d75-128">La serie de identificador que se asigna a los parámetros de método no es consecutiva o no empiezan en 0.</span><span class="sxs-lookup"><span data-stu-id="c5d75-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="c5d75-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="c5d75-129">0x80041039</span></span> | <span data-ttu-id="c5d75-130">El valor devuelto para un método tiene un **ID** calificador.</span><span class="sxs-lookup"><span data-stu-id="c5d75-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="c5d75-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="c5d75-131">0x80041034</span></span> | <span data-ttu-id="c5d75-132">Se intentó reutilizar un nombre de método existente de una clase principal y las firmas no coincidían.</span><span class="sxs-lookup"><span data-stu-id="c5d75-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c5d75-133">0</span><span class="sxs-lookup"><span data-stu-id="c5d75-133">0</span></span> | <span data-ttu-id="c5d75-134">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="c5d75-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c5d75-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5d75-135">Remarks</span></span>

<span data-ttu-id="c5d75-136">Esta función contiene una llamada a la [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.</span><span class="sxs-lookup"><span data-stu-id="c5d75-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="c5d75-137">Esta llamada al método solo se admite si `ptr` es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="c5d75-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="c5d75-138">Manipulación de método no está disponible en [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punteros que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="c5d75-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="c5d75-139">Los usuarios no pueden crear métodos con nombres que empiezan o terminan con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="c5d75-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="c5d75-140">Esto está reservado para las propiedades y clases del sistema.</span><span class="sxs-lookup"><span data-stu-id="c5d75-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="c5d75-141">Para un método, el `in` y `out` se describen los parámetros como propiedades en [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objetos.</span><span class="sxs-lookup"><span data-stu-id="c5d75-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="c5d75-142">Un `[in/out]` parámetros pueden definirse mediante la adición de la misma propiedad a ambos objetos al que apunta el `pInSignature` y `pOutSignature` parámetros.</span><span class="sxs-lookup"><span data-stu-id="c5d75-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="c5d75-143">En este caso, las propiedades comparten el mismo **ID** valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="c5d75-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="c5d75-144">Cada propiedad en un [__Parameters](/windows/desktop/WmiSdk/--parameters) distinto de la clase de objeto `ReturnValue` debe tener un **ID** calificador, un valor numérico de base cero que identifica el orden en que aparecen los parámetros.</span><span class="sxs-lookup"><span data-stu-id="c5d75-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="c5d75-145">No hay dos parámetros pueden tener el mismo **ID** valor y no **ID** se puede omitir el valor.</span><span class="sxs-lookup"><span data-stu-id="c5d75-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="c5d75-146">Si se produce alguna de estas condiciones, el `PutMethod` función devuelve `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="c5d75-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="c5d75-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5d75-147">Example</span></span>

<span data-ttu-id="c5d75-148">Para obtener un ejemplo, vea el [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.</span><span class="sxs-lookup"><span data-stu-id="c5d75-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c5d75-149">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5d75-149">Requirements</span></span>  
 <span data-ttu-id="c5d75-150">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5d75-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5d75-151">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c5d75-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c5d75-152">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c5d75-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d75-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5d75-153">See also</span></span>

- [<span data-ttu-id="c5d75-154">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c5d75-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
