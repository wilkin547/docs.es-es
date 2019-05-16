---
title: Get (función) (referencia de API no administrada)
description: La función Get recupera el valor de propiedad especificado.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8a1942f903b1c7c15e58077e35b6a72a86a9419
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636524"
---
# <a name="get-function"></a>Función Get

Recupera el valor de propiedad especificado si existe.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```

## <a name="parameters"></a>Parámetros

`vFunc`\
[in] Este parámetro se usa.

`ptr`\
[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.

`wszName`\
[in] El nombre de la propiedad.

`lFlags`\
[in] Reservado. Este parámetro debe ser 0.

`pVal`\
[out] Si la función devuelve correctamente, contiene el valor de la `wszName` propiedad. El `pval` argumento se asigna el tipo correcto y el valor del calificador.

`pvtType`\
[out] Si la función devuelve correctamente, contiene un [constante de tipo de CIM](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) que indica el tipo de propiedad. Su valor puede ser también `null`. 

`plFlavor`\
[out] Si la función devuelve correctamente, recibe información acerca del origen de la propiedad. Su valor puede ser `null`, o una de las siguientes constantes WBEM_FLAVOR_TYPE definidas en el *WbemCli.h* archivo de encabezado: 

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La propiedad es una propiedad estándar del sistema. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Para una clase: La propiedad se hereda de la clase primaria. <br> Para una instancia: La propiedad, mientras se hereda de la clase primaria, no se ha modificado por la instancia.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Para una clase: La propiedad pertenece a la clase derivada. <br> Para una instancia: Se modifica la propiedad por la instancia; es decir, se proporcionó un valor o un calificador se ha agregado o modificado. |

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Ha habido un error general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró la propiedad especificada. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | No hay suficiente memoria disponible para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |

## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) método.

El `Get` función también puede devolver las propiedades del sistema.

El `pVal` argumento se asigna el tipo correcto y el valor para el calificador y el COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) (función)

## <a name="requirements"></a>Requisitos

 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Encabezado**: WMINet_Utils.idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
