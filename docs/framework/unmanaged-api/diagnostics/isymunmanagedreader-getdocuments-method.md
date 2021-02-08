---
description: 'Más información acerca de: ISymUnmanagedReader:: Getdocuments ((método)'
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
ms.openlocfilehash: 8ee2a2d8e83fcbe2f5b39960fa99e11de2ab4cd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800219"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="70dcb-103">ISymUnmanagedReader::GetDocuments (Método)</span><span class="sxs-lookup"><span data-stu-id="70dcb-103">ISymUnmanagedReader::GetDocuments Method</span></span>

<span data-ttu-id="70dcb-104">Devuelve una matriz de todos los documentos definidos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="70dcb-104">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70dcb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70dcb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70dcb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70dcb-106">Parameters</span></span>  

 `cDocs`  
 <span data-ttu-id="70dcb-107">[in] Tamaño de la matriz `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="70dcb-107">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="70dcb-108">enuncia Puntero a una variable que recibe la longitud de la matriz.</span><span class="sxs-lookup"><span data-stu-id="70dcb-108">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="70dcb-109">enuncia Puntero a una variable que recibe la matriz del documento.</span><span class="sxs-lookup"><span data-stu-id="70dcb-109">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70dcb-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="70dcb-110">Return Value</span></span>  

 <span data-ttu-id="70dcb-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="70dcb-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70dcb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70dcb-112">Requirements</span></span>  

 <span data-ttu-id="70dcb-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="70dcb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70dcb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="70dcb-114">See also</span></span>

- [<span data-ttu-id="70dcb-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="70dcb-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
