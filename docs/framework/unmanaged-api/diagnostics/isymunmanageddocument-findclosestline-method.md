---
title: ISymUnmanagedDocument::FindClosestLine (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96ad0e34bf638c378f37e317f790696c2ac7cb25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519702"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="abfea-102">ISymUnmanagedDocument::FindClosestLine (Método)</span><span class="sxs-lookup"><span data-stu-id="abfea-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="abfea-103">Devuelve la línea más próxima que sea un punto de secuencia, se especifica una línea en este documento que puede o no ser un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="abfea-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abfea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abfea-104">Syntax</span></span>  
  
```  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abfea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abfea-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="abfea-106">[in] Una línea en este documento.</span><span class="sxs-lookup"><span data-stu-id="abfea-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="abfea-107">[out] Un puntero a una variable que recibe la línea.</span><span class="sxs-lookup"><span data-stu-id="abfea-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abfea-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="abfea-108">Return Value</span></span>  
 <span data-ttu-id="abfea-109">S_OK si el método se realiza correctamente; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="abfea-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfea-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="abfea-110">See also</span></span>
- [<span data-ttu-id="abfea-111">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abfea-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
