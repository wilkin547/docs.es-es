---
title: "Elemento &lt;qualifyAssembly&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<qualifyAssembly> (elemento)"
  - "etiquetas contenedoras, <qualifyAssembly> (elemento)"
  - "qualifyAssembly (elemento)"
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Elemento &lt;qualifyAssembly&gt;
Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.  
  
## Sintaxis  
  
```  
  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`partialName`|Atributo necesario.<br /><br /> Especifica el nombre parcial del ensamblado tal y como aparece en el código.|  
|`fullName`|Atributo necesario.<br /><br /> Especifica el nombre completo del ensamblado tal y como aparece la caché global de ensamblados.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Al llamar al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> mediante nombres de ensamblado parciales, Common Language Runtime buscará el ensamblado solo en el directorio base de la aplicación.  Utilice el elemento de **\<qualifyAssembly\>** en el archivo de configuración de la aplicación para proporcionar información completa del ensamblado \(nombre, versión, el token de clave pública, y referencia cultural\) y producir Common Language Runtime para buscar el ensamblado en la caché global de ensamblados.  
  
 El atributo **fullName** debe incluir los cuatro campos de la identidad del ensamblado: nombre, versión, símbolo \(token\) de la clave pública y referencia cultural.  El atributo **partialName** debe hacer parcialmente referencia a un ensamblado.  Se ha de especificar al menos el nombre de texto del ensamblado \(caso más habitual\), si bien también se puede incluir la versión, el símbolo \(token\) de la clave pública o la referencia cultural \(o cualquier combinación de estos cuatro campos, pero no los cuatro conjuntamente\).  El atributo **partialName** debe coincidir con el nombre especificado en la llamada.  Por ejemplo, no se puede especificar `"math"` como atributo **partialName** en el archivo de configuración y llamar a `Assembly.Load("math, Version=3.3.3.3")` en el código.  
  
## Ejemplo  
 En el siguiente ejemplo, se convierte de manera lógica la llamada a `Assembly.Load("math")` en una llamada a `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [NIB: Partial Assembly References](http://msdn.microsoft.com/es-es/ec90f07a-398c-4306-9401-0fc5ff9cb59f)