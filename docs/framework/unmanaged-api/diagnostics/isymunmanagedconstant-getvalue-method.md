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
ms.openlocfilehash: 1043a7efe70798fbbc52ce6d1d0e16510e7c0503
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499150"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="be9b6-102">ISymUnmanagedConstant::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="be9b6-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="be9b6-103">Obtiene el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="be9b6-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be9b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be9b6-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be9b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be9b6-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="be9b6-106">[out] Un puntero a una variable que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="be9b6-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be9b6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="be9b6-107">Return Value</span></span>  
 <span data-ttu-id="be9b6-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="be9b6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be9b6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be9b6-109">Requirements</span></span>  
 <span data-ttu-id="be9b6-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="be9b6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be9b6-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="be9b6-111">See also</span></span>
- [<span data-ttu-id="be9b6-112">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="be9b6-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="be9b6-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="be9b6-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="be9b6-114">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="be9b6-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
