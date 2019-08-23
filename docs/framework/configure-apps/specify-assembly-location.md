---
title: Especificar la ubicación de un ensamblado
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 43cd1d0edbb607f69f27661aae3372e93564b3b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932336"
---
# <a name="specifying-an-assemblys-location"></a>Especificar la ubicación de un ensamblado
Hay dos maneras de especificar la ubicación de un ensamblado:  
  
- Usar el elemento de [ \<>](./file-schema/runtime/codebase-element.md) codebase.  
  
- Usar el elemento de [ \<>](./file-schema/runtime/probing-element.md) de sondeo.  
  
 También puede usar la [herramienta de configuración de .NET Framework (Mscorcfg. msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) para especificar ubicaciones de ensamblados o especificar ubicaciones para la Common Language Runtime para sondear ensamblados.  
  
## <a name="using-the-codebase-element"></a>Usar el \<elemento codebase >  
 Solo puede utilizar el  **\<** elemento codebase > en archivos de configuración de la máquina o de directiva de edición que también redirijan la versión del ensamblado. Cuando el tiempo de ejecución determina la versión de ensamblado que se va a usar, aplica la configuración de base de código del archivo que determina la versión. Si no se indica ninguna base de código, el tiempo de ejecución sondea el ensamblado de la manera normal. Para obtener más información, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
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
  
 El atributo **version** es necesario para todos los ensamblados con nombre seguro, pero debe omitirse para los ensamblados que no tengan un nombre seguro. **El\<** elemento codebase > requiere el atributo **href** . No se pueden especificar intervalos de versiones  **\<** en el elemento codebase >.  
  
> [!NOTE]
> Si va a proporcionar una sugerencia base de código para un ensamblado que no tiene un nombre seguro, la sugerencia debe apuntar a la base de la aplicación o a un subdirectorio del directorio base de la aplicación.  
  
## <a name="using-the-probing-element"></a>Usar el \<elemento de > de sondeo  
 El motor en tiempo de ejecución ubica los ensamblados que no tienen una base de código mediante sondeo. Para obtener más información sobre el sondeo, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Puede usar el [ \<](./file-schema/runtime/probing-element.md) elemento de > de sondeo del archivo de configuración de la aplicación para especificar subdirectorios en los que el tiempo de ejecución debe buscar al localizar un ensamblado. En el ejemplo siguiente se muestra cómo especificar los directorios en los que debe buscar el tiempo de ejecución.  
  
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

- [Ensamblados en Common Language Runtime](../app-domains/assemblies-in-the-common-language-runtime.md)
- [Programar con ensamblados](../app-domains/programming-with-assemblies.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Configuración de aplicaciones mediante archivos de configuración](index.md)
