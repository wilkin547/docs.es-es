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
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725253"
---
# <a name="call_id-structure"></a><span data-ttu-id="f2a26-102">CALL_ID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="f2a26-102">CALL_ID Structure</span></span>

<span data-ttu-id="f2a26-103">Proporciona información a un depurador sobre una función a la que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="f2a26-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="f2a26-104">Vea la interfaz [INotifySink2](inotifysink2-interface.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="f2a26-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a26-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2a26-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f2a26-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="f2a26-106">Members</span></span>  
  
|<span data-ttu-id="f2a26-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="f2a26-107">Member</span></span>|<span data-ttu-id="f2a26-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2a26-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="f2a26-109">Identifica el equipo que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2a26-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="f2a26-110">Identifica el procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="f2a26-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="f2a26-111">Identifica el subproceso que está ejecutando la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2a26-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="f2a26-112">Especifica la dirección de la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f2a26-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="f2a26-113">Especifica la dirección de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2a26-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="f2a26-114">Identifica el equipo que ejecutará la llamada.</span><span class="sxs-lookup"><span data-stu-id="f2a26-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2a26-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2a26-115">Requirements</span></span>  

 <span data-ttu-id="f2a26-116">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="f2a26-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a26-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2a26-117">See also</span></span>

- [<span data-ttu-id="f2a26-118">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2a26-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="f2a26-119">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f2a26-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
