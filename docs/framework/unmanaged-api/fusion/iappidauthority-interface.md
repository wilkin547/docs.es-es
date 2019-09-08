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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91ab2f71e7fb74f8e0e517b566d46d61c316ebe2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796839"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority (Interfaz)
Proporciona métodos que generan y comparan las claves de las identidades y referencias de la aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Obtiene un valor que indica si las dos instancias de [IDefinitionAppId](idefinitionappid-interface.md) especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::AreReferencesEqual`|Obtiene un valor que indica si las dos instancias de [IReferenceAppId](ireferenceappid-interface.md) especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Obtiene un valor que indica si las dos definiciones de cadena especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Obtiene un valor que indica si las dos referencias de cadena especificadas son iguales. Puede pasar el valor de marca IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para omitir la información de versión correspondiente.|  
|`IAppIdAuthority::CreateDefinition`|Obtiene un puntero de interfaz a una instancia `IDefinitionAppId` recién generada que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::CreateReference`|Obtiene un puntero de interfaz a un que `IReferenceAppId` se acaba de crear que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::DefinitionToText`|Obtiene una versión de cadena del especificado `IDefinitionAppId`, utilizando los valores de marca especificados.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Obtiene un valor que indica si el especificado `IDefinitionAppId` y `IReferenceAppId` representa el mismo ensamblado.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Obtiene un valor que indica si la cadena de definición especificada y la cadena de referencia representan el mismo ensamblado.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Obtiene una clave de cadena que representa la `IDefinitionAppId` instancia de especificada.|  
|`IAppIdAuthority::GenerateReferenceKey`|Obtiene una clave de cadena que representa la `IReferenceAppId` instancia de especificada.|  
|`IAppIdAuthority::HashDefinition`|Obtiene una clave hash para la instancia `IDefinitionAppId` de especificada.|  
|`IAppIdAuthority::HashReference`|Obtiene una clave hash para la instancia `IReferenceAppId` de especificada.|  
|`IAppIdAuthority::ReferenceToText`|Obtiene una versión de cadena del especificado `IReferenceAppId`, utilizando los valores de marca especificados.|  
|`IAppIdAuthority::TextToDefinition`|Obtiene un puntero de interfaz a `IDefinitionAppId` una instancia de que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
|`IAppIdAuthority::TextToReference`|Obtiene un puntero de interfaz a `IReferenceAppId` una instancia de que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
