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
ms.openlocfilehash: 692ac4ef4fe8ea64c6a63dc2f02cc04244a842c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iidentityauthority-interface"></a>IIdentityAuthority (Interfaz)
Administra las claves de identidad para los objetos de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|Obtiene un valor que indica si las dos especificadas [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instancias son iguales.|  
|`IIdentityAuthority::AreReferencesEqual`|Obtiene un valor que indica si las dos especificadas [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instancias son iguales.|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Obtiene un valor que indica si las dos representaciones de identidad de definición de la cadena especificada son iguales.|  
|`IIdentityAuthority::AreTextualReferencesEqual`|Obtiene un valor que indica si las dos representaciones de identidad de referencia de la cadena especificada son iguales.|  
|`IIdentityAuthority::CreateDefinition`|Obtiene un puntero a una nueva `IDefinitionIdentity` instancia que representa el objeto de código en el ámbito actual.|  
|`IIdentityAuthority::CreateReference`|Obtiene un puntero a una nueva `IReferenceIdentity` instancia que representa el objeto de código en el ámbito actual.|  
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
|`IIdentityAuthority::TextToDefinition`|Obtiene un puntero de interfaz a un `IDefinitionIdentity` instancia generada a partir de lo especificado la cadena con formato.|  
|`IIdentityAuthority::TextToReference`|Obtiene un puntero de interfaz a un `IReferenceIdentity` instancia generada a partir de lo especificado la cadena con formato.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Isolation.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
