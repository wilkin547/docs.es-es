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
ms.openlocfilehash: e28a351b6d47d14f171b9e760b2fa2c6755e3f8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986204"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="55c21-102">ISymUnmanagedScope::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="55c21-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="55c21-103">Obtiene el desplazamiento final de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="55c21-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55c21-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c21-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55c21-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="55c21-106">[out] Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="55c21-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55c21-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="55c21-107">Return Value</span></span>  
 <span data-ttu-id="55c21-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="55c21-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c21-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55c21-109">Requirements</span></span>  
 <span data-ttu-id="55c21-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="55c21-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c21-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="55c21-111">See also</span></span>

- [<span data-ttu-id="55c21-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55c21-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="55c21-113">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="55c21-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
