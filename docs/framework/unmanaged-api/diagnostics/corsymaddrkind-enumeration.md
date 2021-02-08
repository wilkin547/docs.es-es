---
description: 'Más información sobre: enumeración Corsymaddrkind ('
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
ms.openlocfilehash: 94ee9f3da63a33a9f4a80289dbf9b03969d37b3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800505"
---
# <a name="corsymaddrkind-enumeration"></a>CorSymAddrKind (Enumeración)

Indica el tipo de dirección de memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|Indica una variable local o un índice de parámetro de lenguaje intermedio de Microsoft (MSIL).|  
|`ADDR_NATIVE_RVA`|Indica una dirección virtual relativa en un módulo.|  
|`ADDR_NATIVE_REGISTER`|Indica un registro de CPU.|  
|`ADDR_NATIVE_REGREL`|Indica que la primera dirección es un registro y la segunda dirección es un desplazamiento.|  
|`ADDR_NATIVE_OFFSET`|Indica un desplazamiento a partir de una dirección base.|  
|`ADDR_NATIVE_REGREG`|Indica que la primera dirección es la parte baja de un registro y la segunda es la parte alta.|  
|`ADDR_NATIVE_REGSTK`|Indica que la primera dirección es la parte inferior de un registro, la segunda es la parte alta y la tercera es un desplazamiento.|  
|`ADDR_NATIVE_STKREG`|Indica que la primera dirección es un registro, la segunda es un desplazamiento y la tercera es la parte alta del registro.|  
|`ADDR_BITFIELD`|Indica que la primera dirección es el inicio de un campo y la segunda dirección es la longitud del campo.|  
|`ADDR_NATIVE_ISECTOFFSET`|Indica que la primera dirección es la sección y la segunda dirección es un desplazamiento.|  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de almacén de símbolos de diagnósticos](diagnostics-symbol-store-enumerations.md)
