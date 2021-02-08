---
description: 'Más información sobre: ICorPublishProcess:: IsManaged ((método)'
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
ms.openlocfilehash: 55f620a896efd87c2f154ac68ef2db1a1b0a1ebc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790508"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="73819-103">ICorPublishProcess::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="73819-103">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="73819-104">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md) tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="73819-104">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73819-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73819-105">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73819-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73819-106">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="73819-107">enuncia Un puntero a un valor booleano que indica si el proceso tiene código administrado.</span><span class="sxs-lookup"><span data-stu-id="73819-107">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="73819-108">El valor es `true` si el proceso tiene código administrado; de lo contrario, es `false` .</span><span class="sxs-lookup"><span data-stu-id="73819-108">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73819-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73819-109">Remarks</span></span>  

 <span data-ttu-id="73819-110">Dado que la versión actual de `ICorPublishProcess` solo permite el acceso a los procesos que tienen código administrado, `IsManaged` siempre devuelve `true` .</span><span class="sxs-lookup"><span data-stu-id="73819-110">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73819-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73819-111">Requirements</span></span>  

 <span data-ttu-id="73819-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73819-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73819-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="73819-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="73819-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73819-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73819-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73819-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73819-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="73819-116">See also</span></span>

- [<span data-ttu-id="73819-117">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73819-117">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
