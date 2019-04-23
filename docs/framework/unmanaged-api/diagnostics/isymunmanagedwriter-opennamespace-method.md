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
ms.openlocfilehash: 1585acce8bba0dff327c961f5e32ef6b46794401
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126339"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="c0931-102">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="c0931-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="c0931-103">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c0931-103">Opens a new namespace.</span></span> <span data-ttu-id="c0931-104">Llame a este método antes de definir métodos o variables que ocupan un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c0931-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="c0931-105">Los espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="c0931-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0931-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0931-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0931-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0931-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c0931-108">[in] Un puntero al nombre del nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c0931-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0931-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c0931-109">Return Value</span></span>  
 <span data-ttu-id="c0931-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c0931-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0931-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0931-111">Requirements</span></span>  
 <span data-ttu-id="c0931-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c0931-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0931-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0931-113">See also</span></span>

- [<span data-ttu-id="c0931-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0931-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="c0931-115">CloseNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="c0931-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
