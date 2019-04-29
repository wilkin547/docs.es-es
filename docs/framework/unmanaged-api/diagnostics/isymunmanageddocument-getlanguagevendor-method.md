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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939833"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="01a2e-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="01a2e-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="01a2e-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="01a2e-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a2e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01a2e-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01a2e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01a2e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="01a2e-106">[out] Un puntero a una variable que recibe el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="01a2e-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01a2e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="01a2e-107">Return Value</span></span>  
 <span data-ttu-id="01a2e-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="01a2e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a2e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="01a2e-109">See also</span></span>

- [<span data-ttu-id="01a2e-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="01a2e-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
