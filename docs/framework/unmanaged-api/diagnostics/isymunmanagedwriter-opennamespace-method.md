---
title: ISymUnmanagedWriter::OpenNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a108ec27cc4f8ed9d9d3c9227bf6ab0815fa933
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739698"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="a0a31-102">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="a0a31-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="a0a31-103">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0a31-103">Opens a new namespace.</span></span> <span data-ttu-id="a0a31-104">Llame a este método antes de definir métodos o variables que ocupan un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0a31-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="a0a31-105">Los espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="a0a31-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a31-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0a31-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0a31-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0a31-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="a0a31-108">[in] Un puntero al nombre del nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a0a31-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0a31-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a0a31-109">Return Value</span></span>  
 <span data-ttu-id="a0a31-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a0a31-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a31-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0a31-111">Requirements</span></span>  
 <span data-ttu-id="a0a31-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a0a31-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a31-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0a31-113">See also</span></span>
- [<span data-ttu-id="a0a31-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a0a31-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="a0a31-115">CloseNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="a0a31-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
