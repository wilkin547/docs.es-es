---
title: '&lt;codeBase&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d7563d3a0ba545bfd8d1b80981fcce607d230873
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399247"
---
# <a name="ltcodebasegt-element"></a>&lt;codeBase&gt; elemento
Especifica que common language runtime puede encontrar un ensamblado.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<assemblyBinding >  
\<dependentAssembly >  
\<codeBase >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`href`|Atributo necesario.<br /><br /> Especifica la dirección URL donde el tiempo de ejecución puede encontrar la versión especificada del ensamblado.|  
|`version`|Atributo necesario.<br /><br /> Especifica la versión del ensamblado que se aplica el código base. El formato de un número de versión del ensamblado es *principal.secundaria.compilación.revisión*.|  
  
## <a name="version-attribute"></a>Atributo de versión  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Los valores válidos para cada parte del número de versión van del 0 a 65535.|No es aplicable.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`buildproviders`|Define una colección de proveedores de generación que se utiliza para compilar archivos de recursos personalizados. Puede tener cualquier número de proveedores de generación.|  
|`compilation`|Configura todas las opciones de compilación que utiliza ASP.NET.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`System.web`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## <a name="remarks"></a>Comentarios  
 Para el tiempo de ejecución usar el  **\<codeBase >** establecer en un archivo de configuración del equipo o un archivo de directiva de publicador, el archivo también debe redirigir la versión del ensamblado. Archivos de configuración de la aplicación pueden tener una configuración de código base sin redirigir la versión del ensamblado. Después de determinar qué versión del ensamblado, el tiempo de ejecución aplica la configuración del código base del archivo que determina la versión. Si no se indica ningún código base, el tiempo de ejecución sondea el ensamblado de la forma habitual.  
  
 Si el ensamblado tiene un nombre seguro, la configuración de la base de código puede ser en cualquier lugar en la intranet local o en Internet. Si el ensamblado es un ensamblado privado, la configuración de la base de código debe ser una ruta de acceso relativa al directorio de la aplicación.  
  
 Para los ensamblados sin un nombre seguro, se omite la versión y el cargador usa la primera aparición de \<codebase > dentro de \<dependentAssembly >. Si hay una entrada en el archivo de configuración de aplicación que redirija el enlace a otro ensamblado, la redirección tendrá prioridad incluso si la versión del ensamblado no coincide con la solicitud de enlace.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo especificar que el tiempo de ejecución puede encontrar un ensamblado.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Especificar la ubicación de un ensamblado](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
