---
title: Función CompareTo (referencia de API no administrada)
description: La función CompareTo compara un objeto con otro objeto WMI.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compareto-function"></a>CompareTo (función)
Compara un objeto con otro objeto de administración de Windows.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.

`flags`  
[in] Una combinación bit a bit de los marcadores que especifican las características de objeto deben tener en cuenta para la comparación. Consulte la [comentarios](#remarks) sección para obtener más información.

`pCompareTo`  

[in] El objeto para la comparación. `pcompareTo` debe ser un tipo válido [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia; no puede ser `null`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda llamada a `BeginEnumeration` se realizó sin una llamada intermedia a [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Los objetos son diferentes. |
| `WBEM_S_SAME` | 0 | Los objetos son iguales en función de las marcas de comparación. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) método.

Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código. Puede especificar las características individuales implicado en la comparación mediante la especificación de una combinación bit a bit de los siguientes indicadores:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Pasar por alto el origen (el servidor y el espacio de nombres que proceden). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Pasar por alto todos los calificadores (incluidos **clave** y **dinámica**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Omitir los valores predeterminados de propiedades. Esta marca solo se aplica a la comparación de las clases. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0 x 20 | Omitir los modos del calificador. Aún así, esta marca tiene calificadores en cuenta, pero omite las distinciones como las reglas de propagación y reemplaza las restricciones. |
| `WBEM_FLAG_IGNORE_CASE` | 0 x 10 | Omitir mayúsculas y minúsculas en la comparación de valores de cadena. Esto se aplica tanto a las cadenas y valores de calificador. La comparación de nombres de propiedad y el calificador de no distingue entre mayúsculas y minúsculas, independientemente de si se establece esta marca. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Se supone que los objetos que se comparan son instancias de la misma clase. Por lo tanto, esta marca compara sólo información relacionada con la instancia. Utilice este marcas para optimizar el rendimiento. Si los objetos no son de la misma clase, los resultados son indefinidos. |

O bien, puede especificar una marca compuesta única como se indica a continuación:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Tenga en cuenta todas las características de la comparación. |

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
