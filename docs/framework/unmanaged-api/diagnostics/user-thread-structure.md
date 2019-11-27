---
title: USER_THREAD (Estructura)
ms.date: 03/30/2017
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
ms.openlocfilehash: 51db7a2b6464b562e09ce061991898a8d604ead1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437968"
---
# <a name="user_thread-structure"></a><span data-ttu-id="f8041-102">USER_THREAD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f8041-102">USER_THREAD Structure</span></span>
<span data-ttu-id="f8041-103">Proporciona información a un depurador sobre un subproceso.</span><span class="sxs-lookup"><span data-stu-id="f8041-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="f8041-104">Para obtener más información, vea el método [INotifySource2 (:: SetNotifyFilter (](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f8041-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8041-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8041-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="f8041-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="f8041-106">Members</span></span>  
  
|<span data-ttu-id="f8041-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f8041-107">Member</span></span>|<span data-ttu-id="f8041-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8041-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="f8041-109">Dirección del búfer de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f8041-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="f8041-110">Longitud del búfer de subprocesos, en bytes.</span><span class="sxs-lookup"><span data-stu-id="f8041-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="f8041-111">IDENTIFICADOR de subproceso.</span><span class="sxs-lookup"><span data-stu-id="f8041-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8041-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8041-112">Requirements</span></span>  
 <span data-ttu-id="f8041-113">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="f8041-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8041-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8041-114">See also</span></span>

- [<span data-ttu-id="f8041-115">SetNotifyFilter (método)</span><span class="sxs-lookup"><span data-stu-id="f8041-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="f8041-116">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f8041-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
