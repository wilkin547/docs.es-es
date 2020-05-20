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
ms.openlocfilehash: 5144feab742bc5dac36563d701d81a699d0bb2f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609448"
---
# <a name="user_thread-structure"></a><span data-ttu-id="eca25-102">USER_THREAD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="eca25-102">USER_THREAD Structure</span></span>
<span data-ttu-id="eca25-103">Proporciona información a un depurador sobre un subproceso.</span><span class="sxs-lookup"><span data-stu-id="eca25-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="eca25-104">Para obtener más información, vea el método [INotifySource2 (:: SetNotifyFilter (](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eca25-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca25-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eca25-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="eca25-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="eca25-106">Members</span></span>  
  
|<span data-ttu-id="eca25-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="eca25-107">Member</span></span>|<span data-ttu-id="eca25-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="eca25-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="eca25-109">Dirección del búfer de subproceso.</span><span class="sxs-lookup"><span data-stu-id="eca25-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="eca25-110">Longitud del búfer de subprocesos, en bytes.</span><span class="sxs-lookup"><span data-stu-id="eca25-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="eca25-111">IDENTIFICADOR de subproceso.</span><span class="sxs-lookup"><span data-stu-id="eca25-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eca25-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eca25-112">Requirements</span></span>  
 <span data-ttu-id="eca25-113">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="eca25-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca25-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="eca25-114">See also</span></span>

- [<span data-ttu-id="eca25-115">Método SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="eca25-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="eca25-116">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="eca25-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
