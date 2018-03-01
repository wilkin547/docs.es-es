---
title: "ISymUnmanagedWriter::CloseScope (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d47be1d220729ed32fcf77a77e611003085c15d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="58027-102">ISymUnmanagedWriter::CloseScope (Método)</span><span class="sxs-lookup"><span data-stu-id="58027-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="58027-103">Cierra el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="58027-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58027-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58027-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58027-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58027-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="58027-106">[in] El desplazamiento desde el principio del método del punto al final de la última instrucción del ámbito léxico, en bytes.</span><span class="sxs-lookup"><span data-stu-id="58027-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58027-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58027-107">Return Value</span></span>  
 <span data-ttu-id="58027-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="58027-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58027-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58027-109">Remarks</span></span>  
 <span data-ttu-id="58027-110">Una vez se ha cerrado un ámbito, no hay más variables se pueden definir dentro de él.</span><span class="sxs-lookup"><span data-stu-id="58027-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="58027-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que puede utilizarse con [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) a posteriormente, define un ámbito de desplazamiento inicial y final.</span><span class="sxs-lookup"><span data-stu-id="58027-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="58027-112">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y `ISymUnmanagedWriter::CloseScope`.</span><span class="sxs-lookup"><span data-stu-id="58027-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="58027-113">Los identificadores de ámbito sólo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="58027-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58027-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58027-114">Requirements</span></span>  
 <span data-ttu-id="58027-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="58027-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58027-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="58027-116">See Also</span></span>  
 [<span data-ttu-id="58027-117">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58027-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
