---
title: "CorSymVarFlag (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymVarFlag
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymVarFlag
helpviewer_keywords: CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: edbbc8109eb44494c7f4fac0ed8756e23bdc955b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="b8e42-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b8e42-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="b8e42-103">Indica si una variable es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="b8e42-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8e42-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="b8e42-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b8e42-105">Members</span></span>  
  
|<span data-ttu-id="b8e42-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b8e42-106">Member</span></span>|<span data-ttu-id="b8e42-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8e42-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="b8e42-108">Indica que la variable determinada es generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="b8e42-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8e42-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8e42-109">Requirements</span></span>  
 <span data-ttu-id="b8e42-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8e42-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e42-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8e42-111">See Also</span></span>  
 [<span data-ttu-id="b8e42-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b8e42-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
