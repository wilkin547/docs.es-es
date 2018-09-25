---
title: '&lt;assemblyIdentity&gt; (elemento) para &lt;en tiempo de ejecución&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2b0d7968ce2cf8f326004c9e564cb2e7912c1a0a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077348"
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a>&lt;assemblyIdentity&gt; (elemento) para &lt;en tiempo de ejecución&gt;
Contiene información de identificación sobre el ensamblado.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<assemblyBinding >  
\<dependentAssembly >  
\<assemblyIdentity >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> El nombre del ensamblado|  
|`culture`|Atributo opcional.<br /><br /> Cadena que especifica el idioma y país o región del ensamblado.|  
|`publicKeyToken`|Atributo opcional.<br /><br /> Un valor hexadecimal que especifica el nombre seguro del ensamblado.|  
|`processorArchitecture`|Atributo opcional.<br /><br /> Uno de los valores "x86", "amd64", "msil" o "ia64", que se especifica la arquitectura de procesador para un ensamblado que contiene código específico del procesador. Los valores no distinguen mayúsculas de minúsculas. Si el atributo se asigna a cualquier otro valor, toda la `<assemblyIdentity>` se omite el elemento. Vea <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>Atributo processorArchitecture  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`amd64`|Un procesador AMD de 64 bits sólo.|  
|`ia64`|Un procesador Intel de 64 bits sólo.|  
|`msil`|Neutral respecto al procesador y bits por palabra|  
|`x86`|Un procesador Intel de 32 bits, o nativo o en el Windows en el entorno de Windows (WOW) en una plataforma de 64 bits.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`dependentAssembly`|Encapsula la directiva de enlace y la ubicación de cada ensamblado. Utilice uno `<dependentAssembly>` (elemento) para cada ensamblado.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Cada  **\<dependentAssembly >** elemento debe tener una  **\<assemblyIdentity >** elemento secundario.  
  
 Si el `processorArchitecture` atributo está presente, el `<assemblyIdentity>` elemento se aplica solo al ensamblado con la arquitectura del procesador correspondiente. Si el `processorArchitecture` atributo no está presente, el `<assemblyIdentity>` elemento puede aplicarse a un ensamblado con cualquier arquitectura de procesador.  
  
 El ejemplo siguiente muestra un archivo de configuración para los dos ensamblados con el mismo nombre que tienen como destino dos arquitecturas diferentes de un procesador de dos y cuyas versiones no se haya mantenido en sincronía. Cuando la aplicación se ejecuta en el x86 la primera plataforma `<assemblyIdentity>` se aplica el elemento y se omite el resto. Si la aplicación se ejecuta en una plataforma distinta x86 o ia64, ambos se omiten.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 Si un archivo de configuración contiene un `<assemblyIdentity>` elemento sin ningún `processorArchitecture` de atributo y no contiene un elemento que coincide con la plataforma, el elemento sin el `processorArchitecture` se usa el atributo.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo proporcionar información sobre un ensamblado.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Redirigir versiones de ensamblado](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
