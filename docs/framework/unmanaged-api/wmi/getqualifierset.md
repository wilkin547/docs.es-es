---
title: Función GetQualifierSet (referencia de API no administrada)
description: La función GetQualifierSet recupera el calificador establecido para una instancia o clase.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 635dc7605af00f2662a9f9553adefafcd25f9452
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079469"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="f8875-103">Función GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="f8875-103">GetQualifierSet function</span></span>
<span data-ttu-id="f8875-104">Recupera el calificador establecido para una instancia o una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="f8875-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f8875-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8875-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="f8875-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8875-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f8875-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="f8875-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f8875-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="f8875-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="f8875-109">[out] Recibe el puntero de interfaz que permite el acceso a los calificadores del objeto de clase.</span><span class="sxs-lookup"><span data-stu-id="f8875-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="f8875-110">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="f8875-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="f8875-111">Si se produce un error, no se devuelve un nuevo objeto y el puntero se deja sin modificar.</span><span class="sxs-lookup"><span data-stu-id="f8875-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f8875-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f8875-112">Return value</span></span>

<span data-ttu-id="f8875-113">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="f8875-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f8875-114">Constante</span><span class="sxs-lookup"><span data-stu-id="f8875-114">Constant</span></span>  |<span data-ttu-id="f8875-115">Valor</span><span class="sxs-lookup"><span data-stu-id="f8875-115">Value</span></span>  |<span data-ttu-id="f8875-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8875-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="f8875-117">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="f8875-117">0x80041001</span></span> | <span data-ttu-id="f8875-118">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="f8875-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="f8875-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="f8875-119">0x80041002</span></span> | <span data-ttu-id="f8875-120">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="f8875-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f8875-121">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="f8875-121">0x80041006</span></span> | <span data-ttu-id="f8875-122">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="f8875-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f8875-123">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="f8875-123">0x80041008</span></span> | <span data-ttu-id="f8875-124">Es un parámetro `null`.</span><span class="sxs-lookup"><span data-stu-id="f8875-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f8875-125">0</span><span class="sxs-lookup"><span data-stu-id="f8875-125">0</span></span> | <span data-ttu-id="f8875-126">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="f8875-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f8875-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8875-127">Remarks</span></span>

<span data-ttu-id="f8875-128">Esta función contiene una llamada a la [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) método.</span><span class="sxs-lookup"><span data-stu-id="f8875-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="f8875-129">El [IWbemQualifierSet puntero](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="f8875-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="f8875-130">Estos calificadores agregados, modificados o eliminados se aplican a toda la definición de clase o instancia.</span><span class="sxs-lookup"><span data-stu-id="f8875-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="f8875-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8875-131">Requirements</span></span>  
<span data-ttu-id="f8875-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8875-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8875-133">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f8875-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f8875-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f8875-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8875-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8875-135">See also</span></span>  
[<span data-ttu-id="f8875-136">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="f8875-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
