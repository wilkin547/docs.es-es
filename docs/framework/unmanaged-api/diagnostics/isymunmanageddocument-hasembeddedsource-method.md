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
ms.openlocfilehash: 350aecb9f9c99c9aa44ae6df6d31c7cb69ae5760
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430350"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="a8443-102">ISymUnmanagedDocument::HasEmbeddedSource (Método)</span><span class="sxs-lookup"><span data-stu-id="a8443-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="a8443-103">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="a8443-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8443-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8443-104">Syntax</span></span>  
  
```  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8443-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8443-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a8443-106">[out] Un puntero a una variable que indica si el documento tiene código fuente incrustado en los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="a8443-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8443-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a8443-107">Return Value</span></span>  
 <span data-ttu-id="a8443-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="a8443-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8443-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8443-109">See Also</span></span>  
 [<span data-ttu-id="a8443-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8443-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
