---
title: "CorParamAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorParamAttr
helpviewer_keywords: CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 469c148dbce4139a3d72021991185f3ed6f7c5da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="75eb2-102">CorParamAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="75eb2-102">CorParamAttr Enumeration</span></span>
<span data-ttu-id="75eb2-103">Contiene valores que describen los metadatos de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="75eb2-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75eb2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75eb2-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="75eb2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="75eb2-105">Members</span></span>  
  
|<span data-ttu-id="75eb2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="75eb2-106">Member</span></span>|<span data-ttu-id="75eb2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="75eb2-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="75eb2-108">Especifica que el parámetro se pasa en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="75eb2-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="75eb2-109">Especifica que el parámetro se pasa desde el método de devolución.</span><span class="sxs-lookup"><span data-stu-id="75eb2-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="75eb2-110">Especifica que el parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="75eb2-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="75eb2-111">Reservado para uso interno por common language runtime.</span><span class="sxs-lookup"><span data-stu-id="75eb2-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="75eb2-112">Especifica que el parámetro tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="75eb2-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="75eb2-113">Especifica que el parámetro tiene información de serialización.</span><span class="sxs-lookup"><span data-stu-id="75eb2-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="75eb2-114">Sin usar.</span><span class="sxs-lookup"><span data-stu-id="75eb2-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75eb2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75eb2-115">Requirements</span></span>  
 <span data-ttu-id="75eb2-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75eb2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75eb2-117">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="75eb2-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="75eb2-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75eb2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75eb2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="75eb2-119">See Also</span></span>  
 [<span data-ttu-id="75eb2-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="75eb2-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
