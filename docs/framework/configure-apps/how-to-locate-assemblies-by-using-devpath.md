---
title: Procedimiento para buscar ensamblados mediante DEVPATH
description: Compruebe que un ensamblado compartido funciona correctamente con muchas aplicaciones en .NET mediante el uso de un archivo de configuración de equipo XML y la variable de entorno DEVPATH.
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 8ae807e46b11d2adb06d6af0c86e1c7297caa0c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161989"
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Procedimiento para buscar ensamblados mediante DEVPATH

Los desarrolladores pueden querer asegurarse de que un ensamblado compartido que se está compilando funciona correctamente con varias aplicaciones. En lugar de colocar continuamente el ensamblado en la caché global de ensamblados durante el ciclo de desarrollo, el desarrollador puede crear una variable de entorno DEVPATH que apunte al directorio de resultados de la compilación para el ensamblado.  
  
 Por ejemplo, suponga que está creando un ensamblado compartido denominado MySharedAssembly y que el directorio de salida es C:\MySharedAssembly\Debug. Puede colocar C:\MySharedAssembly\Debug en la variable DEVPATH. A continuación, debe especificar el [\<developmentMode>](./file-schema/runtime/developmentmode-element.md) elemento en el archivo de configuración del equipo. Este elemento indica al Common Language Runtime que utilice DEVPATH para buscar ensamblados.  
  
 El tiempo de ejecución debe poder detectar el ensamblado compartido.  Para especificar un directorio privado para resolver las referencias de ensamblado, use el [ \<codeBase> elemento](./file-schema/runtime/codebase-element.md) o [ \<probing> elemento](./file-schema/runtime/probing-element.md) en un archivo de configuración, tal y como se describe en [especificar la ubicación de un ensamblado](specify-assembly-location.md).  También puede colocar el ensamblado en un subdirectorio del directorio de la aplicación. Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
> [!NOTE]
> Se trata de una característica avanzada, diseñada solo para el desarrollo.  
  
 En el ejemplo siguiente se muestra cómo hacer que el tiempo de ejecución busque ensamblados en los directorios especificados por la variable de entorno DEVPATH.  
  
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
> Use esta configuración solo en tiempo de desarrollo. El motor en tiempo de ejecución no comprueba las versiones de los ensamblados con nombre seguro que se encuentran en la DEVPATH. Simplemente usa el primer ensamblado que encuentra.  
  
## <a name="see-also"></a>Consulte también

- [Configurar aplicaciones con archivos de configuración](index.md)
