---
title: Función PutMethod (referencia de la API no administrada)
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
ms.openlocfilehash: 1d409507de593cf198fe87340eece6820eaefc63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127342"
---
# <a name="putmethod-function"></a><span data-ttu-id="5b657-103">PutMethod función)</span><span class="sxs-lookup"><span data-stu-id="5b657-103">PutMethod function</span></span>
<span data-ttu-id="5b657-104">Crea un método.</span><span class="sxs-lookup"><span data-stu-id="5b657-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5b657-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b657-105">Syntax</span></span>  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="5b657-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5b657-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5b657-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5b657-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5b657-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5b657-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="5b657-109">de Nombre del método que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="5b657-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="5b657-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="5b657-110">[in] Reserved.</span></span> <span data-ttu-id="5b657-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="5b657-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="5b657-112">de Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene los parámetros del `in` para el método.</span><span class="sxs-lookup"><span data-stu-id="5b657-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="5b657-113">Se omite este parámetro si se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="5b657-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="5b657-114">de  Un puntero a una copia de la [clase del sistema __Parameters](/windows/desktop/WmiSdk/--parameters) que contiene los parámetros del `out` para el método.</span><span class="sxs-lookup"><span data-stu-id="5b657-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="5b657-115">Se omite este parámetro si se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="5b657-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5b657-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5b657-116">Return value</span></span>

<span data-ttu-id="5b657-117">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="5b657-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5b657-118">Constante</span><span class="sxs-lookup"><span data-stu-id="5b657-118">Constant</span></span>  |<span data-ttu-id="5b657-119">Valor</span><span class="sxs-lookup"><span data-stu-id="5b657-119">Value</span></span>  |<span data-ttu-id="5b657-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b657-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5b657-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5b657-121">0x80041008</span></span> | <span data-ttu-id="5b657-122">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="5b657-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="5b657-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="5b657-123">0x80041043</span></span> | <span data-ttu-id="5b657-124">El parámetro de método `[in, out]` especificado en los objetos *pInSignature* y *pOutSignature* tiene calificadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="5b657-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="5b657-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="5b657-125">0x80041036</span></span> | <span data-ttu-id="5b657-126">Falta la especificación del calificador de **identificador** en un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="5b657-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="5b657-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="5b657-127">0x80041038</span></span> | <span data-ttu-id="5b657-128">La serie de IDENTIFICADOres que se asigna a los parámetros de método no es consecutiva o no comienza en 0.</span><span class="sxs-lookup"><span data-stu-id="5b657-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="5b657-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="5b657-129">0x80041039</span></span> | <span data-ttu-id="5b657-130">El valor devuelto para un método tiene un calificador de **identificador** .</span><span class="sxs-lookup"><span data-stu-id="5b657-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="5b657-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="5b657-131">0x80041034</span></span> | <span data-ttu-id="5b657-132">Se intentó reutilizar un nombre de método existente de una clase primaria y las firmas no coincidían.</span><span class="sxs-lookup"><span data-stu-id="5b657-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5b657-133">0</span><span class="sxs-lookup"><span data-stu-id="5b657-133">0</span></span> | <span data-ttu-id="5b657-134">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5b657-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="5b657-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b657-135">Remarks</span></span>

<span data-ttu-id="5b657-136">Esta función contiene una llamada al método [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .</span><span class="sxs-lookup"><span data-stu-id="5b657-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="5b657-137">Esta llamada al método solo se admite si `ptr` es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="5b657-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="5b657-138">La manipulación de métodos no está disponible en los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="5b657-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="5b657-139">Los usuarios no pueden crear métodos con nombres que comiencen o terminen con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="5b657-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="5b657-140">Está reservado para las propiedades y clases del sistema.</span><span class="sxs-lookup"><span data-stu-id="5b657-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="5b657-141">Para un método, los parámetros `in` y `out` se describen como propiedades en objetos [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5b657-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="5b657-142">Un parámetro `[in/out]` se puede definir agregando la misma propiedad a ambos objetos a los que apuntan los parámetros `pInSignature` y `pOutSignature`.</span><span class="sxs-lookup"><span data-stu-id="5b657-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="5b657-143">En este caso, las propiedades comparten el mismo valor de calificador de **identificador** .</span><span class="sxs-lookup"><span data-stu-id="5b657-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="5b657-144">Cada propiedad de un objeto de clase [__Parameters](/windows/desktop/WmiSdk/--parameters) que no sea `ReturnValue` debe tener un calificador de **identificador** , un valor numérico basado en cero que identifique el orden en el que aparecen los parámetros.</span><span class="sxs-lookup"><span data-stu-id="5b657-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="5b657-145">Dos parámetros no pueden tener el mismo valor de **identificador** y no se puede omitir ningún valor de **identificador** .</span><span class="sxs-lookup"><span data-stu-id="5b657-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="5b657-146">Si se produce alguna de estas condiciones, la función `PutMethod` devuelve `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span><span class="sxs-lookup"><span data-stu-id="5b657-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="5b657-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b657-147">Example</span></span>

<span data-ttu-id="5b657-148">Para obtener un ejemplo, vea el método [IWbemClassObject::P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) .</span><span class="sxs-lookup"><span data-stu-id="5b657-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b657-149">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b657-149">Requirements</span></span>  
 <span data-ttu-id="5b657-150">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b657-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b657-151">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="5b657-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5b657-152">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5b657-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b657-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b657-153">See also</span></span>

- [<span data-ttu-id="5b657-154">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="5b657-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
