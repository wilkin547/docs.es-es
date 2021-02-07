---
description: 'Más información acerca de: estructura SYMLINEDELTA ('
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
ms.openlocfilehash: ae00d2be9809b48180d2cd99d05e410624033419
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761452"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="5b3ef-103">SYMLINEDELTA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5b3ef-103">SYMLINEDELTA Structure</span></span>

<span data-ttu-id="5b3ef-104">Proporciona información al controlador de símbolos sobre los métodos que se movieron como resultado de las ediciones.</span><span class="sxs-lookup"><span data-stu-id="5b3ef-104">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b3ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b3ef-105">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="5b3ef-106">Members</span><span class="sxs-lookup"><span data-stu-id="5b3ef-106">Members</span></span>  
  
|<span data-ttu-id="5b3ef-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="5b3ef-107">Member</span></span>|<span data-ttu-id="5b3ef-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b3ef-108">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="5b3ef-109">Token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="5b3ef-109">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="5b3ef-110">Número de líneas que se ha despasado el método.</span><span class="sxs-lookup"><span data-stu-id="5b3ef-110">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b3ef-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b3ef-111">Requirements</span></span>  

 <span data-ttu-id="5b3ef-112">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="5b3ef-112">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3ef-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b3ef-113">See also</span></span>

- [<span data-ttu-id="5b3ef-114">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="5b3ef-114">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
