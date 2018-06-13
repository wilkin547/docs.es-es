---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c84aceb0faabd879911e9595a7f3154065e2191
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426203"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="52ae8-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="52ae8-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="52ae8-103">Devuelve una matriz de los métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="52ae8-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ae8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52ae8-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="52ae8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52ae8-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="52ae8-106">[in] El documento especificado.</span><span class="sxs-lookup"><span data-stu-id="52ae8-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="52ae8-107">[in] La línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="52ae8-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="52ae8-108">[in] La columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="52ae8-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="52ae8-109">[in] Tamaño de la matriz `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="52ae8-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="52ae8-110">[out] Un puntero a una variable que recibe el número de elementos devueltos en la `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="52ae8-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="52ae8-111">[out] Una matriz de punteros, cada uno de los cuales señala a un [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) objeto que representa un método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="52ae8-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52ae8-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52ae8-112">Return Value</span></span>  
 <span data-ttu-id="52ae8-113">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="52ae8-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52ae8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52ae8-114">Requirements</span></span>  
 <span data-ttu-id="52ae8-115">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="52ae8-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ae8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ae8-116">See Also</span></span>  
 [<span data-ttu-id="52ae8-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52ae8-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
