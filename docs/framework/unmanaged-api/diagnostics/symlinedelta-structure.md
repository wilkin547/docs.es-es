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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d98ebed2eb853d5dc8177b0b044bf654c3978494
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744350"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="2e766-102">SYMLINEDELTA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2e766-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="2e766-103">Proporciona información al controlador de símbolos acerca de los métodos que se movieron como resultado de las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="2e766-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e766-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e766-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="2e766-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2e766-105">Members</span></span>  
  
|<span data-ttu-id="2e766-106">Member</span><span class="sxs-lookup"><span data-stu-id="2e766-106">Member</span></span>|<span data-ttu-id="2e766-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2e766-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="2e766-108">Token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="2e766-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="2e766-109">El número de líneas que se ha movido el método.</span><span class="sxs-lookup"><span data-stu-id="2e766-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e766-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e766-110">Requirements</span></span>  
 <span data-ttu-id="2e766-111">**Encabezado**: CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="2e766-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e766-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e766-112">See also</span></span>

- [<span data-ttu-id="2e766-113">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="2e766-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
