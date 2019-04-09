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
ms.openlocfilehash: 11551221732e454e48111d48d60ca9b72f7f9b66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127170"
---
# <a name="userthread-structure"></a><span data-ttu-id="5be03-102">USER_THREAD (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5be03-102">USER_THREAD Structure</span></span>
<span data-ttu-id="5be03-103">Proporciona información a un depurador sobre un subproceso.</span><span class="sxs-lookup"><span data-stu-id="5be03-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="5be03-104">Para obtener más información, consulte el [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5be03-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be03-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5be03-105">Syntax</span></span>  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="5be03-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="5be03-106">Members</span></span>  
  
|<span data-ttu-id="5be03-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="5be03-107">Member</span></span>|<span data-ttu-id="5be03-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5be03-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="5be03-109">Dirección del búfer de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5be03-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="5be03-110">Longitud del búfer de subproceso, en bytes.</span><span class="sxs-lookup"><span data-stu-id="5be03-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="5be03-111">Identificador de subproceso.</span><span class="sxs-lookup"><span data-stu-id="5be03-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5be03-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5be03-112">Requirements</span></span>  
 <span data-ttu-id="5be03-113">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="5be03-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be03-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5be03-114">See also</span></span>

- [<span data-ttu-id="5be03-115">Método SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="5be03-115">SetNotifyFilter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="5be03-116">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="5be03-116">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
