---
title: Función GetErrorInfo (Referencia de API no administrada)
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
ms.openlocfilehash: 802ee66a5be213ac7a599b193ec6de589773ea17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176817"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="2d719-103">Función GetErrorInfo</span><span class="sxs-lookup"><span data-stu-id="2d719-103">GetErrorInfo function</span></span>
<span data-ttu-id="2d719-104">Recupera información sobre el error de la llamada de función anterior.</span><span class="sxs-lookup"><span data-stu-id="2d719-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2d719-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d719-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="2d719-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d719-106">Return value</span></span>

<span data-ttu-id="2d719-107">Un puntero a un [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) objeto si `null` la llamada de función se realiza correctamente o si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="2d719-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="2d719-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2d719-108">Remarks</span></span>

<span data-ttu-id="2d719-109">Esta función ajusta una llamada a la [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) método.</span><span class="sxs-lookup"><span data-stu-id="2d719-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2d719-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d719-110">Requirements</span></span>  
 <span data-ttu-id="2d719-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d719-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d719-112">**Encabezado:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="2d719-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="2d719-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2d719-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d719-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d719-114">See also</span></span>

- [<span data-ttu-id="2d719-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="2d719-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
