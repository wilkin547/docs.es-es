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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74f515626f5001cbea1a25e8268338c588524bde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740536"
---
# <a name="corilmap-structure"></a>COR_IL_MAP (Estructura)
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`oldOffset`|El antiguo lenguaje intermedio de Microsoft (MSIL) de desplazamiento en relación con el principio de la función.|  
|`newOffset`|Nuevo desplazamiento MSIL en relación con el principio de la función.|  
|`fAccurate`|`true` Si se conoce la asignación para ser precisos; en caso contrario, `false`.|  
  
## <a name="remarks"></a>Comentarios  
 El formato de la asignación es como sigue: El depurador supondrá que `oldOffset` hace referencia a un desplazamiento de MSIL dentro del código MSIL original, sin modificar. El `newOffset` parámetro hace referencia al desplazamiento de MSIL correspondiente dentro del nuevo código instrumentado.  
  
 Para la ejecución paso a paso para que funcionen correctamente, deben cumplirse los siguientes requisitos:  
  
- El mapa se debe ordenar en orden ascendente.  
  
- No se debe reordenar código MSIL instrumentado.  
  
- No se debe quitar el código de MSIL original.  
  
- La asignación debería incluir las entradas para asignar todos los puntos de secuencia del archivo de programa (PDB) de la base de datos.  
  
 El mapa no interpola las entradas que faltan. El ejemplo siguiente muestra un mapa y sus resultados.  
  
 Mapa:  
  
- desplazamiento anterior 0, 0 nuevo desplazamiento  
  
- desplazamiento anterior 5, 10 nuevo desplazamiento  
  
- desplazamiento anterior 9, 20 nuevo desplazamiento  
  
 Resultados:  
  
- Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignará a un nuevo desplazamiento de 0.  
  
- Un desplazamiento anterior de 5, 6, 7 u 8 se asignará al nuevo desplazamiento de 10.  
  
- Un desplazamiento anterior de 9 o versiones posteriores se asignará al nuevo desplazamiento de 20.  
  
- Se asignará un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al anterior desplazamiento de 0.  
  
- Un nuevo desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 se asignará al anterior desplazamiento 5.  
  
- Se asignará un nuevo desplazamiento de 20 o superior al desplazamiento anterior de 9.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
