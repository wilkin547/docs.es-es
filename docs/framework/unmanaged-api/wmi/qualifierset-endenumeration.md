---
title: Función QualifierSet_EndEnumeration (referencia de la API no administrada)
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
ms.openlocfilehash: 2c5a817174ec4c4e4407c19bb1d6d2d852d86dd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798316"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="fa666-103">QualifierSet_EndEnumeration función)</span><span class="sxs-lookup"><span data-stu-id="fa666-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="fa666-104">Finaliza la enumeración iniciada con una llamada a la función [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="fa666-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fa666-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa666-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="fa666-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa666-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fa666-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fa666-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="fa666-108">de Puntero a una instancia de [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="fa666-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="fa666-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fa666-109">Return value</span></span>

<span data-ttu-id="fa666-110">El siguiente valor devuelto por esta función se define en el archivo de encabezado *WbemCli. h* , o bien se puede definir como una constante en el código:</span><span class="sxs-lookup"><span data-stu-id="fa666-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="fa666-111">Constante</span><span class="sxs-lookup"><span data-stu-id="fa666-111">Constant</span></span>  |<span data-ttu-id="fa666-112">Value</span><span class="sxs-lookup"><span data-stu-id="fa666-112">Value</span></span>  |<span data-ttu-id="fa666-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fa666-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fa666-114">0</span><span class="sxs-lookup"><span data-stu-id="fa666-114">0</span></span> | <span data-ttu-id="fa666-115">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fa666-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fa666-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa666-116">Remarks</span></span>

<span data-ttu-id="fa666-117">Esta función contiene una llamada al método [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .</span><span class="sxs-lookup"><span data-stu-id="fa666-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="fa666-118">Se recomienda esta llamada, pero no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="fa666-118">This call is recommended, but not required.</span></span> <span data-ttu-id="fa666-119">Libera inmediatamente los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="fa666-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="fa666-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa666-120">Requirements</span></span>  

<span data-ttu-id="fa666-121">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa666-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="fa666-122">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fa666-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="fa666-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fa666-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa666-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa666-124">See also</span></span>

- [<span data-ttu-id="fa666-125">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="fa666-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
