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
ms.openlocfilehash: 084f3ae12d906f5e80fdb86e65b09d2371fd246b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614596"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="8e185-102">ISymUnmanagedDocument::GetLanguage (Método)</span><span class="sxs-lookup"><span data-stu-id="8e185-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="8e185-103">Obtiene el identificador de idioma de este documento.</span><span class="sxs-lookup"><span data-stu-id="8e185-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e185-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e185-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e185-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e185-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8e185-106">enuncia Puntero a una variable que recibe el identificador de idioma.</span><span class="sxs-lookup"><span data-stu-id="8e185-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e185-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e185-107">Return Value</span></span>  
 <span data-ttu-id="8e185-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e185-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e185-109">Consulta también</span><span class="sxs-lookup"><span data-stu-id="8e185-109">See also</span></span>

- [<span data-ttu-id="8e185-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e185-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
