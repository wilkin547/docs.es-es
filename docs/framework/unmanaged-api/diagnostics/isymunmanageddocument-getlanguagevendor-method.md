---
title: ISymUnmanagedDocument::GetLanguageVendor (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd01dcbd45ecae84ccccffb510c20f580ae8c598
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080814"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="bd3e9-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="bd3e9-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="bd3e9-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd3e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd3e9-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd3e9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd3e9-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="bd3e9-106">[out] Un puntero a una variable que recibe el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd3e9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd3e9-107">Return Value</span></span>  
 <span data-ttu-id="bd3e9-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="bd3e9-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3e9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd3e9-109">See also</span></span>

- [<span data-ttu-id="bd3e9-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd3e9-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
