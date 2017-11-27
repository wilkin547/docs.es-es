---
title: "ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ad64d5722df68859e7be9d44b94b95cf1f43823f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="d3b54-102">ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="d3b54-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="d3b54-103">Devuelve el método que contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="d3b54-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3b54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3b54-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3b54-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3b54-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="d3b54-106">[in] El documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d3b54-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="d3b54-107">[in] La línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d3b54-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="d3b54-108">[in] La columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d3b54-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d3b54-109">[out] Un puntero a la dirección de un [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) objeto que representa el método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="d3b54-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3b54-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d3b54-110">Return Value</span></span>  
 <span data-ttu-id="d3b54-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d3b54-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3b54-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3b54-112">Requirements</span></span>  
 <span data-ttu-id="d3b54-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d3b54-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3b54-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3b54-114">See Also</span></span>  
 [<span data-ttu-id="d3b54-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3b54-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
