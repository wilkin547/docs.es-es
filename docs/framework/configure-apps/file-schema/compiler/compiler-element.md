---
title: '&lt;compilador&gt; elemento'
ms.date: 03/30/2017
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
ms.openlocfilehash: b033e26d64f23398a4da6842bb4688cc94627d68
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcompilergt-element"></a>&lt;compilador&gt; elemento
Especifica los atributos de configuración del compilador para un proveedor de lenguaje.  
  
 \<Elemento de configuración >  
\<System.CodeDom (elemento) >  
\<Elemento compilers >  
\<compilador > elemento  
  
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
|`compilerOptions`|Atributo opcional.<br /><br /> Especifica los argumentos específicos del compilador adicionales para la compilación. Los valores para el `compilerOptions` atributo normalmente se muestran en un tema de opciones del compilador para que el compilador. En la documentación de Visual Studio 2005, puede localizar las opciones del compilador, busque "opciones del compilador" en el índice.|  
|`extension`|Atributo necesario.<br /><br /> Proporciona una lista separada por comas de extensiones de nombre de archivo utilizado por los archivos de origen para el proveedor de lenguaje. Por ejemplo, ". cs".|  
|`language`|Atributo necesario.<br /><br /> Proporciona una lista separada por comas de nombres de los idiomas admitidos por el proveedor de lenguaje. Por ejemplo, "c#; cs; csharp".|  
|`type`|Atributo necesario.<br /><br /> Especifica el nombre de tipo del proveedor de lenguaje, incluido el nombre del ensamblado que contiene la implementación del proveedor. El nombre de tipo debe cumplir los requisitos definidos en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
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
 Cada `<compiler>` elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico. Extiende el proveedor de la <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> clase para un idioma específico; el `<compiler>` elemento define la configuración de generador de código para el proveedor de lenguaje y compilador.  
  
 .NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config). Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.  
  
 Elementos de compilador de la aplicación o el archivo de configuración Web pueden complementar o reemplazar la configuración en el archivo de configuración de equipo. Si se configura más de una implementación de proveedor para el mismo nombre de lenguaje o la misma extensión de archivo, la última configuración coincidente invalida cualquier proveedor configurado anteriormente para esa extensión de archivo o nombre de idioma.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un elemento típico de configuración del compilador.  
  
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
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<los compiladores > elemento](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [Especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [Elemento Compiler aplicado a compilers para compilation (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))
