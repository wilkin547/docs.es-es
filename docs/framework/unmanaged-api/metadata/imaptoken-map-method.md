---
description: 'Más información acerca de: IMapToken:: Map (método)'
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
ms.openlocfilehash: da78f22e944a0e4ec25adcd7cdf97b69131a6612
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706742"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="c5571-103">IMapToken::Map (Método)</span><span class="sxs-lookup"><span data-stu-id="c5571-103">IMapToken::Map Method</span></span>

<span data-ttu-id="c5571-104">Asigna una relación entre los ensamblados mediante firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c5571-104">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5571-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5571-105">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5571-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5571-106">Parameters</span></span>  

 `tkImp`  
 <span data-ttu-id="c5571-107">de Token de metadatos que representa el objeto de código importado.</span><span class="sxs-lookup"><span data-stu-id="c5571-107">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="c5571-108">de Token de metadatos que representa el objeto de código emitido.</span><span class="sxs-lookup"><span data-stu-id="c5571-108">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5571-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5571-109">Remarks</span></span>  

 <span data-ttu-id="c5571-110">Cuando se produce la reasignación del token durante una combinación, el ámbito del token original se encuentra en el ámbito de metadatos (origen) importado y el ámbito del nuevo token se encuentra en el ámbito de los metadatos emitidos (de destino).</span><span class="sxs-lookup"><span data-stu-id="c5571-110">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5571-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5571-111">Requirements</span></span>  

 <span data-ttu-id="c5571-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5571-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5571-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c5571-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5571-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c5571-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5571-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5571-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5571-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5571-116">See also</span></span>

- [<span data-ttu-id="c5571-117">IMapToken (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5571-117">IMapToken Interface</span></span>](imaptoken-interface.md)
