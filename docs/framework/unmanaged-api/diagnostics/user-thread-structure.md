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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0191f1fa17d436944fcb590d88dd4004adfa1aba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744301"
---
# <a name="userthread-structure"></a><span data-ttu-id="18a08-102">USER_THREAD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="18a08-102">USER_THREAD Structure</span></span>
<span data-ttu-id="18a08-103">Proporciona información a un depurador sobre un subproceso.</span><span class="sxs-lookup"><span data-stu-id="18a08-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="18a08-104">Para obtener más información, consulte el [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="18a08-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a08-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18a08-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="18a08-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="18a08-106">Members</span></span>  
  
|<span data-ttu-id="18a08-107">Member</span><span class="sxs-lookup"><span data-stu-id="18a08-107">Member</span></span>|<span data-ttu-id="18a08-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="18a08-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="18a08-109">Dirección del búfer de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="18a08-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="18a08-110">Longitud del búfer de subproceso, en bytes.</span><span class="sxs-lookup"><span data-stu-id="18a08-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="18a08-111">Identificador de subproceso.</span><span class="sxs-lookup"><span data-stu-id="18a08-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18a08-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18a08-112">Requirements</span></span>  
 <span data-ttu-id="18a08-113">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="18a08-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a08-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="18a08-114">See also</span></span>

- [<span data-ttu-id="18a08-115">SetNotifyFilter (método)</span><span class="sxs-lookup"><span data-stu-id="18a08-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="18a08-116">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="18a08-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
