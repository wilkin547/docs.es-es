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
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609305"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="40589-102">SYMLINEDELTA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="40589-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="40589-103">Proporciona información al controlador de símbolos sobre los métodos que se movieron como resultado de las ediciones.</span><span class="sxs-lookup"><span data-stu-id="40589-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40589-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40589-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="40589-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="40589-105">Members</span></span>  
  
|<span data-ttu-id="40589-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="40589-106">Member</span></span>|<span data-ttu-id="40589-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="40589-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="40589-108">Token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="40589-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="40589-109">Número de líneas que se ha despasado el método.</span><span class="sxs-lookup"><span data-stu-id="40589-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40589-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40589-110">Requirements</span></span>  
 <span data-ttu-id="40589-111">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="40589-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40589-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="40589-112">See also</span></span>

- [<span data-ttu-id="40589-113">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="40589-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
