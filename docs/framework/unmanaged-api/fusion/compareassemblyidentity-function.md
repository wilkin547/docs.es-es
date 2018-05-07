---
title: CompareAssemblyIdentity (Función)
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b48adcb8e9de49a312af77c8a9b80a07455ebfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity (Función)
Compara dos identidades de ensamblado para determinar si son equivalentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzAssemblyIdentity1`  
 [in] Identidad textual del primer ensamblado de la comparación.  
  
 `fUnified1`  
 [in] Una marca booleana que indica la unificación especificada por el usuario para `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 [in] Identidad textual del segundo ensamblado de la comparación.  
  
 `fUnified2`  
 [in] Una marca booleana que indica la unificación especificada por el usuario para `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 [out] Una marca booleana que indica si los dos ensamblados son equivalentes.  
  
 `pResult`  
 [out] Un [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeración que contiene información detallada sobre la comparación.  
  
## <a name="return-value"></a>Valor devuelto  
 `pfEquivalent` Devuelve un valor booleano que indica si los dos ensamblados son equivalentes. `pResult` Devuelve uno de los `AssemblyComparisonResult` valores para dar el motivo más detallado para el valor de `pfEquivalent`.  
  
## <a name="remarks"></a>Comentarios  
 `CompareAssemblyIdentity` comprueba si `pwzAssemblyIdentity1` y `pwzAssemblyIdentity2` son equivalentes. `pfEquivalent` se establece en `true` en una o varias de las condiciones siguientes:  
  
-   Las dos identidades de ensamblado son equivalentes. Para los ensamblados con nombre seguro, la equivalencia requiere que el nombre del ensamblado, versión, token de clave pública y la referencia cultural para que sean idénticos. Para los ensamblados con nombres simples, equivalencia requiere a una coincidencia en el nombre del ensamblado y la referencia cultural.  
  
-   Ambas identidades de ensamblado hacen referencia a ensamblados que se ejecutan en .NET Framework. Esta condición devuelve `true` incluso si no coinciden los números de versión de ensamblado.  
  
-   Los dos ensamblados no son ensamblados administrados, pero `fUnified1` o `fUnified2` se estableció en `true`.  
  
 El `fUnified` marca indica que todos los números de versión hasta el número de versión del ensamblado con nombre seguro se consideran equivalentes al ensamblado con nombre seguro. Por ejemplo, si el valor de `pwzAssemblyIndentity1` es "MyAssembly, versión = 3.0.0.0, culture = neutral, publicKeyToken =..." y el valor de `fUnified1` es `true`, esto indica que todas las versiones de MyAssembly desde la versión 0.0.0.0 hasta la versión 3.0.0.0 deberían se tratan como equivalentes. En tal caso, si `pwzAssemblyIndentity2` hace referencia al mismo ensamblado como `pwzAssemblyIndentity1`, salvo que tenga un número de versión menor, `pfEquivalent` está establecido en `true`. Si `pwzAssemblyIdentity2` hace referencia a un número de versión mayor, `pfEquivalent` está establecido en `true` sólo si el valor de `fUnified2` es `true`.  
  
 El `pResult` parámetro incluye información específica sobre por qué los dos ensamblados se consideran equivalentes o no equivalentes. Para obtener más información, consulte [AssemblyComparisonResult (enumeración)](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [AssemblyComparisonResult (enumeración)](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
