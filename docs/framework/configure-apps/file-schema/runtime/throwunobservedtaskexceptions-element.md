---
title: '&lt;ThrowUnobservedTaskExceptions&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d171c2058a79476d99c5952cc6a697f126af81c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a>&lt;ThrowUnobservedTaskExceptions&gt; elemento
Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<ThrowUnobservedTaskExceptions >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si las excepciones no controladas tarea deben finalizar el proceso en ejecución.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No termina con el proceso en ejecución para una excepción de tarea no controlada. Este es el valor predeterminado.|  
|`true`|Finaliza el proceso en ejecución para una excepción de tarea no controlada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
|||  
  
## <a name="remarks"></a>Comentarios  
 Si una excepción que está asociada con un <xref:System.Threading.Tasks.Task> no se cumplió con ninguna, no hay ningún <xref:System.Threading.Tasks.Task.Wait%2A> operación, el elemento primario no está conectado y el <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> propiedad no se puede leer la excepción de la tarea se considera inadvertida.  
  
 En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], valor predeterminado, si un <xref:System.Threading.Tasks.Task> que tiene un inadvertida excepción es la recolección, el finalizador produce una excepción y finaliza el proceso. La terminación del proceso está determinada por el tiempo de finalización y de recolección de elementos.  
  
 Para facilitar a los desarrolladores a escribir código asincrónico basado en tareas, el [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] cambia este comportamiento predeterminado para las excepciones inadvertidas. Excepciones inadvertidas hacen que se siga el <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> evento, pero de forma predeterminada, el proceso no finaliza. En su lugar, se omite la excepción después de que se genera el evento, independientemente de si la excepción ajusta a un controlador de eventos.  
  
 En el [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], puede usar el [ \<ThrowUnobservedTaskExceptions > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) en un archivo de configuración de aplicación para habilitar la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] comportamiento de producir una excepción.  
  
 También puede especificar el comportamiento de excepción en una de las maneras siguientes:  
  
-   Estableciendo la variable de entorno `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
-   Al establecer el valor DWORD del Registro valor ThrowUnobservedTaskExceptions = 1 en el HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Tecla NETFramework.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar el inicio de excepciones en tareas mediante un archivo de configuración de aplicación.  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo se produce una excepción no observada desde una tarea. El código debe ejecutarse como un programa publicado para que funcione correctamente.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
