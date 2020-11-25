---
title: Función QualifierSet_Next (referencia de la API no administrada)
description: La función QualifierSet_Next recupera el calificador siguiente en una enumeración.
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
ms.openlocfilehash: 54d79a3dc081e9cdcb42153b6f7aa457557e3399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721132"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="f4246-103">Función QualifierSet_Next</span><span class="sxs-lookup"><span data-stu-id="f4246-103">QualifierSet_Next function</span></span>

<span data-ttu-id="f4246-104">Recupera el siguiente calificador en una enumeración que se inició con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f4246-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f4246-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4246-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="f4246-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4246-106">Parameters</span></span>

<span data-ttu-id="f4246-107">`vFunc` de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="f4246-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="f4246-108">`ptr` de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="f4246-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="f4246-109">`lFlags` de Sector.</span><span class="sxs-lookup"><span data-stu-id="f4246-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="f4246-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="f4246-110">This parameter must be 0.</span></span>

<span data-ttu-id="f4246-111">`pstrName` enuncia Nombre del calificador.</span><span class="sxs-lookup"><span data-stu-id="f4246-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="f4246-112">Si `null` es, este parámetro se omite; de lo contrario, `pstrName` no debe apuntar a un válido `BSTR` o se produce una fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="f4246-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="f4246-113">Si no es null, la función siempre asigna un nuevo `BSTR` cuando devuelve `WBEM_S_NO_ERROR` .</span><span class="sxs-lookup"><span data-stu-id="f4246-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="f4246-114">`pVal` enuncia Cuando se realiza correctamente, el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="f4246-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="f4246-115">Si se produce un error en la función, el `VARIANT` señalado por `pVal` no se modifica.</span><span class="sxs-lookup"><span data-stu-id="f4246-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="f4246-116">Si este parámetro es `null` , se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="f4246-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="f4246-117">`plFlavor` enuncia Un puntero a un LONG que recibe el tipo de calificador.</span><span class="sxs-lookup"><span data-stu-id="f4246-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="f4246-118">Si no se desea información de tipo, este parámetro puede ser `null` .</span><span class="sxs-lookup"><span data-stu-id="f4246-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f4246-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f4246-119">Return value</span></span>

<span data-ttu-id="f4246-120">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="f4246-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f4246-121">Constante</span><span class="sxs-lookup"><span data-stu-id="f4246-121">Constant</span></span>  |<span data-ttu-id="f4246-122">Value</span><span class="sxs-lookup"><span data-stu-id="f4246-122">Value</span></span>  |<span data-ttu-id="f4246-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4246-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f4246-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f4246-124">0x80041008</span></span> | <span data-ttu-id="f4246-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="f4246-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="f4246-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f4246-126">0x8004101d</span></span> | <span data-ttu-id="f4246-127">El autor de la llamada no llama a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f4246-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f4246-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f4246-128">0x80041006</span></span> | <span data-ttu-id="f4246-129">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="f4246-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="f4246-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="f4246-130">0x40005</span></span> | <span data-ttu-id="f4246-131">No quedan más calificadores en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f4246-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f4246-132">0</span><span class="sxs-lookup"><span data-stu-id="f4246-132">0</span></span> | <span data-ttu-id="f4246-133">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f4246-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f4246-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4246-134">Remarks</span></span>

<span data-ttu-id="f4246-135">Esta función contiene una llamada al método [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .</span><span class="sxs-lookup"><span data-stu-id="f4246-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="f4246-136">Llame a la `QualifierSet_Next` función varias veces para enumerar todos los calificadores hasta que la función devuelva `WBEM_S_NO_MORE_DATA` .</span><span class="sxs-lookup"><span data-stu-id="f4246-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="f4246-137">Para finalizar la enumeración pronto, llame a la función [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="f4246-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="f4246-138">El orden de los calificadores devueltos durante la enumeración es indefinido.</span><span class="sxs-lookup"><span data-stu-id="f4246-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4246-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4246-139">Requirements</span></span>  

 <span data-ttu-id="f4246-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4246-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4246-141">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f4246-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f4246-142">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f4246-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4246-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4246-143">See also</span></span>

- [<span data-ttu-id="f4246-144">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="f4246-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
