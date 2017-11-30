---
title: IAppIdAuthority (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppIdAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IAppIdAuthority
helpviewer_keywords: IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07bfd26a43d264babc9854b0fd0da909dd329405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iappidauthority-interface"></a>IAppIdAuthority (Interfaz)
Proporciona métodos que generan y comparan las identidades de la aplicación y referencias de claves.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Obtiene un valor que indica si las dos especificadas [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instancias son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::AreReferencesEqual`|Obtiene un valor que indica si las dos especificadas [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instancias son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Obtiene un valor que indica si las dos definiciones de cadena especificadas son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Obtiene un valor que indica si las dos referencias de cadena especificadas son iguales. Puede pasar el valor de marcador IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION para pasar por alto la información de versión respectiva.|  
|`IAppIdAuthority::CreateDefinition`|Obtiene un puntero de interfaz a un recién generado `IDefinitionAppId` instancia que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::CreateReference`|Obtiene un puntero de interfaz en otra recién creada `IReferenceAppId` que representa el ensamblado en el ámbito actual.|  
|`IAppIdAuthority::DefinitionToText`|Obtiene una versión de cadena del elemento especificado `IDefinitionAppId`, utilizando los valores de indicador especificado.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Obtiene un valor que indica si el texto especificado `IDefinitionAppId` y `IReferenceAppId` representan el mismo ensamblado.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Obtiene un valor que indica si la cadena de referencia y la cadena de definición especificado representan el mismo ensamblado.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Obtiene una clave de cadena que representa el parámetro `IDefinitionAppId` instancia.|  
|`IAppIdAuthority::GenerateReferenceKey`|Obtiene una clave de cadena que representa el parámetro `IReferenceAppId` instancia.|  
|`IAppIdAuthority::HashDefinition`|Obtiene una clave hash para el elemento especificado `IDefinitionAppId` instancia.|  
|`IAppIdAuthority::HashReference`|Obtiene una clave hash para el elemento especificado `IReferenceAppId` instancia.|  
|`IAppIdAuthority::ReferenceToText`|Obtiene una versión de cadena del elemento especificado `IReferenceAppId`, utilizando los valores de indicador especificado.|  
|`IAppIdAuthority::TextToDefinition`|Obtiene un puntero de interfaz a un `IDefinitionAppId` instancia que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
|`IAppIdAuthority::TextToReference`|Obtiene un puntero de interfaz a un `IReferenceAppId` instancia que representa el ensamblado al que hace referencia la clave de cadena especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
