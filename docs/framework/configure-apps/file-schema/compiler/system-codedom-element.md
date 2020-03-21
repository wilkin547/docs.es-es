---
title: Elemento <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155393"
---
# <a name="systemcodedom-element"></a>\<system.codedom> Element
Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.  
  
[**\<configuración>**](../configuration-element.md)  
&nbsp;&nbsp;**\<>system.codedom**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<compiladores>](compilers-element.md)|Contenedor para elementos de configuración del compilador; contiene cero [ \<](compiler-element.md) o más elementos de>del compilador.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuración>](../configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="net-framework-version-20"></a>.NET Framework Versión 2.0  
 <xref:Microsoft.CSharp.CSharpCodeProvider> <xref:Microsoft.VisualBasic.VBCodeProvider>El [ \<elemento>system.codedom](system-codedom-element.md) contiene los valores de configuración del compilador para los proveedores de lenguaje instalados en un equipo además de los proveedores predeterminados que se instalan con .NET Framework, como el archivo . El [ \<elemento>de compiladores](compilers-element.md) contiene cero o más [ \<](compiler-element.md) elementos de>del compilador. Cada elemento [ \<de>del compilador](compiler-element.md) especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.  
  
 Los desarrolladores y proveedores de compiladores pueden agregar valores <xref:System.CodeDom.Compiler.CodeDomProvider> de configuración al archivo de configuración del equipo (Machine.config) para una nueva implementación. Use <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> el método para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguaje identificados por la configuración del compilador en un equipo.  
  
> [!NOTE]
> En las versiones 1.0 y 1.1 de .NET Framework, los proveedores de lenguaje predeterminados proporcionados por .NET Framework se identifican en los [ \<compiladores>](compilers-element.md) elemento. En la versión 2.0 de .NET Framework, los proveedores de lenguaje predeterminados <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> no se identifican en los [ \<compiladores>](compilers-element.md) elemento, pero se pueden enumerar mediante el método.  
  
## <a name="net-framework-versions-10-and-11"></a>Las versiones 1.0 y 1.1 de .NET Framework  
 El elemento [ \<>system.codedom](system-codedom-element.md) contiene la configuración del compilador para los proveedores de lenguaje en un equipo. El [ \<elemento>de compiladores](compilers-element.md) contiene cero o más [ \<](compiler-element.md) elementos de>del compilador. Cada elemento [ \<de>del compilador](compiler-element.md) especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.  
  
 .NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config). Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede utilizar en el archivo de configuración de la máquina y el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una configuración típica del compilador.  
  
```xml  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Esquema del archivo de configuración](../index.md)
- [Esquema de configuración del compilador y del proveedor de lenguaje](index.md)
- [\<compilador> elemento](compiler-element.md)
