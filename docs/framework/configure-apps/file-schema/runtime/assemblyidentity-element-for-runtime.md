---
title: "&lt;assemblyIdentity&gt; (Elemento para &lt;runtime&gt;) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<assemblyIdentity> (elemento)"
  - "assemblyIdentity (elemento)"
  - "etiquetas contenedoras, <assemblyIdentity> (elemento)"
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;assemblyIdentity&gt; (Elemento para &lt;runtime&gt;)
Contiene la información de identificación del ensamblado.  
  
## Sintaxis  
  
```  
  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Es el nombre del ensamblado.|  
|`culture`|Atributo opcional.<br /><br /> Cadena que especifica el idioma y el país o región del ensamblado.|  
|`publicKeyToken`|Atributo opcional.<br /><br /> Valor hexadecimal que especifica el nombre seguro del ensamblado.|  
|`processorArchitecture`|Atributo opcional.<br /><br /> Uno de los valores "x86", "amd64", "msil" o "ia64" que especifica la arquitectura del procesador para un ensamblado que contiene código específico del procesador.  En estos valores no se distinguen mayúsculas de minúsculas.  Si se asigna cualquier otro valor al atributo, se omite todo el elemento `<assemblyIdentity>`.  Vea <xref:System.Reflection.ProcessorArchitecture>.|  
  
## Atributo processorArchitecture  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`amd64`|Un procesador AMD de 64 bits sólo.|  
|`ia64`|Un procesador AMD de 64 bits sólo.|  
|`msil`|Neutral con respecto al procesador y bits\-por\-palabra|  
|`x86`|Un procesador Intel de 32 bits, o nativo o en el entorno WOW en una plataforma de 64 bits.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`dependentAssembly`|Encapsula la directiva de enlace y la ubicación de cada ensamblado.  Utilice un elemento `<dependentAssembly>` para cada ensamblado.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Cada elemento de **\<dependentAssembly\>** debe tener un elemento secundario de **\<assemblyIdentity\>** .  
  
 Si está presente el atributo `processorArchitecture`, el elemento `<assemblyIdentity>` sólo se aplica al ensamblado con la arquitectura del procesador correspondiente.  Si el atributo `processorArchitecture` no está presente, el elemento `<assemblyIdentity>` se puede aplicar a un ensamblado con cualquier arquitectura de procesador.  
  
 En el ejemplo siguiente se muestra un archivo de configuración para dos ensamblados con el mismo nombre que se destinan a dos arquitecturas de procesadores diferentes y cuyas versiones no se han mantenido sincronizadas.  Cuando la aplicación se ejecuta en la plataforma x86, se aplica el primer elemento `<assemblyIdentity>` y se omite el otro.  Si la aplicación se ejecuta en una plataforma distinta de x86 o ia64, se omiten ambos.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Si un archivo de configuración contiene un elemento `<assemblyIdentity>` sin el atributo `processorArchitecture` y no contiene un elemento que coincida con la plataforma, se utiliza el elemento sin el atributo `processorArchitecture`.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo proporcionar la información de un ensamblado.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Redirigir versiones de ensamblado](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)