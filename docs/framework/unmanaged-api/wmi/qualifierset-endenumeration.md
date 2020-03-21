---
title: QualifierSet_EndEnumeration (Referencia de API no administrada)
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
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176752"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="47bae-103">Función QualifierSet_EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="47bae-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="47bae-104">Termina la enumeración iniciada con una llamada a la [función QualifierSet_BeginEnumeration.](qualifierset-beginenumeration.md)</span><span class="sxs-lookup"><span data-stu-id="47bae-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="47bae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47bae-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="47bae-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47bae-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="47bae-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="47bae-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="47bae-108">`ptr`[en] Puntero a una instancia de [IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="47bae-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="47bae-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47bae-109">Return value</span></span>

<span data-ttu-id="47bae-110">El siguiente valor devuelto por esta función se define en el archivo de encabezado *WbemCli.h,* o puede definirlo como una constante en el código:</span><span class="sxs-lookup"><span data-stu-id="47bae-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="47bae-111">Constante</span><span class="sxs-lookup"><span data-stu-id="47bae-111">Constant</span></span>  |<span data-ttu-id="47bae-112">Value</span><span class="sxs-lookup"><span data-stu-id="47bae-112">Value</span></span>  |<span data-ttu-id="47bae-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="47bae-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="47bae-114">0</span><span class="sxs-lookup"><span data-stu-id="47bae-114">0</span></span> | <span data-ttu-id="47bae-115">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="47bae-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="47bae-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47bae-116">Remarks</span></span>

<span data-ttu-id="47bae-117">Esta función ajusta una llamada a la [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="47bae-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="47bae-118">Esta llamada se recomienda, pero no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="47bae-118">This call is recommended, but not required.</span></span> <span data-ttu-id="47bae-119">Libera inmediatamente los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="47bae-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="47bae-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47bae-120">Requirements</span></span>  

<span data-ttu-id="47bae-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47bae-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="47bae-122">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="47bae-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="47bae-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="47bae-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47bae-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47bae-124">See also</span></span>

- [<span data-ttu-id="47bae-125">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="47bae-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
