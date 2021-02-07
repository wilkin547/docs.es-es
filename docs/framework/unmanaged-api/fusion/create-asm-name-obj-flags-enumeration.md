---
description: 'Más información acerca de: enumeración CREATE_ASM_NAME_OBJ_FLAGS'
title: CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: b68eed0671d57893e7ffbfbd8127c7ef872d5eb0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761205"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="90d97-103">CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="90d97-103">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>

<span data-ttu-id="90d97-104">Especifica los atributos de un objeto de [interfaz de IAssemblyName](iassemblyname-interface.md) cuando se construye mediante la función [createassemblynameobject (](createassemblynameobject-function.md) .</span><span class="sxs-lookup"><span data-stu-id="90d97-104">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90d97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90d97-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="90d97-106">Members</span><span class="sxs-lookup"><span data-stu-id="90d97-106">Members</span></span>  
  
|<span data-ttu-id="90d97-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="90d97-107">Member</span></span>|<span data-ttu-id="90d97-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="90d97-108">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="90d97-109">Indica que el parámetro pasado es una identidad textual.</span><span class="sxs-lookup"><span data-stu-id="90d97-109">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="90d97-110">Establece algunos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="90d97-110">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="90d97-111">Comprueba la regla de ensamblado de confianza (solo el nombre y la clave pública).</span><span class="sxs-lookup"><span data-stu-id="90d97-111">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="90d97-112">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="90d97-112">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="90d97-113">Combinación de las `CANOF_PARSE_DISPLAY_NAME` marcas y `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` .</span><span class="sxs-lookup"><span data-stu-id="90d97-113">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="90d97-114">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="90d97-114">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90d97-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90d97-115">Requirements</span></span>  

 <span data-ttu-id="90d97-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90d97-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90d97-117">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="90d97-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="90d97-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90d97-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d97-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="90d97-119">See also</span></span>

- [<span data-ttu-id="90d97-120">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90d97-120">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="90d97-121">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="90d97-121">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="90d97-122">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="90d97-122">Fusion Enumerations</span></span>](fusion-enumerations.md)
