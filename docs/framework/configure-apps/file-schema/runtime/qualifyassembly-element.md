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
ms.openlocfilehash: 6a4741c6a4745bdba00fdb525b39b70d0b15e005
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109453"
---
# <a name="qualifyassembly-element"></a>\<qualifyAssembly > elemento
Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.  
  
 \<configuration>  
\<runtime>  
\<assemblyBinding>  
\<qualifyAssembly>  
  
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
|`partialName`|Atributo necesario.<br /><br /> Especifica el nombre parcial del ensamblado tal como aparece en el código.|  
|`fullName`|Atributo necesario.<br /><br /> Especifica el nombre completo del ensamblado tal como aparece en la caché global de ensamblados.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Una llamada a la <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> método utilizando nombres de ensamblado parciales hace que common language runtime que se busca el ensamblado sólo en el directorio de base de la aplicación. Use la  **\<qualifyAssembly >** elemento en el archivo de configuración de aplicación para proporcionar la información de ensamblado completo (nombre, versión, referencia cultural y token de clave pública) y hacer que common language runtime buscar para el ensamblado en la caché global de ensamblados.  
  
 El **fullName** atributo debe incluir los cuatro campos de identidad del ensamblado: nombre, versión, referencia cultural y token de clave pública. El **partialName** atributo parcialmente debe hacer referencia a un ensamblado. Debe especificar al menos el nombre del ensamblado texto (el caso más común), pero también puede incluir versión, token de clave pública, o referencia cultural (o cualquier combinación de los cuatro, pero no los cuatro). El **partialName** debe coincidir con el nombre especificado en la llamada. Por ejemplo, no se puede especificar `"math"` como el **partialName** atributo en el archivo de configuración y la llamada `Assembly.Load("math, Version=3.3.3.3")` en el código.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente convierte de manera lógica la llamada `Assembly.Load("math")` en `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.  
  
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

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Referencias a ensamblados parciales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
