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
ms.openlocfilehash: b0065b2cbbd17c5bb3dca6773951cdb8729e59fa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583566"
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
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`wszQualifierName`  
[in] Un puntero a una `LPCWSTR` que especifica un nombre de calificador que opera como parte de un filtro. Para obtener más información, consulte el [comentarios](#remarks) sección. Este parámetro puede ser `null`. 

`lFlags`  
[in] Una combinación de campos de bits. Para obtener más información, consulte el [comentarios](#remarks) sección.

`pQualifierValue`   
[in] Un puntero a una `VARIANT` estructura inicializada con un valor de filtro. Este parámetro puede ser `null`. 

`pstrNames`  
[out] Un `SAFEARRAY` estructura que contiene los nombres de propiedad. En la entrada, este parámetro siempre debe ser un puntero a `null`. Consulte la [comentarios](#remarks) sección para obtener más información. 

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Ha habido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos o se especificó una combinación de marcas y los parámetros incorrecta. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) método.

Con el nombre devuelto se controla mediante una combinación de marcas y los parámetros. Por ejemplo, la función puede devolver los nombres de todas las propiedades o solo los nombres de las propiedades de clave.  El filtro primario se especifica en el `lFlags` parámetro y los demás parámetros varían en función de lo.

Valores de la marca de `lFlags` son campos de bits


Las marcas que se pueden pasar como el `lEnumFlags` argumento son campos de bits que se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.  Puede combinar una marca de todos los grupos con cualquier marca de cualquier otro grupo. Sin embargo, las marcas del mismo grupo se excluyen mutuamente. 

| Marcas de grupo 1 |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | Devolver todos los nombres de propiedad. `strQualifierName` y `pQualifierVal` no se usan. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | Devolver solo las propiedades que tienen un calificador del nombre especificado por el `strQualifierName` parámetro. Si se usa esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  Devolver solo las propiedades que no tienen un calificador del nombre especificado por el `strQualifierName` parámetro. Si se usa esta marca, debe especificar `strQualifierName`. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | Devolver solo las propiedades que tienen un calificador del nombre especificado por el `wszQualifierName` parámetro y también tiene un valor idéntico al especificado por el `pQualifierVal` estructura. Si se usa esta marca, debe especificar tanto un `wszQualifierName` y un `pQualifierValue`. |

| Marcas de grupo 2 |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | Devolver solo los nombres de propiedades que definen las claves. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | Valor devuelto solo nombres de propiedad que son referencias a objetos. |

| Marcas de grupo 3 |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Devolver solo los nombres de propiedad que pertenecen a la clase más derivada. Excluir propiedades de las clases principales. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Devolver solo los nombres de propiedad que pertenecen a las clases principales. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | Devolver solo los nombres de las propiedades del sistema. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | Devolver solo los nombres de propiedades que no son de sistema. |

La función siempre asigna un nuevo `SAFEARRAY` si devuelve `WBEM_S_NO_ERROR`, y `pstrNames` siempre se establece para que apunte a él. La matriz devuelta puede tener 0 elementos si no hay propiedades coinciden con los filtros especificados. Si la función devuelve un valor distinto de `WBM_S_NO_ERROR`, un nuevo `SAFEARRAY` estructura no se devuelve.
 
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también
- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
