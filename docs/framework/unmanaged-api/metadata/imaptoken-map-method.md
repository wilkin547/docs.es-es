---
title: "IMapToken::Map (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMapToken.Map
api_location: mscoree.dll
api_type: COM
f1_keywords: IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2e3a9701bab27764803442a3cd0c24c4e412deaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="482e8-102">IMapToken::Map (Método)</span><span class="sxs-lookup"><span data-stu-id="482e8-102">IMapToken::Map Method</span></span>
<span data-ttu-id="482e8-103">Asigna una relación entre los ensamblados utilizando firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="482e8-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="482e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="482e8-104">Syntax</span></span>  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="482e8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="482e8-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="482e8-106">[in] El token de metadatos que representa el objeto de código importado.</span><span class="sxs-lookup"><span data-stu-id="482e8-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="482e8-107">[in] El token de metadatos que representa el objeto de código emitido.</span><span class="sxs-lookup"><span data-stu-id="482e8-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="482e8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="482e8-108">Remarks</span></span>  
 <span data-ttu-id="482e8-109">Cuando el token volver a asignar se produce durante una mezcla, el token original tiene un ámbito en el ámbito de metadatos importados (origen) y el nuevo token tiene un ámbito en el ámbito de metadatos emitido (destino).</span><span class="sxs-lookup"><span data-stu-id="482e8-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="482e8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="482e8-110">Requirements</span></span>  
 <span data-ttu-id="482e8-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="482e8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="482e8-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="482e8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="482e8-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="482e8-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="482e8-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="482e8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="482e8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="482e8-115">See Also</span></span>  
 [<span data-ttu-id="482e8-116">IMapToken (interfaz)</span><span class="sxs-lookup"><span data-stu-id="482e8-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
