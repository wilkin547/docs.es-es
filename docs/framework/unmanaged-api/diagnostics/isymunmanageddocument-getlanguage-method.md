---
title: ISymUnmanagedDocument::GetLanguage (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 186ea5fd46ca5c6205ff1f98d8964e656655a2ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666038"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="62c56-102">ISymUnmanagedDocument::GetLanguage (Método)</span><span class="sxs-lookup"><span data-stu-id="62c56-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="62c56-103">Obtiene el identificador de idioma de este documento</span><span class="sxs-lookup"><span data-stu-id="62c56-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62c56-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62c56-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62c56-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="62c56-106">[out] Un puntero a una variable que recibe el identificador de idioma.</span><span class="sxs-lookup"><span data-stu-id="62c56-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62c56-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="62c56-107">Return Value</span></span>  
 <span data-ttu-id="62c56-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="62c56-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c56-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="62c56-109">See also</span></span>
- [<span data-ttu-id="62c56-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="62c56-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
