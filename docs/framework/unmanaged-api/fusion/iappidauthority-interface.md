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
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206660"
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority (Interfaz)
Proporciona métodos que generan y comparan las identidades de aplicaciones y las referencias de claves.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Obtiene un valor que indica si los dos especifica [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instancias son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::AreReferencesEqual`|Obtiene un valor que indica si los dos especifica [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instancias son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Obtiene un valor que indica si las dos definiciones de la cadena especificada son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Obtiene un valor que indica si las dos referencias de cadena especificada son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::CreateDefinition`|Obtiene un puntero de interfaz a una recién generado `IDefinitionAppId` instancia que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::CreateReference`|Obtiene un puntero de interfaz en otra recién creada `IReferenceAppId` que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::DefinitionToText`|Obtiene una versión de cadena del elemento especificado `IDefinitionAppId`, utilizando los valores de marcador especificado.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Obtiene un valor que indica si el texto especificado `IDefinitionAppId` y `IReferenceAppId` representan el mismo ensamblado.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Obtiene un valor que indica si la cadena de referencia y la cadena de definición especificado representan el mismo ensamblado.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Obtiene una clave de cadena que representa el parámetro `IDefinitionAppId` instancia.|  
|`IAppIdAuthority::GenerateReferenceKey`|Obtiene una clave de cadena que representa el parámetro `IReferenceAppId` instancia.|  
|`IAppIdAuthority::HashDefinition`|Obtiene una clave hash para el elemento especificado `IDefinitionAppId` instancia.|  
|`IAppIdAuthority::HashReference`|Obtiene una clave hash para el elemento especificado `IReferenceAppId` instancia.|  
|`IAppIdAuthority::ReferenceToText`|Obtiene una versión de cadena del elemento especificado `IReferenceAppId`, utilizando los valores de marcador especificado.|  
|`IAppIdAuthority::TextToDefinition`|Obtiene un puntero de interfaz a un `IDefinitionAppId` instancia que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
|`IAppIdAuthority::TextToReference`|Obtiene un puntero de interfaz a un `IReferenceAppId` instancia que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
