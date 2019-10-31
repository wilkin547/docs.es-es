---
title: IIdentityAuthority (Interfaz)
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
ms.openlocfilehash: 3e2d2335e37ced9139ea44092f10b19566894681
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127090"
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority (Interfaz)

Administra claves de identidad para objetos de código.

## <a name="methods"></a>Métodos

|Método|Descripción|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|Obtiene un valor que indica si las dos instancias de [IDefinitionIdentity](idefinitionidentity-interface.md) especificadas son iguales.|
|`IIdentityAuthority::AreReferencesEqual`|Obtiene un valor que indica si las dos instancias de [IReferenceIdentity](ireferenceidentity-interface.md) especificadas son iguales.|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Obtiene un valor que indica si las dos representaciones de identidad de definición de cadena especificadas son iguales.|
|`IIdentityAuthority::AreTextualReferencesEqual`|Obtiene un valor que indica si las dos representaciones de identidad de referencia de cadena especificadas son iguales.|
|`IIdentityAuthority::CreateDefinition`|Obtiene un puntero a una nueva instancia de `IDefinitionIdentity` que representa el objeto de código en el ámbito actual.|
|`IIdentityAuthority::CreateReference`|Obtiene un puntero a una nueva instancia de `IReferenceIdentity` que representa el objeto de código en el ámbito actual.|
|`IIdentityAuthority::DefinitionToText`|Obtiene una versión de cadena con formato del `IDefinitionIdentity`especificado.|
|`IIdentityAuthority::DefinitionToTextBuffer`|Rellena el búfer de caracteres anchos especificado con una versión de cadena del `IDefinitionIdentity`especificado.|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Obtiene un valor que indica si las instancias de `IDefinitionIdentity` y `IReferenceIdentity` especificadas hacen referencia al mismo objeto de código.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.|
|`IIdentityAuthority::GenerateDefinitionKey`|Obtiene un puntero a una clave de cadena recién creada para el `IDefinitionIdentity`especificado.|
|`IIdentityAuthority::GenerateReferenceKey`|Obtiene un puntero a una clave de cadena recién creada para el `IReferenceIdentity`especificado.|
|`IIdentityAuthority::HashDefinition`|Obtiene un valor hash para el `IDefinitionIdentity`especificado.|
|`IIdentityAuthority::HashReference`|Obtiene un valor hash para el `IReferenceIdentity`especificado.|
|`IIdentityAuthority::ReferenceToText`|Obtiene una versión de cadena con formato del `IReferenceIdentity`especificado.|
|`IIdentityAuthority::ReferenceToTextBuffer`|Rellena el búfer de caracteres anchos especificado con una versión de cadena del `IReferenceIdentity`especificado.|
|`IIdentityAuthority::TextToDefinition`|Obtiene un puntero de interfaz a una instancia de `IDefinitionIdentity` generada a partir de la cadena con formato especificada.|
|`IIdentityAuthority::TextToReference`|Obtiene un puntero de interfaz a una instancia de `IReferenceIdentity` generada a partir de la cadena con formato especificada.|

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** Isolation. h

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
