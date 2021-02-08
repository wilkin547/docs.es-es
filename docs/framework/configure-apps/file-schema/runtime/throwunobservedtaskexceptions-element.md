---
description: 'Más información acerca de: <ThrowUnobservedTaskExceptions> elemento'
title: <ThrowUnobservedTaskExceptions> (Elemento)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: 53f3f1275ea8419bed52fd73726c043e1c49eed7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802403"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="a55c7-103">\<ThrowUnobservedTaskExceptions> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a55c7-103">\<ThrowUnobservedTaskExceptions> Element</span></span>

<span data-ttu-id="a55c7-104">Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55c7-104">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a><span data-ttu-id="a55c7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a55c7-105">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a55c7-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a55c7-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a55c7-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a55c7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a55c7-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a55c7-108">Attributes</span></span>  
  
|<span data-ttu-id="a55c7-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a55c7-109">Attribute</span></span>|<span data-ttu-id="a55c7-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a55c7-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a55c7-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a55c7-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a55c7-112">Especifica si las excepciones de tareas no controladas deben terminar el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55c7-112">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a55c7-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a55c7-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="a55c7-114">Value</span><span class="sxs-lookup"><span data-stu-id="a55c7-114">Value</span></span>|<span data-ttu-id="a55c7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a55c7-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a55c7-116">No finaliza el proceso en ejecución para una excepción de tarea no controlada.</span><span class="sxs-lookup"><span data-stu-id="a55c7-116">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="a55c7-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a55c7-117">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a55c7-118">Finaliza el proceso de ejecución de una excepción de tarea no controlada.</span><span class="sxs-lookup"><span data-stu-id="a55c7-118">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a55c7-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a55c7-119">Child Elements</span></span>  

 <span data-ttu-id="a55c7-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a55c7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a55c7-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a55c7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a55c7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a55c7-122">Element</span></span>|<span data-ttu-id="a55c7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a55c7-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a55c7-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a55c7-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a55c7-125">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a55c7-125">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="a55c7-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a55c7-126">Remarks</span></span>  

 <span data-ttu-id="a55c7-127">Si no se ha observado una excepción asociada a un <xref:System.Threading.Tasks.Task> , no hay ninguna <xref:System.Threading.Tasks.Task.Wait%2A> operación, no se adjunta el elemento primario y no se <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> leyó la propiedad, se considera que la excepción de la tarea no se ha observado.</span><span class="sxs-lookup"><span data-stu-id="a55c7-127">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="a55c7-128">En el .NET Framework 4, de forma predeterminada, si un <xref:System.Threading.Tasks.Task> que tiene una excepción no observada se recolecta como elemento no utilizado, el finalizador inicia una excepción y finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="a55c7-128">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="a55c7-129">La terminación del proceso viene determinada por el tiempo de recolección y finalización de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a55c7-129">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="a55c7-130">Para facilitar a los desarrolladores la escritura de código asincrónico basado en tareas, el .NET Framework 4,5 cambia este comportamiento predeterminado en caso de que se produzcan excepciones inadvertidas.</span><span class="sxs-lookup"><span data-stu-id="a55c7-130">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="a55c7-131">Las excepciones no observadas siguen provocando que <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> se produzca el evento, pero, de forma predeterminada, el proceso no finaliza.</span><span class="sxs-lookup"><span data-stu-id="a55c7-131">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="a55c7-132">En su lugar, se omite la excepción una vez provocado el evento, independientemente de si un controlador de eventos observa la excepción.</span><span class="sxs-lookup"><span data-stu-id="a55c7-132">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="a55c7-133">En el .NET Framework 4,5, puede usar el [ \<ThrowUnobservedTaskExceptions> elemento](throwunobservedtaskexceptions-element.md) en un archivo de configuración de la aplicación para habilitar el comportamiento de .NET Framework 4 de producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="a55c7-133">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="a55c7-134">También puede especificar el comportamiento de la excepción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="a55c7-134">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="a55c7-135">Estableciendo la variable de entorno `COMPlus_ThrowUnobservedTaskExceptions` ( `set COMPlus_ThrowUnobservedTaskExceptions=1` ).</span><span class="sxs-lookup"><span data-stu-id="a55c7-135">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="a55c7-136">Estableciendo el valor DWORD del registro ThrowUnobservedTaskExceptions = 1 en el HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\ . Clave NETFramework.</span><span class="sxs-lookup"><span data-stu-id="a55c7-136">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a55c7-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a55c7-137">Example</span></span>  

 <span data-ttu-id="a55c7-138">En el ejemplo siguiente se muestra cómo habilitar el inicio de excepciones en tareas mediante el uso de un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a55c7-138">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="a55c7-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a55c7-139">Example</span></span>  

 <span data-ttu-id="a55c7-140">En el ejemplo siguiente se muestra cómo se produce una excepción no observada desde una tarea.</span><span class="sxs-lookup"><span data-stu-id="a55c7-140">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="a55c7-141">El código debe ejecutarse como un programa lanzado para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="a55c7-141">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a55c7-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="a55c7-142">See also</span></span>

- [<span data-ttu-id="a55c7-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a55c7-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a55c7-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a55c7-144">Configuration File Schema</span></span>](../index.md)
