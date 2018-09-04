---
title: '&lt;compilador&gt; elemento'
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 84000d8762c5d5cfd8d2359a377ffcd5b50ab07c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502855"
---
# <a name="ltcompilergt-element"></a>&lt;compilador&gt; elemento

Especifica los atributos de configuración del compilador para un proveedor de lenguaje.

\<Elemento de configuración > \<elemento system.codedom > \<elemento compilers > \<compilador > elemento

## <a name="syntax"></a>Sintaxis

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`compilerOptions`|Atributo opcional.<br /><br /> Especifica los argumentos específicos del compilador adicionales para la compilación. Los valores para el `compilerOptions` atributo aparecen normalmente en un tema de las opciones del compilador para el compilador.|
|`extension`|Atributo necesario.<br /><br /> Proporciona una lista separada por comas de extensiones de nombre de archivo utilizado por los archivos de origen para el proveedor de lenguaje. Por ejemplo, "cs".|
|`language`|Atributo necesario.<br /><br /> Proporciona una lista separada por comas de nombres de lenguajes admitidos por el proveedor de lenguaje. Por ejemplo, "c#; cs; csharp".|
|`type`|Atributo necesario.<br /><br /> Especifica el nombre de tipo del proveedor del lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor. El nombre de tipo debe cumplir los requisitos definidos en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Atributo opcional.<br /><br /> Especifica el nivel de advertencia del compilador predeterminado; Determina el nivel en el que el proveedor de lenguaje trata las advertencias de compilación como errores.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<providerOption > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Especifica los atributos de versión del compilador para un proveedor de lenguaje.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|[\<System.CodeDom > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.|
|[\<los compiladores > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Contenedor para los elementos de configuración de compilador; contiene cero o más `<compiler>` elementos.|

## <a name="remarks"></a>Comentarios

Cada `<compiler>` elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico. Extiende el proveedor la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> clase para un idioma específico; el `<compiler>` elemento define el compilador y la configuración de generador de código para el proveedor de lenguaje.

.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config). Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.

Elementos de compilador de la aplicación o el archivo de configuración Web pueden complementar o reemplazar la configuración en el archivo de configuración del equipo. Si se configura más de una implementación de proveedor para el mismo nombre de lenguaje o la misma extensión de archivo, la última configuración coincidente invalida cualquier proveedor configurado anteriormente para ese archivo o nombre de la extensión del lenguaje.

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de la aplicación.

## <a name="example"></a>Ejemplo

El ejemplo siguiente muestra un elemento de configuración de compilador típico:

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
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a>Vea también

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<los compiladores > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [Totalmente especificar nombres de tipo completos]-(.. /.. /.. /.. /.. / docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Elemento Compiler aplicado a compilers para compilation (esquema de configuración de ASP.NET)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))
