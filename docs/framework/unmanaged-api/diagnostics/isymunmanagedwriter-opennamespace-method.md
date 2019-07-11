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
ms.openlocfilehash: 5bd07411acd074bf5a25148110dbdf28a004551a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777249"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="3d02a-102">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="3d02a-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="3d02a-103">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3d02a-103">Opens a new namespace.</span></span> <span data-ttu-id="3d02a-104">Llame a este método antes de definir métodos o variables que ocupan un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3d02a-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="3d02a-105">Los espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="3d02a-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d02a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d02a-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d02a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d02a-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3d02a-108">[in] Un puntero al nombre del nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3d02a-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d02a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3d02a-109">Return Value</span></span>  
 <span data-ttu-id="3d02a-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3d02a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d02a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d02a-111">Requirements</span></span>  
 <span data-ttu-id="3d02a-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3d02a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d02a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d02a-113">See also</span></span>

- [<span data-ttu-id="3d02a-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d02a-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="3d02a-115">CloseNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="3d02a-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
