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
ms.openlocfilehash: a81842132769934a6f5f34e6dc462bba77b3854a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138686"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="703fd-102">ICorDebugThread2::GetConnectionID (Método)</span><span class="sxs-lookup"><span data-stu-id="703fd-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="703fd-103">Obtiene el identificador de conexión de este objeto ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="703fd-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="703fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="703fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="703fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="703fd-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="703fd-106">enuncia `CONNID` que representa el identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="703fd-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="703fd-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="703fd-107">Remarks</span></span>  
 <span data-ttu-id="703fd-108">El método `GetConnectionID` devuelve cero en el parámetro `pdwConnectionId`, si este subproceso no forma parte de una conexión.</span><span class="sxs-lookup"><span data-stu-id="703fd-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="703fd-109">Si este subproceso está conectado a una instancia de Microsoft SQL Server 2005 Analysis Services (SSAS), el `CONNID` se asigna a un identificador de proceso de servidor (SPID).</span><span class="sxs-lookup"><span data-stu-id="703fd-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="703fd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="703fd-110">Requirements</span></span>  
 <span data-ttu-id="703fd-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="703fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="703fd-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="703fd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="703fd-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="703fd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="703fd-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="703fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
