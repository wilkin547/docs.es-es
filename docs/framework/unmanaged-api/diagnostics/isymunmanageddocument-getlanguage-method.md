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
ms.openlocfilehash: 05ce47953358b7025e30080fbbaf288a6c0e879d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939846"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="f83e6-102">ISymUnmanagedDocument::GetLanguage (Método)</span><span class="sxs-lookup"><span data-stu-id="f83e6-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="f83e6-103">Obtiene el identificador de idioma de este documento</span><span class="sxs-lookup"><span data-stu-id="f83e6-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f83e6-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f83e6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f83e6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f83e6-106">[out] Un puntero a una variable que recibe el identificador de idioma.</span><span class="sxs-lookup"><span data-stu-id="f83e6-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f83e6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f83e6-107">Return Value</span></span>  
 <span data-ttu-id="f83e6-108">S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="f83e6-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83e6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f83e6-109">See also</span></span>

- [<span data-ttu-id="f83e6-110">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f83e6-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
