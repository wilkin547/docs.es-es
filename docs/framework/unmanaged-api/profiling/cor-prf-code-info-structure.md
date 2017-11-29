---
title: COR_PRF_CODE_INFO (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CODE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CODE_INFO
helpviewer_keywords: COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 007bb5990ec750dccc678a208d755136ea67a05c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="de2b5-102">COR_PRF_CODE_INFO (Estructura)</span><span class="sxs-lookup"><span data-stu-id="de2b5-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="de2b5-103">Representa un bloque contiguo de código nativo almacenado en la memoria.</span><span class="sxs-lookup"><span data-stu-id="de2b5-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de2b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de2b5-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="de2b5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="de2b5-105">Members</span></span>  
  
|<span data-ttu-id="de2b5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="de2b5-106">Member</span></span>|<span data-ttu-id="de2b5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="de2b5-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="de2b5-108">La dirección inicial del bloque contiguo de código.</span><span class="sxs-lookup"><span data-stu-id="de2b5-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="de2b5-109">El tamaño del bloque.</span><span class="sxs-lookup"><span data-stu-id="de2b5-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de2b5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de2b5-110">Requirements</span></span>  
 <span data-ttu-id="de2b5-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de2b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de2b5-112">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="de2b5-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="de2b5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de2b5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de2b5-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de2b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2b5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="de2b5-115">See Also</span></span>  
 [<span data-ttu-id="de2b5-116">Estructuras de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="de2b5-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
