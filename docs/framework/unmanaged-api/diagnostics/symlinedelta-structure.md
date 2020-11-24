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
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690946"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="1f156-102">SYMLINEDELTA (Estructura)</span><span class="sxs-lookup"><span data-stu-id="1f156-102">SYMLINEDELTA Structure</span></span>

<span data-ttu-id="1f156-103">Proporciona información al controlador de símbolos sobre los métodos que se movieron como resultado de las ediciones.</span><span class="sxs-lookup"><span data-stu-id="1f156-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f156-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f156-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="1f156-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1f156-105">Members</span></span>  
  
|<span data-ttu-id="1f156-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1f156-106">Member</span></span>|<span data-ttu-id="1f156-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f156-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="1f156-108">Token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="1f156-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="1f156-109">Número de líneas que se ha despasado el método.</span><span class="sxs-lookup"><span data-stu-id="1f156-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f156-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f156-110">Requirements</span></span>  

 <span data-ttu-id="1f156-111">**Encabezado:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="1f156-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f156-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f156-112">See also</span></span>

- [<span data-ttu-id="1f156-113">Estructuras de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="1f156-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
