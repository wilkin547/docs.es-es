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
ms.openlocfilehash: 0a6830f47d5cac2cf9c84144c18486489b0ec581
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424536"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="5443a-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="5443a-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="5443a-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="5443a-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5443a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5443a-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5443a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5443a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5443a-106">[out] Un puntero a una variable que recibe el proveedor de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5443a-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5443a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5443a-107">Return Value</span></span>  
 <span data-ttu-id="5443a-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="5443a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5443a-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5443a-109">See Also</span></span>  
 [<span data-ttu-id="5443a-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5443a-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
