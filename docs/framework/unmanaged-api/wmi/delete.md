---
title: Delete (función) (referencia de API no administrada)
description: La función de eliminación elimina la propiedad especificada y todas sus calificadores de una definición de clase CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 791e75aa60fd651dde1555339e31664a3523e1eb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554392"
---
# <a name="delete-function"></a><span data-ttu-id="c4bfc-103">Delete (función)</span><span class="sxs-lookup"><span data-stu-id="c4bfc-103">Delete function</span></span>
<span data-ttu-id="c4bfc-104">Elimina la propiedad especificada y todas sus calificadores de una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c4bfc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4bfc-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="c4bfc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4bfc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c4bfc-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c4bfc-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="c4bfc-109">[in] El nombre de la propiedad que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="c4bfc-110">`wszName` debe ser un puntero a una `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c4bfc-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c4bfc-111">Return value</span></span>

<span data-ttu-id="c4bfc-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="c4bfc-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c4bfc-113">Constante</span><span class="sxs-lookup"><span data-stu-id="c4bfc-113">Constant</span></span>  |<span data-ttu-id="c4bfc-114">Valor</span><span class="sxs-lookup"><span data-stu-id="c4bfc-114">Value</span></span>  |<span data-ttu-id="c4bfc-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4bfc-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c4bfc-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="c4bfc-116">0x80041001</span></span> | <span data-ttu-id="c4bfc-117">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="c4bfc-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="c4bfc-118">0x80041016</span></span> | <span data-ttu-id="c4bfc-119">No se puede eliminar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c4bfc-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="c4bfc-120">0x80041008</span></span> | <span data-ttu-id="c4bfc-121">`wszzName` no es válido.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="c4bfc-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c4bfc-122">0x80041002</span></span> | <span data-ttu-id="c4bfc-123">La propiedad especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c4bfc-124">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="c4bfc-124">0x80041006</span></span> | <span data-ttu-id="c4bfc-125">No hay memoria suficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="c4bfc-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="c4bfc-126">0x8004101c</span></span> | <span data-ttu-id="c4bfc-127">La propiedad se hereda de una clase base.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="c4bfc-128">La propiedad es una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c4bfc-129">0</span><span class="sxs-lookup"><span data-stu-id="c4bfc-129">0</span></span> | <span data-ttu-id="c4bfc-130">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="c4bfc-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="c4bfc-131">0x80041030</span></span> | <span data-ttu-id="c4bfc-132">La función eliminó un valor predeterminado de invalidación de la clase actual.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="c4bfc-133">El valor predeterminado para esta propiedad en la clase primaria ha sido reactiviated.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="c4bfc-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4bfc-134">Remarks</span></span>

<span data-ttu-id="c4bfc-135">Esta función contiene una llamada a la [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) método.</span><span class="sxs-lookup"><span data-stu-id="c4bfc-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4bfc-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4bfc-136">Requirements</span></span>  
 <span data-ttu-id="c4bfc-137">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4bfc-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4bfc-138">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c4bfc-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c4bfc-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c4bfc-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4bfc-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4bfc-140">See also</span></span>  
[<span data-ttu-id="c4bfc-141">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c4bfc-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
