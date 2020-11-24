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
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692636"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="a98a6-102">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="a98a6-102">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="a98a6-103">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md) tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="a98a6-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a98a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a98a6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a98a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a98a6-105">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="a98a6-106">enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="a98a6-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="a98a6-107">El valor es `true` si el proceso tiene código administrado; de lo contrario, es `false` .</span><span class="sxs-lookup"><span data-stu-id="a98a6-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a98a6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a98a6-108">Remarks</span></span>  

 <span data-ttu-id="a98a6-109">Dado que la versión actual de `ICorPublishProcess` solo permite el acceso a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="a98a6-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a98a6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a98a6-110">Requirements</span></span>  

 <span data-ttu-id="a98a6-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a98a6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a98a6-112">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="a98a6-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a98a6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a98a6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a98a6-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a98a6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a98a6-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a98a6-115">See also</span></span>

- [<span data-ttu-id="a98a6-116">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a98a6-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
