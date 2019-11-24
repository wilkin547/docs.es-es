---
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
ms.openlocfilehash: 74670a1477546066145bd4bbf2f123a252e10b55
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436472"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="519b5-102">CorPEKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="519b5-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="519b5-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="519b5-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="519b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="519b5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="519b5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="519b5-105">Members</span></span>  
  
|<span data-ttu-id="519b5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="519b5-106">Member</span></span>|<span data-ttu-id="519b5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="519b5-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="519b5-108">Indicates that this is not a PE file.</span><span class="sxs-lookup"><span data-stu-id="519b5-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="519b5-109">Indicates that this PE file contains only managed code.</span><span class="sxs-lookup"><span data-stu-id="519b5-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="519b5-110">Indicates that this PE file makes Win32 calls.</span><span class="sxs-lookup"><span data-stu-id="519b5-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="519b5-111">Indicates that this PE file runs on a 64-bit platform.</span><span class="sxs-lookup"><span data-stu-id="519b5-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="519b5-112">Indicates that this PE file is native code.</span><span class="sxs-lookup"><span data-stu-id="519b5-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="519b5-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="519b5-113">pe32BitPreferred</span></span>|<span data-ttu-id="519b5-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span><span class="sxs-lookup"><span data-stu-id="519b5-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="519b5-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="519b5-115">Remarks</span></span>  
 <span data-ttu-id="519b5-116">These values can be used in bitwise combinations.</span><span class="sxs-lookup"><span data-stu-id="519b5-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="519b5-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="519b5-117">Requirements</span></span>  
 <span data-ttu-id="519b5-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="519b5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="519b5-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="519b5-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="519b5-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="519b5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519b5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="519b5-121">See also</span></span>

- [<span data-ttu-id="519b5-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="519b5-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
