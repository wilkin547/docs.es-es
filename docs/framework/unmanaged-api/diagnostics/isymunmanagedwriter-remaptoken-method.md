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
ms.openlocfilehash: f37630c9631e2e76d9b98730b84086b8b86ec55d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427839"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="c8bb4-102">ISymUnmanagedWriter::RemapToken (Método)</span><span class="sxs-lookup"><span data-stu-id="c8bb4-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="c8bb4-103">Notifica que el escritor de símbolos que se ha reasignado un símbolo (token) de metadatos ya que los metadatos se emiten.</span><span class="sxs-lookup"><span data-stu-id="c8bb4-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="c8bb4-104">Si el escritor de símbolos ha almacenado el antiguo token en el almacén de símbolos, deberá actualizar que el token almacenado con el nuevo valor, o debe guardar el mapa para el lector de símbolos correspondientes para volver a asignar durante la fase de lectura.</span><span class="sxs-lookup"><span data-stu-id="c8bb4-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8bb4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8bb4-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8bb4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8bb4-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="c8bb4-107">[in] El token de metadatos que se ha reasignado.</span><span class="sxs-lookup"><span data-stu-id="c8bb4-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="c8bb4-108">[in] El nuevo token de metadatos a la que `oldToken` se vuelve a asignar.</span><span class="sxs-lookup"><span data-stu-id="c8bb4-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8bb4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c8bb4-109">Return Value</span></span>  
 <span data-ttu-id="c8bb4-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c8bb4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8bb4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8bb4-111">Requirements</span></span>  
 <span data-ttu-id="c8bb4-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c8bb4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8bb4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8bb4-113">See Also</span></span>  
 [<span data-ttu-id="c8bb4-114">ISymUnmanagedWriter (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8bb4-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
