---
title: "ISymUnmanagedMethod::GetOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c60d35b63d083ce4e23119e3fcb5e64c518f0ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="e8f90-102">ISymUnmanagedMethod::GetOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="e8f90-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="e8f90-103">Devuelve el desplazamiento dentro de este método que corresponde a una posición especificada dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="e8f90-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8f90-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8f90-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8f90-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="e8f90-106">[in] Un puntero al documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e8f90-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="e8f90-107">[in] La línea del documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e8f90-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="e8f90-108">[in] Columna del documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="e8f90-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e8f90-109">[out] Un puntero a un `ULONG32` que recibe los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="e8f90-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8f90-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e8f90-110">Return Value</span></span>  
 <span data-ttu-id="e8f90-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e8f90-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f90-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8f90-112">Requirements</span></span>  
 <span data-ttu-id="e8f90-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8f90-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8f90-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8f90-114">See Also</span></span>  
 [<span data-ttu-id="e8f90-115">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8f90-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
