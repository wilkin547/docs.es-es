---
title: Especificar la ubicación de un ensamblado
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646030"
---
# <a name="specifying-an-assemblys-location"></a>Especificar la ubicación de un ensamblado
Hay dos maneras de especificar la ubicación de un ensamblaje:  
  
- Mediante [ \<el elemento>codeBase.](./file-schema/runtime/codebase-element.md)  
  
- Usando [ \<](./file-schema/runtime/probing-element.md) el elemento>de sondeo.  
  
 También puede usar la herramienta de configuración de [.NET Framework (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) para especificar ubicaciones de ensamblado o ubicaciones para que Common Language Runtime sondee los ensamblados.  
  
## <a name="using-the-codebase-element"></a>Uso \<del elemento de> codeBase  
 Puede usar ** \<** el elemento>codeBase solo en la configuración del equipo o en los archivos de directiva de publicador que también redirigen la versión del ensamblado. Cuando el tiempo de ejecución determina qué versión de ensamblado se va a usar, aplica la configuración base de código del archivo que determina la versión. Si no se indica ninguna base de código, el tiempo de ejecución sondea el ensamblado de la manera normal. Para obtener más información, vea [Cómo el tiempo de ejecución localiza ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
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
  
 El atributo **version** es necesario para todos los ensamblados con nombre seguro, pero debe omitirse para los ensamblados que no tienen nombre seguro. El ** \<** elemento>codeBase requiere el atributo **href.** No puede especificar intervalos ** \<** de versiones en el elemento>codeBase.  
  
> [!NOTE]
> Si proporciona una sugerencia de base de código para un ensamblado que no tiene nombre seguro, la sugerencia debe apuntar a la base de la aplicación o a un subdirectorio del directorio base de la aplicación.  
  
## <a name="using-the-probing-element"></a>Uso \<del elemento> de sondeo  
 El tiempo de ejecución localiza ensamblados que no tienen una base de código mediante sondeo. Para obtener más información acerca de la sondeo, vea Cómo el tiempo de [ejecución localiza ensamblados](../deployment/how-the-runtime-locates-assemblies.md).  
  
 Puede utilizar [ \<](./file-schema/runtime/probing-element.md) el elemento>de sondeo en el archivo de configuración de la aplicación para especificar los subdirectorios que el tiempo de ejecución debe buscar al localizar un ensamblado. En el ejemplo siguiente se muestra cómo especificar directorios que el tiempo de ejecución debe buscar.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 El atributo **privatePath** contiene los directorios que el tiempo de ejecución debe buscar para los ensamblados. Si la aplicación se encuentra en C:-Archivos de programa-MyApp, el tiempo de ejecución buscará ensamblados que no especifiquen una base de código en C:-Archivos de programa-MiApp-Bin, C:-Archivos de programa-MyApp-Bin2-Subbin, y C:-Archivos de programa-MyApp-Bin3. Los directorios especificados en **privatePath** deben ser subdirectorios del directorio base de la aplicación.  
  
## <a name="see-also"></a>Consulte también

- [Ensamblados de .NET](../../standard/assembly/index.md)
- [Programar con ensamblados](../../standard/assembly/index.md)
- [Cómo el motor en tiempo de ejecución localiza ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Configurar aplicaciones con archivos de configuración](index.md)
