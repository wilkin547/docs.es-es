---
description: 'Más información sobre: enumeración Cordeclsecurity ('
title: CorDeclSecurity (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: 4c4b57c09ea8b3ec1b98ff120d72a5920dc5aa4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784553"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="6f9c1-103">CorDeclSecurity (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6f9c1-103">CorDeclSecurity Enumeration</span></span>

<span data-ttu-id="6f9c1-104">Especifica las acciones de seguridad que se pueden realizar mediante la seguridad declarativa.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-104">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f9c1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f9c1-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="6f9c1-106">Members</span><span class="sxs-lookup"><span data-stu-id="6f9c1-106">Members</span></span>  
  
|<span data-ttu-id="6f9c1-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="6f9c1-107">Member</span></span>|<span data-ttu-id="6f9c1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f9c1-108">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="6f9c1-109">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-109">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="6f9c1-110">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-110">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="6f9c1-111">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-111">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="6f9c1-112">Todos los autores de llamada de la pila necesitan que se les conceda el permiso especificado por el objeto de permiso actual.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-112">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="6f9c1-113">El código de llamada puede tener acceso al recurso identificado por el objeto de permiso actual, incluso si los autores de la llamada situados en una posición más alta de la pila no tienen permiso para obtener acceso al recurso.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-113">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="6f9c1-114">La capacidad de tener acceso al recurso especificado por el objeto de permiso actual se deniega a los llamadores, incluso si se les ha concedido permiso de acceso.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-114">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="6f9c1-115">Solo se puede acceder a los recursos especificados por este objeto de permiso, aunque al código se le haya concedido permiso de acceso a otros recursos.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-115">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="6f9c1-116">Se requiere que el llamador inmediato tenga concedido el permiso especificado para un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-116">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="6f9c1-117">La clase derivada que hereda otra clase o invalida un método debe tener concedido el permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-117">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="6f9c1-118">El autor de la llamada puede solicitar los permisos mínimos necesarios para que se ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-118">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="6f9c1-119">Esta acción solo se puede usar en el ámbito del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-119">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="6f9c1-120">El autor de la llamada puede solicitar permisos adicionales que son opcionales (no es necesario ejecutar).</span><span class="sxs-lookup"><span data-stu-id="6f9c1-120">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="6f9c1-121">Esta solicitud rechaza implícitamente todos los demás permisos no solicitados específicamente.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-121">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="6f9c1-122">Esta acción solo se puede usar en el ámbito del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-122">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="6f9c1-123">No se concederá la solicitud del llamador de los permisos que se puedan usar inconvenientemente.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-123">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="6f9c1-124">Esta acción solo se puede usar en el ámbito del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-124">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="6f9c1-125">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-125">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="6f9c1-126">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-126">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="6f9c1-127">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-127">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="6f9c1-128">Es necesario que el llamador inmediato haya recibido el permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-128">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="6f9c1-129">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-129">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="6f9c1-130">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-130">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="6f9c1-131">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-131">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="6f9c1-132">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-132">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="6f9c1-133">Reservado.</span><span class="sxs-lookup"><span data-stu-id="6f9c1-133">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f9c1-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f9c1-134">Requirements</span></span>  

 <span data-ttu-id="6f9c1-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f9c1-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f9c1-136">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="6f9c1-136">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6f9c1-137">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f9c1-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f9c1-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f9c1-138">See also</span></span>

- [<span data-ttu-id="6f9c1-139">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="6f9c1-139">Metadata Enumerations</span></span>](metadata-enumerations.md)
