---
title: ISymUnmanagedScope::GetStartOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19d116825efc4eb2ec1de22f232f46f8fb0fdf18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425916"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="62e99-102">ISymUnmanagedScope::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="62e99-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="62e99-103">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="62e99-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62e99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62e99-104">Syntax</span></span>  
  
```  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62e99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62e99-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="62e99-106">[out] Un puntero a un `ULONG32` que contiene el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="62e99-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62e99-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62e99-107">Return Value</span></span>  
 <span data-ttu-id="62e99-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="62e99-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62e99-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62e99-109">Requirements</span></span>  
 <span data-ttu-id="62e99-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="62e99-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62e99-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="62e99-111">See Also</span></span>  
 [<span data-ttu-id="62e99-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62e99-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="62e99-113">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="62e99-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
