---
title: <qualifyAssembly> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 581b19cf74dcb5c2d5c4a549847629503fe0b6ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252368"
---
# <a name="qualifyassembly-element"></a>\<qualifyAssembly >, elemento
Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> assemblyBinding**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`partialName`|Atributo necesario.<br /><br /> Especifica el nombre parcial del ensamblado tal y como aparece en el código.|  
|`fullName`|Atributo necesario.<br /><br /> Especifica el nombre completo del ensamblado tal y como aparece en la caché global de ensamblados.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 La llamada <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> al método utilizando nombres de ensamblado parciales hace que el Common Language Runtime busque el ensamblado solo en el directorio base de la aplicación. Use el  **\<elemento > de qualifyAssembly** en el archivo de configuración de la aplicación para proporcionar la información de ensamblado completa (nombre, versión, token de clave pública y referencia cultural) y hacer que el Common Language Runtime busque el ensamblado en el caché global de ensamblados.  
  
 El atributo **FullName** debe incluir los cuatro campos de la identidad del ensamblado: nombre, versión, token de clave pública y referencia cultural. El atributo **partialName** debe hacer referencia a un ensamblado parcialmente. Debe especificar al menos el nombre de texto del ensamblado (el caso más común), pero también puede incluir la versión, el token de clave pública o la referencia cultural (o cualquier combinación de los cuatro, pero no los cuatro). **PartialName** debe coincidir con el nombre especificado en la llamada. Por ejemplo, no puede especificar `"math"` como el atributo **partialName** en el archivo de configuración y `Assembly.Load("math, Version=3.3.3.3")` llamar a en el código.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se convierte lógicamente la `Assembly.Load("math")` llamada `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`en.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Referencias de ensamblado parciales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
