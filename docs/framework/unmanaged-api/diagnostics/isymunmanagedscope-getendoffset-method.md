---
title: ISymUnmanagedScope::GetEndOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 47db4313354b00514084ec1110710cbd174a3788
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492626"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="c06b7-102">ISymUnmanagedScope::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="c06b7-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="c06b7-103">Obtiene el desplazamiento final de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c06b7-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c06b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c06b7-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c06b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c06b7-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c06b7-106">[out] Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="c06b7-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c06b7-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c06b7-107">Return Value</span></span>  
 <span data-ttu-id="c06b7-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c06b7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c06b7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c06b7-109">Requirements</span></span>  
 <span data-ttu-id="c06b7-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c06b7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06b7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c06b7-111">See also</span></span>
- [<span data-ttu-id="c06b7-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c06b7-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="c06b7-113">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="c06b7-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
