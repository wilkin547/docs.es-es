---
title: Función CompareTo (referencia de API no administrada)
description: La función CompareTo compara un objeto a otro objeto WMI.
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
ms.openlocfilehash: fa46cf1fde4306af562248b4c12b048e3d8e2a51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717654"
---
# <a name="compareto-function"></a>CompareTo (función)
Compara un objeto de administración de Windows con otro.  

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
[in] Este parámetro se usa.

`ptr`  
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`flags`  
[in] Una combinación bit a bit de los marcadores que especifican las características de objeto deben tener en cuenta para la comparación. Consulte la [comentarios](#remarks) sección para obtener más información.

`pCompareTo`  

[in] El objeto para la comparación. `pcompareTo` debe ser válido [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia; no puede ser `null`.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Se ha producido un error no especificado. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parámetro no es válido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda llamada a `BeginEnumeration` se realizó sin una llamada intermedia a [ `EndEnumeration` ](endenumeration.md). |
| `WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
| `WBEM_S_DIFFERENT` | 0x40003 | Los objetos son diferentes. |
| `WBEM_S_SAME` | 0 | Los objetos son iguales según las marcas de comparación. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) método.

Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código. Puede especificar las características individuales implicadas en la comparación mediante la especificación de una combinación bit a bit de los siguientes indicadores:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | Omitir el origen (el servidor y el espacio de nombres que proceden). |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | Omitir todos los calificadores (incluidos **clave** y **dinámica**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | Pasar por alto los valores predeterminados de propiedades. Esta marca solo se aplica a la comparación de las clases. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | Omitir los tipos de calificador. Esta marca todavía tiene calificadores en cuenta, pero omite las distinciones de modos tales como las reglas de propagación y reemplazar las restricciones. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | Omitir mayúsculas y minúsculas al comparar los valores de cadena. Esto se aplica tanto a las cadenas y valores del calificador. La comparación de los nombres de propiedades y calificadores siempre distingue mayúsculas de minúsculas, independientemente de si se establece esta marca. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | Se supone que los objetos que se comparan son instancias de la misma clase. Por lo tanto, esta marca compara solo información relacionada con la instancia. Utilice este marcas para optimizar el rendimiento. Si los objetos no son de la misma clase, los resultados son indefinidos. |

O bien, puede especificar una única marca compuesta como sigue:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | Tenga en cuenta todas las características en la comparación. |

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también
- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
