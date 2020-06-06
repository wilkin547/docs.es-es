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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155393"
---
# <a name="systemcodedom-element"></a>\<system.codedom> (Elemento)
Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
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
|[\<compilers>](compilers-element.md)|Contenedor para los elementos de configuración del compilador; contiene cero o más [\<compiler>](compiler-element.md) elementos.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="net-framework-version-20"></a>.NET Framework versión 2,0  
 El [\<system.codedom>](system-codedom-element.md) elemento contiene los valores de configuración del compilador para los proveedores de lenguajes instalados en un equipo, además de los proveedores predeterminados que se instalan con el .NET Framework, como <xref:Microsoft.CSharp.CSharpCodeProvider> y <xref:Microsoft.VisualBasic.VBCodeProvider> . El [\<compilers>](compilers-element.md) elemento contiene cero o más [\<compiler>](compiler-element.md) elementos. Cada [\<compiler>](compiler-element.md) elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.  
  
 Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración al archivo de configuración del equipo (Machine. config) para una nueva <xref:System.CodeDom.Compiler.CodeDomProvider> implementación. Utilice el <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> método para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguajes identificados por los valores de configuración del compilador en un equipo.  
  
> [!NOTE]
> En las versiones .NET Framework 1,0 y 1,1, los proveedores de lenguajes predeterminados proporcionados por el .NET Framework se identifican en el [\<compilers>](compilers-element.md) elemento. En el .NET Framework versión 2,0, los proveedores de lenguajes predeterminados no se identifican en el [\<compilers>](compilers-element.md) elemento, pero se pueden enumerar mediante el <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> método.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework versiones 1,0 y 1,1  
 El [\<system.codedom>](system-codedom-element.md) elemento contiene los valores de configuración del compilador para los proveedores de lenguajes de un equipo. El [\<compilers>](compilers-element.md) elemento contiene cero o más [\<compiler>](compiler-element.md) elementos. Cada [\<compiler>](compiler-element.md) elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico.  
  
 .NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config). Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Esquema de los archivos de configuración](../index.md)
- [Esquema de configuración de compilador y proveedor de lenguaje](index.md)
- [\<compiler>Element](compiler-element.md)
