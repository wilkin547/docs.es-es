---
title: "&lt;providerOption&gt; (Elemento) | Microsoft Docs"
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
  - "provideroption"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<provideroption> (elemento)"
  - "provideroption (elemento)"
  - "providerOptions"
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
caps.latest.revision: 22
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 22
---
# &lt;providerOption&gt; (Elemento)
Especifica los atributos de versión del compilador para un proveedor de lenguaje.  
  
## Sintaxis  
  
```  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Especifica el nombre de la opción; por ejemplo, "CompilerVersion".|  
|`value`|Atributo necesario.<br /><br /> Especifica el valor de la opción; por ejemplo, "v3.5".|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.|  
|[\<system.codedom\> \(Elemento\)](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Especifica las opciones de configuración del compilador para los proveedores de lenguaje disponibles.|  
|[Elemento \<compilers\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenedor de elementos de configuración del compilador; contiene el cero o más elementos `<compiler>`.|  
|[Elemento \<compiler\>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
## Comentarios  
 En .NET Framework 3.5, los proveedores de código CodeDOM \(Code Document Object Model\) pueden admitir opciones específicas del proveedor utilizando el elemento `<providerOption>`.  
  
 .NET Framework 3.5 incluye ensamblados actualizados de .NET Framework 2.0 y proporciona ensamblados de la nueva versión 3.5 que contienen nuevos tipos.  Los proveedores de código de Microsoft C\# y Visual Basic se encuentran en ensamblados de .NET Framework 2.0 pero se han actualizado para admitir compiladores de la versión 3.5.  De forma predeterminada, los proveedores actualizados de código generan código para compiladores de la versión 2.0.  Puede utilizar el elemento `<providerOption>` para cambiar la versión del compilador de destino a la 3.5.  Para ello, especifique "CompilerVersion" para el atributo `name` y "v3.5" para el atributo `value`.  El número de versión debe ir precedido de una "v" minúscula.  
  
 Puede hacer que la especificación de la versión sea global, agregando el elemento `<providerOption>` al archivo Machine.config o Web.config raíz de .NET Framework 2.0.  Si actualiza la versión de compilador predeterminada a 3.5 en el archivo Machine.config, puede volver a cambiarlo a 2.0 en cada aplicación utilizando el elemento `<providerOption>` en el archivo de configuración de la aplicación.  
  
 Los implementadores de proveedores de código CodeDOM pueden procesar opciones personalizadas proporcionando un constructor que tome un parámetro `providerOptions` de tipo <xref:System.Collections.Generic.IDictionary%602>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que se debe utilizar la versión 3.5 del proveedor de código de C\#.  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
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