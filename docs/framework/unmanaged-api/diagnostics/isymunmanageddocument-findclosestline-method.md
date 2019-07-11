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
ms.openlocfilehash: 8d6be64137b59c84dfadbd7f0e4895eac2fb27e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776801"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="1c989-102">ISymUnmanagedDocument::FindClosestLine (Método)</span><span class="sxs-lookup"><span data-stu-id="1c989-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="1c989-103">Devuelve la línea más próxima que sea un punto de secuencia, se especifica una línea en este documento que puede o no ser un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="1c989-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c989-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c989-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c989-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c989-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="1c989-106">[in] Una línea en este documento.</span><span class="sxs-lookup"><span data-stu-id="1c989-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1c989-107">[out] Un puntero a una variable que recibe la línea.</span><span class="sxs-lookup"><span data-stu-id="1c989-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c989-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1c989-108">Return Value</span></span>  
 <span data-ttu-id="1c989-109">S_OK si el método se realiza correctamente; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="1c989-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c989-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c989-110">See also</span></span>

- [<span data-ttu-id="1c989-111">ISymUnmanagedDocument (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c989-111">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
