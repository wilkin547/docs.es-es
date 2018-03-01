---
title: "ISymUnmanagedDocument::GetURL (Método)"
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
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2688c2c50181c7bac7b7ee869b4e1fa5094d0ea9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="0d02f-102">ISymUnmanagedDocument::GetURL (Método)</span><span class="sxs-lookup"><span data-stu-id="0d02f-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="0d02f-103">Devuelve el localizador uniforme de recursos (URL) de este documento.</span><span class="sxs-lookup"><span data-stu-id="0d02f-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d02f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d02f-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d02f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d02f-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="0d02f-106">[in] Tamaño, en caracteres, del búfer de `szURL`.</span><span class="sxs-lookup"><span data-stu-id="0d02f-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="0d02f-107">[out] Un puntero a una variable que recibe el tamaño de la dirección URL, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="0d02f-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="0d02f-108">[out] El búfer que contiene la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="0d02f-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d02f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0d02f-109">Return Value</span></span>  
 <span data-ttu-id="0d02f-110">S_OK si el método tiene éxito; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="0d02f-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d02f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d02f-111">See Also</span></span>  
 [<span data-ttu-id="0d02f-112">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d02f-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
