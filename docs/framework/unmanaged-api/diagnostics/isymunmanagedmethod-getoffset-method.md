---
title: ISymUnmanagedMethod::GetOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6485688c2964d477f0c5f68a3da714f084fa308f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515314"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="fc010-102">ISymUnmanagedMethod::GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="fc010-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="fc010-103">Devuelve el desplazamiento dentro de este método que corresponde a una posición dada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="fc010-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc010-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc010-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc010-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc010-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="fc010-106">[in] Un puntero al documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="fc010-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="fc010-107">[in] La línea del documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="fc010-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="fc010-108">[in] Columna del documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="fc010-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fc010-109">[out] Un puntero a un `ULONG32` que recibe los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="fc010-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc010-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fc010-110">Return Value</span></span>  
 <span data-ttu-id="fc010-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="fc010-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc010-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc010-112">Requirements</span></span>  
 <span data-ttu-id="fc010-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fc010-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc010-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc010-114">See also</span></span>
- [<span data-ttu-id="fc010-115">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc010-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
