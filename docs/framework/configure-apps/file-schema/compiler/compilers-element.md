---
title: '&lt;los compiladores&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e51298e86c1b3167f822e060693d0a2ee4193b67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723477"
---
# <a name="ltcompilersgt-element"></a>&lt;los compiladores&gt; elemento
Contenedor para los elementos de configuración del compilador; contiene cero o más elementos [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md).  
  
 \<configuration>  
\<system.codedom>  
\<los compiladores > elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Especifica los atributos de configuración del compilador para un proveedor de lenguaje.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|[\<system.codedom> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Especifica los valores de configuración del compilador para los proveedores de lenguaje disponibles.|  
  
## <a name="remarks"></a>Comentarios  
 El [ \<compiladores >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) elemento contiene los valores de configuración de compilador para los proveedores de lenguaje en un equipo. Cada [ \<compilador >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elemento especifica los atributos de configuración de compilador para un proveedor de lenguaje específico.  
  
 .NET Framework define la inicial del compilador y la configuración del proveedor de lenguaje en el archivo de configuración del equipo (Machine.config). Los desarrolladores y los proveedores de compiladores pueden agregar valores de configuración para una nueva implementación de <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>. Use el método <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> para enumerar mediante programación los valores de configuración del compilador y del proveedor de lenguaje en un equipo.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento se puede usar en el archivo de configuración del equipo y el archivo de configuración de la aplicación.  
  
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
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Esquema de configuración de compilador y proveedor de lenguaje](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [Elemento \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
