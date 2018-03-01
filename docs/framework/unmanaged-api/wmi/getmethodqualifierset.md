---
title: "Función GetMethodQualifierSet (referencia de API no administrada)"
description: "La función GetMethodQualifierSet recupera el conjunto de calificadores de un método."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2999bef31576cf2bc025868260c2b1782a9b69f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="8b4a1-103">GetMethodQualifierSet (función)</span><span class="sxs-lookup"><span data-stu-id="8b4a1-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="8b4a1-104">Recupera el calificador establecido para un método concreto.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8b4a1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b4a1-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="8b4a1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b4a1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8b4a1-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8b4a1-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="8b4a1-109">[in] El nombre del método.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-109">[in] The method  name.</span></span> <span data-ttu-id="8b4a1-110">`wszMethod`debe apuntar a válido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="8b4a1-111">[out] Recibe el puntero de interfaz que permite el acceso a los calificadores del método.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="8b4a1-112">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="8b4a1-113">Si se produce un error, no se devuelve un nuevo objeto y el puntero se establece para que apunte a `null`.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="8b4a1-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8b4a1-114">Return value</span></span>

<span data-ttu-id="8b4a1-115">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="8b4a1-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8b4a1-116">Constante</span><span class="sxs-lookup"><span data-stu-id="8b4a1-116">Constant</span></span>  |<span data-ttu-id="8b4a1-117">Valor</span><span class="sxs-lookup"><span data-stu-id="8b4a1-117">Value</span></span>  |<span data-ttu-id="8b4a1-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b4a1-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="8b4a1-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8b4a1-119">0x80041002</span></span> | <span data-ttu-id="8b4a1-120">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8b4a1-121">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="8b4a1-121">0x80041008</span></span> | <span data-ttu-id="8b4a1-122">Un parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8b4a1-123">0</span><span class="sxs-lookup"><span data-stu-id="8b4a1-123">0</span></span> | <span data-ttu-id="8b4a1-124">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8b4a1-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b4a1-125">Remarks</span></span>

<span data-ttu-id="8b4a1-126">Esta función contiene una llamada a la [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="8b4a1-127">Una llamada a esta función solo se admite si el objeto actual es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="8b4a1-128">No está disponible para la manipulación de los métodos [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters que apuntan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-128">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="8b4a1-129">Dado que cada método puede tener sus propio calificadores, el [IWbemQualifierSet puntero](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="8b4a1-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b4a1-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b4a1-130">Requirements</span></span>  
<span data-ttu-id="8b4a1-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b4a1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b4a1-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8b4a1-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8b4a1-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8b4a1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b4a1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b4a1-134">See also</span></span>  
[<span data-ttu-id="8b4a1-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="8b4a1-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
