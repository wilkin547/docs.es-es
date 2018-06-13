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
ms.openlocfilehash: a6a9c5ff91989fc1ad7da4e23df0e80d9d74ec7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424981"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="7b0d5-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7b0d5-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="7b0d5-103">Indica si una variable es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="7b0d5-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b0d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b0d5-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="7b0d5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7b0d5-105">Members</span></span>  
  
|<span data-ttu-id="7b0d5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="7b0d5-106">Member</span></span>|<span data-ttu-id="7b0d5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b0d5-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="7b0d5-108">Indica que la variable determinada es generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="7b0d5-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b0d5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b0d5-109">Requirements</span></span>  
 <span data-ttu-id="7b0d5-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b0d5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0d5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b0d5-111">See Also</span></span>  
 [<span data-ttu-id="7b0d5-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="7b0d5-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
