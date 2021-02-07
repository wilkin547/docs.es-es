---
description: 'Más información acerca de: <compiler> elemento'
title: <compiler> (Elemento)
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
ms.openlocfilehash: 91540d2217320b225ae67a48d616720ef2a0b679
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699225"
---
# <a name="compiler-element"></a>\<compiler> (Elemento)

Especifica los atributos de configuración del compilador para un proveedor de lenguaje.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**

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
|`compilerOptions`|Atributo opcional.<br /><br /> Especifica argumentos adicionales específicos del compilador para la compilación. Los valores del `compilerOptions` atributo se enumeran normalmente en un tema de opciones del compilador para el compilador.|
|`extension`|Atributo necesario.<br /><br /> Proporciona una lista separada por puntos y comas de extensiones de nombre de archivo usadas por los archivos de código fuente para el proveedor de lenguaje. Por ejemplo, ".cs".|
|`language`|Atributo necesario.<br /><br /> Proporciona una lista separada por puntos y comas de nombres de idioma admitidos por el proveedor de lenguaje. Por ejemplo, "C#;cs;csharp".|
|`type`|Atributo necesario.<br /><br /> Especifica el nombre de tipo del proveedor de lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor. El nombre de tipo debe cumplir los requisitos definidos en la [especificación de nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Atributo opcional.<br /><br /> Especifica el nivel de advertencia del compilador predeterminado; determina el nivel en el que el proveedor de lenguaje trata las advertencias de compilación como errores.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[Elemento \<providerOption>](provideroption-element.md)|Especifica los atributos de versión del compilador para un proveedor de lenguaje.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[Elemento \<configuration>](../configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|[Elemento \<system.codedom>](system-codedom-element.md)|Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.|
|[Elemento \<compilers>](compilers-element.md)|Contenedor para los elementos de configuración del compilador; contiene cero o más `<compiler>` elementos.|

## <a name="remarks"></a>Observaciones

Cada `<compiler>` elemento especifica los atributos de configuración del compilador para un proveedor de lenguaje específico. El proveedor extiende la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> clase para un lenguaje específico; el `<compiler>` elemento define la configuración del compilador y del generador de código para el proveedor de lenguaje.

.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config). Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.

Los elementos del compilador de la aplicación o el archivo de configuración Web pueden complementar o invalidar la configuración del archivo de configuración del equipo. Si se configura más de una implementación de proveedor para el mismo nombre de idioma o la misma extensión de archivo, la última configuración coincidente invalida todos los proveedores configurados anteriormente para ese nombre de idioma o extensión de archivo.

## <a name="configuration-file"></a>Archivo de configuración

Este elemento se puede usar en el archivo de configuración del equipo y en el archivo de configuración de la aplicación.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un elemento de configuración de compilador típico:

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
- [Esquema de los archivos de configuración](../index.md)
- [Elemento \<compilers>](compilers-element.md)
- [Especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Elemento compiler aplicado a compilers para compilation (Esquema de configuración de ASP.NET)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
