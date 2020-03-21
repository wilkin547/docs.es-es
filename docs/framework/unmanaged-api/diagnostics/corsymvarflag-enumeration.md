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
ms.openlocfilehash: 21e92d8f2fb80c4c41d516ef281bf4fc8a75f4e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176648"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="17a9c-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="17a9c-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="17a9c-103">Indica si una variable se genera en el compilador.</span><span class="sxs-lookup"><span data-stu-id="17a9c-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a9c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17a9c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="17a9c-105">Members</span><span class="sxs-lookup"><span data-stu-id="17a9c-105">Members</span></span>  
  
|<span data-ttu-id="17a9c-106">Member</span><span class="sxs-lookup"><span data-stu-id="17a9c-106">Member</span></span>|<span data-ttu-id="17a9c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="17a9c-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="17a9c-108">Indica que la variable dada se genera en el compilador.</span><span class="sxs-lookup"><span data-stu-id="17a9c-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17a9c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17a9c-109">Requirements</span></span>  
 <span data-ttu-id="17a9c-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17a9c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a9c-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17a9c-111">See also</span></span>

- [<span data-ttu-id="17a9c-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="17a9c-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
