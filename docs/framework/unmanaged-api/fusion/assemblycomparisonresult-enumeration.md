---
description: 'Más información sobre: enumeración Assemblycomparisonresult ('
title: AssemblyComparisonResult (Enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: 093cff830aa87d28ee86ecaeb6965887279a72d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761296"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult (Enumeración)

Indica la equivalencia de dos identidades de ensamblado, según lo determinado por la función [CompareAssemblyIdentity (](compareassemblyidentity-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>Members  
  
|Nombre del miembro|Descripción|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Indica que todos los campos de ensamblado de la comparación coinciden.|  
|`ACR_EquivalentFXUnified`|Indica que los ensamblados se consideran equivalentes según la unificación de la versión de Common Language Runtime (CLR) de los números de versión de ensamblado en la .NET Framework versión 2,0.|  
|`ACR_EquivalentPartialFXUnified`|Indica una coincidencia parcial de los ensamblados en función de la unificación CLR de los números de versión de ensamblado en el .NET Framework 2,0.|  
|`ACR_EquivalentPartialMatch`|Indica una coincidencia parcial de los ensamblados.|  
|`ACR_EquivalentPartialUnified`|Indica una coincidencia parcial de los ensamblados basándose en la unificación heredada de números de versión.|  
|`ACR_EquivalentPartialWeakNamed`|Indica una coincidencia parcial de ensamblados simplemente con nombre.|  
|`ACR_EquivalentUnified`|Indica que los ensamblados se consideran equivalentes en función de la unificación de CLR de los números de versión de las versiones heredadas del .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Indica una coincidencia entre dos ensamblados simplemente con nombre cuyos números de versión se omitieron.|  
|`ACR_NonEquivalent`|Indica que no se ha producido ninguna coincidencia entre los dos ensamblados.|  
|`ACR_NonEquivalentPartialVersion`|Indica que los dos ensamblados coinciden, excepto en el caso de sus números de versión, que solo coinciden parcialmente.|  
|`ACR_NonEquivalentVersion`|Indica que los dos ensamblados coinciden, excepto los números de versión, que no coinciden.|  
|`ACR_Unknown`|Indica que no se conoce el motivo de la no equivalencia.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [CompareAssemblyIdentity (Función)](compareassemblyidentity-function.md)
- [Enumeraciones de fusión](fusion-enumerations.md)
