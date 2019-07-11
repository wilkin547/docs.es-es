---
title: IMapToken::Map (Método)
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ac12d5b6bc2911e3bd879285a9a12f65c426f0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745857"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="bf5a4-102">IMapToken::Map (Método)</span><span class="sxs-lookup"><span data-stu-id="bf5a4-102">IMapToken::Map Method</span></span>
<span data-ttu-id="bf5a4-103">Asigna una relación entre los ensamblados utilizando firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="bf5a4-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf5a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf5a4-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf5a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf5a4-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="bf5a4-106">[in] El token de metadatos que representa el objeto de código importados.</span><span class="sxs-lookup"><span data-stu-id="bf5a4-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="bf5a4-107">[in] El token de metadatos que representa el objeto de código emitido.</span><span class="sxs-lookup"><span data-stu-id="bf5a4-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf5a4-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf5a4-108">Remarks</span></span>  
 <span data-ttu-id="bf5a4-109">Cuando el token volver a asignar se produce durante una combinación, el token original se limita el ámbito de metadatos importados (origen) y el nuevo token se enfoca en el ámbito de metadatos emitido (destino).</span><span class="sxs-lookup"><span data-stu-id="bf5a4-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf5a4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf5a4-110">Requirements</span></span>  
 <span data-ttu-id="bf5a4-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf5a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf5a4-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf5a4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf5a4-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf5a4-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf5a4-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf5a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf5a4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf5a4-115">See also</span></span>

- [<span data-ttu-id="bf5a4-116">IMapToken (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf5a4-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
