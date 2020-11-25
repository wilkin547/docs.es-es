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
ms.openlocfilehash: 69b72ce66a203f403fcfe0fd4b4e728ece7397e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725877"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="a6c26-102">ISymUnmanagedScope::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="a6c26-102">ISymUnmanagedScope::GetStartOffset Method</span></span>

<span data-ttu-id="a6c26-103">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="a6c26-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6c26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6c26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6c26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6c26-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="a6c26-106">enuncia Un puntero a un `ULONG32` que contiene el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="a6c26-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6c26-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a6c26-107">Return Value</span></span>  

 <span data-ttu-id="a6c26-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a6c26-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6c26-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6c26-109">Requirements</span></span>  

 <span data-ttu-id="a6c26-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="a6c26-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c26-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6c26-111">See also</span></span>

- [<span data-ttu-id="a6c26-112">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6c26-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="a6c26-113">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="a6c26-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
