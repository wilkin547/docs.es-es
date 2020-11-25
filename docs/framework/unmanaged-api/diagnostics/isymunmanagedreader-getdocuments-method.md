---
title: ISymUnmanagedReader::GetDocuments (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
ms.openlocfilehash: 757b7fecbbb187da079c8a5c51462ec58431966f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707625"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="1c28f-102">ISymUnmanagedReader::GetDocuments (Método)</span><span class="sxs-lookup"><span data-stu-id="1c28f-102">ISymUnmanagedReader::GetDocuments Method</span></span>

<span data-ttu-id="1c28f-103">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="1c28f-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c28f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c28f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c28f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c28f-105">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="1c28f-106">[in] Tamaño de la matriz `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="1c28f-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="1c28f-107">enuncia Puntero a una variable que recibe la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="1c28f-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="1c28f-108">enuncia Puntero a una variable que recibe la matriz del documento.</span><span class="sxs-lookup"><span data-stu-id="1c28f-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c28f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1c28f-109">Return Value</span></span>  

 <span data-ttu-id="1c28f-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1c28f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c28f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c28f-111">Requirements</span></span>  

 <span data-ttu-id="1c28f-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1c28f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c28f-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c28f-113">See also</span></span>

- [<span data-ttu-id="1c28f-114">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c28f-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
