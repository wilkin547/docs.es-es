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
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420635"
---
# <a name="call_id-structure"></a><span data-ttu-id="746a9-102">CALL_ID (Estructura)</span><span class="sxs-lookup"><span data-stu-id="746a9-102">CALL_ID Structure</span></span>
<span data-ttu-id="746a9-103">Proporciona información a un depurador sobre una función a la que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="746a9-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="746a9-104">Vea la interfaz [INotifySink2](inotifysink2-interface.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="746a9-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="746a9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="746a9-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="746a9-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="746a9-106">Members</span></span>  
  
|<span data-ttu-id="746a9-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="746a9-107">Member</span></span>|<span data-ttu-id="746a9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="746a9-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="746a9-109">Identifica el equipo que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="746a9-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="746a9-110">Identifica el procesador del equipo.</span><span class="sxs-lookup"><span data-stu-id="746a9-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="746a9-111">Identifica el subproceso que está ejecutando la llamada.</span><span class="sxs-lookup"><span data-stu-id="746a9-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="746a9-112">Especifica la dirección de la pila de llamadas.</span><span class="sxs-lookup"><span data-stu-id="746a9-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="746a9-113">Especifica la dirección de la llamada.</span><span class="sxs-lookup"><span data-stu-id="746a9-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="746a9-114">Identifica el equipo que ejecutará la llamada.</span><span class="sxs-lookup"><span data-stu-id="746a9-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="746a9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="746a9-115">Requirements</span></span>  
 <span data-ttu-id="746a9-116">**Encabezado:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="746a9-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746a9-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="746a9-117">See also</span></span>

- [<span data-ttu-id="746a9-118">INotifySink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="746a9-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="746a9-119">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="746a9-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
