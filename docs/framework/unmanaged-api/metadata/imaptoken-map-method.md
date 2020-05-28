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
ms.openlocfilehash: 027694cee1b3e4d990796ba31300918f6d859679
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008201"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="dd28c-102">IMapToken::Map (Método)</span><span class="sxs-lookup"><span data-stu-id="dd28c-102">IMapToken::Map Method</span></span>
<span data-ttu-id="dd28c-103">Asigna una relación entre los ensamblados mediante firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="dd28c-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd28c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd28c-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd28c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dd28c-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="dd28c-106">de Token de metadatos que representa el objeto de código importado.</span><span class="sxs-lookup"><span data-stu-id="dd28c-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="dd28c-107">de Token de metadatos que representa el objeto de código emitido.</span><span class="sxs-lookup"><span data-stu-id="dd28c-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd28c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd28c-108">Remarks</span></span>  
 <span data-ttu-id="dd28c-109">Cuando se produce la reasignación del token durante una combinación, el ámbito del token original se encuentra en el ámbito de metadatos (origen) importado y el ámbito del nuevo token se encuentra en el ámbito de los metadatos emitidos (de destino).</span><span class="sxs-lookup"><span data-stu-id="dd28c-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd28c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd28c-110">Requirements</span></span>  
 <span data-ttu-id="dd28c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd28c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd28c-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dd28c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd28c-113">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dd28c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd28c-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd28c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd28c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd28c-115">See also</span></span>

- [<span data-ttu-id="dd28c-116">IMapToken (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd28c-116">IMapToken Interface</span></span>](imaptoken-interface.md)
