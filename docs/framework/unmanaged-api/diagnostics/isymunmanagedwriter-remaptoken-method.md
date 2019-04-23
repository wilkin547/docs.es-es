---
title: ISymUnmanagedWriter::RemapToken (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 979d14b4c404c3bf12c427bd5b8b1d4997805e7b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160685"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="d6281-102">ISymUnmanagedWriter::RemapToken (Método)</span><span class="sxs-lookup"><span data-stu-id="d6281-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="d6281-103">Notifica al escritor de símbolos que se ha reasignado un token de metadatos que se emitieron los metadatos.</span><span class="sxs-lookup"><span data-stu-id="d6281-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="d6281-104">Si el escritor de símbolos ha almacenado el antiguo token en el almacén de símbolos, deberá actualizar que el token almacenado con el nuevo valor, o bien guardar la asignación del lector de símbolos correspondiente para volver a asignar durante la fase de lectura.</span><span class="sxs-lookup"><span data-stu-id="d6281-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6281-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6281-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6281-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6281-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="d6281-107">[in] El token de metadatos que se ha reasignado.</span><span class="sxs-lookup"><span data-stu-id="d6281-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="d6281-108">[in] El nuevo token de metadatos a la que `oldToken` se volvió a asignar.</span><span class="sxs-lookup"><span data-stu-id="d6281-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6281-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6281-109">Return Value</span></span>  
 <span data-ttu-id="d6281-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d6281-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6281-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6281-111">Requirements</span></span>  
 <span data-ttu-id="d6281-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d6281-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6281-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6281-113">See also</span></span>

- [<span data-ttu-id="d6281-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6281-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
