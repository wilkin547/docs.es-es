---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 506e7873fab8e41fce121587c22d85600a8b1760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158778"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence> (Elemento)

Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia para la seguridad de acceso del código (CAS).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|No crea ninguna <xref:System.Security.Policy.Publisher> evidencia.|  
|`true`|Crea una <xref:System.Security.Policy.Publisher> evidencia. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> En el .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblados. Para obtener más información, consulte la sección "simplificación de la Directiva de seguridad" en [cambios de seguridad](/previous-versions/dotnet/framework/security/security-changes).  
  
 El Common Language Runtime (CLR) intenta comprobar la firma Authenticode en el momento de la carga para crear una <xref:System.Security.Policy.Publisher> evidencia para el ensamblado. Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no necesitan <xref:System.Security.Policy.Publisher> evidencia. La Directiva CAS estándar no se basa en <xref:System.Security.Policy.PublisherMembershipCondition> . Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador, a menos que la aplicación se ejecute en un equipo con una directiva de CA personalizada o que pretenda satisfacer las demandas de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial. (Las peticiones de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza).  
  
> [!NOTE]
> Se recomienda que los servicios utilicen el `<generatePublisherEvidence>` elemento para mejorar el rendimiento de inicio.  El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.  
  
## <a name="configuration-file"></a>Archivo de configuración  

 Este elemento solo se puede usar en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo usar el `<generatePublisherEvidence>` elemento para deshabilitar la comprobación de la Directiva de publicador CAS para una aplicación.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
