---
description: 'Más información acerca de: ISymUnmanagedScope:: Getstartoffset ((método)'
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
ms.openlocfilehash: c95fbc5229512f08052ffc00f0092f64983ea3f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763324"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="abae2-103">ISymUnmanagedScope::GetStartOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="abae2-103">ISymUnmanagedScope::GetStartOffset Method</span></span>

<span data-ttu-id="abae2-104">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="abae2-104">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abae2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abae2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abae2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abae2-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="abae2-107">enuncia Un puntero a un `ULONG32` que contiene el desplazamiento inicial.</span><span class="sxs-lookup"><span data-stu-id="abae2-107">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abae2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="abae2-108">Return Value</span></span>  

 <span data-ttu-id="abae2-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="abae2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abae2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abae2-110">Requirements</span></span>  

 <span data-ttu-id="abae2-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="abae2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abae2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="abae2-112">See also</span></span>

- [<span data-ttu-id="abae2-113">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="abae2-113">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="abae2-114">GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="abae2-114">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
