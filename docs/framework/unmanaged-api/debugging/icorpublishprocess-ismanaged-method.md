---
title: ICorPublishProcess::IsManaged (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: 3eec84624866b2be7068d7875cd650828c283fd2
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421103"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="b0012-102">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="b0012-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="b0012-103">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md) tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="b0012-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0012-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0012-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0012-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b0012-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="b0012-106">enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="b0012-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="b0012-107">El valor es `true` si el proceso tiene código administrado; de lo contrario, es `false` .</span><span class="sxs-lookup"><span data-stu-id="b0012-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0012-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b0012-108">Remarks</span></span>  
 <span data-ttu-id="b0012-109">Dado que la versión actual de `ICorPublishProcess` solo permite el acceso a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="b0012-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0012-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0012-110">Requirements</span></span>  
 <span data-ttu-id="b0012-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0012-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0012-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="b0012-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b0012-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0012-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0012-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0012-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0012-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b0012-115">See also</span></span>

- [<span data-ttu-id="b0012-116">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0012-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
