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
ms.openlocfilehash: cf2784ce0ac6e614e75a341660808b9fe03ada0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699448"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="1ee36-102">ISymUnmanagedMethod::GetScopeFromOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="1ee36-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>

<span data-ttu-id="1ee36-103">Obtiene el ámbito léxico más envolvente dentro de este método que incluye el desplazamiento determinado.</span><span class="sxs-lookup"><span data-stu-id="1ee36-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="1ee36-104">Se puede usar para iniciar búsquedas de variables locales.</span><span class="sxs-lookup"><span data-stu-id="1ee36-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee36-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ee36-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ee36-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ee36-106">Parameters</span></span>  

 `offset`  
 <span data-ttu-id="1ee36-107">de Un `ULONG` que contiene el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="1ee36-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1ee36-108">enuncia Puntero que se establece en la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="1ee36-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ee36-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ee36-109">Return Value</span></span>  

 <span data-ttu-id="1ee36-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1ee36-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee36-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ee36-111">Requirements</span></span>  

 <span data-ttu-id="1ee36-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1ee36-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee36-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ee36-113">See also</span></span>

- [<span data-ttu-id="1ee36-114">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ee36-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
