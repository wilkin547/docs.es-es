---
description: 'Más información sobre: enumeración AssemblyRefFlags ('
title: AssemblyRefFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 1b33faf816194c8b386f34a63d885ba37c4329a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678911"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="aa08c-103">AssemblyRefFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="aa08c-103">AssemblyRefFlags Enumeration</span></span>

<span data-ttu-id="aa08c-104">Contiene valores que describen las características de una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa08c-104">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa08c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa08c-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="aa08c-106">Members</span><span class="sxs-lookup"><span data-stu-id="aa08c-106">Members</span></span>  
  
|<span data-ttu-id="aa08c-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="aa08c-107">Member</span></span>|<span data-ttu-id="aa08c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa08c-108">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="aa08c-109">Especifica que la referencia de ensamblado contiene información completa sin hash sobre el publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa08c-109">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa08c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa08c-110">Requirements</span></span>  

 <span data-ttu-id="aa08c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa08c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa08c-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aa08c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa08c-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa08c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa08c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa08c-114">See also</span></span>

- [<span data-ttu-id="aa08c-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="aa08c-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="aa08c-116">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa08c-116">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="aa08c-117">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="aa08c-117">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
