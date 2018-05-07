---
title: GetNames (función) (referencia de API no administrada)
description: La función de GetNames recupera los nombres de las propiedades de un objeto.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 108946428cdfadcfb9c653b7e444bf278dfa2782
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="getnames-function"></a>GetNames (función)
Recupera un subconjunto o todos los nombres de las propiedades de un objeto. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`wszQualifierName`  
[in] Un puntero a un válido `LPCWSTR` que especifica un nombre de calificador que funciona como parte de un filtro. Para obtener más información, consulte el [comentarios](#remarks) sección. Este parámetro puede ser `null`. 

`lFlags`  
[in] Una combinación de los campos de bits. Para obtener más información, consulte el [comentarios](#remarks) sección.

`pQualifierValue`   
[in] Un puntero a un válido `VARIANT` estructura inicializada con un valor de filtro. Este parámetro puede ser `null`. 

`pstrNames`  
[out] Un `SAFEARRAY` estructura que contiene los nombres de propiedad. En la entrada, este parámetro siempre debe ser un puntero a `null`. Consulte la [comentarios](#remarks) sección para obtener más información. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | Ha habido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Uno o más parámetros no son válidos o se especificó una combinación incorrecta de marcas y los parámetros. |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) método.

El nombre devuelto se controla mediante una combinación de marcas y los parámetros. Por ejemplo, la función puede devolver los nombres de todas las propiedades o solo los nombres de las propiedades de clave.  El filtro primario se especifica en el `lFlags` parámetro y los demás parámetros varían dependen de él.

Valores de la marca de `lFlags` son campos de bits


Las marcas que se pueden pasar como el `lEnumFlags` argumento son campos de bits que se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código.  Puede combinar una marca de todos los grupos con cualquier marca de ningún otro grupo. Sin embargo, las marcas del mismo grupo son mutuamente excluyentes. 

| Indicadores de grupo 1 |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Devolver todos los nombres de propiedad. `strQualifierName` y `pQualifierVal` están sin utilizar. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Devolver solo las propiedades que tienen un calificador del nombre especificado por el `strQualifierName` parámetro. Si se usa esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Devolver solo las propiedades que no tienen un calificador del nombre especificado por el `strQualifierName` parámetro. Si se usa esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Devolver solo las propiedades que tienen un calificador del nombre especificado por el `wszQualifierName` parámetro y también tienen un valor idéntico al especificado por el `pQualifierVal` estructura. Si se utiliza esta marca, debe especificar tanto una `wszQualifierName` y `pQualifierValue`. |

| Indicadores de grupo 2 |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Devolver solo los nombres de propiedades que definen las claves. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Valor devuelto solo nombres de propiedad que son referencias de objeto. |

| Indicadores de grupo 3 |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Devolver solo los nombres de propiedad que pertenecen a la clase más derivada. Excluir propiedades de las clases principales. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0 x 20 | Devolver solo los nombres de propiedad que pertenecen a las clases principales. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0 x 30 | Devolver solo los nombres de propiedades del sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Devolver solo los nombres de propiedades no son del sistema. |

La función siempre asigna un nuevo `SAFEARRAY` si devuelve `WBEM_S_NO_ERROR`, y `pstrNames` siempre se establece para que apunte a él. La matriz devuelta puede tener 0 elementos si no hay propiedades coinciden con los filtros especificados. Si la función devuelve un valor distinto de `WBM_S_NO_ERROR`, un nuevo `SAFEARRAY` estructura no se devuelve.
 
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
