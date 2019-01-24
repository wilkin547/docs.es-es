---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b844a660da6a1e8d96ed7f5833435b413219e29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645631"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult (Enumeración)
Indica la equivalencia de dos identidades de ensamblado, según lo determinado por la [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
## <a name="members"></a>Miembros  
  
|Nombre de miembro|Descripción|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Indica que el ensamblado de todos los campos en la coincidencia de comparación.|  
|`ACR_EquivalentFXUnified`|Indica que los ensamblados se consideran equivalentes basándose en la unificación de versión (CLR) en tiempo de ejecución de lenguaje común de los números de versión de ensamblado en la versión 2.0 de .NET Framework.|  
|`ACR_EquivalentPartialFXUnified`|Indica a una coincidencia parcial de los ensamblados en función de la unificación de CLR de números de versión de ensamblado de .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Indica a una coincidencia parcial de los ensamblados.|  
|`ACR_EquivalentPartialUnified`|Indica a una coincidencia parcial de los ensamblados basada en la unificación heredada de números de versión.|  
|`ACR_EquivalentPartialWeakNamed`|Indica a una coincidencia parcial de ensamblados con nombres simples.|  
|`ACR_EquivalentUnified`|Indica que los ensamblados se consideran equivalentes basándose en la unificación de CLR de los números de versión de las versiones heredadas de .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Indica a una coincidencia entre dos ensamblados con nombres simples cuyos números de versión se han omitido.|  
|`ACR_NonEquivalent`|Indica que se produjo ninguna coincidencia entre los dos ensamblados.|  
|`ACR_NonEquivalentPartialVersion`|Indica que los dos ensamblados coinciden, aunque sus números de versión sólo coinciden parcialmente.|  
|`ACR_NonEquivalentVersion`|Indica que los dos ensamblados coinciden, aunque sus números de versión que no coinciden.|  
|`ACR_Unknown`|Indica que se desconoce la razón de no equivalencia.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [CompareAssemblyIdentity (Función)](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [Enumeraciones de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
