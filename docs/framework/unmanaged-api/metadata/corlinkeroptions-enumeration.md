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
ms.openlocfilehash: 188301d31b2fcfaf7b1c6139111e8f1296ccf7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677250"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="c1b57-102">CorLinkerOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c1b57-102">CorLinkerOptions Enumeration</span></span>

<span data-ttu-id="c1b57-103">Especifica marcas para seleccionar las opciones del vinculador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c1b57-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1b57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1b57-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="c1b57-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c1b57-105">Members</span></span>  
  
|<span data-ttu-id="c1b57-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c1b57-106">Member</span></span>|<span data-ttu-id="c1b57-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1b57-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="c1b57-108">Los tipos privados y las funciones globales no se conservan.</span><span class="sxs-lookup"><span data-stu-id="c1b57-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="c1b57-109">Se conservan los tipos privados y las funciones globales.</span><span class="sxs-lookup"><span data-stu-id="c1b57-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1b57-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1b57-110">Requirements</span></span>  

 <span data-ttu-id="c1b57-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1b57-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1b57-112">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="c1b57-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c1b57-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1b57-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b57-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1b57-114">See also</span></span>

- [<span data-ttu-id="c1b57-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c1b57-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
