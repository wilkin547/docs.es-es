---
title: ISymUnmanagedMethod::GetScopeFromOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 36b1b2394907f242c0e8c5e277c0d1c5b3b02e1b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448903"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="52160-102">ISymUnmanagedMethod::GetScopeFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="52160-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="52160-103">Obtiene el ámbito léxico más envolvente dentro de este método que incluye el desplazamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="52160-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="52160-104">Se puede usar para iniciar búsquedas de variables locales.</span><span class="sxs-lookup"><span data-stu-id="52160-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52160-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52160-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52160-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52160-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="52160-107">de `ULONG` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="52160-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="52160-108">enuncia Puntero que se establece en la interfaz [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="52160-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52160-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52160-109">Return Value</span></span>  
 <span data-ttu-id="52160-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="52160-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52160-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52160-111">Requirements</span></span>  
 <span data-ttu-id="52160-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="52160-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52160-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="52160-113">See also</span></span>

- [<span data-ttu-id="52160-114">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52160-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
