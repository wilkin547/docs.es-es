---
title: <generatePublisherEvidence> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154119"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence> (Elemento)
Especifica si el <xref:System.Security.Policy.Publisher> tiempo de ejecución crea pruebas para la seguridad de acceso al código (CAS).  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si el <xref:System.Security.Policy.Publisher> tiempo de ejecución crea pruebas.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
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
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> En .NET Framework 4 y versiones posteriores, este elemento no tiene ningún efecto en los tiempos de carga del ensamblado. Para obtener más información, consulte la sección "Simplificación de directivas de seguridad" en [Cambios](../../../security/security-changes.md)de seguridad .  
  
 Common Language Runtime (CLR) intenta comprobar la firma Authenticode en tiempo de carga para crear <xref:System.Security.Policy.Publisher> evidencia para el ensamblado. Sin embargo, de forma <xref:System.Security.Policy.Publisher> predeterminada, la mayoría de las aplicaciones no necesitan evidencia. La directiva CAS estándar <xref:System.Security.Policy.PublisherMembershipCondition>no confía en el . Debe evitar el costo de inicio innecesario asociado con la comprobación de la firma del publicador a <xref:System.Security.Permissions.PublisherIdentityPermission> menos que la aplicación se ejecute en un equipo con directiva CAS personalizada o tenga la intención de satisfacer las demandas en un entorno de confianza parcial. (Las demandas de permisos de identidad siempre se realizan correctamente en un entorno de plena confianza.)  
  
> [!NOTE]
> Se recomienda que `<generatePublisherEvidence>` los servicios usen el elemento para mejorar el rendimiento de inicio.  El uso de este elemento también puede ayudar a evitar retrasos que pueden provocar un tiempo de espera y la cancelación del inicio del servicio.  
  
## <a name="configuration-file"></a>Archivo de configuración  
 Este elemento solo se puede utilizar en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente `<generatePublisherEvidence>` se muestra cómo utilizar el elemento para deshabilitar la comprobación de la directiva de publicador CAS para una aplicación.  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
