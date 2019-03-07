---
title: ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42c677ae5aeb1e1b70ab68be8920fc71215cfe63
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472006"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="f1667-102">ISymENCUnmanagedMethod::GetDocumentsForMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="f1667-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="f1667-103">Obtiene los documentos que este método tiene líneas.</span><span class="sxs-lookup"><span data-stu-id="f1667-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1667-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1667-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1667-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1667-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="f1667-106">[in] La longitud del búfer que apunta `pcDocs`.</span><span class="sxs-lookup"><span data-stu-id="f1667-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="f1667-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener los documentos.</span><span class="sxs-lookup"><span data-stu-id="f1667-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="f1667-108">[in] Búfer que contiene los documentos.</span><span class="sxs-lookup"><span data-stu-id="f1667-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1667-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f1667-109">Return Value</span></span>  
 <span data-ttu-id="f1667-110">S_OK si el método se realiza correctamente; en caso contrario, un código de error.</span><span class="sxs-lookup"><span data-stu-id="f1667-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1667-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1667-111">Requirements</span></span>  
 <span data-ttu-id="f1667-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f1667-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1667-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1667-113">See also</span></span>
- [<span data-ttu-id="f1667-114">ISymENCUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1667-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
