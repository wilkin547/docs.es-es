---
description: 'Más información sobre: enumeración Cormethodattr ('
title: CorMethodAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
ms.openlocfilehash: 4050235675f4b237b184d31378a614a0613ab3df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784384"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="c9a84-103">CorMethodAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c9a84-103">CorMethodAttr Enumeration</span></span>

<span data-ttu-id="c9a84-104">Contiene valores que describen las características de un método.</span><span class="sxs-lookup"><span data-stu-id="c9a84-104">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a84-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9a84-105">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c9a84-106">Members</span><span class="sxs-lookup"><span data-stu-id="c9a84-106">Members</span></span>  
  
|<span data-ttu-id="c9a84-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="c9a84-107">Member</span></span>|<span data-ttu-id="c9a84-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9a84-108">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="c9a84-109">Especifica el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="c9a84-109">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="c9a84-110">Especifica que no se puede hacer referencia al miembro.</span><span class="sxs-lookup"><span data-stu-id="c9a84-110">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="c9a84-111">Especifica que solo el tipo primario puede tener acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="c9a84-111">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="c9a84-112">Especifica que solo los subtipos de este ensamblado pueden obtener acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="c9a84-112">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="c9a84-113">Especifica que el miembro es accesible para cualquier persona del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9a84-113">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="c9a84-114">Especifica que solo se puede tener acceso al miembro por tipo y subtipos.</span><span class="sxs-lookup"><span data-stu-id="c9a84-114">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="c9a84-115">Especifica que el miembro es accesible por las clases derivadas y por otros tipos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c9a84-115">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="c9a84-116">Especifica que todos los tipos con acceso al ámbito pueden obtener acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="c9a84-116">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="c9a84-117">Especifica que el miembro se define como parte del tipo en lugar de como miembro de una instancia de.</span><span class="sxs-lookup"><span data-stu-id="c9a84-117">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="c9a84-118">Especifica que el método no se puede invalidar.</span><span class="sxs-lookup"><span data-stu-id="c9a84-118">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="c9a84-119">Especifica que el método se puede invalidar.</span><span class="sxs-lookup"><span data-stu-id="c9a84-119">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="c9a84-120">Especifica que el método se oculta por nombre y firma, en lugar de simplemente por nombre.</span><span class="sxs-lookup"><span data-stu-id="c9a84-120">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="c9a84-121">Especifica el diseño de la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="c9a84-121">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="c9a84-122">Especifica que se reutilizará la ranura utilizada para este método en la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="c9a84-122">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="c9a84-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c9a84-123">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="c9a84-124">Especifica que el método siempre obtiene una nueva ranura en la tabla virtual.</span><span class="sxs-lookup"><span data-stu-id="c9a84-124">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="c9a84-125">Especifica que el método puede ser invalidado por los mismos tipos en los que está visible.</span><span class="sxs-lookup"><span data-stu-id="c9a84-125">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="c9a84-126">Especifica que el método no está implementado.</span><span class="sxs-lookup"><span data-stu-id="c9a84-126">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="c9a84-127">Especifica que el método es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="c9a84-127">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="c9a84-128">Especifica que la implementación del método se reenvía mediante PInvoke.</span><span class="sxs-lookup"><span data-stu-id="c9a84-128">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="c9a84-129">Especifica que el método es un método administrado exportado a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c9a84-129">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="c9a84-130">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c9a84-130">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="c9a84-131">Especifica que el Common Language Runtime debe comprobar la codificación del nombre del método.</span><span class="sxs-lookup"><span data-stu-id="c9a84-131">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="c9a84-132">Especifica que el método tiene seguridad asociada.</span><span class="sxs-lookup"><span data-stu-id="c9a84-132">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="c9a84-133">Especifica que el método llama a otro método que contiene código de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c9a84-133">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9a84-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9a84-134">Requirements</span></span>  

 <span data-ttu-id="c9a84-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9a84-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9a84-136">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c9a84-136">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c9a84-137">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9a84-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a84-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9a84-138">See also</span></span>

- [<span data-ttu-id="c9a84-139">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c9a84-139">Metadata Enumerations</span></span>](metadata-enumerations.md)
