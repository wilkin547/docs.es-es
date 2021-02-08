---
description: 'Más información sobre: enumeración Corparamattr ('
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
ms.openlocfilehash: c07569d3fb92b20a7985dbfeb2205af727866051
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784293"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="19514-103">CorParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="19514-103">CorParamAttr Enumeration</span></span>

<span data-ttu-id="19514-104">Contiene valores que describen los metadatos de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="19514-104">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19514-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19514-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="19514-106">Members</span><span class="sxs-lookup"><span data-stu-id="19514-106">Members</span></span>  
  
|<span data-ttu-id="19514-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="19514-107">Member</span></span>|<span data-ttu-id="19514-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="19514-108">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="19514-109">Especifica que el parámetro se pasa a la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="19514-109">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="19514-110">Especifica que el parámetro se pasa desde el método devuelto.</span><span class="sxs-lookup"><span data-stu-id="19514-110">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="19514-111">Especifica que este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="19514-111">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="19514-112">Reservado para uso interno por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="19514-112">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="19514-113">Especifica que el parámetro tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="19514-113">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="19514-114">Especifica que el parámetro tiene información de serialización.</span><span class="sxs-lookup"><span data-stu-id="19514-114">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="19514-115">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="19514-115">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19514-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19514-116">Requirements</span></span>  

 <span data-ttu-id="19514-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19514-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19514-118">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="19514-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="19514-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19514-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19514-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="19514-120">See also</span></span>

- [<span data-ttu-id="19514-121">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="19514-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
