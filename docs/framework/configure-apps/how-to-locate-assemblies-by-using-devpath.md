---
title: Procedimiento Buscar ensamblados mediante DEVPATH
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 0d238ceb4f96905031cb4a30f50727050381277e
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084502"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Procedimiento Buscar ensamblados mediante DEVPATH
Pueden que los desarrolladores desean asegurarse de que un ensamblado compartido que están creando funciona correctamente con varias aplicaciones. En lugar de poner constantemente el ensamblado en la caché global de ensamblados durante el ciclo de desarrollo, el desarrollador puede crear una variable de entorno DEVPATH que apunta al directorio de resultados de compilación para el ensamblado.  
  
 Por ejemplo, suponga que está creando un ensamblado compartido denominado MySharedAssembly y el directorio de salida es C:\MySharedAssembly\Debug. Puede poner C:\MySharedAssembly\Debug en la variable DEVPATH. A continuación, debe especificar el [ \<developmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) elemento en el archivo de configuración del equipo. Este elemento indica a common language runtime que utilice DEVPATH para buscar ensamblados.  
  
 El ensamblado compartido debe ser reconocible para el tiempo de ejecución.  Para especificar un directorio para resolver el uso de referencias de ensamblado privado el [ \<codeBase > elemento](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) o [ \<probing > elemento](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) en un archivo de configuración, como se describe en [Especificar la ubicación del ensamblado](../../../docs/framework/configure-apps/specify-assembly-location.md).  También puede colocar el ensamblado en un subdirectorio del directorio de la aplicación. Para más información, consulte [Cómo ubica ensamblados el tiempo de ejecución](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
>  Esto es una característica avanzada, dirigida al desarrollo de.  
  
 El ejemplo siguiente muestra cómo hacer que el runtime busca ensamblados en los directorios especificados por la variable de entorno DEVPATH.  
  
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
>  Use esta opción solo en tiempo de desarrollo. El tiempo de ejecución no comprueba las versiones de ensamblados con nombre seguro que se encuentra en la variable DEVPATH. Simplemente usa el primer ensamblado que encuentra.  
  
## <a name="see-also"></a>Vea también
- [Configurar aplicaciones de .NET Framework](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
