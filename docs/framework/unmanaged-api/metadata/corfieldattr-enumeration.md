---
title: CorFieldAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
ms.openlocfilehash: dea69e18fc517eddddc5b99950a6f3b16ee3e426
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007408"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="552a4-102">CorFieldAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="552a4-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="552a4-103">Contiene valores que describen los metadatos de un campo.</span><span class="sxs-lookup"><span data-stu-id="552a4-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="552a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="552a4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="552a4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="552a4-105">Members</span></span>  
  
|<span data-ttu-id="552a4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="552a4-106">Member</span></span>|<span data-ttu-id="552a4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="552a4-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="552a4-108">Especifica la información de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="552a4-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="552a4-109">Indica que no se pueden crear referencias al campo.</span><span class="sxs-lookup"><span data-stu-id="552a4-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="552a4-110">Especifica que el campo es accesible únicamente por su tipo primario.</span><span class="sxs-lookup"><span data-stu-id="552a4-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="552a4-111">Especifica que el campo es accesible por las clases derivadas de su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="552a4-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="552a4-112">Especifica que todos los tipos del ensamblado pueden obtener acceso al campo.</span><span class="sxs-lookup"><span data-stu-id="552a4-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="552a4-113">Especifica que solo los tipos y las clases derivadas pueden tener acceso al campo.</span><span class="sxs-lookup"><span data-stu-id="552a4-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="552a4-114">Especifica que el campo es accesible por las clases derivadas y por todos los tipos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="552a4-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="552a4-115">Especifica que todos los tipos con visibilidad de este ámbito pueden obtener acceso al campo.</span><span class="sxs-lookup"><span data-stu-id="552a4-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="552a4-116">Especifica que el campo es un miembro de su tipo en lugar de un miembro de instancia.</span><span class="sxs-lookup"><span data-stu-id="552a4-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="552a4-117">Especifica que el campo no se puede cambiar una vez inicializado.</span><span class="sxs-lookup"><span data-stu-id="552a4-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="552a4-118">Especifica que el valor del campo es una constante de tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="552a4-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="552a4-119">Especifica que el campo no se serializa cuando su tipo es remoto.</span><span class="sxs-lookup"><span data-stu-id="552a4-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="552a4-120">Especifica que el campo es especial y que su nombre describe cómo.</span><span class="sxs-lookup"><span data-stu-id="552a4-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="552a4-121">Especifica que la implementación del campo se reenvía a través de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="552a4-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="552a4-122">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="552a4-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="552a4-123">Especifica que las API internas de metadatos de Common Language Runtime deben comprobar la codificación del nombre.</span><span class="sxs-lookup"><span data-stu-id="552a4-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="552a4-124">Especifica que el campo contiene información de cálculo de referencias.</span><span class="sxs-lookup"><span data-stu-id="552a4-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="552a4-125">Especifica que el campo tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="552a4-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="552a4-126">Especifica que el campo tiene una dirección virtual relativa.</span><span class="sxs-lookup"><span data-stu-id="552a4-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="552a4-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="552a4-127">Requirements</span></span>  
 <span data-ttu-id="552a4-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="552a4-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="552a4-129">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="552a4-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="552a4-130">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="552a4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="552a4-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="552a4-131">See also</span></span>

- [<span data-ttu-id="552a4-132">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="552a4-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
