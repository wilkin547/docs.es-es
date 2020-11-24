---
title: ISymUnmanagedWriter3::Commit (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
ms.openlocfilehash: 394832d6144509717d2f79a78afaff50ad81c01d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683308"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="0bd81-102">ISymUnmanagedWriter3::Commit (Método)</span><span class="sxs-lookup"><span data-stu-id="0bd81-102">ISymUnmanagedWriter3::Commit Method</span></span>

<span data-ttu-id="0bd81-103">Confirma los cambios escritos hasta el momento en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0bd81-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bd81-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bd81-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0bd81-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0bd81-105">Return Value</span></span>  

 <span data-ttu-id="0bd81-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0bd81-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bd81-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bd81-107">Requirements</span></span>  

 <span data-ttu-id="0bd81-108">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0bd81-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bd81-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bd81-109">See also</span></span>

- [<span data-ttu-id="0bd81-110">ISymUnmanagedWriter3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bd81-110">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
