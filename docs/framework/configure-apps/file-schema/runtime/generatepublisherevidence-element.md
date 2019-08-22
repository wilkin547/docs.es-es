---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caec297f8d0f6febad5cf46adb0a2658960c6bb1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663671"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence >, elemento
Especifica si el tiempo de <xref:System.Security.Policy.Publisher> ejecución crea evidencia para la seguridad de acceso del código (CAS).  
  
 \<configuration>  
\<> en tiempo de ejecución  
\<generatePublisherEvidence>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el tiempo de <xref:System.Security.Policy.Publisher> ejecución crea evidencia.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`false`|No crea <xref:System.Security.Policy.Publisher> ninguna evidencia.|  
|`true`|Crea <xref:System.Security.Policy.Publisher> una evidencia. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  En el .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga de ensamblados. Para obtener más información, consulte la sección "simplificación de la Directiva de seguridad" en [cambios de seguridad](../../../security/security-changes.md).  
  
 El Common Language Runtime (CLR) intenta comprobar la firma Authenticode en el momento de la carga <xref:System.Security.Policy.Publisher> para crear una evidencia para el ensamblado. Sin embargo, de forma predeterminada, la mayoría de <xref:System.Security.Policy.Publisher> las aplicaciones no necesitan evidencia. La <xref:System.Security.Policy.PublisherMembershipCondition>Directiva CAS estándar no se basa en. Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador, a menos que la aplicación se ejecute en un equipo con una directiva de CA personalizada o <xref:System.Security.Permissions.PublisherIdentityPermission> que pretenda satisfacer las demandas de en un entorno de confianza parcial. (Las peticiones de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza).  
  
> [!NOTE]
>  Se recomienda que los servicios utilicen `<generatePublisherEvidence>` el elemento para mejorar el rendimiento de inicio.  El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento solo se puede usar en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar `<generatePublisherEvidence>` el elemento para deshabilitar la comprobación de la Directiva de publicador CAS para una aplicación.  
  
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
