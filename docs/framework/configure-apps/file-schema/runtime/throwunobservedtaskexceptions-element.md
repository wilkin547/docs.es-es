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
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153820"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<ThrowUnobservedTaskExceptions> (Elemento)
Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si las excepciones de tareas no controladas deben terminar el proceso en ejecución.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|No finaliza el proceso en ejecución para una excepción de tarea no controlada. Este es el valor predeterminado.|  
|`true`|Finaliza el proceso de ejecución de una excepción de tarea no controlada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
|||  
  
## <a name="remarks"></a>Comentarios  
 Si no se ha observado una excepción asociada a un <xref:System.Threading.Tasks.Task> , no hay ninguna <xref:System.Threading.Tasks.Task.Wait%2A> operación, no se adjunta el elemento primario y no se <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> leyó la propiedad, se considera que la excepción de la tarea no se ha observado.  
  
 En el .NET Framework 4, de forma predeterminada, si un <xref:System.Threading.Tasks.Task> que tiene una excepción no observada se recolecta como elemento no utilizado, el finalizador inicia una excepción y finaliza el proceso. La terminación del proceso viene determinada por el tiempo de recolección y finalización de elementos no utilizados.  
  
 Para facilitar a los desarrolladores la escritura de código asincrónico basado en tareas, el .NET Framework 4,5 cambia este comportamiento predeterminado en caso de que se produzcan excepciones inadvertidas. Las excepciones no observadas siguen provocando que <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> se produzca el evento, pero, de forma predeterminada, el proceso no finaliza. En su lugar, se omite la excepción una vez provocado el evento, independientemente de si un controlador de eventos observa la excepción.  
  
 En el .NET Framework 4,5, puede usar el [ \<ThrowUnobservedTaskExceptions> elemento](throwunobservedtaskexceptions-element.md) en un archivo de configuración de la aplicación para habilitar el comportamiento de .NET Framework 4 de producir una excepción.  
  
 También puede especificar el comportamiento de la excepción de una de las siguientes maneras:  
  
- Estableciendo la variable de entorno `COMPlus_ThrowUnobservedTaskExceptions` ( `set COMPlus_ThrowUnobservedTaskExceptions=1` ).  
  
- Estableciendo el valor DWORD del registro ThrowUnobservedTaskExceptions = 1 en el HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft \\ . Clave NETFramework.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar el inicio de excepciones en tareas mediante el uso de un archivo de configuración de la aplicación.  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo se produce una excepción no observada desde una tarea. El código debe ejecutarse como un programa lanzado para que funcione correctamente.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
