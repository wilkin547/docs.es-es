---
title: Función QualifierSet_EndEnumeration (referencia de API no administrada)
description: La función QualifierSet_EndEnumeration finaliza una enumeración.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbf47dbfddac7d48b78c9d52969de1ef03385c15
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486823"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="31dc0-103">Función QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="31dc0-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="31dc0-104">Finaliza la enumeración iniciada con una llamada a la [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) función.</span><span class="sxs-lookup"><span data-stu-id="31dc0-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="31dc0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31dc0-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="31dc0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31dc0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="31dc0-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="31dc0-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="31dc0-108">[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.</span><span class="sxs-lookup"><span data-stu-id="31dc0-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="31dc0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="31dc0-109">Return value</span></span>

<span data-ttu-id="31dc0-110">El siguiente valor devuelto por esta función se define en el *WbemCli.h* archivo de encabezado, también puede definir como una constante en el código:</span><span class="sxs-lookup"><span data-stu-id="31dc0-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="31dc0-111">Constante</span><span class="sxs-lookup"><span data-stu-id="31dc0-111">Constant</span></span>  |<span data-ttu-id="31dc0-112">Valor</span><span class="sxs-lookup"><span data-stu-id="31dc0-112">Value</span></span>  |<span data-ttu-id="31dc0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="31dc0-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="31dc0-114">0</span><span class="sxs-lookup"><span data-stu-id="31dc0-114">0</span></span> | <span data-ttu-id="31dc0-115">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="31dc0-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="31dc0-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31dc0-116">Remarks</span></span>

<span data-ttu-id="31dc0-117">Esta función contiene una llamada a la [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="31dc0-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="31dc0-118">Esta llamada es recomendable, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="31dc0-118">This call is recommended, but not required.</span></span> <span data-ttu-id="31dc0-119">Inmediatamente libera los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="31dc0-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="31dc0-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31dc0-120">Requirements</span></span>  

<span data-ttu-id="31dc0-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31dc0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="31dc0-122">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="31dc0-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="31dc0-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="31dc0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31dc0-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="31dc0-124">See also</span></span>  
[<span data-ttu-id="31dc0-125">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="31dc0-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
