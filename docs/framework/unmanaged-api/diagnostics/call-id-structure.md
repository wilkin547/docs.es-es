---
title: CALL_ID (Estructura)
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6fa729b131d12b2825a2def700fd918ce8acc40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986484"
---
# <a name="callid-structure"></a><span data-ttu-id="66901-102">CALL_ID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="66901-102">CALL_ID Structure</span></span>
<span data-ttu-id="66901-103">Proporciona información a un depurador sobre una función que se llama.</span><span class="sxs-lookup"><span data-stu-id="66901-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="66901-104">Consulte la [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interfaz para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="66901-104">See the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66901-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66901-105">Syntax</span></span>  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="66901-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="66901-106">Members</span></span>  
  
|<span data-ttu-id="66901-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="66901-107">Member</span></span>|<span data-ttu-id="66901-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="66901-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="66901-109">Identifica el equipo que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="66901-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="66901-110">Identifica el procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="66901-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="66901-111">Identifica el subproceso que se está ejecutando la llamada.</span><span class="sxs-lookup"><span data-stu-id="66901-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="66901-112">Especifica la dirección de la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="66901-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="66901-113">Especifica la dirección de la llamada.</span><span class="sxs-lookup"><span data-stu-id="66901-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="66901-114">Identifica el equipo que ejecutará la llamada.</span><span class="sxs-lookup"><span data-stu-id="66901-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66901-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66901-115">Requirements</span></span>  
 <span data-ttu-id="66901-116">**Encabezado**: ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="66901-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66901-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="66901-117">See also</span></span>

- [<span data-ttu-id="66901-118">INotifySink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="66901-118">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="66901-119">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="66901-119">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
