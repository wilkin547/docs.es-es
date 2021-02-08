---
description: 'Más información acerca de: estructura de CALL_ID'
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
ms.openlocfilehash: 4ef6023e382e8c5fead48494f428648a37f3bef4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800492"
---
# <a name="call_id-structure"></a><span data-ttu-id="db8f5-103">CALL_ID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="db8f5-103">CALL_ID Structure</span></span>

<span data-ttu-id="db8f5-104">Proporciona información a un depurador sobre una función a la que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="db8f5-104">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="db8f5-105">Vea la interfaz [INotifySink2](inotifysink2-interface.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="db8f5-105">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db8f5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db8f5-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="db8f5-107">Members</span><span class="sxs-lookup"><span data-stu-id="db8f5-107">Members</span></span>  
  
|<span data-ttu-id="db8f5-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="db8f5-108">Member</span></span>|<span data-ttu-id="db8f5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="db8f5-109">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="db8f5-110">Identifica el equipo que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="db8f5-110">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="db8f5-111">Identifica el procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="db8f5-111">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="db8f5-112">Identifica el subproceso que está ejecutando la llamada.</span><span class="sxs-lookup"><span data-stu-id="db8f5-112">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="db8f5-113">Especifica la dirección de la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="db8f5-113">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="db8f5-114">Especifica la dirección de la llamada.</span><span class="sxs-lookup"><span data-stu-id="db8f5-114">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="db8f5-115">Identifica el equipo que ejecutará la llamada.</span><span class="sxs-lookup"><span data-stu-id="db8f5-115">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db8f5-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db8f5-116">Requirements</span></span>  

 <span data-ttu-id="db8f5-117">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="db8f5-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db8f5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="db8f5-118">See also</span></span>

- [<span data-ttu-id="db8f5-119">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db8f5-119">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="db8f5-120">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="db8f5-120">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
