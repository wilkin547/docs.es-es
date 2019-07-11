---
title: ISymUnmanagedScope::GetParent (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78a0f4b1c111e7978af0259f684402bb98566272
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777862"
---
# <a name="isymunmanagedscopegetparent-method"></a><span data-ttu-id="a9d75-102">ISymUnmanagedScope::GetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="a9d75-102">ISymUnmanagedScope::GetParent Method</span></span>
<span data-ttu-id="a9d75-103">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="a9d75-103">Gets the parent scope of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d75-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9d75-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9d75-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9d75-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a9d75-106">[out] Un puntero a la devuelta [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="a9d75-106">[out] A pointer to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9d75-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9d75-107">Return Value</span></span>  
 <span data-ttu-id="a9d75-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a9d75-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d75-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9d75-109">Requirements</span></span>  
 <span data-ttu-id="a9d75-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a9d75-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d75-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9d75-111">See also</span></span>

- [<span data-ttu-id="a9d75-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9d75-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="a9d75-113">GetChildren (método)</span><span class="sxs-lookup"><span data-stu-id="a9d75-113">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)
