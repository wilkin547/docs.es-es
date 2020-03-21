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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153820"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<Elemento de> ThrowUnobservedTaskExceptions
Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
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
|`enabled`|Atributo necesario.<br /><br /> Especifica si las excepciones de tarea no controladas deben terminar el proceso en ejecución.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|No termina el proceso de ejecución para una excepción de tarea no controlada. Este es el valor predeterminado.|  
|`true`|Termina el proceso de ejecución para una excepción de tarea no controlada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
|||  
  
## <a name="remarks"></a>Observaciones  
 Si no se ha <xref:System.Threading.Tasks.Task> observado una excepción asociada <xref:System.Threading.Tasks.Task.Wait%2A> a una, no hay ninguna <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> operación, el elemento primario no está asociado y la propiedad no se leyó la excepción de tarea se considera que no se observa.  
  
 En .NET Framework 4, de <xref:System.Threading.Tasks.Task> forma predeterminada, si se recopila una excepción no observada, el finalizador produce una excepción y finaliza el proceso. La terminación del proceso viene determinada por el momento de la recolección y finalización de elementos no utilizados.  
  
 Para facilitar a los desarrolladores escribir código asincrónico basado en tareas, .NET Framework 4.5 cambia este comportamiento predeterminado para las excepciones no observadas. Las excepciones no observadas siguen provocando que se genere el <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> evento, pero de forma predeterminada, el proceso no finaliza. En su lugar, la excepción se omite después de que se genera el evento, independientemente de si un controlador de eventos observa la excepción.  
  
 En .NET Framework 4.5, puede usar el [ \<elemento de> ThrowUnobservedTaskExceptions](throwunobservedtaskexceptions-element.md) en un archivo de configuración de aplicación para habilitar el comportamiento de .NET Framework 4 de producir una excepción.  
  
 También puede especificar el comportamiento de excepción de una de las siguientes maneras:  
  
- Estableciendo la `COMPlus_ThrowUnobservedTaskExceptions` variable`set COMPlus_ThrowUnobservedTaskExceptions=1`de entorno ( ).  
  
- Al establecer el valor DWORD del Registro ThrowUnobservedTaskExceptions\\, en el HKEY_LOCAL_MACHINE,SOFTWARE, Microsoft . Clave NETFramework.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar el lanzamiento de excepciones en tareas mediante un archivo de configuración de aplicación.  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo se produce una excepción no observada desde una tarea. El código debe ejecutarse como un programa liberado para que funcione correctamente.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
