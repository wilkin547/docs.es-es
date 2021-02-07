---
description: 'Más información acerca de: ISymUnmanagedDocument:: Getlanguagevendor ((método)'
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
ms.openlocfilehash: 247c6c24f57211b3b46ad773d8e77d7e0f16fd01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710249"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="515da-103">ISymUnmanagedDocument::GetLanguageVendor (Método)</span><span class="sxs-lookup"><span data-stu-id="515da-103">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>

<span data-ttu-id="515da-104">Obtiene el proveedor de lenguaje de este documento.</span><span class="sxs-lookup"><span data-stu-id="515da-104">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="515da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="515da-105">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="515da-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="515da-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="515da-107">enuncia Puntero a una variable que recibe el proveedor de idioma.</span><span class="sxs-lookup"><span data-stu-id="515da-107">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="515da-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="515da-108">Return Value</span></span>  

 <span data-ttu-id="515da-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="515da-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515da-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="515da-110">See also</span></span>

- [<span data-ttu-id="515da-111">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="515da-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
