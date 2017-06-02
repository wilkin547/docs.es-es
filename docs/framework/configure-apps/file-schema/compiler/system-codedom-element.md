---
title: "&lt;system.codedom&gt; (Elemento) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<system.codedom> (elemento)"
  - "elementos de configuración de compilador, <system.codedom> (elemento)"
  - "system.codedom (elemento)"
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;system.codedom&gt; (Elemento)
Especifica las opciones de configuración del compilador para los proveedores de lenguaje disponibles.  
  
## Sintaxis  
  
```  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenedor para elementos de configuración del compilador; contiene cero o más elementos de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) .|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## Comentarios  
  
## Versión 2.0 de .NET Framework  
 El elemento de [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) contiene valores de configuración del compilador para los proveedores de lenguaje instalados en un equipo además de los proveedores predeterminados instalados con .NET Framework, como <xref:Microsoft.CSharp.CSharpCodeProvider> y <xref:Microsoft.VisualBasic.VBCodeProvider>.  El elemento de [\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) contiene cero o más elementos de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) .  Cada elemento de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) especifica los atributos de la configuración del compilador para un proveedor específico del lenguaje.  
  
 Los desarrolladores y proveedores de compiladores pueden agregar opciones de configuración al archivo de configuración del equipo \(Machine.config\) para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.  Utilice el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguaje identificados mediante las opciones de configuración del compilador en un equipo.  
  
> [!NOTE]
>  En las versiones 1.0 y 1,1 de .NET Framework, los proveedores de idioma predeterminados proporcionados por .NET Framework se identifican en el elemento de [\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) .  En la versión 2.0 de .NET Framework, los proveedores de idioma predeterminado no se identifican en el elemento de [\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) , pero se pueden mostrar mediante el método de <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> .  
  
## Versiones 1.0 y 1.1 de .NET Framework  
 El elemento de [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) contiene valores de configuración del compilador para los proveedores de lenguaje en un equipo.  El elemento de [\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) contiene cero o más elementos de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) .  Cada elemento de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) especifica los atributos de la configuración del compilador para un proveedor específico del lenguaje.  
  
 .NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo \(Machine.config\).  Los desarrolladores y los proveedores de compiladores pueden agregar opciones de configuración a una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.  Utilice el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> para enumerar mediante programación los proveedores de lenguaje y las opciones de configuración del compilador en un equipo.  
  
## Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.  
  
## Ejemplo  
 El ejemplo siguiente ilustra una configuración típica del compilador.  
  
```  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
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