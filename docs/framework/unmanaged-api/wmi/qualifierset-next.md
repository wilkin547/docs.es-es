---
title: función QualifierSet_Next (Referencia de API no administrada)
description: La función QualifierSet_Next recupera el siguiente calificador de una enumeración.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174880"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="b3c02-103">Función QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="b3c02-103">QualifierSet_Next function</span></span>
<span data-ttu-id="b3c02-104">Recupera el siguiente calificador en una enumeración que se inició con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b3c02-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b3c02-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3c02-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="b3c02-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3c02-106">Parameters</span></span>

<span data-ttu-id="b3c02-107">`vFunc`[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b3c02-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="b3c02-108">`ptr`[en] Puntero a una instancia de [IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="b3c02-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="b3c02-109">`lFlags`[en] Reservados.</span><span class="sxs-lookup"><span data-stu-id="b3c02-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="b3c02-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="b3c02-110">This parameter must be 0.</span></span>

<span data-ttu-id="b3c02-111">`pstrName`[fuera] El nombre del calificador.</span><span class="sxs-lookup"><span data-stu-id="b3c02-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="b3c02-112">Si `null`, se omite este parámetro; de `pstrName` lo contrario, no `BSTR` debe apuntar a una pérdida de memoria válida o se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="b3c02-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="b3c02-113">Si no es null, la `BSTR` función `WBEM_S_NO_ERROR`siempre asigna un nuevo cuando devuelve .</span><span class="sxs-lookup"><span data-stu-id="b3c02-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="b3c02-114">`pVal`[fuera] Cuando se realiza correctamente, el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="b3c02-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="b3c02-115">Si se produce `VARIANT` un error `pVal` en la función, no se modifica el punto por.</span><span class="sxs-lookup"><span data-stu-id="b3c02-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="b3c02-116">Si este `null`parámetro es , se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="b3c02-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="b3c02-117">`plFlavor`[fuera] Un puntero a un LONG que recibe el sabor del calificador.</span><span class="sxs-lookup"><span data-stu-id="b3c02-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="b3c02-118">Si no se desea información de `null`sabor, este parámetro puede ser .</span><span class="sxs-lookup"><span data-stu-id="b3c02-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b3c02-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b3c02-119">Return value</span></span>

<span data-ttu-id="b3c02-120">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b3c02-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b3c02-121">Constante</span><span class="sxs-lookup"><span data-stu-id="b3c02-121">Constant</span></span>  |<span data-ttu-id="b3c02-122">Value</span><span class="sxs-lookup"><span data-stu-id="b3c02-122">Value</span></span>  |<span data-ttu-id="b3c02-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3c02-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b3c02-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b3c02-124">0x80041008</span></span> | <span data-ttu-id="b3c02-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="b3c02-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="b3c02-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="b3c02-126">0x8004101d</span></span> | <span data-ttu-id="b3c02-127">El autor de la llamada no llamó a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b3c02-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b3c02-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b3c02-128">0x80041006</span></span> | <span data-ttu-id="b3c02-129">No hay suficiente memoria disponible para comenzar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="b3c02-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="b3c02-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="b3c02-130">0x40005</span></span> | <span data-ttu-id="b3c02-131">No quedan más calificadores en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b3c02-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b3c02-132">0</span><span class="sxs-lookup"><span data-stu-id="b3c02-132">0</span></span> | <span data-ttu-id="b3c02-133">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b3c02-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b3c02-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b3c02-134">Remarks</span></span>

<span data-ttu-id="b3c02-135">Esta función ajusta una llamada a la [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) método.</span><span class="sxs-lookup"><span data-stu-id="b3c02-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="b3c02-136">Llamar a `QualifierSet_Next` la función repetidamente para enumerar todos `WBEM_S_NO_MORE_DATA`los calificadores hasta que la función devuelve .</span><span class="sxs-lookup"><span data-stu-id="b3c02-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="b3c02-137">Para finalizar la enumeración antes de tiempo, llame a la [función QualifierSet_EndEnumeration.](qualifierset-endenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="b3c02-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="b3c02-138">El orden de los calificadores devueltos durante la enumeración es indefinido.</span><span class="sxs-lookup"><span data-stu-id="b3c02-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3c02-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3c02-139">Requirements</span></span>  
 <span data-ttu-id="b3c02-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3c02-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c02-141">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b3c02-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b3c02-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b3c02-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c02-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3c02-143">See also</span></span>

- [<span data-ttu-id="b3c02-144">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b3c02-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
