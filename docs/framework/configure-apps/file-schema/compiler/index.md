---
description: 'Más información acerca de: esquema de configuración de proveedor de lenguaje y compilador'
title: Esquema de configuración de compilador y proveedor de lenguaje
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: 64dd57581711358c9051cda5609e0c5ff4fc05bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699199"
---
# <a name="compiler-and-language-provider-settings-schema"></a>Esquema de configuración de compilador y proveedor de lenguaje

La configuración de compilador y proveedor de lenguaje especifica los elementos de configuración del compilador para los proveedores de lenguaje disponibles. Cada elemento de configuración de compilador especifica el nombre del tipo de proveedor de código, los parámetros del compilador, los nombres de lenguaje admitidos y las extensiones de archivo admitidas.  
  
.NET Framework define la configuración inicial del compilador en el archivo de configuración del equipo (Machine.config). Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider>. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.codedom>](system-codedom-element.md)|Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.|  
|[\<compilers>](compilers-element.md)|Contenedor para los elementos de configuración del compilador; contiene cero o más [\<compiler>](compiler-element.md) elementos.|  
|[\<compiler>](compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
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
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
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
- [Elemento \<compiler>](compiler-element.md)
