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
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914646"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="b1a4f-102">SYMLINEDELTA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="b1a4f-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="b1a4f-103">Proporciona información al controlador de símbolos acerca de los métodos que se movieron como resultado de las modificaciones.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a4f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1a4f-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="b1a4f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b1a4f-105">Members</span></span>  
  
|<span data-ttu-id="b1a4f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b1a4f-106">Member</span></span>|<span data-ttu-id="b1a4f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1a4f-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="b1a4f-108">Token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="b1a4f-109">El número de líneas que se ha movido el método.</span><span class="sxs-lookup"><span data-stu-id="b1a4f-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1a4f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1a4f-110">Requirements</span></span>  
 <span data-ttu-id="b1a4f-111">**Encabezado**: CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="b1a4f-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a4f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1a4f-112">See also</span></span>

- [<span data-ttu-id="b1a4f-113">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b1a4f-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
