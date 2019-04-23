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
ms.openlocfilehash: 75cc16f44ddf29b161c758718b697cc2aaba8e08
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204671"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="1d155-102">ISymUnmanagedConstant::GetValue (Método)</span><span class="sxs-lookup"><span data-stu-id="1d155-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="1d155-103">Obtiene el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="1d155-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d155-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d155-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d155-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d155-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="1d155-106">[out] Un puntero a una variable que recibe el valor.</span><span class="sxs-lookup"><span data-stu-id="1d155-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d155-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1d155-107">Return Value</span></span>  
 <span data-ttu-id="1d155-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1d155-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d155-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d155-109">Requirements</span></span>  
 <span data-ttu-id="1d155-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1d155-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d155-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d155-111">See also</span></span>

- [<span data-ttu-id="1d155-112">ISymUnmanagedConstant (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d155-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="1d155-113">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="1d155-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="1d155-114">GetSignature (método)</span><span class="sxs-lookup"><span data-stu-id="1d155-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
