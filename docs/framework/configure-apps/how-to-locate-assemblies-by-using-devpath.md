---
title: "Cómo: Buscar ensamblados mediante DEVPATH"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 70448f7ce4c00274dde14bace603e5c8852bf148
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Cómo: Buscar ensamblados mediante DEVPATH
Los desarrolladores conviene asegurarse de que un ensamblado compartido que están generando funciona correctamente con varias aplicaciones. En lugar de poner constantemente el ensamblado en la caché global de ensamblados durante el ciclo de desarrollo, el programador puede crear una variable de entorno DEVPATH que señala al directorio de salida de compilación para el ensamblado.  
  
 Por ejemplo, suponga que está creando un ensamblado compartido denominado MySharedAssembly y que el directorio de resultados es C:\MySharedAssembly\Debug. Se puede poner C:\MySharedAssembly\Debug en la variable DEVPATH. A continuación, debe especificar el [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento en el archivo de configuración del equipo. Este elemento indica a common language runtime que utilice DEVPATH al buscar ensamblados.  
  
 El ensamblado compartido debe ser reconocible por el tiempo de ejecución.  Para especificar un directorio para resolver el uso de referencias de ensamblado privado el [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) o [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) en un archivo de configuración, como se describe en [Especificar la ubicación de un ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).  También puede colocar el ensamblado en un subdirectorio del directorio de la aplicación. Para más información, consulte [Cómo ubica ensamblados el tiempo de ejecución](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Se trata de una característica avanzada, diseñada únicamente para su desarrollo.  
  
 En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución buscar ensamblados en los directorios especificados por la variable de entorno DEVPATH.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 El valor predeterminado es false.  
  
> [!NOTE]
>  Use esta opción solo en tiempo de desarrollo. El tiempo de ejecución no comprueba las versiones de ensamblados con nombre seguro que se encuentran en la variable DEVPATH. Simplemente utiliza el primer ensamblado que encuentre.  
  
## <a name="see-also"></a>Vea también  
 [Configurar aplicaciones de .NET Framework](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
