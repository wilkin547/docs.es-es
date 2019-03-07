---
title: ISymUnmanagedDocument::GetURL (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b4e501629198c9bac627979547a5603d3e7866a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467134"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="fe657-102">ISymUnmanagedDocument::GetURL (Método)</span><span class="sxs-lookup"><span data-stu-id="fe657-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="fe657-103">Devuelve el localizador uniforme de recursos (URL) para este documento.</span><span class="sxs-lookup"><span data-stu-id="fe657-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe657-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe657-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe657-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe657-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="fe657-106">[in] Tamaño, en caracteres, del búfer de `szURL`.</span><span class="sxs-lookup"><span data-stu-id="fe657-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="fe657-107">[out] Un puntero a una variable que recibe el tamaño de la dirección URL, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="fe657-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="fe657-108">[out] El búfer que contiene la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="fe657-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe657-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fe657-109">Return Value</span></span>  
 <span data-ttu-id="fe657-110">S_OK si el método se realiza correctamente; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="fe657-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe657-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe657-111">See also</span></span>
- [<span data-ttu-id="fe657-112">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe657-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
