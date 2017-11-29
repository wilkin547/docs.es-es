---
title: "ISymUnmanagedWriter::CloseScope (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8df22e5f9ea2ca294f502fcebf4b2ed5cd7900d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="1c2ec-102">ISymUnmanagedWriter::CloseScope (Método)</span><span class="sxs-lookup"><span data-stu-id="1c2ec-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="1c2ec-103">Cierra el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="1c2ec-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c2ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c2ec-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c2ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c2ec-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="1c2ec-106">[in] El desplazamiento desde el principio del método del punto al final de la última instrucción del ámbito léxico, en bytes.</span><span class="sxs-lookup"><span data-stu-id="1c2ec-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c2ec-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1c2ec-107">Return Value</span></span>  
 <span data-ttu-id="1c2ec-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1c2ec-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c2ec-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c2ec-109">Remarks</span></span>  
 <span data-ttu-id="1c2ec-110">Una vez se ha cerrado un ámbito, no hay más variables se pueden definir dentro de él.</span><span class="sxs-lookup"><span data-stu-id="1c2ec-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="1c2ec-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) devuelve un identificador de ámbito opaco que puede utilizarse con [ISymUnmanagedWriter:: SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) a posteriormente, define un ámbito de desplazamiento inicial y final.</span><span class="sxs-lookup"><span data-stu-id="1c2ec-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="1c2ec-112">En este caso, se omiten los desplazamientos pasados a `ISymUnmanagedWriter::OpenScope` y `ISymUnmanagedWriter::CloseScope`.</span><span class="sxs-lookup"><span data-stu-id="1c2ec-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="1c2ec-113">Los identificadores de ámbito sólo son válidos en el método actual.</span><span class="sxs-lookup"><span data-stu-id="1c2ec-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c2ec-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c2ec-114">Requirements</span></span>  
 <span data-ttu-id="1c2ec-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1c2ec-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2ec-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c2ec-116">See Also</span></span>  
 [<span data-ttu-id="1c2ec-117">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c2ec-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
