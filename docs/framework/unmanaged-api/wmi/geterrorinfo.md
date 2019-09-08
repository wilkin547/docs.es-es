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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab801ec7899403f568d953535fcd430a862a2fd8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798583"
---
# <a name="geterrorinfo-function"></a><span data-ttu-id="0399d-103">GetErrorInfo función)</span><span class="sxs-lookup"><span data-stu-id="0399d-103">GetErrorInfo function</span></span>
<span data-ttu-id="0399d-104">Recupera información sobre el error de la llamada de función anterior.</span><span class="sxs-lookup"><span data-stu-id="0399d-104">Retrieves error information from the previous function call.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0399d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0399d-105">Syntax</span></span>  
  
```cpp  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a><span data-ttu-id="0399d-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0399d-106">Return value</span></span>

<span data-ttu-id="0399d-107">Un puntero a un objeto [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) si la llamada de función se realiza correctamente `null` , o si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="0399d-107">An pointer to an [IErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) object if the function call succeeds, or `null` if it fails.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0399d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0399d-108">Remarks</span></span>

<span data-ttu-id="0399d-109">Esta función contiene una llamada al método [IComThreadingInfo:: GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .</span><span class="sxs-lookup"><span data-stu-id="0399d-109">This function wraps a call to the [IComThreadingInfo::GetErrorInfo](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0399d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0399d-110">Requirements</span></span>  
 <span data-ttu-id="0399d-111">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0399d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0399d-112">**Encabezado**: WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="0399d-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="0399d-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0399d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0399d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0399d-114">See also</span></span>

- [<span data-ttu-id="0399d-115">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="0399d-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
