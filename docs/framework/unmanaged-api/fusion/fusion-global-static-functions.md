---
title: "Funciones estáticas globales de la fusión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged global static functions [.NET Framework], fusion
- fusion global static functions [.NET Framework]
- global static functions [.NET Framework fusion]
ms.assetid: 229b2188-9168-4b44-a987-e1f515494688
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38462833e3b0ccd56265b02d9a1bc9f37ac12f5f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="fusion-global-static-functions"></a>Funciones estáticas globales de la fusión
Esta sección describen las funciones estáticas globales no administradas que utiliza la API de fusión.  
  
## <a name="in-this-section"></a>En esta sección  
 [ClearDownloadCache (función)](../../../../docs/framework/unmanaged-api/fusion/cleardownloadcache-function.md)  
 Borra la caché global de ensamblados de los ensamblados descargados.  
  
 [CompareAssemblyIdentity (función)](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 Compara dos identidades de ensamblado para determinar si son equivalentes.  
  
 [CreateApplicationContext (función)](../../../../docs/framework/unmanaged-api/fusion/createapplicationcontext-function.md)  
 Solo para uso interno. (Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código).  
  
 [CreateAssemblyCache (función)](../../../../docs/framework/unmanaged-api/fusion/createassemblycache-function.md)  
 Obtiene un puntero a una nueva [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instancia que representa la caché global de ensamblados.  
  
 [CreateAssemblyEnum (función)](../../../../docs/framework/unmanaged-api/fusion/createassemblyenum-function.md)  
 Obtiene un puntero a un [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instancia que representa una lista de objetos que existen en el ensamblado especificado.  
  
 [CreateAssemblyNameObject (función)](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 Obtiene un puntero a un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instancia que representa la identidad única del ensamblado con el nombre especificado.  
  
 [CreateHistoryReader (función)](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 Crea un lector de historial para el archivo especificado.  
  
 [CreateInstallReferenceEnum (función)](../../../../docs/framework/unmanaged-api/fusion/createinstallreferenceenum-function.md)  
 Obtiene un puntero a un [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instancia que representa una lista de referencias de una aplicación para el ensamblado especificado.  
  
 [GetAppIdAuthority (función)](../../../../docs/framework/unmanaged-api/fusion/getappidauthority-function.md)  
 Obtiene un puntero a un [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instancia que administra las claves para las identidades de la aplicación y referencias.  
  
 [GetAssemblyIdentityFromFile (función)](../../../../docs/framework/unmanaged-api/fusion/getassemblyidentityfromfile-function.md)  
 Obtiene un puntero a un `IUnknown` objeto con los valores especificados `IID` en el ensamblado en la ruta de acceso de archivo especificado.  
  
 [GetCachePath (función)](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 Obtiene la ruta de acceso al ensamblado almacenado en caché, con las marcas especificadas.  
  
 [GetHistoryFileDirectory (función)](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 Recupera la ruta de acceso del directorio de historial de la aplicación.  
  
 [GetIdentityAuthority (función)](../../../../docs/framework/unmanaged-api/fusion/getidentityauthority-function.md)  
 Obtiene un puntero a un [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instancia que administra las claves para los objetos de código.  
  
 [IsFrameworkAssembly (función)](../../../../docs/framework/unmanaged-api/fusion/isframeworkassembly-function.md)  
 Obtiene un valor que indica si el ensamblado especificado es administrado.  
  
 [NukeDownloadedCache (función)](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 Elimina la caché de descarga de common language runtime.  
  
 [PreBindAssemblyEx (función)](../../../../docs/framework/unmanaged-api/fusion/prebindassemblyex-function.md)  
 Obtiene el nombre para mostrar tras aplicar la directiva de un ensamblado.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
  
 [Enumeraciones de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [Estructuras de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
  
 [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
