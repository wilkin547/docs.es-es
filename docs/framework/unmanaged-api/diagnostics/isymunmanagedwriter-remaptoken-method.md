---
description: 'Más información acerca de: ISymUnmanagedWriter:: RemapToken ((método)'
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
ms.openlocfilehash: c065d42c3d2749f0262fdd81a74de918274ba67d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762089"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="2b88f-103">ISymUnmanagedWriter::RemapToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2b88f-103">ISymUnmanagedWriter::RemapToken Method</span></span>

<span data-ttu-id="2b88f-104">Notifica al escritor de símbolos que se ha reasignado un token de metadatos cuando se emitieron los metadatos.</span><span class="sxs-lookup"><span data-stu-id="2b88f-104">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="2b88f-105">Si el escritor de símbolos ha almacenado el token anterior en el almacén de símbolos, debe actualizar el token almacenado con el nuevo valor, o bien debe guardar el mapa del lector de símbolos correspondiente para reasignarlo durante la fase de lectura.</span><span class="sxs-lookup"><span data-stu-id="2b88f-105">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b88f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b88f-106">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b88f-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b88f-107">Parameters</span></span>  

 `oldToken`  
 <span data-ttu-id="2b88f-108">de Token de metadatos que se reasignó.</span><span class="sxs-lookup"><span data-stu-id="2b88f-108">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="2b88f-109">de Nuevo token de metadatos al que `oldToken` se ha reasignado.</span><span class="sxs-lookup"><span data-stu-id="2b88f-109">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b88f-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2b88f-110">Return Value</span></span>  

 <span data-ttu-id="2b88f-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2b88f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b88f-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b88f-112">Requirements</span></span>  

 <span data-ttu-id="2b88f-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2b88f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b88f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b88f-114">See also</span></span>

- [<span data-ttu-id="2b88f-115">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b88f-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
