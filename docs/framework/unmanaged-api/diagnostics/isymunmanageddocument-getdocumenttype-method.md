---
title: "ISymUnmanagedDocument::GetDocumentType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetDocumentType
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b6e2d81680c2aa5973c0095a6a3ba7cfa158031
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="c7f5b-102">ISymUnmanagedDocument::GetDocumentType (Método)</span><span class="sxs-lookup"><span data-stu-id="c7f5b-102">ISymUnmanagedDocument::GetDocumentType Method</span></span>
<span data-ttu-id="c7f5b-103">Obtiene el tipo de documento de este documento.</span><span class="sxs-lookup"><span data-stu-id="c7f5b-103">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7f5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7f5b-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7f5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c7f5b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="c7f5b-106">[out] Puntero a una variable que recibe el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="c7f5b-106">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7f5b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c7f5b-107">Return Value</span></span>  
 <span data-ttu-id="c7f5b-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="c7f5b-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f5b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7f5b-109">See Also</span></span>  
 [<span data-ttu-id="c7f5b-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c7f5b-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
