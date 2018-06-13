---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f756a6e80eee0998398b4955d1d091d97b2ad73f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426164"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="d9a99-102">ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="d9a99-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="d9a99-103">Devuelve el método que contiene el punto de interrupción en la posición especificada en un documento.</span><span class="sxs-lookup"><span data-stu-id="d9a99-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a99-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9a99-104">Syntax</span></span>  
  
```  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9a99-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9a99-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="d9a99-106">[in] El documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d9a99-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="d9a99-107">[in] La línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d9a99-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="d9a99-108">[in] La columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="d9a99-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="d9a99-109">[out] Un puntero a la dirección de un [ISymUnmanagedMethod (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) objeto que representa el método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="d9a99-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9a99-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9a99-110">Return Value</span></span>  
 <span data-ttu-id="d9a99-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d9a99-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9a99-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9a99-112">Requirements</span></span>  
 <span data-ttu-id="d9a99-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d9a99-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a99-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9a99-114">See Also</span></span>  
 [<span data-ttu-id="d9a99-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9a99-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
