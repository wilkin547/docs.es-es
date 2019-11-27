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
ms.openlocfilehash: 9d1ee82f24e1908af1998e424006415af3134456
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446273"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="b9fa3-102">ISymUnmanagedScope::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="b9fa3-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="b9fa3-103">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b9fa3-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9fa3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9fa3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9fa3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9fa3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="b9fa3-106">enuncia Puntero a una `ULONG32` que contiene el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="b9fa3-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9fa3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9fa3-107">Return Value</span></span>  
 <span data-ttu-id="b9fa3-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b9fa3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9fa3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9fa3-109">Requirements</span></span>  
 <span data-ttu-id="b9fa3-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b9fa3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9fa3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9fa3-111">See also</span></span>

- [<span data-ttu-id="b9fa3-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9fa3-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="b9fa3-113">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="b9fa3-113">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)
