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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a072e124343641c9f75fb9f924a6409efc8e1d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719942"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="53011-102">CorLinkerOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="53011-102">CorLinkerOptions Enumeration</span></span>
<span data-ttu-id="53011-103">Especifica marcas para seleccionar las opciones del vinculador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="53011-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53011-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53011-104">Syntax</span></span>  
  
```  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="53011-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="53011-105">Members</span></span>  
  
|<span data-ttu-id="53011-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="53011-106">Member</span></span>|<span data-ttu-id="53011-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="53011-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="53011-108">No se conservan los tipos privados y funciones globales.</span><span class="sxs-lookup"><span data-stu-id="53011-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="53011-109">Los tipos privados y funciones globales se conservan.</span><span class="sxs-lookup"><span data-stu-id="53011-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53011-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53011-110">Requirements</span></span>  
 <span data-ttu-id="53011-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53011-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53011-112">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="53011-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="53011-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53011-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53011-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="53011-114">See also</span></span>
- [<span data-ttu-id="53011-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="53011-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
