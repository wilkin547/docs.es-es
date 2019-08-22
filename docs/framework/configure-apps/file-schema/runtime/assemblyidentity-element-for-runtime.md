---
title: Elemento <assemblyIdentity> para <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: 815e1c26a328d986f91992a1e67e438a563ffea6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663886"
---
# <a name="assemblyidentity-element-for-runtime"></a>\<elemento de > assemblyIdentity \<para > en tiempo de ejecución
Contiene información de identificación sobre el ensamblado.  
  
 \<configuration>  
\<> en tiempo de ejecución  
\<assemblyBinding>  
\<dependentAssembly>  
\<assemblyIdentity>  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Nombre del ensamblado.|  
|`culture`|Atributo opcional.<br /><br /> Cadena que especifica el idioma y el país o región del ensamblado.|  
|`publicKeyToken`|Atributo opcional.<br /><br /> Valor hexadecimal que especifica el nombre seguro del ensamblado.|  
|`processorArchitecture`|Atributo opcional.<br /><br /> Uno de los valores "x86", "AMD64", "MSIL" o "ia64", que especifica la arquitectura de procesador para un ensamblado que contiene código específico del procesador. Los valores no distinguen mayúsculas de minúsculas. Si el atributo tiene asignado cualquier otro valor, se omite `<assemblyIdentity>` todo el elemento. Vea <xref:System.Reflection.ProcessorArchitecture>.|  
  
## <a name="processorarchitecture-attribute"></a>processorArchitecture (atributo)  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`amd64`|Solo arquitectura de AMD x86-64.|  
|`ia64`|Solo la arquitectura Intel Itanium.|  
|`msil`|Neutro con respecto al procesador y los bits por palabra.|  
|`x86`|Un procesador x86 de 32 bits, ya sea nativo o en el entorno de Windows en Windows (WOW) en una plataforma de 64 bits.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`dependentAssembly`|Encapsula la directiva de enlace y la ubicación de cada ensamblado. Use un `<dependentAssembly>` elemento para cada ensamblado.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 **Cada\<elemento dependentAssembly >** debe tener una  **\<>** elemento secundario assemblyIdentity.  
  
 Si el `processorArchitecture` atributo está presente, el `<assemblyIdentity>` elemento solo se aplica al ensamblado con la arquitectura de procesador correspondiente. Si el `processorArchitecture` atributo no está presente, el `<assemblyIdentity>` elemento se puede aplicar a un ensamblado con cualquier arquitectura de procesador.  
  
 En el ejemplo siguiente se muestra un archivo de configuración para dos ensamblados con el mismo nombre que tienen como destino dos arquitecturas de dos procesadores diferentes y cuyas versiones no se han mantenido en la sincronización. Cuando la aplicación se ejecuta en la plataforma x86, se `<assemblyIdentity>` aplica el primer elemento y se omite el otro. Si la aplicación se ejecuta en una plataforma distinta de x86 o IA64, ambos se omiten.  
  
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
  
 Si un archivo de configuración contiene `<assemblyIdentity>` un elemento `processorArchitecture` sin atributo y no contiene un elemento que coincida con la plataforma, se usa el elemento sin `processorArchitecture` el atributo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo proporcionar información sobre un ensamblado.  
  
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

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Redirigir versiones de ensamblado](../../redirect-assembly-versions.md)
