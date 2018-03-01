---
title: "ISymUnmanagedDocument::GetLanguageVendor (Método)"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc0d05e3d0536f596fc305e32863a39d27a77fe9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="ad457-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="ad457-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="ad457-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="ad457-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad457-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad457-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad457-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad457-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ad457-106">[out] Un puntero a una variable que recibe el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ad457-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad457-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ad457-107">Return Value</span></span>  
 <span data-ttu-id="ad457-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="ad457-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad457-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad457-109">See Also</span></span>  
 [<span data-ttu-id="ad457-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad457-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
