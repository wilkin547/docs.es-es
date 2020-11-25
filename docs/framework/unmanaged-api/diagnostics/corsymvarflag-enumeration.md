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
ms.openlocfilehash: ed08d9f818f6fc180dbd655243488bf8a527ae11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725292"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="0afb3-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0afb3-102">CorSymVarFlag Enumeration</span></span>

<span data-ttu-id="0afb3-103">Indica si una variable es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="0afb3-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0afb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0afb3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="0afb3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0afb3-105">Members</span></span>  
  
|<span data-ttu-id="0afb3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0afb3-106">Member</span></span>|<span data-ttu-id="0afb3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0afb3-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="0afb3-108">Indica que la variable especificada es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="0afb3-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0afb3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0afb3-109">Requirements</span></span>  

 <span data-ttu-id="0afb3-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0afb3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0afb3-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0afb3-111">See also</span></span>

- [<span data-ttu-id="0afb3-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0afb3-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
