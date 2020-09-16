---
title: Especificar la ubicación de un ensamblado
description: Vea cómo especificar la ubicación de un ensamblado en .NET mediante el elemento codebase o el elemento de sondeo en un archivo de configuración XML.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 3b24ff99eee9027d507ef89ca855162f221f826a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555125"
---
# <a name="specifying-an-assemblys-location"></a>Especificar la ubicación de un ensamblado
Hay dos maneras de especificar la ubicación de un ensamblado:  
  
- Usar el [\<codeBase>](./file-schema/runtime/codebase-element.md) elemento.  
  
- Usar el [\<probing>](./file-schema/runtime/probing-element.md) elemento.  
  
 También puede usar la [herramienta de configuración de .NET Framework (Mscorcfg. msc)](/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) para especificar ubicaciones de ensamblados o especificar ubicaciones para la Common Language Runtime para sondear ensamblados.  
  
## <a name="using-the-codebase-element"></a>Usar el \<codeBase> elemento  
 Puede usar el **\<codeBase>** elemento solo en los archivos de configuración del equipo o de directiva de edición que también redirigen la versión del ensamblado. Cuando el tiempo de ejecución determina la versión de ensamblado que se va a usar, aplica la configuración de base de código del archivo que determina la versión. Si no se indica ninguna base de código, el tiempo de ejecución sondea el ensamblado de la manera normal. Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
 En el ejemplo siguiente se muestra cómo especificar la ubicación de un ensamblado.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 El atributo **version** es necesario para todos los ensamblados con nombre seguro, pero debe omitirse para los ensamblados que no tengan un nombre seguro. El **\<codeBase>** elemento requiere el atributo **href** . No se pueden especificar intervalos de versiones en el **\<codeBase>** elemento.  
  
> [!NOTE]
> Si va a proporcionar una sugerencia base de código para un ensamblado que no tiene un nombre seguro, la sugerencia debe apuntar a la base de la aplicación o a un subdirectorio del directorio base de la aplicación.  
  
## <a name="using-the-probing-element"></a>Usar el \<probing> elemento  
 El motor en tiempo de ejecución ubica los ensamblados que no tienen una base de código mediante sondeo. Para obtener más información sobre el sondeo, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Puede usar el [\<probing>](./file-schema/runtime/probing-element.md) elemento en el archivo de configuración de la aplicación para especificar subdirectorios en los que el tiempo de ejecución debe buscar al localizar un ensamblado. En el ejemplo siguiente se muestra cómo especificar los directorios en los que debe buscar el tiempo de ejecución.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 El atributo **privatePath** contiene los directorios en los que el tiempo de ejecución debe buscar los ensamblados. Si la aplicación se encuentra en C:\Archivos de Programa\myapp, el tiempo de ejecución buscará los ensamblados que no especifiquen una base de código en C:\Archivos de Files\MyApp\Bin, C:\Archivos de Files\MyApp\Bin2\Subbin y C:\Program Files\MyApp\Bin3. Los directorios especificados en **privatePath** deben ser subdirectorios del directorio base de la aplicación.  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../standard/assembly/index.md)
- [Programar con ensamblados](../../standard/assembly/index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurar aplicaciones con archivos de configuración](index.md)
