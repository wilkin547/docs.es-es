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
ms.openlocfilehash: 75bf52fbf9552dc464d9c646f0a2b1bc01cf89c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723334"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="b5474-103">Función GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="b5474-103">GetQualifierSet function</span></span>
<span data-ttu-id="b5474-104">Recupera el calificador establecido para una instancia o una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="b5474-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b5474-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5474-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="b5474-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5474-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b5474-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="b5474-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b5474-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="b5474-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="b5474-109">[out] Recibe el puntero de interfaz que permite el acceso a los calificadores del objeto de clase.</span><span class="sxs-lookup"><span data-stu-id="b5474-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="b5474-110">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="b5474-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="b5474-111">Si se produce un error, no se devuelve un nuevo objeto y el puntero se deja sin modificar.</span><span class="sxs-lookup"><span data-stu-id="b5474-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="b5474-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b5474-112">Return value</span></span>

<span data-ttu-id="b5474-113">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b5474-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b5474-114">Constante</span><span class="sxs-lookup"><span data-stu-id="b5474-114">Constant</span></span>  |<span data-ttu-id="b5474-115">Valor</span><span class="sxs-lookup"><span data-stu-id="b5474-115">Value</span></span>  |<span data-ttu-id="b5474-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="b5474-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="b5474-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b5474-117">0x80041001</span></span> | <span data-ttu-id="b5474-118">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="b5474-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="b5474-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="b5474-119">0x80041002</span></span> | <span data-ttu-id="b5474-120">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="b5474-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b5474-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b5474-121">0x80041006</span></span> | <span data-ttu-id="b5474-122">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="b5474-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b5474-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b5474-123">0x80041008</span></span> | <span data-ttu-id="b5474-124">Es un parámetro `null`.</span><span class="sxs-lookup"><span data-stu-id="b5474-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b5474-125">0</span><span class="sxs-lookup"><span data-stu-id="b5474-125">0</span></span> | <span data-ttu-id="b5474-126">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="b5474-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b5474-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5474-127">Remarks</span></span>

<span data-ttu-id="b5474-128">Esta función contiene una llamada a la [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) método.</span><span class="sxs-lookup"><span data-stu-id="b5474-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="b5474-129">El [IWbemQualifierSet puntero](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="b5474-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="b5474-130">Estos calificadores agregados, modificados o eliminados se aplican a toda la definición de clase o instancia.</span><span class="sxs-lookup"><span data-stu-id="b5474-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="b5474-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5474-131">Requirements</span></span>  
<span data-ttu-id="b5474-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5474-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5474-133">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b5474-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b5474-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b5474-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5474-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5474-135">See also</span></span>

- [<span data-ttu-id="b5474-136">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b5474-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
