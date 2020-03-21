---
title: <providerOption> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155406"
---
# <a name="provideroption-element"></a>\<providerOption> Element
Especifica los atributos de versión del compilador para un proveedor de lenguaje.  

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.codedom**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiladores>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>del compilador**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Especifica el nombre de la opción; por ejemplo, "CompilerVersion".|  
|`value`|Atributo necesario.<br /><br /> Especifica el valor de la opción; por ejemplo, "v3.5".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<configuración> Elemento](../configuration-element.md)|Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.|  
|[\<system.codedom> Element](system-codedom-element.md)|Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.|  
|[\<compiladores> Element](compilers-element.md)|Contenedor para elementos de configuración del compilador; contiene cero `<compiler>` o más elementos.|  
|[\<compilador> elemento](compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
## <a name="remarks"></a>Observaciones  
 En la versión 3.5 de .NET Framework, los proveedores de código del `<providerOption>` modelo de objetos de documento de código (CodeDOM) pueden admitir opciones específicas del proveedor mediante el elemento.  
  
 .NET Framework 3.5 incluye ensamblados actualizados de .NET Framework 2.0 y proporciona nuevos ensamblados de la versión 3.5 que contienen nuevos tipos. Los proveedores de código de Microsoft C y Visual Basic están contenidos en ensamblados de .NET Framework 2.0, pero se han actualizado para admitir compiladores de la versión 3.5. De forma predeterminada, los proveedores de código actualizados generan código para los compiladores de la versión 2.0. Puede usar `<providerOption>` el elemento para cambiar la versión del compilador de destino a 3.5. Para ello, especifique "CompilerVersion" `name` para el atributo y "v3.5" para el `value` atributo. Debe preceder el número de versión con una "v" en minúsculas.  
  
 Puede hacer que la especificación `<providerOption>` de versión sea global agregando el elemento al archivo Machine.config o Web.config raíz de .NET Framework 2.0. Si actualiza la versión predeterminada del compilador a 3.5 en el archivo Machine.config, puede volver `<providerOption>` a cambiarla a 2.0 por aplicación mediante el elemento del archivo de configuración de la aplicación.  
  
 Los implementadores de proveedores de código CodeDOM `providerOptions` pueden procesar <xref:System.Collections.Generic.IDictionary%602>opciones personalizadas proporcionando un constructor que toma un parámetro de tipo .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que se debe usar la versión 3.5 del proveedor de código de C.  
  
```xml  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Esquema del archivo de configuración](../index.md)
- [\<compiladores> Element](compilers-element.md)
- [Especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Elemento compiler aplicado a compilers para compilation (Esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
