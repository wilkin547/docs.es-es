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
ms.openlocfilehash: 086e17185df9caa823b44b51cf027f95d635c48d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450273"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="06d34-102">CorLinkerOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="06d34-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="06d34-103">Especifica marcas para seleccionar las opciones del vinculador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="06d34-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d34-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06d34-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="06d34-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="06d34-105">Members</span></span>  
  
|<span data-ttu-id="06d34-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="06d34-106">Member</span></span>|<span data-ttu-id="06d34-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="06d34-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="06d34-108">The private types and global functions are not preserved.</span><span class="sxs-lookup"><span data-stu-id="06d34-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="06d34-109">The private types and global functions are preserved.</span><span class="sxs-lookup"><span data-stu-id="06d34-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06d34-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06d34-110">Requirements</span></span>  
 <span data-ttu-id="06d34-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06d34-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d34-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="06d34-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="06d34-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d34-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06d34-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="06d34-114">See also</span></span>

- [<span data-ttu-id="06d34-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="06d34-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
