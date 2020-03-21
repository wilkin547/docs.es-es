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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176076"
---
# <a name="imaptokenmap-method"></a><span data-ttu-id="5a617-102">IMapToken::Map (Método)</span><span class="sxs-lookup"><span data-stu-id="5a617-102">IMapToken::Map Method</span></span>
<span data-ttu-id="5a617-103">Asigna una relación entre los ensamblados mediante firmas de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5a617-103">Maps a relationship between the assemblies using metadata signatures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a617-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a617-104">Syntax</span></span>  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a617-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a617-105">Parameters</span></span>  
 `tkImp`  
 <span data-ttu-id="5a617-106">[en] El token de metadatos que representa el objeto de código importado.</span><span class="sxs-lookup"><span data-stu-id="5a617-106">[in] The metadata token that represents the imported code object.</span></span>  
  
 `tkEmit`  
 <span data-ttu-id="5a617-107">[en] El token de metadatos que representa el objeto de código emitido.</span><span class="sxs-lookup"><span data-stu-id="5a617-107">[in] The metadata token that represents the emitted code object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a617-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a617-108">Remarks</span></span>  
 <span data-ttu-id="5a617-109">Cuando el token se vuelve a asignar durante una combinación, el token original tiene el ámbito en el ámbito de metadatos importado (origen) y el nuevo token tiene un ámbito en el ámbito de metadatos emitido (destino).</span><span class="sxs-lookup"><span data-stu-id="5a617-109">When the token re-map occurs during a merge, the original token is scoped in the imported (source) metadata scope and the new token is scoped in the emitted (target) metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a617-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a617-110">Requirements</span></span>  
 <span data-ttu-id="5a617-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a617-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a617-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a617-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a617-113">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a617-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a617-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a617-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a617-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a617-115">See also</span></span>

- [<span data-ttu-id="5a617-116">IMapToken (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a617-116">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
