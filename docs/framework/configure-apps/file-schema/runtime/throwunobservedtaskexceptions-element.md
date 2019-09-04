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
ms.openlocfilehash: 3ed1e66c4aadab656455686a7a1e5028b035676a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252265"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<ThrowUnobservedTaskExceptions >, elemento
Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si las excepciones de tareas no controladas deben terminar el proceso en ejecución.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`false`|No finaliza el proceso en ejecución para una excepción de tarea no controlada. Este es el valor predeterminado.|  
|`true`|Finaliza el proceso de ejecución de una excepción de tarea no controlada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
|||  
  
## <a name="remarks"></a>Comentarios  
 Si no se ha observado una excepción asociada <xref:System.Threading.Tasks.Task> a un, no hay ninguna <xref:System.Threading.Tasks.Task.Wait%2A> operación, <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> no se adjunta el elemento primario y no se leyó la propiedad, se considera que la excepción de la tarea no se ha observado.  
  
 En el .NET Framework 4, de forma predeterminada, si <xref:System.Threading.Tasks.Task> un que tiene una excepción no observada se recolecta como elemento no utilizado, el finalizador inicia una excepción y finaliza el proceso. La terminación del proceso viene determinada por el tiempo de recolección y finalización de elementos no utilizados.  
  
 Para facilitar a los desarrolladores la escritura de código asincrónico basado en tareas, el .NET Framework 4,5 cambia este comportamiento predeterminado en caso de que se produzcan excepciones inadvertidas. Las excepciones no observadas siguen <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> provocando que se produzca el evento, pero, de forma predeterminada, el proceso no finaliza. En su lugar, se omite la excepción una vez provocado el evento, independientemente de si un controlador de eventos observa la excepción.  
  
 En el .NET Framework 4,5, puede usar el [ \<elemento de > ThrowUnobservedTaskExceptions](throwunobservedtaskexceptions-element.md) en un archivo de configuración de la aplicación para habilitar el comportamiento de .NET Framework 4 de producir una excepción.  
  
 También puede especificar el comportamiento de la excepción de una de las siguientes maneras:  
  
- Estableciendo la variable `COMPlus_ThrowUnobservedTaskExceptions` de entorno (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
- Estableciendo el valor DWORD del registro ThrowUnobservedTaskExceptions = 1 en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Clave NETFramework.  
  
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
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
