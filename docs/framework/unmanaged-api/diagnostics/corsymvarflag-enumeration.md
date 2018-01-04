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
ms.workload: dotnet
ms.openlocfilehash: b548a66f471eb3641da7407ed14d107c6b4fec8c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="f478c-102">CorSymVarFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f478c-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="f478c-103">Indica si una variable es generada por el compilador.</span><span class="sxs-lookup"><span data-stu-id="f478c-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f478c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f478c-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="f478c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f478c-105">Members</span></span>  
  
|<span data-ttu-id="f478c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f478c-106">Member</span></span>|<span data-ttu-id="f478c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f478c-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="f478c-108">Indica que la variable determinada es generado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="f478c-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f478c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f478c-109">Requirements</span></span>  
 <span data-ttu-id="f478c-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f478c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f478c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f478c-111">See Also</span></span>  
 [<span data-ttu-id="f478c-112">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="f478c-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
