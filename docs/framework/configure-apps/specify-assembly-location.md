---
title: Especificar la ubicación de un ensamblado
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 328fe08872a2b57d0bdf87ea9be9224795ca9ad9
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825412"
---
# <a name="specifying-an-assemblys-location"></a>Especificar la ubicación de un ensamblado
Hay dos maneras de especificar una ubicación de ensamblado:  
  
-   Mediante el [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elemento.  
  
-   Mediante el [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento.  
  
 También puede usar el [herramienta de configuración de .NET Framework (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) para especificar ubicaciones de ensamblados o especificar ubicaciones para common language runtime sondear ensamblados.  
  
## <a name="using-the-codebase-element"></a>Mediante el \<codeBase > elemento  
 Puede usar el  **\<codeBase >** elemento sólo en configuración o publicador directiva archivos del equipo que también redirigir la versión del ensamblado. Cuando el tiempo de ejecución determina qué versión del ensamblado, se aplica el valor de la base de código del archivo que determina la versión. Si no se indica ningún código base, el tiempo de ejecución sondea el ensamblado de la manera normal. Para obtener más información, consulte [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 El ejemplo siguiente muestra cómo especificar una ubicación de ensamblado.  
  
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
  
 El **versión** atributo es necesario para todos los ensamblados con nombre seguro, pero se debe omitir para los ensamblados que no tienen nombres seguros. El  **\<codeBase >** elemento requiere la **href** atributo. No se puede especificar intervalos de versiones en el  **\<codeBase >** elemento.  
  
> [!NOTE]
>  Si se proporciona una sugerencia de base de código de un ensamblado que no tiene nombre seguro, la sugerencia debe apuntar a la base de la aplicación o en un subdirectorio del directorio base.  
  
## <a name="using-the-probing-element"></a>Mediante el \<probing > elemento  
 El tiempo de ejecución ubica ensamblados que no tienen un código base mediante sondeo. Para obtener más información sobre las búsquedas, consulte [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Puede usar el [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento en el archivo de configuración para especificar el tiempo de ejecución debe buscar para encontrar un ensamblado de subdirectorios. El ejemplo siguiente muestra cómo especificar los directorios que se debe buscar en el tiempo de ejecución.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 El **privatePath** atributo contiene los directorios que el tiempo de ejecución debe buscar los ensamblados. Si la aplicación se encuentra en C:\Program programa\myapp, el tiempo de ejecución busca ensamblados que no especifican un código base en C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin y C:\Program Files\MyApp\Bin3. Los directorios especificados en **privatePath** deben ser subdirectorios del directorio base.  
  
## <a name="see-also"></a>Vea también
- [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Configurar aplicaciones con archivos de configuración](index.md)
