---
title: COR_IL_MAP (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e2772833d75ced2209896ca37cf6cf37fb965f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corilmap-structure"></a>COR_IL_MAP (Estructura)
Especifica los cambios en el desplazamiento relativo de una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`oldOffset`|El antiguo lenguaje intermedio de Microsoft (MSIL) desplaza en relación con el principio de la función.|  
|`newOffset`|El desplazamiento MSIL nueva relativa al comienzo de la función.|  
|`fAccurate`|`true`Si la asignación se sabe que es preciso; en caso contrario, `false`.|  
  
## <a name="remarks"></a>Comentarios  
 El formato de la asignación es como sigue: el depurador supondrá que `oldOffset` hace referencia a un desplazamiento MSIL dentro del código MSIL original, sin modificar. El `newOffset` parámetro hace referencia al desplazamiento correspondiente de MSIL dentro del nuevo código instrumentado.  
  
 Para la ejecución paso a paso para que funcione correctamente, deben cumplirse los siguientes requisitos:  
  
-   La asignación se debe ordenar en orden ascendente.  
  
-   No se debe reordenar el código MSIL instrumentado.  
  
-   Código de MSIL original no se debe quitar.  
  
-   La asignación debería incluir las entradas para asignar todos los puntos de secuencia del archivo de programa (PDB) de la base de datos.  
  
 El mapa no interpola las entradas que faltan. En el ejemplo siguiente se muestra un mapa y sus resultados.  
  
 Asignar:  
  
-   0 desplazamiento anterior, 0 nuevo desplazamiento  
  
-   desplazamiento anterior 5, 10 desvío nueva  
  
-   desplazamiento anterior 9, 20 nuevo desplazamiento  
  
 Resultados:  
  
-   Un desplazamiento anterior de 0, 1, 2, 3 o 4 se asignarán a un nuevo desplazamiento de 0.  
  
-   Un desplazamiento anterior de 5, 6, 7 u 8 se asignarán al nuevo desplazamiento de 10.  
  
-   Un desplazamiento anterior de 9 o versiones posteriores se asignarán al nuevo desplazamiento de 20.  
  
-   Se asignará un nuevo desplazamiento de 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al anterior desplazamiento de 0.  
  
-   Un desplazamiento de 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 nuevos se asignarán al anterior desplazamiento de 5.  
  
-   Se asignará un nuevo desplazamiento de 20 o superior al anterior desplazamiento de 9.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
