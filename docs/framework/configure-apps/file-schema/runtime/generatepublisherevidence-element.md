---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116573"
---
# <a name="generatepublisherevidence-element"></a>\<elemento > generatePublisherEvidence
Especifica si el tiempo de ejecución crea <xref:System.Security.Policy.Publisher> evidencia para la seguridad de acceso del código (CAS).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**  
  
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
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No crea <xref:System.Security.Policy.Publisher> evidencia.|  
|`true`|Crea <xref:System.Security.Policy.Publisher> evidencia. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> En el .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblados. Para obtener más información, consulte la sección "simplificación de la Directiva de seguridad" en [cambios de seguridad](../../../security/security-changes.md).  
  
 El Common Language Runtime (CLR) intenta comprobar la firma Authenticode en el momento de la carga para crear <xref:System.Security.Policy.Publisher> evidencia para el ensamblado. Sin embargo, de forma predeterminada, la mayoría de las aplicaciones no necesitan <xref:System.Security.Policy.Publisher> evidencia. La Directiva CAS estándar no se basa en el <xref:System.Security.Policy.PublisherMembershipCondition>. Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador, a menos que la aplicación se ejecute en un equipo con una directiva de CA personalizada o que pretenda satisfacer las demandas de <xref:System.Security.Permissions.PublisherIdentityPermission> en un entorno de confianza parcial. (Las peticiones de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza).  
  
> [!NOTE]
> Se recomienda que los servicios utilicen el elemento `<generatePublisherEvidence>` para mejorar el rendimiento de inicio.  El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento solo se puede usar en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el elemento `<generatePublisherEvidence>` para deshabilitar la comprobación de la Directiva de publicador CAS para una aplicación.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
