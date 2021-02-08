---
description: 'Más información sobre: enumeración CorPEKind ('
title: CorPEKind (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 6d1f29a220ce9d4be4151d8eff6557fa8c693ed2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784280"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="e136e-103">CorPEKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e136e-103">CorPEKind Enumeration</span></span>

<span data-ttu-id="e136e-104">Contiene valores que describen un archivo portable ejecutable (PE), tal y como se devuelve de una llamada a [IMetaDataImport2:: getpekind (](imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="e136e-104">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e136e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e136e-105">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="e136e-106">Members</span><span class="sxs-lookup"><span data-stu-id="e136e-106">Members</span></span>  
  
|<span data-ttu-id="e136e-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e136e-107">Member</span></span>|<span data-ttu-id="e136e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e136e-108">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="e136e-109">Indica que este no es un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="e136e-109">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="e136e-110">Indica que este archivo PE contiene solo código administrado.</span><span class="sxs-lookup"><span data-stu-id="e136e-110">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="e136e-111">Indica que este archivo PE realiza llamadas a Win32.</span><span class="sxs-lookup"><span data-stu-id="e136e-111">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="e136e-112">Indica que este archivo PE se ejecuta en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e136e-112">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="e136e-113">Indica que este archivo PE es código nativo.</span><span class="sxs-lookup"><span data-stu-id="e136e-113">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="e136e-114">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="e136e-114">pe32BitPreferred</span></span>|<span data-ttu-id="e136e-115">Indica que este archivo PE es independiente de la plataforma y prefiere que se cargue en un entorno de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="e136e-115">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e136e-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e136e-116">Remarks</span></span>  

 <span data-ttu-id="e136e-117">Estos valores se pueden usar en combinaciones bit a bit.</span><span class="sxs-lookup"><span data-stu-id="e136e-117">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e136e-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e136e-118">Requirements</span></span>  

 <span data-ttu-id="e136e-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e136e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e136e-120">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="e136e-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e136e-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e136e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e136e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e136e-122">See also</span></span>

- [<span data-ttu-id="e136e-123">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="e136e-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
