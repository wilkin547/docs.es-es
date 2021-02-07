---
description: 'Más información acerca de: ISymUnmanagedDocument:: Getdocumenttype ((método)'
title: ISymUnmanagedDocument::GetDocumentType (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetDocumentType
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetDocumentType
helpviewer_keywords:
- ISymUnmanagedDocument::GetDocumentType method [.NET Framework debugging]
- GetDocumentType method [.NET Framework debugging]
ms.assetid: 2d381ab1-7e7c-4281-af2b-e54d879b3ef8
topic_type:
- apiref
ms.openlocfilehash: cf2ceffccb33eb7cba0d45af203e12d1e4244f60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710327"
---
# <a name="isymunmanageddocumentgetdocumenttype-method"></a><span data-ttu-id="752de-103">ISymUnmanagedDocument::GetDocumentType (Método)</span><span class="sxs-lookup"><span data-stu-id="752de-103">ISymUnmanagedDocument::GetDocumentType Method</span></span>

<span data-ttu-id="752de-104">Obtiene el tipo de documento de este documento.</span><span class="sxs-lookup"><span data-stu-id="752de-104">Gets the document type of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="752de-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="752de-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentType(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="752de-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="752de-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="752de-107">enuncia Puntero a una variable que recibe el tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="752de-107">[out] Pointer to a variable that receives the document type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="752de-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="752de-108">Return Value</span></span>  

 <span data-ttu-id="752de-109">S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="752de-109">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="752de-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="752de-110">See also</span></span>

- [<span data-ttu-id="752de-111">ISymUnmanagedDocument (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="752de-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
