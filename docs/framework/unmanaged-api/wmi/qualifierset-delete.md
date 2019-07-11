---
title: Función QualifierSet_Delete (referencia de API no administrada)
description: La función QualifierSet_Delete elimina un calificador por su nombre.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 956abe8ddf8075b7b8f8c057db0aa7187982e1d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782610"
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="2a274-103">QualifierSet_Delete function</span><span class="sxs-lookup"><span data-stu-id="2a274-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="2a274-104">Elimina un calificador específico por el nombre.</span><span class="sxs-lookup"><span data-stu-id="2a274-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2a274-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a274-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="2a274-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a274-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2a274-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="2a274-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="2a274-108">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="2a274-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="2a274-109">[in] El nombre del calificador que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="2a274-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="2a274-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2a274-110">Return value</span></span>

<span data-ttu-id="2a274-111">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="2a274-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2a274-112">Constante</span><span class="sxs-lookup"><span data-stu-id="2a274-112">Constant</span></span>  |<span data-ttu-id="2a274-113">Value</span><span class="sxs-lookup"><span data-stu-id="2a274-113">Value</span></span>  |<span data-ttu-id="2a274-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2a274-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2a274-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2a274-115">0x80041008</span></span> | <span data-ttu-id="2a274-116">El parámetro `wszName` no es válido.</span><span class="sxs-lookup"><span data-stu-id="2a274-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="2a274-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="2a274-117">0x80041016</span></span> | <span data-ttu-id="2a274-118">Eliminar este calificador no es válido.</span><span class="sxs-lookup"><span data-stu-id="2a274-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="2a274-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="2a274-119">0x80041002</span></span> | <span data-ttu-id="2a274-120">No se encontró el calificador especificado.</span><span class="sxs-lookup"><span data-stu-id="2a274-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2a274-121">0</span><span class="sxs-lookup"><span data-stu-id="2a274-121">0</span></span> | <span data-ttu-id="2a274-122">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="2a274-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="2a274-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="2a274-123">0x40002</span></span> | <span data-ttu-id="2a274-124">Se eliminó la invalidación local y el calificador del objeto primario original ha reanudado el ámbito.</span><span class="sxs-lookup"><span data-stu-id="2a274-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="2a274-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a274-125">Remarks</span></span>

<span data-ttu-id="2a274-126">Esta función contiene una llamada a la [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) método.</span><span class="sxs-lookup"><span data-stu-id="2a274-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="2a274-127">Debido a las reglas de propagación de calificador, un calificador determinado puede haberse se hereda de otro objeto y simplemente se reemplaza en la clase o instancia actual.</span><span class="sxs-lookup"><span data-stu-id="2a274-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="2a274-128">En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor original heredado.</span><span class="sxs-lookup"><span data-stu-id="2a274-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="2a274-129">En este caso, la función devuelve el código de estado `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="2a274-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="2a274-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a274-130">Requirements</span></span>  
 <span data-ttu-id="2a274-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a274-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a274-132">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2a274-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2a274-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2a274-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a274-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a274-134">See also</span></span>

- [<span data-ttu-id="2a274-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="2a274-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
