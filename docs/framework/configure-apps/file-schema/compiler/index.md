---
title: "Esquema de configuraci&#243;n de compilador y proveedor de lenguaje | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "elementos de configuración de compilador"
  - "elementos de configuración de compilador, esquema"
  - "valores de configuración del compilador"
  - "valores de configuración del compilador, esquema"
  - "esquema de configuración [.NET Framework], configuración del compilador"
  - "valores de configuración [.NET Framework], compiladores"
  - "proveedores de lenguaje"
  - "proveedores de lenguaje, esquema de configuración"
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Esquema de configuraci&#243;n de compilador y proveedor de lenguaje
La configuración del compilador y del proveedor de lenguaje especifican los elementos de configuración de compilador para los proveedores de lenguaje disponibles.  Cada elemento de configuración de compilador especifica el nombre de tipo del proveedor de código, los parámetros del compilador, los nombres de lenguaje admitidos y las extensiones de archivo admitidas.  
  
 .NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo \(Machine.config\).  Los desarrolladores y los proveedores de compiladores pueden agregar opciones de configuración a una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.  Utilice el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> para enumerar mediante programación los proveedores de lenguaje y las opciones de configuración del compilador en un equipo.  
  
 [Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)  
  
 [\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
  
 [\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.codedom\>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Especifica las opciones de configuración del compilador para los proveedores de lenguaje disponibles.|  
|[\<compiladores\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenedor para elementos de configuración del compilador; contiene cero o más elementos de [\<compilador\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) .|  
|[\<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
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
 [Elemento \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)