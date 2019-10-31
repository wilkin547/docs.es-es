---
title: IAppIdAuthority (Interfaz)
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127136"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority (Interfaz)
Proporciona métodos que generan y comparan las claves de las identidades y referencias de la aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Obtiene un valor que indica si las dos instancias de [IDefinitionAppId](idefinitionappid-interface.md) especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::AreReferencesEqual`|Obtiene un valor que indica si las dos instancias de [IReferenceAppId](ireferenceappid-interface.md) especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Obtiene un valor que indica si las dos definiciones de cadena especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Obtiene un valor que indica si las dos referencias de cadena especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::CreateDefinition`|Obtiene un puntero de interfaz a una instancia de `IDefinitionAppId` recién generada que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::CreateReference`|Obtiene un puntero de interfaz a un `IReferenceAppId` recién creado que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::DefinitionToText`|Obtiene una versión de cadena del `IDefinitionAppId`especificado, utilizando los valores de marca especificados.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Obtiene un valor que indica si el `IDefinitionAppId` y `IReferenceAppId` especificados representan el mismo ensamblado.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Obtiene un valor que indica si la cadena de definición especificada y la cadena de referencia representan el mismo ensamblado.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Obtiene una clave de cadena que representa la instancia de `IDefinitionAppId` especificada.|  
|`IAppIdAuthority::GenerateReferenceKey`|Obtiene una clave de cadena que representa la instancia de `IReferenceAppId` especificada.|  
|`IAppIdAuthority::HashDefinition`|Obtiene una clave hash para la instancia de `IDefinitionAppId` especificada.|  
|`IAppIdAuthority::HashReference`|Obtiene una clave hash para la instancia de `IReferenceAppId` especificada.|  
|`IAppIdAuthority::ReferenceToText`|Obtiene una versión de cadena del `IReferenceAppId`especificado, utilizando los valores de marca especificados.|  
|`IAppIdAuthority::TextToDefinition`|Obtiene un puntero de interfaz a una instancia de `IDefinitionAppId` que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
|`IAppIdAuthority::TextToReference`|Obtiene un puntero de interfaz a una instancia de `IReferenceAppId` que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
