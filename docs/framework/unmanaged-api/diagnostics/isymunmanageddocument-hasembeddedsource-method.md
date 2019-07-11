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
ms.openlocfilehash: 459a24e2ed9b97a67dc0266231fdfc32a9c853a6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776650"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="28973-102">ISymUnmanagedDocument::HasEmbeddedSource (Método)</span><span class="sxs-lookup"><span data-stu-id="28973-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="28973-103">Devuelve `true` si el documento tiene código fuente incrustado en los símbolos de depuración; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="28973-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28973-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28973-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28973-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28973-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="28973-106">[out] Un puntero a una variable que indica si el documento tiene código fuente incrustado en los símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="28973-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28973-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28973-107">Return Value</span></span>  
 <span data-ttu-id="28973-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="28973-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28973-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="28973-109">See also</span></span>

- [<span data-ttu-id="28973-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28973-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
