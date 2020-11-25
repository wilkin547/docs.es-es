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
ms.openlocfilehash: 75d5638a6f01ba9569a03e5255a7217371c9d177
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725942"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="6d144-102">ISymUnmanagedScope::GetMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="6d144-102">ISymUnmanagedScope::GetMethod Method</span></span>

<span data-ttu-id="6d144-103">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="6d144-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d144-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d144-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d144-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d144-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="6d144-106">enuncia Puntero a la interfaz [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="6d144-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6d144-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6d144-107">Return Value</span></span>  

 <span data-ttu-id="6d144-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6d144-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d144-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d144-109">Requirements</span></span>  

 <span data-ttu-id="6d144-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6d144-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d144-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d144-111">See also</span></span>

- [<span data-ttu-id="6d144-112">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d144-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
