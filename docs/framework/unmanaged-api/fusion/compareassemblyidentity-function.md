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
ms.openlocfilehash: b52d3af38bd09ce5864c25d27e148dbd7f4639b0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795445"
---
# <a name="compareassemblyidentity-function"></a>CompareAssemblyIdentity (Función)
Compara dos identidades de ensamblado para determinar si son equivalentes.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzAssemblyIdentity1`  
 de Identidad textual del primer ensamblado de la comparación.  
  
 `fUnified1`  
 de Una marca booleana que indica la unificación especificada por el `pwzAssemblyIdentity1`usuario para.  
  
 `pwzAssemblyIdentity2`  
 de La identidad textual del segundo ensamblado de la comparación.  
  
 `fUnified2`  
 de Una marca booleana que indica la unificación especificada por el `pwzAssemblyIdentity2`usuario para.  
  
 `pfEquivalent`  
 enuncia Una marca booleana que indica si los dos ensamblados son equivalentes.  
  
 `pResult`  
 enuncia Una enumeración [assemblycomparisonresult (](assemblycomparisonresult-enumeration.md) que contiene información detallada acerca de la comparación.  
  
## <a name="return-value"></a>Valor devuelto  
 `pfEquivalent`Devuelve un valor booleano que indica si los dos ensamblados son equivalentes. `pResult`devuelve uno de los `AssemblyComparisonResult` valores de, para proporcionar un motivo más detallado para el valor `pfEquivalent`de.  
  
## <a name="remarks"></a>Comentarios  
 `CompareAssemblyIdentity`comprueba si `pwzAssemblyIdentity1` y `pwzAssemblyIdentity2` son equivalentes. `pfEquivalent`está establecido `true` en una o varias de las condiciones siguientes:  
  
- Las dos identidades de ensamblado son equivalentes. En el caso de los ensamblados con nombre seguro, la equivalencia requiere que el nombre de ensamblado, la versión, el token de clave pública y la referencia cultural sean idénticos. En el caso de los ensamblados con nombre, la equivalencia requiere una coincidencia en el nombre y la referencia cultural del ensamblado.  
  
- Ambas identidades de ensamblado hacen referencia a ensamblados que se ejecutan en el .NET Framework. Esta condición devuelve `true` aunque los números de versión de ensamblado no coincidan.  
  
- Los dos ensamblados no son ensamblados administrados `fUnified2` , pero `fUnified1` o `true`se estableció en.  
  
 La `fUnified` marca indica que todos los números de versión hasta el número de versión del ensamblado con nombre seguro se consideran equivalentes al ensamblado con nombre seguro. Por ejemplo, si el valor de `pwzAssemblyIndentity1` es "myAssembly, version = 3.0.0.0, Culture = neutral, PublicKeyToken =...." y el valor de `fUnified1` es `true`, indica que todas las versiones de myAssembly de la versión 0.0.0.0 a 3.0.0.0 deben ser se trata como equivalente. En `pwzAssemblyIndentity2` tal caso, si hace referencia al mismo ensamblado que `pwzAssemblyIndentity1`, salvo que tiene un número de versión inferior, `pfEquivalent` se establece en. `true` Si `pwzAssemblyIdentity2` hace referencia a un número de versión `pfEquivalent` superior, se `true` establece en solo si el `fUnified2` valor `true`de es.  
  
 El `pResult` parámetro incluye información específica sobre por qué los dos ensamblados se consideran equivalentes o no equivalentes. Para obtener más información, vea [enumeración assemblycomparisonresult (](assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
- [AssemblyComparisonResult (enumeración)](assemblycomparisonresult-enumeration.md)
