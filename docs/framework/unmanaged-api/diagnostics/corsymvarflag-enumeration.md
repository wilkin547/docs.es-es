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
ms.openlocfilehash: d41e048b67d4bc7159f6dd5266457651f1658290
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420596"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="0fd50-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0fd50-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="0fd50-103">Indica si una variable es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="0fd50-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fd50-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="0fd50-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0fd50-105">Members</span></span>  
  
|<span data-ttu-id="0fd50-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0fd50-106">Member</span></span>|<span data-ttu-id="0fd50-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fd50-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="0fd50-108">Indica que la variable especificada es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="0fd50-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fd50-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fd50-109">Requirements</span></span>  
 <span data-ttu-id="0fd50-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0fd50-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd50-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0fd50-111">See also</span></span>

- [<span data-ttu-id="0fd50-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0fd50-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
