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
ms.openlocfilehash: adef1010d08561c0a0fe38480fe0d2f519a80b49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133529"
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind (Enumeración)
Indica el tipo de dirección de memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Indica un lenguaje intermedio (MSIL) local variable o parámetro de índice de Microsoft.|  
|`ADDR_NATIVE_RVA`|Indica una dirección virtual relativa en un módulo.|  
|`ADDR_NATIVE_REGISTER`|Indica un registro de la CPU.|  
|`ADDR_NATIVE_REGREL`|Indica que la primera dirección es un registro y la segunda dirección es un desplazamiento.|  
|`ADDR_NATIVE_OFFSET`|Indica un desplazamiento desde una dirección base.|  
|`ADDR_NATIVE_REGREG`|Indica que la primera dirección es la parte baja de un registro y la segunda dirección es la parte alta.|  
|`ADDR_NATIVE_REGSTK`|Indica que la primera dirección es la parte baja de un registro, la segunda es la parte alta y el tercero es un desplazamiento.|  
|`ADDR_NATIVE_STKREG`|Indica que la primera dirección es un registro, el segundo es un desplazamiento y el tercero es la parte alta del registro.|  
|`ADDR_BITFIELD`|Indica que la primera dirección es el inicio de un campo y la segunda dirección es la longitud de campo.|  
|`ADDR_NATIVE_ISECTOFFSET`|Indica que la primera dirección es la sección y la segunda dirección es un desplazamiento.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
