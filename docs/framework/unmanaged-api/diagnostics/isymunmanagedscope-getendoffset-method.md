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
ms.openlocfilehash: d13006bc5c09ed065ae1671ee75cf8dce066669d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426308"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="3bb05-102">ISymUnmanagedScope::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="3bb05-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="3bb05-103">Obtiene el desplazamiento final de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="3bb05-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bb05-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bb05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bb05-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="3bb05-106">[out] Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="3bb05-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bb05-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3bb05-107">Return Value</span></span>  
 <span data-ttu-id="3bb05-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3bb05-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb05-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bb05-109">Requirements</span></span>  
 <span data-ttu-id="3bb05-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3bb05-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb05-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bb05-111">See Also</span></span>  
 [<span data-ttu-id="3bb05-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bb05-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="3bb05-113">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="3bb05-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
