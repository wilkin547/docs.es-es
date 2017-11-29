---
title: "Especificar un ensamblado &#39; s ubicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f747d921e9c131edaa8a1749c5adc5eae14623c7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="specifying-an-assembly39s-location"></a>Especificar un ensamblado &#39; s ubicación
Hay dos maneras de especificar la ubicación de un ensamblado:  
  
-   Mediante el [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elemento.  
  
-   Mediante el [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento.  
  
 También puede usar el [herramienta de configuración de .NET Framework (Mscorcfg.msc)](http://msdn.microsoft.com/en-us/a7106c52-68da-490e-b129-971b2c743764) para especificar ubicaciones de ensamblados o ubicaciones de common language runtime buscar ensamblados.  
  
## <a name="using-the-codebase-element"></a>Mediante el \<codeBase > elemento  
 Puede usar el  **\<codeBase >** elemento solo en máquina configuración o Editor de archivos de directivas que también redirigen la versión del ensamblado. Cuando el tiempo de ejecución determina qué versión del ensamblado, se aplica el valor del código base del archivo que determina la versión. Si no se indica ningún código base, el tiempo de ejecución sondea el ensamblado de la forma habitual. Para obtener más información, consulte [cómo el tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
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
  
 El **versión** atributo es necesario para todos los ensamblados con nombre seguro, pero se deben omitir para los ensamblados que no tienen nombres seguros. El  **\<codeBase >** elemento requiere la **href** atributo. No se puede especificar intervalos de versiones en el  **\<codeBase >** elemento.  
  
> [!NOTE]
>  Si se proporciona una sugerencia de código base para un ensamblado que no es un nombre seguro, la sugerencia debe apuntar a la base de la aplicación o en un subdirectorio del directorio de base de la aplicación.  
  
## <a name="using-the-probing-element"></a>Mediante el \<probing > elemento  
 El tiempo de ejecución ubica ensamblados que no tienen un código base mediante sondeo. Para obtener más información sobre las búsquedas, vea [cómo el tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Puede usar el [ \<probing >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elemento en el archivo de configuración de aplicación para especificar subdirectorios en el tiempo de ejecución debe buscar para encontrar un ensamblado. En el ejemplo siguiente se muestra cómo especificar los directorios que se debe buscar el tiempo de ejecución.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 El **privatePath** atributo contiene los directorios que el tiempo de ejecución debe buscar ensamblados. Si la aplicación se encuentra en C:\Program programa\myapp, el tiempo de ejecución busca ensamblados que no especifican un código base en C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin y C:\Program Files\MyApp\Bin3. Los directorios especificados en **privatePath** deben ser subdirectorios del directorio de base de la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Configurar aplicaciones de .NET Framework](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
