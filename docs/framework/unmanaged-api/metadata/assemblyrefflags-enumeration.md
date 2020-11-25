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
ms.openlocfilehash: 0a99d2f79645bdc46ff4db86d7280614eeb1faf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732767"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="07708-102">AssemblyRefFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="07708-102">AssemblyRefFlags Enumeration</span></span>

<span data-ttu-id="07708-103">Contiene valores que describen las características de una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07708-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07708-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07708-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="07708-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="07708-105">Members</span></span>  
  
|<span data-ttu-id="07708-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="07708-106">Member</span></span>|<span data-ttu-id="07708-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="07708-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="07708-108">Especifica que la referencia de ensamblado contiene información completa sin hash sobre el publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="07708-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07708-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07708-109">Requirements</span></span>  

 <span data-ttu-id="07708-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07708-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07708-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="07708-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07708-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07708-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07708-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07708-113">See also</span></span>

- [<span data-ttu-id="07708-114">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="07708-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="07708-115">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07708-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="07708-116">Método DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="07708-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
