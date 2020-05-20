---
title: EClrUnhandledException (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 63b07dda2293d3e05bd3c8fcdc45f20a498ea54c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616312"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="ef317-102">EClrUnhandledException (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ef317-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="ef317-103">Describe las opciones disponibles para administrar excepciones que no se controlan en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="ef317-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef317-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef317-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="ef317-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ef317-105">Members</span></span>  
  
|<span data-ttu-id="ef317-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ef317-106">Member</span></span>|<span data-ttu-id="ef317-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef317-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="ef317-108">Especifica que se produce el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef317-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="ef317-109">El proceso se ha anulado.</span><span class="sxs-lookup"><span data-stu-id="ef317-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="ef317-110">Especifica que el Common Language Runtime (CLR) omite las excepciones no controladas y permite que el host determine cualquier acción más.</span><span class="sxs-lookup"><span data-stu-id="ef317-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef317-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef317-111">Remarks</span></span>  
 <span data-ttu-id="ef317-112">Para especificar que el CLR se comporte como versiones anteriores, utilice el `eHostDeterminedPolicy` miembro.</span><span class="sxs-lookup"><span data-stu-id="ef317-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef317-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef317-113">Requirements</span></span>  
 <span data-ttu-id="ef317-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef317-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef317-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ef317-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef317-116">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef317-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef317-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef317-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef317-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ef317-118">See also</span></span>

- [<span data-ttu-id="ef317-119">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ef317-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="ef317-120">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ef317-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="ef317-121">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef317-121">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="ef317-122">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="ef317-122">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="ef317-123">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef317-123">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="ef317-124">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="ef317-124">Hosting Enumerations</span></span>](hosting-enumerations.md)
