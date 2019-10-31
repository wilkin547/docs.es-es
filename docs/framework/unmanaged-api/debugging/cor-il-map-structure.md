---
title: COR_IL_MAP (Estructura)
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: c37f039d9636854c464e7981693c573bd60deab9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132337"
---
# <a name="cor_il_map-structure"></a>COR_IL_MAP (Estructura)
Especifica los cambios en el desplazamiento relativo de una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`oldOffset`|El desplazamiento anterior del lenguaje intermedio de Microsoft (MSIL) con respecto al principio de la función.|  
|`newOffset`|Nuevo desplazamiento de MSIL relativo al principio de la función.|  
|`fAccurate`|`true` si se sabe que la asignación es precisa; de lo contrario, `false`.|  
  
## <a name="remarks"></a>Comentarios  
 El formato del mapa es el siguiente: el depurador supondrá que `oldOffset` hace referencia a un desplazamiento de MSIL en el código MSIL original y sin modificar. El parámetro `newOffset` hace referencia al desplazamiento de MSIL correspondiente en el nuevo código instrumentado.  
  
 Para que funcione correctamente, deben cumplirse los siguientes requisitos:  
  
- El mapa se debe ordenar en orden ascendente.  
  
- No se debe reordenar el código MSIL instrumentado.  
  
- El código MSIL original no se debe quitar.  
  
- La asignación debe incluir entradas para asignar todos los puntos de secuencia del archivo de base de datos de programa (PDB).  
  
 La asignación no interpola las entradas que faltan. En el ejemplo siguiente se muestra una asignación y sus resultados.  
  
 Conectarse  
  
- 0 desplazamiento anterior, 0 nuevo desplazamiento  
  
- 5 desplazamiento anterior, 10 nuevo desplazamiento  
  
- 9 desplazamiento anterior, 20 nuevo desplazamiento  
  
 Resultados  
  
- Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará a un nuevo desplazamiento de 0.  
  
- Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.  
  
- Un desplazamiento anterior de 9 o superior se asignará al nuevo desplazamiento 20.  
  
- Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento anterior 0.  
  
- Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.  
  
- Un nuevo desplazamiento de 20 o superior se asignará al anterior desplazamiento 9.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl, Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
