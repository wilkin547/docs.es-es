---
title: "GetErrorInfo (función) (referencia de API no administrada)"
description: "La función GetErrorInfo recupera información de error de la llamada de función anterior."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetErrorInfo
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetErrorInfo
helpviewer_keywords: GetErrorInfo function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1bdaa72723855c6688a7c8c7704b958f6196dfd
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="1f27b-103">GetErrorInfo (función)</span><span class="sxs-lookup"><span data-stu-id="1f27b-103">GetErrorInfo function</span></span>
<span data-ttu-id="1f27b-104">Recupera información de error de la llamada de función anterior.</span><span class="sxs-lookup"><span data-stu-id="1f27b-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1f27b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f27b-105">Syntax</span></span>  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="1f27b-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1f27b-106">Return value</span></span>

<span data-ttu-id="1f27b-107">Un puntero a un [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) objeto si la llamada de función se realiza correctamente, o `null` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="1f27b-107">An pointer to an [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1f27b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f27b-108">Remarks</span></span>

<span data-ttu-id="1f27b-109">Esta función contiene una llamada a la [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="1f27b-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1f27b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f27b-110">Requirements</span></span>  
 <span data-ttu-id="1f27b-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f27b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f27b-112">**Encabezado:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="1f27b-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="1f27b-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1f27b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f27b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f27b-114">See also</span></span>  
[<span data-ttu-id="1f27b-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="1f27b-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
