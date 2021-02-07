---
description: 'Más información acerca de: ICorDebugCode:: GetAddress (método)'
title: ICorDebugCode::GetAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
ms.openlocfilehash: 4c074a407d8153703fd92aeddb53e9fa05b0ef01
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711341"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="e2401-103">ICorDebugCode::GetAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="e2401-103">ICorDebugCode::GetAddress Method</span></span>

<span data-ttu-id="e2401-104">Obtiene la dirección virtual relativa (RVA) del segmento de código que esta interfaz "ICorDebugCode" representa.</span><span class="sxs-lookup"><span data-stu-id="e2401-104">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2401-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2401-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2401-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2401-106">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="e2401-107">enuncia Puntero a la RVA del segmento de código.</span><span class="sxs-lookup"><span data-stu-id="e2401-107">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2401-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2401-108">Requirements</span></span>  

 <span data-ttu-id="e2401-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2401-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2401-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2401-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2401-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2401-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2401-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2401-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
