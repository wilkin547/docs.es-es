---
title: "Función QualifierSet_EndEnumeration (referencia de API no administrada)"
description: "La función QualifierSet_EndEnumeration finaliza una enumeración."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="b3eb6-103">QualifierSet_EndEnumeration (función)</span><span class="sxs-lookup"><span data-stu-id="b3eb6-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="b3eb6-104">Finaliza la enumeración iniciada con una llamada a la [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (función).</span><span class="sxs-lookup"><span data-stu-id="b3eb6-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b3eb6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3eb6-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="b3eb6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3eb6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b3eb6-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b3eb6-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="b3eb6-108">[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="b3eb6-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="b3eb6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b3eb6-109">Return value</span></span>

<span data-ttu-id="b3eb6-110">El siguiente valor devuelto por esta función se define en el *WbemCli.h* archivo de encabezado, o puede definirla como una constante en el código:</span><span class="sxs-lookup"><span data-stu-id="b3eb6-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="b3eb6-111">Constante</span><span class="sxs-lookup"><span data-stu-id="b3eb6-111">Constant</span></span>  |<span data-ttu-id="b3eb6-112">Valor</span><span class="sxs-lookup"><span data-stu-id="b3eb6-112">Value</span></span>  |<span data-ttu-id="b3eb6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3eb6-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b3eb6-114">0</span><span class="sxs-lookup"><span data-stu-id="b3eb6-114">0</span></span> | <span data-ttu-id="b3eb6-115">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="b3eb6-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b3eb6-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b3eb6-116">Remarks</span></span>

<span data-ttu-id="b3eb6-117">Esta función contiene una llamada a la [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="b3eb6-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="b3eb6-118">Esta llamada se recomienda, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="b3eb6-118">This call is recommended, but not required.</span></span> <span data-ttu-id="b3eb6-119">Inmediatamente libera los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b3eb6-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3eb6-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3eb6-120">Requirements</span></span>  

<span data-ttu-id="b3eb6-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3eb6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="b3eb6-122">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b3eb6-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="b3eb6-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b3eb6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3eb6-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3eb6-124">See also</span></span>  
[<span data-ttu-id="b3eb6-125">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b3eb6-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
