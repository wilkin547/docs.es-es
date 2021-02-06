---
description: 'Más información sobre: ICorDebugThread2:: Getconnectionid ((método)'
title: ICorDebugThread2::GetConnectionID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
ms.openlocfilehash: 0f8035e703d3638b11f4206d9c47e39fe487d71d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658742"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="520c5-103">ICorDebugThread2::GetConnectionID (Método)</span><span class="sxs-lookup"><span data-stu-id="520c5-103">ICorDebugThread2::GetConnectionID Method</span></span>

<span data-ttu-id="520c5-104">Obtiene el identificador de conexión de este objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="520c5-104">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="520c5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="520c5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="520c5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="520c5-106">Parameters</span></span>  

 `pdwConnectionId`  
 <span data-ttu-id="520c5-107">enuncia `CONNID` Que representa el identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="520c5-107">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="520c5-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="520c5-108">Remarks</span></span>  

 <span data-ttu-id="520c5-109">El `GetConnectionID` método devuelve cero en el `pdwConnectionId` parámetro, si este subproceso no forma parte de una conexión.</span><span class="sxs-lookup"><span data-stu-id="520c5-109">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="520c5-110">Si este subproceso está conectado a una instancia de Microsoft SQL Server 2005 Analysis Services (SSAS), se `CONNID` asigna a un identificador de proceso de servidor (SPID).</span><span class="sxs-lookup"><span data-stu-id="520c5-110">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="520c5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="520c5-111">Requirements</span></span>  

 <span data-ttu-id="520c5-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="520c5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="520c5-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="520c5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="520c5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="520c5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="520c5-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="520c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
