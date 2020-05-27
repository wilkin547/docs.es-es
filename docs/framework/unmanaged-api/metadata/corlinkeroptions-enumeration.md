---
title: CorLinkerOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: fe5ffbab93df7168015e2a31d6e32ec45dce0960
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007694"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="88518-102">CorLinkerOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="88518-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="88518-103">Especifica marcas para seleccionar las opciones del vinculador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="88518-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88518-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88518-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="88518-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="88518-105">Members</span></span>  
  
|<span data-ttu-id="88518-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="88518-106">Member</span></span>|<span data-ttu-id="88518-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="88518-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="88518-108">Los tipos privados y las funciones globales no se conservan.</span><span class="sxs-lookup"><span data-stu-id="88518-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="88518-109">Se conservan los tipos privados y las funciones globales.</span><span class="sxs-lookup"><span data-stu-id="88518-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88518-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88518-110">Requirements</span></span>  
 <span data-ttu-id="88518-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88518-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88518-112">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="88518-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="88518-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88518-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88518-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="88518-114">See also</span></span>

- [<span data-ttu-id="88518-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="88518-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
