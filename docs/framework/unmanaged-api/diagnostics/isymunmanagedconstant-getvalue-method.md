---
title: ISymUnmanagedConstant::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f51a41e8f00a0cf88b11078468ba5a8511fd1391
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424744"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="993a1-102">ISymUnmanagedConstant::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="993a1-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="993a1-103">Obtiene el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="993a1-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="993a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="993a1-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="993a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="993a1-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="993a1-106">[out] Un puntero a una variable que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="993a1-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="993a1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="993a1-107">Return Value</span></span>  
 <span data-ttu-id="993a1-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="993a1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="993a1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="993a1-109">Requirements</span></span>  
 <span data-ttu-id="993a1-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="993a1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="993a1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="993a1-111">See Also</span></span>  
 [<span data-ttu-id="993a1-112">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="993a1-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="993a1-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="993a1-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="993a1-114">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="993a1-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
