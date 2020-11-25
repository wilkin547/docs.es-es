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
ms.openlocfilehash: bac0f187409a191dda1ef635ec9b2da1aee25981
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700956"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="0e077-102">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="0e077-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>

<span data-ttu-id="0e077-103">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="0e077-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e077-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e077-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e077-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e077-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="0e077-106">enuncia Puntero a una variable que recibe el proveedor de idioma.</span><span class="sxs-lookup"><span data-stu-id="0e077-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e077-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0e077-107">Return Value</span></span>  

 <span data-ttu-id="0e077-108">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e077-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e077-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e077-109">See also</span></span>

- [<span data-ttu-id="0e077-110">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e077-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
