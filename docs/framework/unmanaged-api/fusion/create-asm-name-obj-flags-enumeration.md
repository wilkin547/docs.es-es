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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 871ad81cd83c40d7299f39ede404e274b95b2ac0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778458"
---
# <a name="createasmnameobjflags-enumeration"></a><span data-ttu-id="0b1cf-102">CREATE_ASM_NAME_OBJ_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0b1cf-102">CREATE_ASM_NAME_OBJ_FLAGS Enumeration</span></span>
<span data-ttu-id="0b1cf-103">Especifica los atributos de un [IAssemblyName (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto cuando se construye mediante la [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="0b1cf-103">Specifies the attributes of an [IAssemblyName Interface](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object when it is constructed by the [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b1cf-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="0b1cf-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0b1cf-105">Members</span></span>  
  
|<span data-ttu-id="0b1cf-106">Member</span><span class="sxs-lookup"><span data-stu-id="0b1cf-106">Member</span></span>|<span data-ttu-id="0b1cf-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0b1cf-107">Description</span></span>|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|<span data-ttu-id="0b1cf-108">Indica que el parámetro pasado es una identidad textual.</span><span class="sxs-lookup"><span data-stu-id="0b1cf-108">Indicates that the parameter passed is a textual identity.</span></span>|  
|`CANOF_SET_DEFAULT_VALUES`|<span data-ttu-id="0b1cf-109">Establece algunos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0b1cf-109">Sets a few default values.</span></span>|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|<span data-ttu-id="0b1cf-110">Comprueba la regla de ensamblado de confianza (solo el nombre y la clave pública).</span><span class="sxs-lookup"><span data-stu-id="0b1cf-110">Verifies the friend assembly rule (only name and public key).</span></span> <span data-ttu-id="0b1cf-111">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0b1cf-111">This member is for internal use only.</span></span>|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|<span data-ttu-id="0b1cf-112">Una combinación de la `CANOF_PARSE_DISPLAY_NAME` y `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` marcas.</span><span class="sxs-lookup"><span data-stu-id="0b1cf-112">A combination of the `CANOF_PARSE_DISPLAY_NAME` and `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` flags.</span></span> <span data-ttu-id="0b1cf-113">Este miembro es solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0b1cf-113">This member is for internal use only.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b1cf-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b1cf-114">Requirements</span></span>  
 <span data-ttu-id="0b1cf-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b1cf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b1cf-116">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0b1cf-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0b1cf-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b1cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1cf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b1cf-118">See also</span></span>

- [<span data-ttu-id="0b1cf-119">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b1cf-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="0b1cf-120">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="0b1cf-120">CreateAssemblyNameObject Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [<span data-ttu-id="0b1cf-121">Enumeraciones de fusión</span><span class="sxs-lookup"><span data-stu-id="0b1cf-121">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
