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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab8965ca5d6c9c96cea5f5b351547ce2d4dfacc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546285"
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority (Interfaz)
Administra las claves de identidad para los objetos de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|Obtiene un valor que indica si los dos especifica [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instancias son iguales.|  
|`IIdentityAuthority::AreReferencesEqual`|Obtiene un valor que indica si los dos especifica [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instancias son iguales.|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Obtiene un valor que indica si las dos representaciones de identidad de definición de cadena especificada son iguales.|  
|`IIdentityAuthority::AreTextualReferencesEqual`|Obtiene un valor que indica si las dos representaciones de identidad de referencia de la cadena especificada son iguales.|  
|`IIdentityAuthority::CreateDefinition`|Obtiene un puntero a un nuevo `IDefinitionIdentity` instancia que representa el objeto de código en el ámbito actual.|  
|`IIdentityAuthority::CreateReference`|Obtiene un puntero a un nuevo `IReferenceIdentity` instancia que representa el objeto de código en el ámbito actual.|  
|`IIdentityAuthority::DefinitionToText`|Obtiene una versión de cadena con formato del elemento especificado `IDefinitionIdentity`.|  
|`IIdentityAuthority::DefinitionToTextBuffer`|Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IDefinitionIdentity`.|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|Obtiene un valor que indica si el texto especificado `IDefinitionIdentity` y `IReferenceIdentity` instancias hacen referencia al mismo objeto de código.|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Obtiene un valor que indica si las cadenas especificadas hacen referencia al mismo objeto de código.|  
|`IIdentityAuthority::GenerateDefinitionKey`|Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IDefinitionIdentity`.|  
|`IIdentityAuthority::GenerateReferenceKey`|Obtiene un puntero a una clave de cadena recién creada para el elemento especificado `IReferenceIdentity`.|  
|`IIdentityAuthority::HashDefinition`|Obtiene un valor hash para el elemento especificado `IDefinitionIdentity`.|  
|`IIdentityAuthority::HashReference`|Obtiene un valor hash para el elemento especificado `IreferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToText`|Obtiene una versión de cadena con formato del elemento especificado `IReferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToTextBuffer`|Llena el búfer de carácter ancho especificado con una versión de cadena del elemento especificado `IReferenceIdentity`.|  
|`IIdentityAuthority::TextToDefinition`|Obtiene un puntero de interfaz a un `IDefinitionIdentity` cadena con formato de instancia generado a partir de la especificada.|  
|`IIdentityAuthority::TextToReference`|Obtiene un puntero de interfaz a un `IReferenceIdentity` cadena con formato de instancia generado a partir de la especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
