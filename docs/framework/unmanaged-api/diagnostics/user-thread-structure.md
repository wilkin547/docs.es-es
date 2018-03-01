---
title: USER_THREAD (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 50533ce25812ad49d538c5a6a6c814d7a9704053
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="userthread-structure"></a><span data-ttu-id="fdf1a-102">USER_THREAD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="fdf1a-102">USER_THREAD Structure</span></span>
<span data-ttu-id="fdf1a-103">Proporciona información a un depurador sobre un subproceso.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="fdf1a-104">Para obtener más información, consulte el [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf1a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdf1a-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="fdf1a-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="fdf1a-106">Members</span></span>  
  
|<span data-ttu-id="fdf1a-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="fdf1a-107">Member</span></span>|<span data-ttu-id="fdf1a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdf1a-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="fdf1a-109">Dirección del búfer de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="fdf1a-110">Longitud del búfer de subprocesos, en bytes.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="fdf1a-111">Identificador de subproceso.</span><span class="sxs-lookup"><span data-stu-id="fdf1a-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fdf1a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdf1a-112">Requirements</span></span>  
 <span data-ttu-id="fdf1a-113">**Encabezado:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="fdf1a-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf1a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdf1a-114">See Also</span></span>  
 [<span data-ttu-id="fdf1a-115">SetNotifyFilter (método)</span><span class="sxs-lookup"><span data-stu-id="fdf1a-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)  
 [<span data-ttu-id="fdf1a-116">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="fdf1a-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
