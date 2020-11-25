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
ms.openlocfilehash: 51cca1ab61027090b0d22781dfd740038bc9372d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718207"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="eedfd-102">IMapToken::Map (Método)</span><span class="sxs-lookup"><span data-stu-id="eedfd-102">IMapToken::Map Method</span></span>

<span data-ttu-id="eedfd-103">Asigna una relación entre los ensamblados mediante firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="eedfd-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eedfd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eedfd-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eedfd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eedfd-105">Parameters</span></span>  

 `tkImp`  
 <span data-ttu-id="eedfd-106">de Token de metadatos que representa el objeto de código importado.</span><span class="sxs-lookup"><span data-stu-id="eedfd-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="eedfd-107">de Token de metadatos que representa el objeto de código emitido.</span><span class="sxs-lookup"><span data-stu-id="eedfd-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eedfd-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eedfd-108">Remarks</span></span>  

 <span data-ttu-id="eedfd-109">Cuando se produce la reasignación del token durante una combinación, el ámbito del token original se encuentra en el ámbito de metadatos (origen) importado y el ámbito del nuevo token se encuentra en el ámbito de los metadatos emitidos (de destino).</span><span class="sxs-lookup"><span data-stu-id="eedfd-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eedfd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eedfd-110">Requirements</span></span>  

 <span data-ttu-id="eedfd-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eedfd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eedfd-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="eedfd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eedfd-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eedfd-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eedfd-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eedfd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedfd-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eedfd-115">See also</span></span>

- [<span data-ttu-id="eedfd-116">IMapToken (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eedfd-116">IMapToken Interface</span></span>](imaptoken-interface.md)
