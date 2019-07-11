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
ms.openlocfilehash: c04ca1d56f3e93c77f335218bb534f890e9053d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776612"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="aba8a-102">ISymUnmanagedWriter::RemapToken (Método)</span><span class="sxs-lookup"><span data-stu-id="aba8a-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="aba8a-103">Notifica al escritor de símbolos que se ha reasignado un token de metadatos que se emitieron los metadatos.</span><span class="sxs-lookup"><span data-stu-id="aba8a-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="aba8a-104">Si el escritor de símbolos ha almacenado el antiguo token en el almacén de símbolos, deberá actualizar que el token almacenado con el nuevo valor, o bien guardar la asignación del lector de símbolos correspondiente para volver a asignar durante la fase de lectura.</span><span class="sxs-lookup"><span data-stu-id="aba8a-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba8a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aba8a-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aba8a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aba8a-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="aba8a-107">[in] El token de metadatos que se ha reasignado.</span><span class="sxs-lookup"><span data-stu-id="aba8a-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="aba8a-108">[in] El nuevo token de metadatos a la que `oldToken` se volvió a asignar.</span><span class="sxs-lookup"><span data-stu-id="aba8a-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aba8a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aba8a-109">Return Value</span></span>  
 <span data-ttu-id="aba8a-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="aba8a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aba8a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aba8a-111">Requirements</span></span>  
 <span data-ttu-id="aba8a-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aba8a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba8a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="aba8a-113">See also</span></span>

- [<span data-ttu-id="aba8a-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aba8a-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
