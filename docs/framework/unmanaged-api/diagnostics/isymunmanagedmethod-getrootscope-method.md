---
title: ISymUnmanagedMethod::GetRootScope (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: 071738c8fb9b40457215e21172240aa7e77198cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699474"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="130d6-102">ISymUnmanagedMethod::GetRootScope (Método)</span><span class="sxs-lookup"><span data-stu-id="130d6-102">ISymUnmanagedMethod::GetRootScope Method</span></span>

<span data-ttu-id="130d6-103">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="130d6-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="130d6-104">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="130d6-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="130d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="130d6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="130d6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="130d6-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="130d6-107">enuncia Puntero que se establece en la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="130d6-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="130d6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="130d6-108">Return Value</span></span>  

 <span data-ttu-id="130d6-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="130d6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="130d6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="130d6-110">Requirements</span></span>  

 <span data-ttu-id="130d6-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="130d6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130d6-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="130d6-112">See also</span></span>

- [<span data-ttu-id="130d6-113">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="130d6-113">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
