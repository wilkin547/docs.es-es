---
title: ISymUnmanagedScope::GetMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12dd485f2b89dc76076410e76a132ff547681597
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616828"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="379e5-102">ISymUnmanagedScope::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="379e5-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="379e5-103">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="379e5-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="379e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="379e5-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="379e5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="379e5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="379e5-106">[out] Un puntero a la devuelta [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="379e5-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="379e5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="379e5-107">Return Value</span></span>  
 <span data-ttu-id="379e5-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="379e5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="379e5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="379e5-109">Requirements</span></span>  
 <span data-ttu-id="379e5-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="379e5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="379e5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="379e5-111">See also</span></span>
- [<span data-ttu-id="379e5-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="379e5-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
