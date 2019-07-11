---
title: CorSymAddrKind (Enumeración)
ms.date: 03/30/2017
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ba24f5394ef8fb31d8bfa4e74ac59e7bd4af86d8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769862"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="83d76-102">CorSymAddrKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="83d76-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="83d76-103">Indica el tipo de dirección de memoria.</span><span class="sxs-lookup"><span data-stu-id="83d76-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83d76-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="83d76-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="83d76-105">Members</span></span>  
  
|<span data-ttu-id="83d76-106">Member</span><span class="sxs-lookup"><span data-stu-id="83d76-106">Member</span></span>|<span data-ttu-id="83d76-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83d76-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="83d76-108">Indica un lenguaje intermedio (MSIL) local variable o parámetro de índice de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="83d76-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="83d76-109">Indica una dirección virtual relativa en un módulo.</span><span class="sxs-lookup"><span data-stu-id="83d76-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="83d76-110">Indica un registro de la CPU.</span><span class="sxs-lookup"><span data-stu-id="83d76-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="83d76-111">Indica que la primera dirección es un registro y la segunda dirección es un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="83d76-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="83d76-112">Indica un desplazamiento desde una dirección base.</span><span class="sxs-lookup"><span data-stu-id="83d76-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="83d76-113">Indica que la primera dirección es la parte baja de un registro y la segunda dirección es la parte alta.</span><span class="sxs-lookup"><span data-stu-id="83d76-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="83d76-114">Indica que la primera dirección es la parte baja de un registro, la segunda es la parte alta y el tercero es un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="83d76-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="83d76-115">Indica que la primera dirección es un registro, el segundo es un desplazamiento y el tercero es la parte alta del registro.</span><span class="sxs-lookup"><span data-stu-id="83d76-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="83d76-116">Indica que la primera dirección es el inicio de un campo y la segunda dirección es la longitud de campo.</span><span class="sxs-lookup"><span data-stu-id="83d76-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="83d76-117">Indica que la primera dirección es la sección y la segunda dirección es un desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="83d76-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83d76-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83d76-118">Requirements</span></span>  
 <span data-ttu-id="83d76-119">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="83d76-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d76-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="83d76-120">See also</span></span>

- [<span data-ttu-id="83d76-121">Enumeraciones de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="83d76-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
