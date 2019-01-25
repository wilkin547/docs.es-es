---
title: ISymUnmanagedScope::GetLocals (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d0e1b764691fd2582e1225cb90003e2a644061f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643694"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="8ef25-102">ISymUnmanagedScope::GetLocals (Método)</span><span class="sxs-lookup"><span data-stu-id="8ef25-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="8ef25-103">Obtiene las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="8ef25-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ef25-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ef25-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ef25-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="8ef25-106">[in] Un `ULONG32` que indica el tamaño de la `locals` matriz.</span><span class="sxs-lookup"><span data-stu-id="8ef25-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="8ef25-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="8ef25-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="8ef25-108">[out] Matriz que recibe las variables locales.</span><span class="sxs-lookup"><span data-stu-id="8ef25-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ef25-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8ef25-109">Return Value</span></span>  
 <span data-ttu-id="8ef25-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8ef25-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef25-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ef25-111">Requirements</span></span>  
 <span data-ttu-id="8ef25-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8ef25-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef25-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ef25-113">See also</span></span>
- [<span data-ttu-id="8ef25-114">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ef25-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
