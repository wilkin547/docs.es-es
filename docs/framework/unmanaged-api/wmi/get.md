---
title: Función Get (Referencia de API no administrada)
description: El Get función recupera el valor de propiedad especificado.
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
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174984"
---
# <a name="get-function"></a>Función Get

Recupera el valor de propiedad especificado si existe.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintaxis

```cpp
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
[en] Este parámetro no se utiliza.

`ptr`\
[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`\
[in] Nombre de la propiedad.

`lFlags`\
[in] Reservado. Este parámetro debe ser 0.

`pVal`\
[fuera] Si la función se devuelve correctamente, contiene el valor de la `wszName` propiedad. Al `pval` argumento se le asigna el tipo y el valor correctos para el calificador.

`pvtType`\
[fuera] Si la función se devuelve correctamente, contiene una [constante de tipo CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) que indica el tipo de propiedad. Su valor también `null`puede ser .

`plFlavor`\
[fuera] Si la función se devuelve correctamente, recibe información sobre el origen de la propiedad. Su valor `null`puede ser , o una de las siguientes constantes WBEM_FLAVOR_TYPE definidas en el archivo de encabezado *WbemCli.h:*

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La propiedad es una propiedad estándar del sistema. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Para una clase: la propiedad se hereda de la clase primaria. <br> Para una instancia: la instancia no ha modificado la propiedad, aunque heredada de la clase primaria.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Para una clase: la propiedad pertenece a la clase derivada. <br> Para una instancia: la instancia modifica la propiedad; es decir, se proporcionó un valor o se agregó o modificó un calificador. |

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:

|Constante  |Value  |Descripción  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Ha habido un fracaso general. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o más parámetros no son válidos. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró la propiedad especificada. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insuficiente para completar la operación. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función se realizó correctamente.  |

## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) método.

La `Get` función también puede devolver propiedades del sistema.

Al `pVal` argumento se le asigna el tipo y el valor correctos para el calificador y la función COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)

## <a name="requirements"></a>Requisitos

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

 **Encabezado:** WMINet_Utils.idl

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
