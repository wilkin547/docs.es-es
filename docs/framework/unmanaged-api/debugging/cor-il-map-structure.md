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
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179292"
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
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`oldOffset`|El antiguo desplazamiento del lenguaje intermedio de Microsoft (MSIL) en relación con el principio de la función.|  
|`newOffset`|El nuevo desplazamiento MSIL en relación con el principio de la función.|  
|`fAccurate`|`true`si se sabe que la asignación es precisa; de `false`lo contrario, .|  
  
## <a name="remarks"></a>Observaciones  
 El formato de la asignación es el `oldOffset` siguiente: el depurador asumirá que hace referencia a un desplazamiento MSIL dentro del código MSIL original sin modificar. El `newOffset` parámetro hace referencia al desplazamiento MSIL correspondiente dentro del nuevo código instrumentado.  
  
 Para que el paso a paso funcione correctamente, se deben cumplir los siguientes requisitos:  
  
- El mapa debe ordenarse en orden ascendente.  
  
- El código MSIL instrumentado no se debe reordenar.  
  
- No se debe quitar el código MSIL original.  
  
- El mapa debe incluir entradas para asignar todos los puntos de secuencia del archivo de base de datos de programa (PDB).  
  
 El mapa no interpola las entradas que faltan. En el ejemplo siguiente se muestra un mapa y sus resultados.  
  
 Mapa:  
  
- 0 desplazamiento antiguo, 0 nuevo desplazamiento  
  
- 5 desplazamiento antiguo, 10 nuevo desplazamiento  
  
- 9 decompensación antigua, 20 nuevos desplazamientos  
  
 Resultados:  
  
- Un desplazamiento antiguo de 0, 1, 2, 3 o 4 se asignará a un nuevo desplazamiento de 0.  
  
- Un desplazamiento antiguo de 5, 6, 7 u 8 se asignará al nuevo desplazamiento 10.  
  
- Un desplazamiento antiguo de 9 o superior se asignará al nuevo desplazamiento 20.  
  
- Un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 se asignará al desplazamiento antiguo 0.  
  
- Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al desplazamiento antiguo 5.  
  
- Un nuevo desplazamiento de 20 o superior se asignará al desplazamiento anterior 9.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
