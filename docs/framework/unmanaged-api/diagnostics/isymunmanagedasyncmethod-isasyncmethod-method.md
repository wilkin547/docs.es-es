---
title: "ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 560690e95e7aa0aef37e3a708183641bd70ee97d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="8e86a-102">ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="8e86a-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="8e86a-103">Comprueba si el método tiene información de async o no.</span><span class="sxs-lookup"><span data-stu-id="8e86a-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="8e86a-104">Si este método devuelve `FALSE` , a continuación, no es válido para llamar a ningún otro método en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="8e86a-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="8e86a-105">Lo harían devuelven todos los `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="8e86a-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e86a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e86a-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e86a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e86a-107">Parameters</span></span>  
  
|<span data-ttu-id="8e86a-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8e86a-108">Parameter</span></span>|<span data-ttu-id="8e86a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e86a-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="8e86a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e86a-110">Return Value</span></span>  
 <span data-ttu-id="8e86a-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8e86a-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e86a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e86a-112">Requirements</span></span>  
 <span data-ttu-id="8e86a-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8e86a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e86a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e86a-114">See Also</span></span>  
 [<span data-ttu-id="8e86a-115">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e86a-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
