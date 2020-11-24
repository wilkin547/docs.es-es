---
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
ms.openlocfilehash: 52d5ad3a18c102422e90621c7d1e23b2692c0000
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683243"
---
# <a name="create_asm_name_obj_flags-enumeration"></a><span data-ttu-id="0bc95-102">CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0bc95-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>

<span data-ttu-id="0bc95-103">Especifica los atributos de un objeto de [interfaz de IAssemblyName](iassemblyname-interface.md) cuando se construye mediante la función [createassemblynameobject (](createassemblynameobject-function.md) .</span><span class="sxs-lookup"><span data-stu-id="0bc95-103">Specifies the attributes of an [IAssemblyName Interface](iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bc95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bc95-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0bc95-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0bc95-105">Members</span></span>  
  
|<span data-ttu-id="0bc95-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0bc95-106">Member</span></span>|<span data-ttu-id="0bc95-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bc95-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="0bc95-108">Indica que el parámetro pasado es una identidad textual.</span><span class="sxs-lookup"><span data-stu-id="0bc95-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="0bc95-109">Establece algunos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0bc95-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="0bc95-110">Comprueba la regla de ensamblado de confianza (solo el nombre y la clave pública).</span><span class="sxs-lookup"><span data-stu-id="0bc95-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="0bc95-111">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0bc95-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="0bc95-112">Combinación de las `CANOF_PARSE_DISPLAY_NAME` marcas y `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` .</span><span class="sxs-lookup"><span data-stu-id="0bc95-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="0bc95-113">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0bc95-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bc95-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bc95-114">Requirements</span></span>  

 <span data-ttu-id="0bc95-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bc95-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc95-116">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="0bc95-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0bc95-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc95-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc95-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0bc95-118">See also</span></span>

- [<span data-ttu-id="0bc95-119">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bc95-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="0bc95-120">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="0bc95-120">CreateAssemblyNameObject Function</span></span>](createassemblynameobject-function.md)
- [<span data-ttu-id="0bc95-121">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="0bc95-121">Fusion Enumerations</span></span>](fusion-enumerations.md)
