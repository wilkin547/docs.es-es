---
description: 'Más información sobre: ICorDebugType:: Getrank ((método)'
title: ICorDebugType::GetRank (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
ms.openlocfilehash: e13416856f900846d2df4b8a39303cf0b6a48ebc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800908"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="92ffc-103">ICorDebugType::GetRank (Método)</span><span class="sxs-lookup"><span data-stu-id="92ffc-103">ICorDebugType::GetRank Method</span></span>

<span data-ttu-id="92ffc-104">Obtiene el número de dimensiones de un tipo de matriz.</span><span class="sxs-lookup"><span data-stu-id="92ffc-104">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92ffc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92ffc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92ffc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92ffc-106">Parameters</span></span>  

 `pnRank`  
 <span data-ttu-id="92ffc-107">enuncia Puntero al número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="92ffc-107">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ffc-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92ffc-108">Requirements</span></span>  

 <span data-ttu-id="92ffc-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92ffc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ffc-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92ffc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92ffc-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92ffc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92ffc-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ffc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
