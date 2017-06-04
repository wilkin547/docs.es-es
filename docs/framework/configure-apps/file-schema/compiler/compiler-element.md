---
title: "Elemento &lt;compiler&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<compiler> (elemento)"
  - "atributos de configuración del compilador"
  - "elementos de configuración de compilador, <compiler> (elemento)"
  - "compiler (elemento)"
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# Elemento &lt;compiler&gt;
Especifica los atributos de configuración del compilador para un proveedor de lenguaje.  
  
## Sintaxis  
  
```  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`compilerOptions`|Atributo opcional.<br /><br /> Especifica los argumentos específicos del compilador adicionales para la compilación.  Normalmente, los valores del atributo `compilerOptions` aparecen en una lista en un tema de opciones del compilador.  En la documentación de Visual Studio 2005, puede encontrar las opciones del compilador buscando "opciones del compilador" en el índice.|  
|`extension`|Atributo necesario.<br /><br /> Proporciona una lista separada por punto y coma con las extensiones de nombre de archivo utilizadas por los archivos de código fuente del proveedor de lenguaje.  Por ejemplo, ".cs".|  
|`language`|Atributo necesario.<br /><br /> Proporciona una lista separada por puntos y comas de nombres de lenguaje admitidos por el proveedor del lenguaje.  Por ejemplo, "c\#;cs;csharp".|  
|`type`|Atributo necesario.<br /><br /> Especifica el nombre de tipo del proveedor del lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor.  El nombre de tipo debe cumplir los requisitos definidos en [Especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`warningLevel`|Atributo opcional.<br /><br /> Especifica el nivel de advertencia del compilador predeterminado; determina el nivel en el que el proveedor del lenguaje trata las advertencias de compilación como errores.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<providerOption\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Especifica los atributos de versión del compilador para un proveedor de lenguaje.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|[\<system.codedom\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Especifica las opciones de configuración del compilador para los proveedores de lenguaje disponibles.|  
|[Elemento \<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenedor de elementos de configuración del compilador; contiene el cero o más elementos `<compiler>`.|  
  
## Comentarios  
 Cada elemento `<compiler>` especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.  El proveedor extiende la clase <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName> para un lenguaje concreto; el elemento `<compiler>` define la configuración del compilador y del generador de código para el proveedor de lenguaje.  
  
 .NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo \(Machine.config\).  Los desarrolladores y los proveedores de compiladores pueden agregar opciones de configuración a una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>.  Utilice el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=fullName> para enumerar mediante programación los proveedores de lenguaje y las opciones de configuración del compilador en un equipo.  
  
 Los elementos de compilador de la aplicación o del archivo de configuración de Web pueden complementar o reemplazar la configuración del archivo de configuración del equipo.  Si se configura más de una implementación de proveedor para el mismo nombre de lenguaje o la misma extensión de archivo, la última configuración que coincida con estos reemplazará cualquier proveedor configurado anteriormente para ese nombre de lenguaje o esa extensión de archivo.  
  
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
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## Vea también  
 <xref:System.CodeDom.Compiler.CompilerInfo>   
 <xref:System.CodeDom.Compiler.CodeDomProvider>   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Elemento \<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)   
 [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)   
 [Elemento compiler aplicado a compilers para compilation \(Esquema de configuración de ASP.NET\)](http://msdn.microsoft.com/es-es/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)