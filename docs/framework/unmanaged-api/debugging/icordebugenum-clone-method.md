---
description: 'Más información acerca de: ICorDebugEnum:: Clone (método)'
title: ICorDebugEnum::Clone (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
ms.openlocfilehash: 18219757980870dcf9663477d195068a76814de1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694583"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="11149-103">ICorDebugEnum::Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="11149-103">ICorDebugEnum::Clone Method</span></span>

<span data-ttu-id="11149-104">Crea una copia de este objeto ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="11149-104">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11149-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11149-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11149-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11149-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="11149-107">enuncia Puntero a la dirección de un `ICorDebugEnum` objeto que es una copia de este `ICorDebugEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="11149-107">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11149-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11149-108">Requirements</span></span>  

 <span data-ttu-id="11149-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11149-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11149-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11149-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11149-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11149-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11149-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11149-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
