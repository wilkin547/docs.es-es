---
description: 'Más información acerca de: estructura de USER_THREAD'
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
ms.openlocfilehash: a4bd22073b7610307e67107781bdb68a15ef795f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761273"
---
# <a name="user_thread-structure"></a><span data-ttu-id="a1053-103">USER_THREAD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a1053-103">USER_THREAD Structure</span></span>

<span data-ttu-id="a1053-104">Proporciona información a un depurador sobre un subproceso.</span><span class="sxs-lookup"><span data-stu-id="a1053-104">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="a1053-105">Para obtener más información, vea el método [INotifySource2 (:: SetNotifyFilter (](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a1053-105">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1053-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1053-106">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="a1053-107">Members</span><span class="sxs-lookup"><span data-stu-id="a1053-107">Members</span></span>  
  
|<span data-ttu-id="a1053-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="a1053-108">Member</span></span>|<span data-ttu-id="a1053-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1053-109">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="a1053-110">Dirección del búfer de subproceso.</span><span class="sxs-lookup"><span data-stu-id="a1053-110">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="a1053-111">Longitud del búfer de subprocesos, en bytes.</span><span class="sxs-lookup"><span data-stu-id="a1053-111">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="a1053-112">IDENTIFICADOR de subproceso.</span><span class="sxs-lookup"><span data-stu-id="a1053-112">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1053-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1053-113">Requirements</span></span>  

 <span data-ttu-id="a1053-114">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="a1053-114">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1053-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1053-115">See also</span></span>

- [<span data-ttu-id="a1053-116">Método SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="a1053-116">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="a1053-117">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a1053-117">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
