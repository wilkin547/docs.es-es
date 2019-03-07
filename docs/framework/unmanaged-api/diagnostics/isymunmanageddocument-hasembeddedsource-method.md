---
title: ISymUnmanagedDocument::HasEmbeddedSource (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 620d303bcd33a4d04155850ec2c1b6293bf788d1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493263"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="03f13-102">ISymUnmanagedDocument::HasEmbeddedSource (Método)</span><span class="sxs-lookup"><span data-stu-id="03f13-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="03f13-103">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="03f13-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03f13-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03f13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03f13-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="03f13-106">[out] Un puntero a una variable que indica si el documento tiene código fuente incrustado en los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="03f13-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03f13-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03f13-107">Return Value</span></span>  
 <span data-ttu-id="03f13-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="03f13-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03f13-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="03f13-109">See also</span></span>
- [<span data-ttu-id="03f13-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03f13-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
