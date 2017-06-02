---
title: "Elemento &lt;compilers&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compilers> (elemento)"
  - "elementos de configuración de compilador, <compilers> (elemento)"
  - "compilers (elemento)"
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Elemento &lt;compilers&gt;
Contenedor para elementos de configuración del compilador; contiene cero o más elementos de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) .  
  
## Sintaxis  
  
```  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[Elemento \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|[\<system.codedom\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Especifica las opciones de configuración del compilador para los proveedores de lenguaje disponibles.|  
  
## Comentarios  
 El elemento de [\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) contiene valores de configuración del compilador para los proveedores de lenguaje en un equipo.  Cada elemento de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) especifica los atributos de la configuración del compilador para un proveedor específico del lenguaje.  
  
 .NET Framework define la configuración inicial del compilador y del proveedor de lenguaje en el archivo de configuración del equipo \(Machine.config\).  Los desarrolladores y los proveedores de compiladores pueden agregar opciones de configuración a una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName>.  Utilice el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> para enumerar mediante programación los proveedores de lenguaje y las opciones de configuración del compilador en un equipo.  
  
## Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente ilustra un elemento de configuración de compilador típico.  
  
```  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## Vea también  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Esquema de configuración de compilador y proveedor de lenguaje](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)   
 [Elemento \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)