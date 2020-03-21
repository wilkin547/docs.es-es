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
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178292"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult (Enumeración)
Indica la equivalencia de dos identidades de ensamblado, según lo determinado por el [CompareAssemblyIdentity](compareassemblyidentity-function.md) función.  
  
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
|`ACR_EquivalentFXUnified`|Indica que los ensamblados se consideran equivalentes en función de la unificación de la versión de Common Language Runtime (CLR) de los números de versión del ensamblado en la versión 2.0 de .NET Framework.|  
|`ACR_EquivalentPartialFXUnified`|Indica una coincidencia parcial de los ensamblados en función de la unificación de CLR de los números de versión del ensamblado en .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Indica una coincidencia parcial de los ensamblados.|  
|`ACR_EquivalentPartialUnified`|Indica una coincidencia parcial de los ensamblados basada en la unificación heredada de los números de versión.|  
|`ACR_EquivalentPartialWeakNamed`|Indica una coincidencia parcial de ensamblados con nombre simple.|  
|`ACR_EquivalentUnified`|Indica que los ensamblados se consideran equivalentes en función de la unificación de CLR de números de versión en versiones heredadas de .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Indica una coincidencia entre dos ensamblados con nombre simple cuyos números de versión se omitieron.|  
|`ACR_NonEquivalent`|Indica que no se ha producido ninguna coincidencia entre los dos ensamblados.|  
|`ACR_NonEquivalentPartialVersion`|Indica que los dos ensamblados coinciden excepto por sus números de versión, que coinciden solo parcialmente.|  
|`ACR_NonEquivalentVersion`|Indica que los dos ensamblados coinciden excepto por sus números de versión, que no coinciden.|  
|`ACR_Unknown`|Indica que no se conoce el motivo de la no equivalencia.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [CompareAssemblyIdentity (Función)](compareassemblyidentity-function.md)
- [Enumeraciones de fusión](fusion-enumerations.md)
