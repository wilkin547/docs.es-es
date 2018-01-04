---
title: Interfaces de Fusion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9226eba1b9f03138180430b2abb960f43f4b4260
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="fusion-interfaces"></a>Interfaces de Fusion
Esta sección describen las interfaces no administradas que utiliza la API de fusión para tener acceso a las propiedades de recursos de la aplicación y a encontrar las versiones correctas de estos recursos para la aplicación.  
  
## <a name="in-this-section"></a>En esta sección  
 [IAppIdAuthority (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 Proporciona métodos que generan y comparan las identidades de la aplicación y referencias de claves.  
  
 [IAssemblyCache (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 Proporciona una representación de la caché global de ensamblados.  
  
 [IAssemblyCacheItem (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 Representa un único ensamblado en la caché global de ensamblados.  
  
 [IAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 Representa un enumerador para una matriz de `IAssemblyName` objetos.  
  
 [IAssemblyName (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 Proporciona métodos para describir y trabajar con la identidad única de un ensamblado.  
  
 [IDefinitionAppId (interfaz)](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 Representa un identificador único para el código que define la aplicación en el ámbito actual.  
  
 [IDefinitionIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 Representa la firma única del código que define la aplicación en el ámbito actual.  
  
 [IEnumDefinitionIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 Actúa como el enumerador para una colección de `IDefinitionIdentity` objetos.  
  
 [IEnumIDENTITY_ATTRIBUTE (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.  
  
 [IEnumReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 Actúa como un enumerador para una colección de `IReferenceIdentity` objetos.  
  
 [IIdentityAuthority (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 Administra las claves de identidad para los objetos de código.  
  
 [IInstallReferenceEnum (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 Representa un enumerador para los ensamblados instalados en la caché global de ensamblados.  
  
 [IInstallReferenceItem (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 Representa un elemento instalado en la caché global de ensamblados.  
  
 [IReferenceAppId (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 Representa una referencia al identificador único para la aplicación en el ámbito actual.  
  
 [IReferenceIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 Representa una referencia a la firma única de un objeto de código.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [Enumeraciones de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [Estructuras de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
