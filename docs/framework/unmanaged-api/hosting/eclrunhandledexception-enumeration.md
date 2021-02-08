---
description: 'Más información sobre: enumeración EClrUnhandledException ('
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
ms.openlocfilehash: 088d448a92c4d9030208537b9c788477c85f9d37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785554"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="d07ce-103">EClrUnhandledException (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d07ce-103">EClrUnhandledException Enumeration</span></span>

<span data-ttu-id="d07ce-104">Describe las opciones disponibles para administrar excepciones que no se controlan en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="d07ce-104">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d07ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d07ce-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="d07ce-106">Members</span><span class="sxs-lookup"><span data-stu-id="d07ce-106">Members</span></span>  
  
|<span data-ttu-id="d07ce-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="d07ce-107">Member</span></span>|<span data-ttu-id="d07ce-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d07ce-108">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="d07ce-109">Especifica que se produce el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d07ce-109">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="d07ce-110">El proceso se ha anulado.</span><span class="sxs-lookup"><span data-stu-id="d07ce-110">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="d07ce-111">Especifica que el Common Language Runtime (CLR) omite las excepciones no controladas y permite que el host determine cualquier acción más.</span><span class="sxs-lookup"><span data-stu-id="d07ce-111">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d07ce-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d07ce-112">Remarks</span></span>  

 <span data-ttu-id="d07ce-113">Para especificar que el CLR se comporte como versiones anteriores, utilice el `eHostDeterminedPolicy` miembro.</span><span class="sxs-lookup"><span data-stu-id="d07ce-113">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d07ce-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d07ce-114">Requirements</span></span>  

 <span data-ttu-id="d07ce-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d07ce-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d07ce-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d07ce-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d07ce-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d07ce-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d07ce-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d07ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07ce-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d07ce-119">See also</span></span>

- [<span data-ttu-id="d07ce-120">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d07ce-120">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="d07ce-121">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d07ce-121">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="d07ce-122">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d07ce-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="d07ce-123">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="d07ce-123">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="d07ce-124">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d07ce-124">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="d07ce-125">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="d07ce-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
