---
title: "Función QualifierSet_Next (referencia de API no administrada)"
description: "La función QualifierSet_Next recupera el siguiente calificador en una enumeración."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 01a9c9d162039547849597aaa9c8a6fa38a31455
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="4fe93-103">QualifierSet_Next (función)</span><span class="sxs-lookup"><span data-stu-id="4fe93-103">QualifierSet_Next function</span></span>
<span data-ttu-id="4fe93-104">Recupera el siguiente calificador en una enumeración que se inició con una llamada a la [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (función).</span><span class="sxs-lookup"><span data-stu-id="4fe93-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4fe93-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fe93-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="4fe93-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fe93-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="4fe93-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="4fe93-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="4fe93-108">[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="4fe93-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="4fe93-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="4fe93-109">[in] Reserved.</span></span> <span data-ttu-id="4fe93-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="4fe93-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="4fe93-111">[out] El nombre del calificador.</span><span class="sxs-lookup"><span data-stu-id="4fe93-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="4fe93-112">Si `null`, este parámetro se omite; en caso contrario, `pstrName` no debe apuntar a válido `BSTR` o se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="4fe93-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="4fe93-113">Si no es null, la función siempre asigna un nuevo `BSTR` cuando devuelve `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="4fe93-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="4fe93-114">[out] Cuando se realiza correctamente, el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="4fe93-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="4fe93-115">Si se produce un error en la función, el `VARIANT` que señala `pVal` no se modifica.</span><span class="sxs-lookup"><span data-stu-id="4fe93-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="4fe93-116">Si este parámetro es `null`, se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="4fe93-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="4fe93-117">[out] Un puntero a un valor largo que recibe el tipo de calificador.</span><span class="sxs-lookup"><span data-stu-id="4fe93-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="4fe93-118">Si no se desea obtener información de tipo, este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="4fe93-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4fe93-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4fe93-119">Return value</span></span>

<span data-ttu-id="4fe93-120">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="4fe93-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4fe93-121">Constante</span><span class="sxs-lookup"><span data-stu-id="4fe93-121">Constant</span></span>  |<span data-ttu-id="4fe93-122">Valor</span><span class="sxs-lookup"><span data-stu-id="4fe93-122">Value</span></span>  |<span data-ttu-id="4fe93-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe93-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4fe93-124">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="4fe93-124">0x80041008</span></span> | <span data-ttu-id="4fe93-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="4fe93-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="4fe93-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4fe93-126">0x8004101d</span></span> | <span data-ttu-id="4fe93-127">El llamador no llamó a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4fe93-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4fe93-128">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="4fe93-128">0x80041006</span></span> | <span data-ttu-id="4fe93-129">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="4fe93-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="4fe93-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="4fe93-130">0x40005</span></span> | <span data-ttu-id="4fe93-131">No hay más calificadores se mantienen en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="4fe93-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4fe93-132">0</span><span class="sxs-lookup"><span data-stu-id="4fe93-132">0</span></span> | <span data-ttu-id="4fe93-133">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="4fe93-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4fe93-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fe93-134">Remarks</span></span>

<span data-ttu-id="4fe93-135">Esta función contiene una llamada a la [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="4fe93-135">This function wraps a call to the [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="4fe93-136">Se llama a la `QualifierSet_Next` función repetidamente para enumerar todos los calificadores hasta que el valor devuelto de función `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="4fe93-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="4fe93-137">Para finalizar la enumeración al principio, llame a la [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) (función).</span><span class="sxs-lookup"><span data-stu-id="4fe93-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="4fe93-138">El orden de los calificadores que se devuelve durante la enumeración es indefinido.</span><span class="sxs-lookup"><span data-stu-id="4fe93-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="4fe93-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fe93-139">Requirements</span></span>  
 <span data-ttu-id="4fe93-140">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fe93-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fe93-141">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4fe93-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4fe93-142">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4fe93-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fe93-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fe93-143">See also</span></span>  
[<span data-ttu-id="4fe93-144">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="4fe93-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
