---
title: "ISymUnmanagedScope::GetLocals (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetLocals
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 07d42423d284da39d40268727de13b4605221b5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="6c2d3-102">ISymUnmanagedScope::GetLocals (Método)</span><span class="sxs-lookup"><span data-stu-id="6c2d3-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="6c2d3-103">Obtiene las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="6c2d3-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c2d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c2d3-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c2d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c2d3-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="6c2d3-106">[in] A `ULONG32` que indica el tamaño de la `locals` matriz.</span><span class="sxs-lookup"><span data-stu-id="6c2d3-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="6c2d3-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="6c2d3-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="6c2d3-108">[out] Matriz que recibe las variables locales.</span><span class="sxs-lookup"><span data-stu-id="6c2d3-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c2d3-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6c2d3-109">Return Value</span></span>  
 <span data-ttu-id="6c2d3-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="6c2d3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c2d3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c2d3-111">Requirements</span></span>  
 <span data-ttu-id="6c2d3-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6c2d3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c2d3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c2d3-113">See Also</span></span>  
 [<span data-ttu-id="6c2d3-114">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c2d3-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
