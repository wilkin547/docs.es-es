---
title: ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5cddf34f1a6277e966901c9692bff63e26a3b8e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940158"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="31b1f-102">ISymUnmanagedAsyncMethod::IsAsyncMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="31b1f-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="31b1f-103">Comprueba si el método tiene información de async o no.</span><span class="sxs-lookup"><span data-stu-id="31b1f-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="31b1f-104">Si este método devuelve `FALSE` , a continuación, no es válido llamar a los otros métodos en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="31b1f-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="31b1f-105">Lo harán todas devuelven `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="31b1f-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31b1f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31b1f-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31b1f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31b1f-107">Parameters</span></span>  
  
|<span data-ttu-id="31b1f-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="31b1f-108">Parameter</span></span>|<span data-ttu-id="31b1f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="31b1f-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="31b1f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="31b1f-110">Return Value</span></span>  
 <span data-ttu-id="31b1f-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="31b1f-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31b1f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31b1f-112">Requirements</span></span>  
 <span data-ttu-id="31b1f-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="31b1f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b1f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="31b1f-114">See also</span></span>

- [<span data-ttu-id="31b1f-115">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="31b1f-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
