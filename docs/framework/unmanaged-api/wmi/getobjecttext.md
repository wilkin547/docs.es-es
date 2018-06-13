---
title: Función GetObjectText (referencia de API no administrada)
description: La función GetObjectText devuelve una representación textual de un objeto en la sintaxis MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2f0e766a3a310bdb58f7cbffd8d49404eb5e0b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459644"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="46c02-103">GetObjectText (función)</span><span class="sxs-lookup"><span data-stu-id="46c02-103">GetObjectText function</span></span>
<span data-ttu-id="46c02-104">Devuelve una representación textual del objeto en la sintaxis de Managed Object Format (MOF).</span><span class="sxs-lookup"><span data-stu-id="46c02-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="46c02-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46c02-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="46c02-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46c02-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="46c02-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="46c02-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="46c02-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="46c02-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="46c02-109">[in] Normalmente 0.</span><span class="sxs-lookup"><span data-stu-id="46c02-109">[in] Normally 0.</span></span> <span data-ttu-id="46c02-110">Si `WBEM_FLAG_NO_FLAVORS` (o 0 x 1) se especifica, se incluyen sin información de propagación o flavor calificadores.</span><span class="sxs-lookup"><span data-stu-id="46c02-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="46c02-111">[out] Un puntero a un `null` en la entrada.</span><span class="sxs-lookup"><span data-stu-id="46c02-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="46c02-112">Devuelve un recién asignado `BSTR` que contiene una representación de la sintaxis MOF del objeto.</span><span class="sxs-lookup"><span data-stu-id="46c02-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="46c02-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="46c02-113">Return value</span></span>

<span data-ttu-id="46c02-114">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="46c02-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="46c02-115">Constante</span><span class="sxs-lookup"><span data-stu-id="46c02-115">Constant</span></span>  |<span data-ttu-id="46c02-116">Valor</span><span class="sxs-lookup"><span data-stu-id="46c02-116">Value</span></span>  |<span data-ttu-id="46c02-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="46c02-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="46c02-118">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="46c02-118">0x80041001</span></span> | <span data-ttu-id="46c02-119">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="46c02-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="46c02-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="46c02-120">0x80041008</span></span> | <span data-ttu-id="46c02-121">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="46c02-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="46c02-122">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="46c02-122">0x80041006</span></span> | <span data-ttu-id="46c02-123">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="46c02-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="46c02-124">0</span><span class="sxs-lookup"><span data-stu-id="46c02-124">0</span></span> | <span data-ttu-id="46c02-125">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="46c02-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="46c02-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46c02-126">Remarks</span></span>

<span data-ttu-id="46c02-127">Esta función contiene una llamada a la [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="46c02-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="46c02-128">El texto MOF devuelto no contiene toda la información sobre el objeto, pero únicamente la información suficiente para que el compilador MOF poder volver a crear el objeto original.</span><span class="sxs-lookup"><span data-stu-id="46c02-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="46c02-129">Por ejemplo, no propagados calificadores o propiedades de la clase primaria se incluyen.</span><span class="sxs-lookup"><span data-stu-id="46c02-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="46c02-130">El siguiente algoritmo se utiliza para reconstruir el texto de los parámetros de un método:</span><span class="sxs-lookup"><span data-stu-id="46c02-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="46c02-131">Se cambia la secuencia de parámetros en el orden de sus valores de identificador.</span><span class="sxs-lookup"><span data-stu-id="46c02-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="46c02-132">Parámetros que se especifican como `[in]` y `[out]` se combinan en un solo parámetro.</span><span class="sxs-lookup"><span data-stu-id="46c02-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="46c02-133">`pstrObjectText` debe ser un puntero a un `null` cuando se llama a la función; no debe apuntar a una cadena que es válida antes de la llamada al método, porque el puntero no se cancela la asignación.</span><span class="sxs-lookup"><span data-stu-id="46c02-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="46c02-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46c02-134">Requirements</span></span>  
<span data-ttu-id="46c02-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46c02-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46c02-136">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="46c02-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="46c02-137">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46c02-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46c02-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="46c02-138">See also</span></span>  
[<span data-ttu-id="46c02-139">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="46c02-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
