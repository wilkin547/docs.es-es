---
title: "Especificar la ubicaci&#243;n de un ensamblado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "configuración de la aplicación[.NET Framework]"
  - "ensamblados [.NET Framework], especificar ubicación"
  - "configuración [.NET Framework], aplicaciones"
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Especificar la ubicaci&#243;n de un ensamblado
La ubicación de un ensamblado se puede especificar de dos maneras:  
  
-   Mediante el elemento de [\<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) .  
  
-   Mediante el elemento de [\<la búsqueda\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) .  
  
 También se puede usar la [herramienta Configuración de .NET Framework \(Mscorcfg.msc\)](http://msdn.microsoft.com/es-es/a7106c52-68da-490e-b129-971b2c743764) para especificar ubicaciones de ensamblados o ubicaciones en las que el Common Language Runtime debe buscar ensamblados.  
  
## Mediante \<el elemento codeBase\>  
 Puede utilizar el elemento de **\<codeBase\>** sólo en la configuración del equipo o los archivos de directivas del editor que también redirige la versión del ensamblado.  Cuando el tiempo de ejecución determina la versión del ensamblado que se va a usar, aplica el valor del código base del archivo que determina la versión.  Si no se indica ningún código base, el tiempo de ejecución busca el ensamblado por los métodos normales.  Para obtener más información, vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 En el ejemplo siguiente se muestra cómo se especifica la ubicación de un ensamblado.  
  
```  
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
  
 El atributo **version** es necesario para todos los ensamblados con nombre seguro, pero se debe omitir para los ensamblados que no tengan nombre seguro.  El elemento de **\<codeBase\>** requiere el atributo de **href** .  No puede especificar intervalos de versiones en el elemento de **\<codeBase\>** .  
  
> [!NOTE]
>  Si se proporciona una sugerencia de código base para un ensamblado que no tiene nombre seguro, la sugerencia debe señalar la base de la aplicación o a un subdirectorio del directorio de la base de la aplicación.  
  
## Mediante \<el elemento\> de sondeo  
 El tiempo de ejecución ubica los ensamblados que no tienen un código base mediante búsquedas.  Para obtener más información sobre las búsquedas, vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Puede utilizar el elemento de [\<la búsqueda\>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) en el archivo de configuración de la aplicación para especificar subdirectorios que el tiempo de ejecución debe buscar al encontrar un ensamblado.  En el siguiente ejemplo se muestra cómo se especifican directorios en los que debe buscar el tiempo de ejecución:  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 El atributo **privatePath** contiene los directorios en los que el tiempo de ejecución debe buscar los ensamblados.  Si la aplicación está en C:\\Program Files\\MyApp, el tiempo de ejecución buscará los ensamblados que no especifican un código base en C:\\Program Files\\MyApp\\Bin, C:\\Program Files\\MyApp\\Bin2\\Subbin y C:\\Program Files\\MyApp\\Bin3.  Los directorios especificados en **privatePath** deben ser subdirectorios del directorio de la base de la aplicación.  
  
## Vea también  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Configuring .NET Framework Apps](http://msdn.microsoft.com/es-es/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)