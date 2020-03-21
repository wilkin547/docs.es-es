---
title: Función PutMethod (Referencia de API no administrada)
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
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174919"
---
# <a name="putmethod-function"></a><span data-ttu-id="45977-103">Función PutMethod</span><span class="sxs-lookup"><span data-stu-id="45977-103">PutMethod function</span></span>
<span data-ttu-id="45977-104">Crea un método.</span><span class="sxs-lookup"><span data-stu-id="45977-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="45977-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45977-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="45977-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45977-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="45977-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="45977-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="45977-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="45977-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="45977-109">[en] El nombre del método que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="45977-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="45977-110">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="45977-110">[in] Reserved.</span></span> <span data-ttu-id="45977-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="45977-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="45977-112">[en] Puntero a una copia de la clase `in` de sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) que contiene los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="45977-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="45977-113">Este parámetro se omite `null`si se establece en .</span><span class="sxs-lookup"><span data-stu-id="45977-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="45977-114">[en]  Puntero a una copia de la clase `out` de sistema [__Parameters](/windows/desktop/WmiSdk/--parameters) que contiene los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="45977-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="45977-115">Este parámetro se omite `null`si se establece en .</span><span class="sxs-lookup"><span data-stu-id="45977-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="45977-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="45977-116">Return value</span></span>

<span data-ttu-id="45977-117">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="45977-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="45977-118">Constante</span><span class="sxs-lookup"><span data-stu-id="45977-118">Constant</span></span>  |<span data-ttu-id="45977-119">Value</span><span class="sxs-lookup"><span data-stu-id="45977-119">Value</span></span>  |<span data-ttu-id="45977-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="45977-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="45977-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="45977-121">0x80041008</span></span> | <span data-ttu-id="45977-122">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="45977-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="45977-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="45977-123">0x80041043</span></span> | <span data-ttu-id="45977-124">El `[in, out]` parámetro de método especificado en los objetos *pInSignature* y *pOutSignature* tiene calificadores diferentes.</span><span class="sxs-lookup"><span data-stu-id="45977-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="45977-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="45977-125">0x80041036</span></span> | <span data-ttu-id="45977-126">A un parámetro de método le falta la especificación del calificador **ID.**</span><span class="sxs-lookup"><span data-stu-id="45977-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="45977-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="45977-127">0x80041038</span></span> | <span data-ttu-id="45977-128">La serie de ID asignada a los parámetros del método no es consecutiva o no comienza en 0.</span><span class="sxs-lookup"><span data-stu-id="45977-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="45977-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="45977-129">0x80041039</span></span> | <span data-ttu-id="45977-130">El valor devuelto para un método tiene un calificador **de identificador.**</span><span class="sxs-lookup"><span data-stu-id="45977-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="45977-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="45977-131">0x80041034</span></span> | <span data-ttu-id="45977-132">Se ha intentado reutilizar un nombre de método existente de una clase primaria y las firmas no coinciden.</span><span class="sxs-lookup"><span data-stu-id="45977-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="45977-133">0</span><span class="sxs-lookup"><span data-stu-id="45977-133">0</span></span> | <span data-ttu-id="45977-134">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="45977-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="45977-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="45977-135">Remarks</span></span>

<span data-ttu-id="45977-136">Esta función ajusta una llamada a la [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.</span><span class="sxs-lookup"><span data-stu-id="45977-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="45977-137">Esta llamada al método `ptr` solo se admite si es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="45977-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="45977-138">La manipulación de métodos no está disponible en los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que apuntan a instancias de CIM.</span><span class="sxs-lookup"><span data-stu-id="45977-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="45977-139">Los usuarios no pueden crear métodos con nombres que comiencen o terminen con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="45977-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="45977-140">Esto está reservado para las clases y propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="45977-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="45977-141">Para un método, los `in` parámetros y `out` se describen como propiedades en [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objetos.</span><span class="sxs-lookup"><span data-stu-id="45977-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="45977-142">Un `[in/out]` parámetro se puede definir agregando la misma `pInSignature` propiedad `pOutSignature` a ambos objetos a los que apunta el y parámetros.</span><span class="sxs-lookup"><span data-stu-id="45977-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="45977-143">En este caso, las propiedades comparten el mismo valor de calificador de **ID.**</span><span class="sxs-lookup"><span data-stu-id="45977-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="45977-144">Cada propiedad de un objeto `ReturnValue` de clase [__Parameters](/windows/desktop/WmiSdk/--parameters) distinto de debe tener un calificador de **identificador,** un valor numérico de base cero que identifica el orden en el que aparecen los parámetros.</span><span class="sxs-lookup"><span data-stu-id="45977-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="45977-145">No hay dos parámetros que puedan tener el mismo valor **de ID** y no se puede omitir ningún valor de **ID.**</span><span class="sxs-lookup"><span data-stu-id="45977-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="45977-146">Si se produce `PutMethod` alguna `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`condición, la función devuelve .</span><span class="sxs-lookup"><span data-stu-id="45977-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="45977-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45977-147">Example</span></span>

<span data-ttu-id="45977-148">Para obtener un ejemplo, vea el [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) método.</span><span class="sxs-lookup"><span data-stu-id="45977-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="45977-149">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45977-149">Requirements</span></span>  
 <span data-ttu-id="45977-150">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45977-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45977-151">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="45977-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="45977-152">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45977-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45977-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45977-153">See also</span></span>

- [<span data-ttu-id="45977-154">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="45977-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
