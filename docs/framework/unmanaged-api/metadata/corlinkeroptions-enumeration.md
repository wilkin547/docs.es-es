---
description: 'Más información sobre: enumeración Corlinkeroptions ('
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
ms.openlocfilehash: 40f8ba6382fc937a072e01f9b3f6f89056f628db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784436"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="9dfcb-103">CorLinkerOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9dfcb-103">CorLinkerOptions Enumeration</span></span>

<span data-ttu-id="9dfcb-104">Especifica marcas para seleccionar las opciones del vinculador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9dfcb-104">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dfcb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dfcb-105">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="9dfcb-106">Members</span><span class="sxs-lookup"><span data-stu-id="9dfcb-106">Members</span></span>  
  
|<span data-ttu-id="9dfcb-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="9dfcb-107">Member</span></span>|<span data-ttu-id="9dfcb-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dfcb-108">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="9dfcb-109">Los tipos privados y las funciones globales no se conservan.</span><span class="sxs-lookup"><span data-stu-id="9dfcb-109">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="9dfcb-110">Se conservan los tipos privados y las funciones globales.</span><span class="sxs-lookup"><span data-stu-id="9dfcb-110">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9dfcb-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dfcb-111">Requirements</span></span>  

 <span data-ttu-id="9dfcb-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dfcb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dfcb-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="9dfcb-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9dfcb-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dfcb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfcb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dfcb-115">See also</span></span>

- [<span data-ttu-id="9dfcb-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="9dfcb-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
