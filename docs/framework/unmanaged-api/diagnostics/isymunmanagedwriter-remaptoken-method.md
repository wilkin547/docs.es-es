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
ms.openlocfilehash: 53cc908e0dc8cc5cc980ec365ccac0df4e620cac
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609773"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="d5d92-102">ISymUnmanagedWriter::RemapToken (Método)</span><span class="sxs-lookup"><span data-stu-id="d5d92-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="d5d92-103">Notifica al escritor de símbolos que se ha reasignado un token de metadatos cuando se emitieron los metadatos.</span><span class="sxs-lookup"><span data-stu-id="d5d92-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="d5d92-104">Si el escritor de símbolos ha almacenado el token anterior en el almacén de símbolos, debe actualizar el token almacenado con el nuevo valor, o bien debe guardar el mapa del lector de símbolos correspondiente para reasignarlo durante la fase de lectura.</span><span class="sxs-lookup"><span data-stu-id="d5d92-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d92-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5d92-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5d92-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5d92-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="d5d92-107">de Token de metadatos que se reasignó.</span><span class="sxs-lookup"><span data-stu-id="d5d92-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="d5d92-108">de Nuevo token de metadatos al que `oldToken` se ha reasignado.</span><span class="sxs-lookup"><span data-stu-id="d5d92-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5d92-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d5d92-109">Return Value</span></span>  
 <span data-ttu-id="d5d92-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d5d92-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5d92-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5d92-111">Requirements</span></span>  
 <span data-ttu-id="d5d92-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="d5d92-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d92-113">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d5d92-113">See also</span></span>

- [<span data-ttu-id="d5d92-114">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5d92-114">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
