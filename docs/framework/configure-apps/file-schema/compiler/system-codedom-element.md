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
ms.openlocfilehash: 43bc3c40bfc0b0ce4c0b18683092faf8b67e1c04
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927696"
---
# <a name="systemcodedom-element"></a>\<Elemento > de System. CodeDom
Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.  
  
 \<Elemento Configuration >  
\<Elemento > de System. CodeDom  
  
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
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](compiler-element.md).|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="net-framework-version-20"></a>.NET Framework versión 2,0  
 <xref:Microsoft.CSharp.CSharpCodeProvider> El [ \<elemento > de System. CodeDom](system-codedom-element.md) contiene los valores de configuración del compilador para los proveedores de lenguajes instalados en un equipo, además de los proveedores predeterminados que se instalan con el .NET Framework, como y. <xref:Microsoft.VisualBasic.VBCodeProvider>. [ El\<](compilers-element.md) elemento compiladores > contiene cero o más [ \<elementos de > del](compiler-element.md) compilador. Cada elemento > del compilador especifica los atributos de configuración del compilador para un proveedor de lenguaje concreto. [ \<](compiler-element.md)  
  
 Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración al archivo de configuración del equipo ( <xref:System.CodeDom.Compiler.CodeDomProvider> Machine. config) para una nueva implementación. Utilice el <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> método para enumerar mediante programación los proveedores de lenguaje predeterminados y los proveedores de lenguajes identificados por los valores de configuración del compilador en un equipo.  
  
> [!NOTE]
> En las versiones .NET Framework 1,0 y 1,1, los proveedores de lenguajes predeterminados proporcionados por el [ \<](compilers-element.md) .NET Framework se identifican en el elemento compiladores >. En el .NET Framework versión 2,0, los proveedores de lenguajes predeterminados no [ \<](compilers-element.md) se identifican en el elemento compiladores >, pero se <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> pueden enumerar mediante el método.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework versiones 1,0 y 1,1  
 El elemento > de [System. CodeDom contiene los valores de configuración del compilador para los proveedores de lenguajes de un equipo. \<](system-codedom-element.md) [ El\<](compilers-element.md) elemento compiladores > contiene cero o más [ \<elementos de > del](compiler-element.md) compilador. Cada elemento > del compilador especifica los atributos de configuración del compilador para un proveedor de lenguaje concreto. [ \<](compiler-element.md)  
  
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
- [Elemento \<compiler>](compiler-element.md)
