---
title: CorThreadSafetyOptions (Enumeración)
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b460c2c4b0d38ec46ee9d7341de9b320a2ecaa7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594647"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="a5524-102">CorThreadSafetyOptions (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a5524-102">CorThreadSafetyOptions Enumeration</span></span>
<span data-ttu-id="a5524-103">Especifica marcas para seleccionar opciones de seguridad para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="a5524-103">Specifies flags to select options for thread safety.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5524-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5524-104">Syntax</span></span>  
  
```  
typedef enum CorThreadSafetyOptions {  
    MDThreadSafetyDefault       = 0x00000000,  
    MDThreadSafetyOff           = 0x00000000,  
    MDThreadSafetyOn            = 0x00000001,  
} CorThreadSafetyOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="a5524-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a5524-105">Members</span></span>  
  
|<span data-ttu-id="a5524-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a5524-106">Member</span></span>|<span data-ttu-id="a5524-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5524-107">Description</span></span>|  
|------------|-----------------|  
|`MDThreadSatetyDefault`|<span data-ttu-id="a5524-108">Valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a5524-108">Default value.</span></span> <span data-ttu-id="a5524-109">Igual a `MDThreadSatetyOff`.</span><span class="sxs-lookup"><span data-stu-id="a5524-109">Same as `MDThreadSatetyOff`.</span></span>|  
|`MDThreadSatetyOff`|<span data-ttu-id="a5524-110">Indica que no se puede establecer un bloqueo de lector/escritor.</span><span class="sxs-lookup"><span data-stu-id="a5524-110">Indicates that a reader/writer lock cannot be set.</span></span>|  
|`MDThreadSatetyOn`|<span data-ttu-id="a5524-111">Indica que se puede establecer un bloqueo de lector/escritor.</span><span class="sxs-lookup"><span data-stu-id="a5524-111">Indicates that a reader/writer lock can be set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5524-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5524-112">Requirements</span></span>  
 <span data-ttu-id="a5524-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5524-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5524-114">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a5524-114">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a5524-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5524-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5524-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5524-116">See also</span></span>
- [<span data-ttu-id="a5524-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="a5524-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
