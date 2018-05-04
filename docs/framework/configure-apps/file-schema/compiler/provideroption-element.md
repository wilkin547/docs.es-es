---
title: '&lt;providerOption&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fa3410cc2c8812c59528676bfad6cd7e887c5f73
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltprovideroptiongt-element"></a>&lt;providerOption&gt; elemento
Especifica los atributos de versión del compilador para un proveedor de lenguaje.  
  
 \<Elemento de configuración >  
\<System.CodeDom (elemento) >  
\<Elemento compilers >  
\<compilador > elemento  
\<providerOption > elemento  
  
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
|`name`|Atributo necesario.<br /><br /> Especifica el nombre de la opción; Por ejemplo, "CompilerVersion".|  
|`value`|Atributo necesario.<br /><br /> Especifica el valor de la opción; Por ejemplo, "v3.5".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.|  
|[\<System.CodeDom > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.|  
|[\<los compiladores > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenedor para los elementos de configuración de compilador; contiene cero o más `<compiler>` elementos.|  
|[Elemento \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
## <a name="remarks"></a>Comentarios  
 En la versión 3.5 de .NET Framework, los proveedores de código Code Document Object Model (CodeDOM) pueden admitir opciones específicas del proveedor mediante el `<providerOption>` elemento.  
  
 .NET Framework 3.5 incluye ensamblados actualizados de .NET Framework 2.0 y proporciona nuevos ensamblados de la versión 3.5 que contienen nuevos tipos. Los proveedores de código de Microsoft C# y Visual Basic se encuentran en los ensamblados de .NET Framework 2.0, pero se han actualizado para admitir los compiladores de la versión 3.5. De forma predeterminada, los proveedores de código actualizado generan código para compiladores de la versión 2.0. Puede usar el `<providerOption>` elemento para cambiar la versión del compilador de destino a la versión 3.5. Para ello, especifique "CompilerVersion" para el `name` atributo y "v3.5" para el `value` atributo. Debe preceder el número de versión con una "v" minúscula.  
  
 Puede hacer que la especificación de versión global mediante la adición de la `<providerOption>` elemento al archivo raíz Web.config o Machine.config de .NET Framework 2.0. Si ha actualizado la versión de compilador predeterminada a 3.5 en el archivo Machine.config, puede cambiarlo a 2.0 en según la aplicación mediante el uso de la `<providerOption>` elemento en el archivo de configuración de aplicación.  
  
 Los implementadores de proveedor de código de codeDOM pueden procesar opciones personalizadas proporcionando un constructor que toma un `providerOptions` parámetro de tipo <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que la versión 3.5 del proveedor de código de C# debe usarse.  
  
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
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<los compiladores > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [Especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [Elemento Compiler aplicado a compilers para compilation (ASP.NET Settings Schema)](http://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
