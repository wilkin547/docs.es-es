---
title: <publisherPolicy> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
ms.openlocfilehash: bd6ab1123ef3f84f7e8a06b25ce48aed37e4bef7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195264"
---
# <a name="publisherpolicy-element"></a>\<publisherPolicy> (Elemento)

Especifica si el tiempo de ejecución aplica la directiva de editor.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`apply`|Especifica si se debe aplicar la Directiva de edición.|  
  
## <a name="apply-attribute"></a>aplicar atributo  
  
|Value|Descripción|  
|-----------|-----------------|  
|`yes`|Aplica la Directiva de edición. Esta es la configuración predeterminada.|  
|`no`|No aplica la Directiva de edición.|  
  
### <a name="child-elements"></a>Elementos secundarios  

Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`assemblyBinding`|Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`dependentAssembly`|Encapsula la directiva de enlace y la ubicación de cada ensamblado. Use un `<dependentAssembly>` elemento para cada ensamblado.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  

 Cuando un proveedor de componentes publica una nueva versión de un ensamblado, el proveedor puede incluir una directiva de edición para que las aplicaciones que usan la versión anterior utilicen ahora la nueva versión. Para especificar si se va a aplicar la Directiva de edición para un ensamblado determinado, coloque el **\<publisherPolicy>** elemento en el **\<dependentAssembly>** elemento.  
  
 La configuración predeterminada para el atributo **aplicar** es **sí**. Al establecer el atributo **Apply** en **no** , se reemplaza cualquier configuración anterior de **sí** para un ensamblado.  
  
 El permiso es necesario para que una aplicación ignore explícitamente la Directiva de edición mediante el [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) elemento en el archivo de configuración de la aplicación. El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca en <xref:System.Security.Permissions.SecurityPermission> . Para obtener más información, vea [permisos de seguridad de redirección de enlace de ensamblados](../../assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se desactiva la Directiva de edición para el ensamblado, `myAssembly` .  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Redirigir versiones de ensamblado](../../redirect-assembly-versions.md)
