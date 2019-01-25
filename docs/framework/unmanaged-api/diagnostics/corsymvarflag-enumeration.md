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
ms.openlocfilehash: 50367358ba5bcf335f8cc2ca3222f6cf7ea2ff70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670145"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="60510-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="60510-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="60510-103">Indica si una variable es generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="60510-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60510-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60510-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="60510-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="60510-105">Members</span></span>  
  
|<span data-ttu-id="60510-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="60510-106">Member</span></span>|<span data-ttu-id="60510-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="60510-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="60510-108">Indica que la variable dada es generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="60510-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60510-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60510-109">Requirements</span></span>  
 <span data-ttu-id="60510-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="60510-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60510-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="60510-111">See also</span></span>
- [<span data-ttu-id="60510-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="60510-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
