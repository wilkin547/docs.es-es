---
title: "Elemento &lt;assemblyBinding&gt; para &lt;runtime&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyBinding> (elemento)"
  - "assemblyBinding (elemento)"
  - "etiquetas contenedoras, <assemblyBinding> (elemento)"
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Elemento &lt;assemblyBinding&gt; para &lt;runtime&gt;
Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.  
  
## Sintaxis  
  
```  
  
        <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|**xmlns**|Atributo necesario.<br /><br /> Especifica el espacio de nombres XML necesario para el enlace de ensamblados.  Utilice la cadena "urn: schemas\-microsoft\-v1" como valor.|  
|**appliesTo**|Especifica la versión en tiempo de ejecución a la que se aplica la redirección del ensamblado de .NET Framework.  Este atributo opcional usa un número de versión de .NET Framework para indicar a qué versión se aplica.  Si no se especifica ningún atributo **appliesTo**, el elemento **\<assemblyBinding\>** se aplica a todas las versiones de .NET Framework.  El atributo **appliesTo** se incorporó en la versión 1.1 de .NET Framework. La versión 1.0 de .NET Framework pasa por alto este atributo.  Esto significa que se aplican todos los elementos **\<assemblyBinding\>** cuando se usa la versión 1.0 de .NET Framework, aunque se especifique un atributo **appliesTo**.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<dependentAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|Encapsula la directiva de enlace y la ubicación de un ensamblado.  Use una etiqueta **\<dependentAssembly\>** para cada ensamblado.|  
|[\<probing\>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|Especifica los subdirectorios en los que busca Common Language Runtime cuando se cargan los ensamblados.|  
|[\<publisherPolicy\>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|Especifica si el tiempo de ejecución aplica la directiva de editor.|  
|[\<qualifyAssembly\>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Ejemplo  
 En el ejemplo siguiente, se muestra cómo redirigir una versión de ensamblado a otra versión y cómo proporcionar un código base.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 En el ejemplo siguiente se muestra cómo usar el atributo **appliesTo** para redirigir el enlace de un ensamblado de .NET Framework.  
  
```  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Redirigir versiones de ensamblado](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)