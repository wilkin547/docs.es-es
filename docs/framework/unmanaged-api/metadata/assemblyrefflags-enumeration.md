---
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
ms.openlocfilehash: 1307f555c9d8b6d28febcf25db89ae856c143d71
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009410"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="ab124-102">AssemblyRefFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ab124-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="ab124-103">Contiene valores que describen las características de una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab124-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab124-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab124-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ab124-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ab124-105">Members</span></span>  
  
|<span data-ttu-id="ab124-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ab124-106">Member</span></span>|<span data-ttu-id="ab124-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab124-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="ab124-108">Especifica que la referencia de ensamblado contiene información completa sin hash sobre el publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab124-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab124-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab124-109">Requirements</span></span>  
 <span data-ttu-id="ab124-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab124-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab124-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ab124-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab124-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab124-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab124-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab124-113">See also</span></span>

- [<span data-ttu-id="ab124-114">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="ab124-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="ab124-115">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab124-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="ab124-116">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="ab124-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
