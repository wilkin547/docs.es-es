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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcfa0c01dc36a68711c42a7e8318cea023b1772f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752432"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="7a058-102">ISymUnmanagedWriter3::Commit (Método)</span><span class="sxs-lookup"><span data-stu-id="7a058-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="7a058-103">Confirma los cambios que se han escrito en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7a058-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a058-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a058-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7a058-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7a058-105">Return Value</span></span>  
 <span data-ttu-id="7a058-106">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7a058-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a058-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a058-107">Requirements</span></span>  
 <span data-ttu-id="7a058-108">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7a058-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a058-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a058-109">See also</span></span>

- [<span data-ttu-id="7a058-110">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a058-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
