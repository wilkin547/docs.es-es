---
title: Función QualifierSet_Next (referencia de API no administrada)
description: La función QualifierSet_Next recupera el siguiente calificador en una enumeración.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35ab5b64b3c7e364e0dd11c002b87a0a413f4335
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532440"
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="1ae44-103">QualifierSet_Next function</span><span class="sxs-lookup"><span data-stu-id="1ae44-103">QualifierSet_Next function</span></span>
<span data-ttu-id="1ae44-104">Recupera el siguiente calificador en una enumeración que se inició con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1ae44-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1ae44-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ae44-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="1ae44-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ae44-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="1ae44-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="1ae44-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="1ae44-108">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="1ae44-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="1ae44-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="1ae44-109">[in] Reserved.</span></span> <span data-ttu-id="1ae44-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="1ae44-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="1ae44-111">[out] El nombre del calificador.</span><span class="sxs-lookup"><span data-stu-id="1ae44-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="1ae44-112">Si `null`, este parámetro se omite; en caso contrario, `pstrName` no debe apuntar a una `BSTR` o se produce una pérdida de memoria.</span><span class="sxs-lookup"><span data-stu-id="1ae44-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="1ae44-113">Si no es null, la función siempre asigna un nuevo `BSTR` cuando devuelve `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="1ae44-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="1ae44-114">[out] Cuando se realiza correctamente, el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="1ae44-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="1ae44-115">Si se produce un error en la función, el `VARIANT` apunta `pVal` no se modifica.</span><span class="sxs-lookup"><span data-stu-id="1ae44-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="1ae44-116">Si este parámetro es `null`, se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="1ae44-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="1ae44-117">[out] Un puntero a un valor largo que recibe el tipo de calificador.</span><span class="sxs-lookup"><span data-stu-id="1ae44-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="1ae44-118">Si no se desea obtener información de tipo, este parámetro puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="1ae44-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="1ae44-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ae44-119">Return value</span></span>

<span data-ttu-id="1ae44-120">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="1ae44-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1ae44-121">Constante</span><span class="sxs-lookup"><span data-stu-id="1ae44-121">Constant</span></span>  |<span data-ttu-id="1ae44-122">Valor</span><span class="sxs-lookup"><span data-stu-id="1ae44-122">Value</span></span>  |<span data-ttu-id="1ae44-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ae44-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1ae44-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1ae44-124">0x80041008</span></span> | <span data-ttu-id="1ae44-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="1ae44-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="1ae44-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="1ae44-126">0x8004101d</span></span> | <span data-ttu-id="1ae44-127">El llamador no llamó a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1ae44-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1ae44-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1ae44-128">0x80041006</span></span> | <span data-ttu-id="1ae44-129">No hay suficiente memoria disponible para comenzar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="1ae44-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="1ae44-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="1ae44-130">0x40005</span></span> | <span data-ttu-id="1ae44-131">No hay más calificadores se mantienen en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="1ae44-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1ae44-132">0</span><span class="sxs-lookup"><span data-stu-id="1ae44-132">0</span></span> | <span data-ttu-id="1ae44-133">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="1ae44-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1ae44-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ae44-134">Remarks</span></span>

<span data-ttu-id="1ae44-135">Esta función contiene una llamada a la [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) método.</span><span class="sxs-lookup"><span data-stu-id="1ae44-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="1ae44-136">Se llama a la `QualifierSet_Next` función varias veces para enumerar todos los calificadores hasta que el valor devuelto de función `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="1ae44-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="1ae44-137">Para finalizar la enumeración al principio, llame a la [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) función.</span><span class="sxs-lookup"><span data-stu-id="1ae44-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="1ae44-138">El orden de los calificadores que ha devuelto durante la enumeración es indefinido.</span><span class="sxs-lookup"><span data-stu-id="1ae44-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ae44-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ae44-139">Requirements</span></span>  
 <span data-ttu-id="1ae44-140">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ae44-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ae44-141">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1ae44-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1ae44-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1ae44-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae44-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ae44-143">See also</span></span>
- [<span data-ttu-id="1ae44-144">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="1ae44-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
