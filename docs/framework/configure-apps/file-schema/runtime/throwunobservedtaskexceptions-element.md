---
title: <ThrowUnobservedTaskExceptions> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb6cfc8e1c3f0409d99d31efa0a645476b47e45e
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456252"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<ThrowUnobservedTaskExceptions > elemento
Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.  
  
 \<configuration>  
\<runtime>  
\<ThrowUnobservedTaskExceptions>  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si las excepciones no controladas de tarea deben finalizar el proceso en ejecución.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No termina el proceso en ejecución para una excepción no controlada de tareas. Este es el valor predeterminado.|  
|`true`|Finaliza el proceso en ejecución para una excepción no controlada de tareas.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
|||  
  
## <a name="remarks"></a>Comentarios  
 Si una excepción que está asociada con un <xref:System.Threading.Tasks.Task> no ha observado, no hay ningún <xref:System.Threading.Tasks.Task.Wait%2A> operación, el elemento primario no está conectado y el <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> propiedad no se ha leído la excepción de la tarea se considera inadvertida.  
  
 En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], de manera predeterminada, si un <xref:System.Threading.Tasks.Task> que tiene un inadvertido excepción es la recolección, finalizador inicia una excepción y termina el proceso. La terminación del proceso viene determinada por el tiempo de finalización y de recolección de elementos.  
  
 Para facilitar a los desarrolladores escribir código asincrónico basado en tareas, .NET Framework 4.5 cambia este comportamiento predeterminado para las excepciones no observadas. Excepciones inadvertidas provocan que el <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> evento, pero de forma predeterminada, el proceso no finaliza. En su lugar, se omite la excepción después de que se genera el evento, independientemente de si un controlador de eventos observa la excepción.  
  
 En .NET Framework 4.5, puede usar el [ \<ThrowUnobservedTaskExceptions > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) en un archivo de configuración para habilitar el comportamiento de .NET Framework 4 de producir una excepción.  
  
 También puede especificar el comportamiento de excepción en una de las maneras siguientes:  
  
- Estableciendo la variable de entorno `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
- Estableciendo el valor DWORD del Registro valor ThrowUnobservedTaskExceptions = 1 en el HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Tecla NETFramework.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo habilitar el inicio de excepciones en tareas mediante el uso de un archivo de configuración de la aplicación.  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo se produce una excepción no observada de una tarea. El código debe ejecutarse como un programa de lanzamiento para que funcione correctamente.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
