---
description: 'Más información acerca de: ISymUnmanagedReader:: Getdocumentversion ((método)'
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
ms.openlocfilehash: e6877a10f0c285186330b320c9b614939f4d9e3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800206"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="9215d-103">ISymUnmanagedReader::GetDocumentVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="9215d-103">ISymUnmanagedReader::GetDocumentVersion Method</span></span>

<span data-ttu-id="9215d-104">Obtiene la versión especificada del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="9215d-104">Gets the specified version of the specified document.</span></span> <span data-ttu-id="9215d-105">La versión del documento comienza en 1 y se incrementa cada vez que se actualiza el documento mediante el método [UpdateSymbolStore (](isymunmanagedreader-updatesymbolstore-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9215d-105">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="9215d-106">Si el `pbCurrent` parámetro es `true` , esta es la versión más reciente del documento.</span><span class="sxs-lookup"><span data-stu-id="9215d-106">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9215d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9215d-107">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9215d-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9215d-108">Parameters</span></span>  

 `pDoc`  
 <span data-ttu-id="9215d-109">de Documento especificado.</span><span class="sxs-lookup"><span data-stu-id="9215d-109">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="9215d-110">enuncia Puntero a una variable que recibe la versión del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="9215d-110">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="9215d-111">enuncia Un puntero a una variable que recibe `true` si se trata de la versión más reciente del documento, o `false` si no es la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="9215d-111">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9215d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9215d-112">Return Value</span></span>  

 <span data-ttu-id="9215d-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9215d-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9215d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9215d-114">Requirements</span></span>  

 <span data-ttu-id="9215d-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9215d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9215d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9215d-116">See also</span></span>

- [<span data-ttu-id="9215d-117">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9215d-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
