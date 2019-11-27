---
title: CorParamAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: 1d58c8c0413346536c3e61e67ca0077c08c2b387
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436494"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="4e2b1-102">CorParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4e2b1-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="4e2b1-103">Contiene valores que describen los metadatos de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e2b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e2b1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="4e2b1-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4e2b1-105">Members</span></span>  
  
|<span data-ttu-id="4e2b1-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4e2b1-106">Member</span></span>|<span data-ttu-id="4e2b1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e2b1-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="4e2b1-108">Especifica que el parámetro se pasa a la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="4e2b1-109">Especifica que el parámetro se pasa desde el método devuelto.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="4e2b1-110">Especifica que el parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="4e2b1-111">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="4e2b1-112">Especifica que el parámetro tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="4e2b1-113">Especifica que el parámetro tiene información de serialización.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="4e2b1-114">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="4e2b1-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e2b1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e2b1-115">Requirements</span></span>  
 <span data-ttu-id="4e2b1-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e2b1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e2b1-117">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="4e2b1-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="4e2b1-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e2b1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e2b1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e2b1-119">See also</span></span>

- [<span data-ttu-id="4e2b1-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="4e2b1-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
