---
title: GetMethodQualifierSet (función) (referencia de API no administrada)
description: GetMethodQualifierSet (función) recupera el conjunto de calificadores de un método.
ms.date: 11/06/2017
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
ms.openlocfilehash: a363591f5db7a2dbcba1147df35d8c023c9b0707
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001414"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="935fe-103">GetMethodQualifierSet (función)</span><span class="sxs-lookup"><span data-stu-id="935fe-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="935fe-104">Recupera el calificador establecido para un método concreto.</span><span class="sxs-lookup"><span data-stu-id="935fe-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="935fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="935fe-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="935fe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="935fe-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="935fe-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="935fe-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="935fe-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="935fe-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`  
<span data-ttu-id="935fe-109">[in] El nombre del método.</span><span class="sxs-lookup"><span data-stu-id="935fe-109">[in] The method  name.</span></span> <span data-ttu-id="935fe-110">`wszMethod` debe apuntar a una `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="935fe-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="935fe-111">[out] Recibe el puntero de interfaz que permite el acceso a los calificadores del método.</span><span class="sxs-lookup"><span data-stu-id="935fe-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="935fe-112">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="935fe-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="935fe-113">Si se produce un error, no se devuelve un nuevo objeto y el puntero se establece para que apunte a `null`.</span><span class="sxs-lookup"><span data-stu-id="935fe-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="935fe-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="935fe-114">Return value</span></span>

<span data-ttu-id="935fe-115">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="935fe-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="935fe-116">Constante</span><span class="sxs-lookup"><span data-stu-id="935fe-116">Constant</span></span>  |<span data-ttu-id="935fe-117">Valor</span><span class="sxs-lookup"><span data-stu-id="935fe-117">Value</span></span>  |<span data-ttu-id="935fe-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="935fe-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="935fe-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="935fe-119">0x80041002</span></span> | <span data-ttu-id="935fe-120">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="935fe-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="935fe-121">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="935fe-121">0x80041008</span></span> | <span data-ttu-id="935fe-122">Es un parámetro `null`.</span><span class="sxs-lookup"><span data-stu-id="935fe-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="935fe-123">0</span><span class="sxs-lookup"><span data-stu-id="935fe-123">0</span></span> | <span data-ttu-id="935fe-124">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="935fe-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="935fe-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="935fe-125">Remarks</span></span>

<span data-ttu-id="935fe-126">Esta función contiene una llamada a la [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) método.</span><span class="sxs-lookup"><span data-stu-id="935fe-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span> 

<span data-ttu-id="935fe-127">Una llamada a esta función solo se admite si el objeto actual es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="935fe-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="935fe-128">No está disponible para la manipulación de los métodos [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="935fe-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters that point to CIM instances.</span></span>

<span data-ttu-id="935fe-129">Dado que cada método puede tener su propio calificadores, el [IWbemQualifierSet puntero](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="935fe-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="935fe-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="935fe-130">Requirements</span></span>  
<span data-ttu-id="935fe-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="935fe-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="935fe-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="935fe-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="935fe-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="935fe-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="935fe-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="935fe-134">See also</span></span>  
[<span data-ttu-id="935fe-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="935fe-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
