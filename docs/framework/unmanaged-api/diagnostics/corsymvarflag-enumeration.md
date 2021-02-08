---
description: 'Más información sobre: enumeración Corsymvarflag ('
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
ms.openlocfilehash: 28f4b4775e20703e5dcaa7daf69affd3548aa3f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800466"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="e2dfe-103">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e2dfe-103">CorSymVarFlag Enumeration</span></span>

<span data-ttu-id="e2dfe-104">Indica si una variable es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="e2dfe-104">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2dfe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2dfe-105">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="e2dfe-106">Members</span><span class="sxs-lookup"><span data-stu-id="e2dfe-106">Members</span></span>  
  
|<span data-ttu-id="e2dfe-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e2dfe-107">Member</span></span>|<span data-ttu-id="e2dfe-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2dfe-108">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="e2dfe-109">Indica que la variable especificada es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="e2dfe-109">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2dfe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2dfe-110">Requirements</span></span>  

 <span data-ttu-id="e2dfe-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e2dfe-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2dfe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2dfe-112">See also</span></span>

- [<span data-ttu-id="e2dfe-113">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="e2dfe-113">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
