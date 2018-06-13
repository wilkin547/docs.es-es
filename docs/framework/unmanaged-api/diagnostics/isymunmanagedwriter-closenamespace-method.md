---
title: ISymUnmanagedWriter::CloseNamespace (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d7e1e4da51445a55387b813e814183bf7433e45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426928"
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="e01ca-102">ISymUnmanagedWriter::CloseNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="e01ca-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="e01ca-103">Se cierra la última abre espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e01ca-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e01ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e01ca-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e01ca-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e01ca-105">Return Value</span></span>  
 <span data-ttu-id="e01ca-106">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e01ca-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e01ca-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e01ca-107">Requirements</span></span>  
 <span data-ttu-id="e01ca-108">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e01ca-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e01ca-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e01ca-109">See Also</span></span>  
 [<span data-ttu-id="e01ca-110">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e01ca-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e01ca-111">OpenNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="e01ca-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
