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
ms.openlocfilehash: 0ec3f94d290423130e3718b32cd8058f59d797d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694521"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="99f79-102">ISymUnmanagedWriter::RemapToken (Método)</span><span class="sxs-lookup"><span data-stu-id="99f79-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="99f79-103">Notifica al escritor de símbolos que se ha reasignado un token de metadatos que se emitieron los metadatos.</span><span class="sxs-lookup"><span data-stu-id="99f79-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="99f79-104">Si el escritor de símbolos ha almacenado el antiguo token en el almacén de símbolos, deberá actualizar que el token almacenado con el nuevo valor, o bien guardar la asignación del lector de símbolos correspondiente para volver a asignar durante la fase de lectura.</span><span class="sxs-lookup"><span data-stu-id="99f79-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99f79-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99f79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99f79-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="99f79-107">[in] El token de metadatos que se ha reasignado.</span><span class="sxs-lookup"><span data-stu-id="99f79-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="99f79-108">[in] El nuevo token de metadatos a la que `oldToken` se volvió a asignar.</span><span class="sxs-lookup"><span data-stu-id="99f79-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99f79-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99f79-109">Return Value</span></span>  
 <span data-ttu-id="99f79-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="99f79-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f79-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99f79-111">Requirements</span></span>  
 <span data-ttu-id="99f79-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="99f79-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f79-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="99f79-113">See also</span></span>
- [<span data-ttu-id="99f79-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="99f79-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
