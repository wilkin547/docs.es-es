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
ms.openlocfilehash: c9c824b0158618848c13183d92f88604460d5099
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141724"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="83c83-103">QualifierSet_Next función)</span><span class="sxs-lookup"><span data-stu-id="83c83-103">QualifierSet_Next function</span></span>
<span data-ttu-id="83c83-104">Recupera el siguiente calificador en una enumeración que se inició con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="83c83-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="83c83-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83c83-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="83c83-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83c83-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="83c83-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="83c83-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="83c83-108">de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="83c83-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="83c83-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="83c83-109">[in] Reserved.</span></span> <span data-ttu-id="83c83-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="83c83-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="83c83-111">enuncia Nombre del calificador.</span><span class="sxs-lookup"><span data-stu-id="83c83-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="83c83-112">Si `null`, se omite este parámetro; de lo contrario, `pstrName` no debe apuntar a un `BSTR` válido o se produce una fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="83c83-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="83c83-113">Si no es null, la función siempre asigna un nuevo `BSTR` cuando devuelve `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="83c83-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="83c83-114">enuncia Cuando se realiza correctamente, el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="83c83-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="83c83-115">Si se produce un error en la función, el `VARIANT` al que apunta `pVal` no se modifica.</span><span class="sxs-lookup"><span data-stu-id="83c83-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="83c83-116">Si este parámetro es `null`, se omite el parámetro.</span><span class="sxs-lookup"><span data-stu-id="83c83-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="83c83-117">enuncia Un puntero a un LONG que recibe el tipo de calificador.</span><span class="sxs-lookup"><span data-stu-id="83c83-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="83c83-118">Si no se desea información de tipo, este parámetro se puede `null`.</span><span class="sxs-lookup"><span data-stu-id="83c83-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="83c83-119">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="83c83-119">Return value</span></span>

<span data-ttu-id="83c83-120">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="83c83-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="83c83-121">Constante</span><span class="sxs-lookup"><span data-stu-id="83c83-121">Constant</span></span>  |<span data-ttu-id="83c83-122">Valor</span><span class="sxs-lookup"><span data-stu-id="83c83-122">Value</span></span>  |<span data-ttu-id="83c83-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="83c83-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="83c83-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="83c83-124">0x80041008</span></span> | <span data-ttu-id="83c83-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="83c83-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="83c83-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="83c83-126">0x8004101d</span></span> | <span data-ttu-id="83c83-127">El autor de la llamada no llama a [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="83c83-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="83c83-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="83c83-128">0x80041006</span></span> | <span data-ttu-id="83c83-129">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="83c83-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="83c83-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="83c83-130">0x40005</span></span> | <span data-ttu-id="83c83-131">No quedan más calificadores en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="83c83-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="83c83-132">0</span><span class="sxs-lookup"><span data-stu-id="83c83-132">0</span></span> | <span data-ttu-id="83c83-133">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="83c83-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="83c83-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83c83-134">Remarks</span></span>

<span data-ttu-id="83c83-135">Esta función contiene una llamada al método [IWbemQualifierSet:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .</span><span class="sxs-lookup"><span data-stu-id="83c83-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="83c83-136">Llame a la función `QualifierSet_Next` varias veces para enumerar todos los calificadores hasta que la función devuelva `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="83c83-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="83c83-137">Para finalizar la enumeración pronto, llame a la función [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="83c83-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="83c83-138">El orden de los calificadores devueltos durante la enumeración es indefinido.</span><span class="sxs-lookup"><span data-stu-id="83c83-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="83c83-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83c83-139">Requirements</span></span>  
 <span data-ttu-id="83c83-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83c83-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c83-141">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="83c83-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="83c83-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="83c83-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c83-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="83c83-143">See also</span></span>

- [<span data-ttu-id="83c83-144">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="83c83-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
