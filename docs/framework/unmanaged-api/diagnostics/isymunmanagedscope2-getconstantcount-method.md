---
title: ISymUnmanagedScope2::GetConstantCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2.GetConstantCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstantCount
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstantCount method [.NET Framework debugging]
- GetConstantCount method [.NET Framework debugging]
ms.assetid: 1e1f0be6-c4e8-4d6c-98cd-d5fa9f686e87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2752cf7dcdf0a33e5b6f4e7a51f3d63476c40e4f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777936"
---
# <a name="isymunmanagedscope2getconstantcount-method"></a><span data-ttu-id="af3c8-102">ISymUnmanagedScope2::GetConstantCount (Método)</span><span class="sxs-lookup"><span data-stu-id="af3c8-102">ISymUnmanagedScope2::GetConstantCount Method</span></span>
<span data-ttu-id="af3c8-103">Obtiene un recuento de las constantes definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="af3c8-103">Gets a count of the constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af3c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af3c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConstantCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af3c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af3c8-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="af3c8-106">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener las constantes.</span><span class="sxs-lookup"><span data-stu-id="af3c8-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af3c8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af3c8-107">Return Value</span></span>  
 <span data-ttu-id="af3c8-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="af3c8-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af3c8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af3c8-109">Requirements</span></span>  
 <span data-ttu-id="af3c8-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="af3c8-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af3c8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="af3c8-111">See also</span></span>

- [<span data-ttu-id="af3c8-112">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af3c8-112">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
