---
title: Procedimiento para buscar ensamblados mediante DEVPATH
ms.date: 03/30/2017
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
ms.openlocfilehash: 6fa864f814d6a9ce04f2bce92c61cd0075ab5145
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912997"
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
