---
title: "Función GetPropertyQualifierSet (referencia de API no administrada)"
description: "La función GetPropertyQualifierSet recupera el calificador establecido para una propiedad."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyQualifierSet
helpviewer_keywords: GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ca2981c8833abaafd5d206b66d6e91f34e2c91d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="b5dab-103">GetPropertyQualifierSet (función)</span><span class="sxs-lookup"><span data-stu-id="b5dab-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="b5dab-104">Recupera el calificador establecido para una propiedad determinada.</span><span class="sxs-lookup"><span data-stu-id="b5dab-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b5dab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5dab-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="b5dab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5dab-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b5dab-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b5dab-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b5dab-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="b5dab-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="b5dab-109">[in] El nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b5dab-109">[in] The property  name.</span></span> <span data-ttu-id="b5dab-110">`wszProperty`debe apuntar a válido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="b5dab-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="b5dab-111">[out] Recibe el puntero de interfaz que permite el acceso a los calificadores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b5dab-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="b5dab-112">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b5dab-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="b5dab-113">Si se produce un error, no se devuelve un nuevo objeto y el puntero se establece para que apunte a `null`.</span><span class="sxs-lookup"><span data-stu-id="b5dab-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="b5dab-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b5dab-114">Return value</span></span>

<span data-ttu-id="b5dab-115">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b5dab-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b5dab-116">Constante</span><span class="sxs-lookup"><span data-stu-id="b5dab-116">Constant</span></span>  |<span data-ttu-id="b5dab-117">Valor</span><span class="sxs-lookup"><span data-stu-id="b5dab-117">Value</span></span>  |<span data-ttu-id="b5dab-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5dab-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b5dab-119">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="b5dab-119">0x80041001</span></span> | <span data-ttu-id="b5dab-120">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="b5dab-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="b5dab-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b5dab-121">0x80041002</span></span> | <span data-ttu-id="b5dab-122">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="b5dab-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b5dab-123">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="b5dab-123">0x80041006</span></span> | <span data-ttu-id="b5dab-124">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b5dab-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b5dab-125">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="b5dab-125">0x80041008</span></span> | <span data-ttu-id="b5dab-126">Un parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="b5dab-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="b5dab-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="b5dab-127">0x80041030</span></span> | <span data-ttu-id="b5dab-128">La función intenta obtener calificadores de una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="b5dab-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b5dab-129">0</span><span class="sxs-lookup"><span data-stu-id="b5dab-129">0</span></span> | <span data-ttu-id="b5dab-130">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="b5dab-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b5dab-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5dab-131">Remarks</span></span>

<span data-ttu-id="b5dab-132">Esta función contiene una llamada a la [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="b5dab-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="b5dab-133">Una llamada a esta función solo se admite si el objeto actual es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="b5dab-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="b5dab-134">No está disponible para la manipulación de los métodos [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters que apuntan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="b5dab-134">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="b5dab-135">Dado que cada método puede tener sus propio calificadores, el [IWbemQualifierSet puntero](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="b5dab-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="b5dab-136">Como propiedades del sistema no tengan ningún calificador, la función devuelve `WBEM_E_SYSTEM_PROPERTY` si se intenta obtener un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) puntero para una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="b5dab-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="b5dab-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5dab-137">Requirements</span></span>  
<span data-ttu-id="b5dab-138">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5dab-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5dab-139">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b5dab-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b5dab-140">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b5dab-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5dab-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5dab-141">See also</span></span>  
[<span data-ttu-id="b5dab-142">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b5dab-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
