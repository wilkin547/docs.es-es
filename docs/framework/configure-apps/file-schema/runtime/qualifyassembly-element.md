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
ms.openlocfilehash: 17cfe9fc39d65f146beef5d02c701f5e3e2fbbe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115785"
---
# <a name="qualifyassembly-element"></a>\<elemento > qualifyAssembly
Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`partialName`|Atributo necesario.<br /><br /> Especifica el nombre parcial del ensamblado tal y como aparece en el código.|  
|`fullName`|Atributo necesario.<br /><br /> Especifica el nombre completo del ensamblado tal y como aparece en la caché global de ensamblados.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 La llamada al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> utilizando nombres de ensamblado parciales hace que el Common Language Runtime busque el ensamblado solo en el directorio base de la aplicación. Use el elemento **\<qualifyAssembly >** en el archivo de configuración de la aplicación para proporcionar la información de ensamblado completa (nombre, versión, token de clave pública y referencia cultural) y hacer que el Common Language Runtime busque el ensamblado en la caché de ensamblados.  
  
 El atributo **FullName** debe incluir los cuatro campos de la identidad del ensamblado: nombre, versión, token de clave pública y referencia cultural. El atributo **partialName** debe hacer referencia a un ensamblado parcialmente. Debe especificar al menos el nombre de texto del ensamblado (el caso más común), pero también puede incluir la versión, el token de clave pública o la referencia cultural (o cualquier combinación de los cuatro, pero no los cuatro). **PartialName** debe coincidir con el nombre especificado en la llamada. Por ejemplo, no puede especificar `"math"` como el atributo **partialName** en el archivo de configuración y llamar a `Assembly.Load("math, Version=3.3.3.3")` en el código.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se convierte lógicamente la `Assembly.Load("math")` de llamada en `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.  
  
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
