---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc4963dcf686fe62f473aea1af86868df03718df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768969"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="e518a-102">ICorDebugThread2::GetConnectionID (Método)</span><span class="sxs-lookup"><span data-stu-id="e518a-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="e518a-103">Obtiene el identificador de conexión para este objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="e518a-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e518a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e518a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e518a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e518a-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="e518a-106">[out] Un `CONNID` que representa el identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="e518a-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e518a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e518a-107">Remarks</span></span>  
 <span data-ttu-id="e518a-108">El `GetConnectionID` método devuelve cero en el `pdwConnectionId` parámetro, si este subproceso no forma parte de una conexión.</span><span class="sxs-lookup"><span data-stu-id="e518a-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="e518a-109">Si este subproceso está conectado a una instancia de Microsoft SQL Server 2005 Analysis Services (SSAS), el `CONNID` se asigna a un identificador de proceso de servidor (SPID).</span><span class="sxs-lookup"><span data-stu-id="e518a-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e518a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e518a-110">Requirements</span></span>  
 <span data-ttu-id="e518a-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e518a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e518a-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e518a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e518a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e518a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e518a-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e518a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
