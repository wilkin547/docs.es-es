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
ms.openlocfilehash: 9a80c0b5522113e704336cda29362a0406077931
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553680"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="42a4b-103">Función GetErrorInfo</span><span class="sxs-lookup"><span data-stu-id="42a4b-103">GetErrorInfo function</span></span>
<span data-ttu-id="42a4b-104">Recupera información sobre el error de la llamada de función anterior.</span><span class="sxs-lookup"><span data-stu-id="42a4b-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="42a4b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42a4b-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo();
```  

## <a name="return-value"></a><span data-ttu-id="42a4b-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="42a4b-106">Return value</span></span>

<span data-ttu-id="42a4b-107">Un puntero a un objeto [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) si la llamada de función se realiza correctamente, o `null` si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="42a4b-107">An pointer to an [IErrorInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="42a4b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42a4b-108">Remarks</span></span>

<span data-ttu-id="42a4b-109">Esta función contiene una llamada al método [IComThreadingInfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="42a4b-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="42a4b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42a4b-110">Requirements</span></span>  
 <span data-ttu-id="42a4b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a4b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a4b-112">**Encabezado:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="42a4b-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="42a4b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42a4b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a4b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="42a4b-114">See also</span></span>

- [<span data-ttu-id="42a4b-115">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="42a4b-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
