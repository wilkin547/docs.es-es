---
title: Función QualifierSet_Delete (referencia de la API no administrada)
description: La función QualifierSet_Delete elimina un calificador por nombre.
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
ms.openlocfilehash: 2000de77903c3dabb43116fa1700b4ed393aeb5a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721158"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="bb299-103">Función QualifierSet_Delete</span><span class="sxs-lookup"><span data-stu-id="bb299-103">QualifierSet_Delete function</span></span>

<span data-ttu-id="bb299-104">Elimina un calificador específico por el nombre.</span><span class="sxs-lookup"><span data-stu-id="bb299-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bb299-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb299-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="bb299-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb299-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bb299-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="bb299-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="bb299-108">`ptr` de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="bb299-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="bb299-109">`wszName` de Nombre del calificador que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="bb299-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="bb299-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bb299-110">Return value</span></span>

<span data-ttu-id="bb299-111">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="bb299-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bb299-112">Constante</span><span class="sxs-lookup"><span data-stu-id="bb299-112">Constant</span></span>  |<span data-ttu-id="bb299-113">Value</span><span class="sxs-lookup"><span data-stu-id="bb299-113">Value</span></span>  |<span data-ttu-id="bb299-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb299-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bb299-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bb299-115">0x80041008</span></span> | <span data-ttu-id="bb299-116">El parámetro `wszName` no es válido.</span><span class="sxs-lookup"><span data-stu-id="bb299-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="bb299-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="bb299-117">0x80041016</span></span> | <span data-ttu-id="bb299-118">No se pudo eliminar este calificador.</span><span class="sxs-lookup"><span data-stu-id="bb299-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="bb299-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="bb299-119">0x80041002</span></span> | <span data-ttu-id="bb299-120">No se encontró el calificador especificado.</span><span class="sxs-lookup"><span data-stu-id="bb299-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bb299-121">0</span><span class="sxs-lookup"><span data-stu-id="bb299-121">0</span></span> | <span data-ttu-id="bb299-122">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="bb299-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="bb299-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="bb299-123">0x40002</span></span> | <span data-ttu-id="bb299-124">Se eliminó la invalidación local y el calificador original del objeto primario ha reanudado el ámbito.</span><span class="sxs-lookup"><span data-stu-id="bb299-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="bb299-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb299-125">Remarks</span></span>

<span data-ttu-id="bb299-126">Esta función contiene una llamada al método [IWbemQualifierSet::D iminar](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) .</span><span class="sxs-lookup"><span data-stu-id="bb299-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="bb299-127">Debido a las reglas de propagación del calificador, un calificador determinado se puede haber heredado de otro objeto y simplemente se ha invalidado en la clase o instancia actual.</span><span class="sxs-lookup"><span data-stu-id="bb299-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="bb299-128">En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor heredado original.</span><span class="sxs-lookup"><span data-stu-id="bb299-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="bb299-129">En este caso, la función devuelve el código de estado `WBEM_S_RESET_TO_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="bb299-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb299-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb299-130">Requirements</span></span>  

 <span data-ttu-id="bb299-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb299-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb299-132">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="bb299-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bb299-133">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb299-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb299-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb299-134">See also</span></span>

- [<span data-ttu-id="bb299-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="bb299-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
