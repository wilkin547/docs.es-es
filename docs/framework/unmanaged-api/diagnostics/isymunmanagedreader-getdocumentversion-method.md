---
title: ISymUnmanagedReader::GetDocumentVersion (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92353cfc2d9ce39074bf43937b5673ff51e34822
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080012"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="a793f-102">ISymUnmanagedReader::GetDocumentVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="a793f-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="a793f-103">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="a793f-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="a793f-104">La versión del documento comienza en 1 y se incrementa cada vez que se actualiza el documento con el [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a793f-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="a793f-105">Si el `pbCurrent` parámetro es `true`, esta es la versión más reciente del documento.</span><span class="sxs-lookup"><span data-stu-id="a793f-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a793f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a793f-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a793f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a793f-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="a793f-108">[in] El documento especificado.</span><span class="sxs-lookup"><span data-stu-id="a793f-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="a793f-109">[out] Un puntero a una variable que recibe la versión del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="a793f-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="a793f-110">[out] Un puntero a una variable que recibe `true` si se trata de la versión más reciente del documento, o `false` si no es la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="a793f-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a793f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a793f-111">Return Value</span></span>  
 <span data-ttu-id="a793f-112">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a793f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a793f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a793f-113">Requirements</span></span>  
 <span data-ttu-id="a793f-114">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a793f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a793f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a793f-115">See also</span></span>

- [<span data-ttu-id="a793f-116">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a793f-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
