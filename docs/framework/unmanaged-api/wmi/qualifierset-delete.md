---
title: función QualifierSet_Delete (Referencia de API no administrada)
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
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174906"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="755bb-103">Función QualifierSet_Delete</span><span class="sxs-lookup"><span data-stu-id="755bb-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="755bb-104">Elimina un calificador específico por el nombre.</span><span class="sxs-lookup"><span data-stu-id="755bb-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="755bb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="755bb-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="755bb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="755bb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="755bb-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="755bb-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="755bb-108">`ptr`[en] Puntero a una instancia de [IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="755bb-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="755bb-109">`wszName`[en] El nombre del calificador que se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="755bb-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="755bb-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="755bb-110">Return value</span></span>

<span data-ttu-id="755bb-111">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="755bb-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="755bb-112">Constante</span><span class="sxs-lookup"><span data-stu-id="755bb-112">Constant</span></span>  |<span data-ttu-id="755bb-113">Value</span><span class="sxs-lookup"><span data-stu-id="755bb-113">Value</span></span>  |<span data-ttu-id="755bb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="755bb-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="755bb-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="755bb-115">0x80041008</span></span> | <span data-ttu-id="755bb-116">El parámetro `wszName` no es válido.</span><span class="sxs-lookup"><span data-stu-id="755bb-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="755bb-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="755bb-117">0x80041016</span></span> | <span data-ttu-id="755bb-118">Eliminar este calificador es ilegal.</span><span class="sxs-lookup"><span data-stu-id="755bb-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="755bb-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="755bb-119">0x80041002</span></span> | <span data-ttu-id="755bb-120">No se encontró el calificador especificado.</span><span class="sxs-lookup"><span data-stu-id="755bb-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="755bb-121">0</span><span class="sxs-lookup"><span data-stu-id="755bb-121">0</span></span> | <span data-ttu-id="755bb-122">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="755bb-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="755bb-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="755bb-123">0x40002</span></span> | <span data-ttu-id="755bb-124">Se eliminó la invalidación local y el calificador original del objeto primario ha reanudado el ámbito.</span><span class="sxs-lookup"><span data-stu-id="755bb-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="755bb-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="755bb-125">Remarks</span></span>

<span data-ttu-id="755bb-126">Esta función ajusta una llamada a la [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) método.</span><span class="sxs-lookup"><span data-stu-id="755bb-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="755bb-127">Debido a las reglas de propagación de calificadores, un calificador determinado puede haber sido heredado de otro objeto y simplemente invalidado en la clase o instancia actual.</span><span class="sxs-lookup"><span data-stu-id="755bb-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="755bb-128">En este caso, el `QualifierSet_Delete` método restablece el calificador a su valor heredado original.</span><span class="sxs-lookup"><span data-stu-id="755bb-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="755bb-129">La función en este `WBEM_S_RESET_TO_DEFAULT`caso devuelve el código de estado .</span><span class="sxs-lookup"><span data-stu-id="755bb-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="755bb-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="755bb-130">Requirements</span></span>  
 <span data-ttu-id="755bb-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="755bb-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="755bb-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="755bb-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="755bb-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="755bb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="755bb-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="755bb-134">See also</span></span>

- [<span data-ttu-id="755bb-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="755bb-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
