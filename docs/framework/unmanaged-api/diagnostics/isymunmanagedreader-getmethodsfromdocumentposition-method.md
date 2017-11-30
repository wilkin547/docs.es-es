---
title: "ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f82cf213e9bcc83055cfaa42b9acab9d395d405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="f1583-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="f1583-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="f1583-103">Devuelve una matriz de los métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="f1583-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1583-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1583-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1583-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1583-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="f1583-106">[in] El documento especificado.</span><span class="sxs-lookup"><span data-stu-id="f1583-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="f1583-107">[in] La línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="f1583-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="f1583-108">[in] La columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="f1583-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="f1583-109">[in] Tamaño de la matriz `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="f1583-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="f1583-110">[out] Un puntero a una variable que recibe el número de elementos devueltos en la `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="f1583-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f1583-111">[out] Una matriz de punteros, cada uno de los cuales señala a un [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) objeto que representa un método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="f1583-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1583-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f1583-112">Return Value</span></span>  
 <span data-ttu-id="f1583-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f1583-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1583-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1583-114">Requirements</span></span>  
 <span data-ttu-id="f1583-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f1583-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1583-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1583-116">See Also</span></span>  
 [<span data-ttu-id="f1583-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1583-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
