---
title: Función GetErrorInfo (referencia de la API no administrada)
description: La función GetErrorInfo recupera información de error de la llamada de función anterior.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5da4eaa459c515689b822e4cb537380245e800e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722770"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="5d984-103">Función GetErrorInfo</span><span class="sxs-lookup"><span data-stu-id="5d984-103">GetErrorInfo function</span></span>

<span data-ttu-id="5d984-104">Recupera información sobre el error de la llamada de función anterior.</span><span class="sxs-lookup"><span data-stu-id="5d984-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5d984-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d984-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="5d984-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5d984-106">Return value</span></span>

<span data-ttu-id="5d984-107">Un puntero a un objeto [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) si la llamada de función se realiza correctamente, o `null` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="5d984-107">An pointer to an [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5d984-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d984-108">Remarks</span></span>

<span data-ttu-id="5d984-109">Esta función contiene una llamada al método [IComThreadingInfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="5d984-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d984-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d984-110">Requirements</span></span>  

 <span data-ttu-id="5d984-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d984-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d984-112">**Encabezado:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="5d984-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="5d984-113">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5d984-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d984-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d984-114">See also</span></span>

- [<span data-ttu-id="5d984-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="5d984-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
