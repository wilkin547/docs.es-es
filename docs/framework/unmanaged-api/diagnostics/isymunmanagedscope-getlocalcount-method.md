---
title: ISymUnmanagedScope::GetLocalCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b3c9c637bdaa0d0e18dbfd9655790ff5ebd46f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986205"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="f31d4-102">ISymUnmanagedScope::GetLocalCount (Método)</span><span class="sxs-lookup"><span data-stu-id="f31d4-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="f31d4-103">Obtiene un recuento de las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="f31d4-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f31d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f31d4-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f31d4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f31d4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f31d4-106">[out] Un puntero a un `ULONG32` que recibe el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="f31d4-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f31d4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f31d4-107">Return Value</span></span>  
 <span data-ttu-id="f31d4-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f31d4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f31d4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f31d4-109">Requirements</span></span>  
 <span data-ttu-id="f31d4-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f31d4-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f31d4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f31d4-111">See also</span></span>

- [<span data-ttu-id="f31d4-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f31d4-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
