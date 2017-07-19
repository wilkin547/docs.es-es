---
title: "Elemento &lt;codeBase&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<codeBase> (elemento)"
  - "codeBase (elemento)"
  - "etiquetas contenedoras, <codeBase> (elemento)"
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Elemento &lt;codeBase&gt;
Especifica dónde puede buscar Common Language Runtime un ensamblado.  
  
## Sintaxis  
  
```  
  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`href`|Atributo necesario.<br /><br /> Especifica la dirección URL en la que el motor de ejecución puede localizar la versión especificada del ensamblado.|  
|`version`|Atributo necesario.<br /><br /> Especifica la versión de ensamblado que aplica el código base.  El formato de un número de versión de ensamblado es *major.minor.build.revision*.|  
  
## Atributo version  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Los valores aceptados para cada parte del número de versión van de 0 a 65535.|No es aplicable|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`buildproviders`|Define una colección de proveedores de compilación que se utiliza para compilar archivos de recursos personalizados.  Puede tener cualquier número de proveedores de compilación.|  
|`compilation`|Configura todas las opciones de compilación que utiliza ASP.NET.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`System.web`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## Comentarios  
 Que el runtime usa **\<codeBase\>** que establece en un archivo de directivas del archivo de configuración o el editor de equipo, el archivo también debe redirigir la versión del ensamblado.  Los archivos de configuración de la aplicación pueden tener una configuración de código base sin redirigir la versión de ensamblado.  Una vez determinada la versión de ensamblado que se utiliza, el motor de ejecución aplica la configuración de código base del archivo que determina la versión.  Si no se indica un código base, el motor de ejecución intenta localizar el ensamblado del modo habitual.  
  
 Si el ensamblado tiene un nombre seguro, el código base puede estar en cualquier lugar de la intranet local o en Internet.  Si es un ensamblado privado, la configuración de código base debe ser una ruta de acceso relativa a un directorio de la aplicación.  
  
 Para los ensamblados sin nombre seguro, se omite la versión y el cargador utiliza la primera aparición \<del código\> base dentro \<dependentAssembly\>.  Si existe una entrada en el archivo de configuración de la aplicación que redirija el enlace a otro ensamblado, la redirección tendrá prioridad incluso aunque la versión del ensamblado no coincida con la solicitud de enlace.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo especificar dónde puede buscar el motor de ejecución un ensamblado.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Especificar la ubicación de un ensamblado](../../../../../docs/framework/configure-apps/specify-assembly-location.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)