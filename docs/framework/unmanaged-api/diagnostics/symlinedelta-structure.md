---
title: SYMLINEDELTA (Estructura)
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: a1e83e4b8cb6603029f3b42b1a3b9ba4810c9039
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438013"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="9a075-102">SYMLINEDELTA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="9a075-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="9a075-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span><span class="sxs-lookup"><span data-stu-id="9a075-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a075-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a075-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="9a075-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9a075-105">Members</span></span>  
  
|<span data-ttu-id="9a075-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9a075-106">Member</span></span>|<span data-ttu-id="9a075-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a075-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="9a075-108">The method's metadata token.</span><span class="sxs-lookup"><span data-stu-id="9a075-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="9a075-109">The number of lines the method was moved.</span><span class="sxs-lookup"><span data-stu-id="9a075-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a075-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a075-110">Requirements</span></span>  
 <span data-ttu-id="9a075-111">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="9a075-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a075-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a075-112">See also</span></span>

- [<span data-ttu-id="9a075-113">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="9a075-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
