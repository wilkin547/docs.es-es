---
title: CorSymVarFlag (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c797378f5e13f39c1c786237a3a7b9cf577fccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198860"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="6fe16-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6fe16-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="6fe16-103">Indica si una variable es generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="6fe16-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fe16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fe16-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="6fe16-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6fe16-105">Members</span></span>  
  
|<span data-ttu-id="6fe16-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6fe16-106">Member</span></span>|<span data-ttu-id="6fe16-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6fe16-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="6fe16-108">Indica que la variable dada es generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="6fe16-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fe16-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fe16-109">Requirements</span></span>  
 <span data-ttu-id="6fe16-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6fe16-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe16-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fe16-111">See also</span></span>

- [<span data-ttu-id="6fe16-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="6fe16-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
