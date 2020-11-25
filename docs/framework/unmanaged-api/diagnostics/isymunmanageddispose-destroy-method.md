---
title: ISymUnmanagedDispose::Destroy (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
ms.openlocfilehash: 6a31026f5b1669c0c29762048dc2c5c1c7bbb6a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732832"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="f90e5-102">ISymUnmanagedDispose::Destroy (Método)</span><span class="sxs-lookup"><span data-stu-id="f90e5-102">ISymUnmanagedDispose::Destroy Method</span></span>

<span data-ttu-id="f90e5-103">Hace que el objeto subyacente libere todas las referencias internas y devuelva un error en cualquier llamada posterior al método.</span><span class="sxs-lookup"><span data-stu-id="f90e5-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f90e5-104">Syntax</span></span>  
  
```cpp  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f90e5-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f90e5-105">Return Value</span></span>  

 <span data-ttu-id="f90e5-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f90e5-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f90e5-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f90e5-107">Requirements</span></span>  

 <span data-ttu-id="f90e5-108">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f90e5-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90e5-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f90e5-109">See also</span></span>

- [<span data-ttu-id="f90e5-110">ISymUnmanagedDispose (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f90e5-110">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)
