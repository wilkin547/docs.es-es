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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045544"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="4edf4-102">CorPEKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4edf4-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="4edf4-103">Contiene valores que describen un archivo ejecutable portable (PE), tal como lo devuelve una llamada a [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="4edf4-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4edf4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4edf4-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="4edf4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4edf4-105">Members</span></span>  
  
|<span data-ttu-id="4edf4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4edf4-106">Member</span></span>|<span data-ttu-id="4edf4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4edf4-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="4edf4-108">Indica que no es un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="4edf4-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="4edf4-109">Indica que este archivo PE contiene sólo código administrado.</span><span class="sxs-lookup"><span data-stu-id="4edf4-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="4edf4-110">Indica que este archivo PE efectúa llamadas a Win32.</span><span class="sxs-lookup"><span data-stu-id="4edf4-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="4edf4-111">Indica que este archivo PE se ejecuta en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="4edf4-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="4edf4-112">Indica que este archivo PE es código nativo.</span><span class="sxs-lookup"><span data-stu-id="4edf4-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="4edf4-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="4edf4-113">pe32BitPreferred</span></span>|<span data-ttu-id="4edf4-114">Indica que este archivo PE es independiente de la plataforma y prefiere que se cargue en un entorno de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="4edf4-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4edf4-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4edf4-115">Remarks</span></span>  
 <span data-ttu-id="4edf4-116">Estos valores se pueden usar en combinaciones bit a bit.</span><span class="sxs-lookup"><span data-stu-id="4edf4-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4edf4-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4edf4-117">Requirements</span></span>  
 <span data-ttu-id="4edf4-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4edf4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4edf4-119">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4edf4-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4edf4-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4edf4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edf4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4edf4-121">See also</span></span>

- [<span data-ttu-id="4edf4-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4edf4-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
