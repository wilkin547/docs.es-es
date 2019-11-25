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
ms.openlocfilehash: a6718173e84ecffc4ba0641f6e865e777aa6b1a4
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088670"
---
# <a name="provideroption-element"></a>\<elemento > providerOption
Especifica los atributos de versión del compilador para un proveedor de lenguaje.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. codedom**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<[**compiladores**](compilers-element.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**compilador**](compiler-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<providerOption >**

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
|`value`|Atributo necesario.<br /><br /> Especifica el valor de la opción; por ejemplo, "v 3.5".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<configuration>](../configuration-element.md)|Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.|  
|[\<elemento > System. CodeDom](system-codedom-element.md)|Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.|  
|[\<compiladores > elemento](compilers-element.md)|Contenedor para los elementos de configuración del compilador; contiene cero o más elementos `<compiler>`.|  
|[Elemento \<compiler>](compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
## <a name="remarks"></a>Comentarios  
 En los proveedores de código .NET Framework versión 3,5, Code Document Object Model (CodeDOM) pueden admitir opciones específicas del proveedor mediante el elemento `<providerOption>`.  
  
 El .NET Framework 3,5 incluye ensamblados de .NET Framework 2,0 actualizados y proporciona nuevos ensamblados de la versión 3,5 que contienen nuevos tipos. Los proveedores C# de código de Microsoft y Visual Basic se encuentran en .NET Framework ensamblados 2,0, pero se han actualizado para admitir los compiladores de la versión 3,5. De forma predeterminada, los proveedores de código actualizados generan código para los compiladores de la versión 2,0. Puede usar el elemento `<providerOption>` para cambiar la versión del compilador de destino a 3,5. Para ello, especifique "CompilerVersion" para el atributo `name` y "v 3.5" para el atributo `value`. Debe preceder el número de versión con una "v" en minúscula.  
  
 Para hacer que la especificación de la versión sea global, agregue el elemento `<providerOption>` al archivo Machine. config de la .NET Framework 2,0 o a la raíz del archivo Web. config. Si actualiza la versión predeterminada del compilador a 3,5 en el archivo Machine. config, puede volver a cambiarla a 2,0 por aplicación mediante el elemento `<providerOption>` del archivo de configuración de la aplicación.  
  
 Los implementadores de proveedores de código CodeDOM pueden procesar opciones personalizadas proporcionando un constructor que toma un parámetro `providerOptions` de tipo <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que se debe usar C# la versión 3,5 del proveedor de código.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Esquema de los archivos de configuración](../index.md)
- [\<compiladores > elemento](compilers-element.md)
- [Especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Elemento Compiler para compiladores para compilation (esquema de configuración de ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
