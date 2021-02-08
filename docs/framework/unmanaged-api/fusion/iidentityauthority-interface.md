---
description: 'Más información acerca de: interfaz Iidentityauthority ('
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
ms.openlocfilehash: 3064a3d95ebe9a098a7cac0766f18654c6fab8b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800143"
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
|`IIdentityAuthority::CreateDefinition`|Obtiene un puntero a una nueva `IDefinitionIdentity` instancia de que representa el objeto de código en el ámbito actual.|
|`IIdentityAuthority::CreateReference`|Obtiene un puntero a una nueva `IReferenceIdentity` instancia de que representa el objeto de código en el ámbito actual.|
|`IIdentityAuthority::DefinitionToText`|Obtiene una versión de cadena con formato del especificado `IDefinitionIdentity` .|
|`IIdentityAuthority::DefinitionToTextBuffer`|Rellena el búfer de caracteres anchos especificado con una versión de cadena del especificado `IDefinitionIdentity` .|
|`IIdentityAuthority::DoesDefinitionMatchReference`|Obtiene un valor que indica si las `IDefinitionIdentity` instancias y especificadas `IReferenceIdentity` hacen referencia al mismo objeto de código.|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.|
|`IIdentityAuthority::GenerateDefinitionKey`|Obtiene un puntero a una clave de cadena recién creada para el especificado `IDefinitionIdentity` .|
|`IIdentityAuthority::GenerateReferenceKey`|Obtiene un puntero a una clave de cadena recién creada para el especificado `IReferenceIdentity` .|
|`IIdentityAuthority::HashDefinition`|Obtiene un valor hash para el especificado `IDefinitionIdentity` .|
|`IIdentityAuthority::HashReference`|Obtiene un valor hash para el especificado `IReferenceIdentity` .|
|`IIdentityAuthority::ReferenceToText`|Obtiene una versión de cadena con formato del especificado `IReferenceIdentity` .|
|`IIdentityAuthority::ReferenceToTextBuffer`|Rellena el búfer de caracteres anchos especificado con una versión de cadena del especificado `IReferenceIdentity` .|
|`IIdentityAuthority::TextToDefinition`|Obtiene un puntero de interfaz a una `IDefinitionIdentity` instancia de generada a partir de la cadena con formato especificada.|
|`IIdentityAuthority::TextToReference`|Obtiene un puntero de interfaz a una `IReferenceIdentity` instancia de generada a partir de la cadena con formato especificada.|

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** Isolation. h

**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
