---
title: "ISymUnmanagedWriter::OpenNamespace (Método)"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77d50f6bac87d5a110b53a69044f96f547c51904
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="8b58b-102">ISymUnmanagedWriter::OpenNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="8b58b-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="8b58b-103">Abre un nuevo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8b58b-103">Opens a new namespace.</span></span> <span data-ttu-id="8b58b-104">Llamar a este método antes de definir métodos o variables que ocupan un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8b58b-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="8b58b-105">Espacios de nombres se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="8b58b-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b58b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b58b-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b58b-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b58b-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8b58b-108">[in] Un puntero al nombre del espacio de nombres nuevo.</span><span class="sxs-lookup"><span data-stu-id="8b58b-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b58b-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8b58b-109">Return Value</span></span>  
 <span data-ttu-id="8b58b-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8b58b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b58b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b58b-111">Requirements</span></span>  
 <span data-ttu-id="8b58b-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8b58b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b58b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b58b-113">See Also</span></span>  
 [<span data-ttu-id="8b58b-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b58b-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="8b58b-115">CloseNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="8b58b-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
