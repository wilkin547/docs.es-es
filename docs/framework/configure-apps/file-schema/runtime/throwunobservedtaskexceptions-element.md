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
ms.openlocfilehash: 876452a0a56d10f169526138cdbbbd153572f457
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658850"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="939fa-102">\<ThrowUnobservedTaskExceptions >, elemento</span><span class="sxs-lookup"><span data-stu-id="939fa-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="939fa-103">Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="939fa-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="939fa-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="939fa-104">\<configuration></span></span>  
<span data-ttu-id="939fa-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="939fa-105">\<runtime></span></span>  
<span data-ttu-id="939fa-106">\<ThrowUnobservedTaskExceptions></span><span class="sxs-lookup"><span data-stu-id="939fa-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="939fa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="939fa-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="939fa-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="939fa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="939fa-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="939fa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="939fa-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="939fa-110">Attributes</span></span>  
  
|<span data-ttu-id="939fa-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="939fa-111">Attribute</span></span>|<span data-ttu-id="939fa-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="939fa-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="939fa-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="939fa-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="939fa-114">Especifica si las excepciones de tareas no controladas deben terminar el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="939fa-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="939fa-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="939fa-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="939fa-116">Valor</span><span class="sxs-lookup"><span data-stu-id="939fa-116">Value</span></span>|<span data-ttu-id="939fa-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="939fa-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="939fa-118">No finaliza el proceso en ejecución para una excepción de tarea no controlada.</span><span class="sxs-lookup"><span data-stu-id="939fa-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="939fa-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="939fa-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="939fa-120">Finaliza el proceso de ejecución de una excepción de tarea no controlada.</span><span class="sxs-lookup"><span data-stu-id="939fa-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="939fa-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="939fa-121">Child Elements</span></span>  
 <span data-ttu-id="939fa-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="939fa-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="939fa-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="939fa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="939fa-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="939fa-124">Element</span></span>|<span data-ttu-id="939fa-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="939fa-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="939fa-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="939fa-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="939fa-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="939fa-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="939fa-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="939fa-128">Remarks</span></span>  
 <span data-ttu-id="939fa-129">Si no se ha observado una excepción asociada <xref:System.Threading.Tasks.Task> a un, no hay ninguna <xref:System.Threading.Tasks.Task.Wait%2A> operación, <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> no se adjunta el elemento primario y no se leyó la propiedad, se considera que la excepción de la tarea no se ha observado.</span><span class="sxs-lookup"><span data-stu-id="939fa-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="939fa-130">En el .NET Framework 4, de forma predeterminada, si <xref:System.Threading.Tasks.Task> un que tiene una excepción no observada se recolecta como elemento no utilizado, el finalizador inicia una excepción y finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="939fa-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="939fa-131">La terminación del proceso viene determinada por el tiempo de recolección y finalización de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="939fa-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="939fa-132">Para facilitar a los desarrolladores la escritura de código asincrónico basado en tareas, el .NET Framework 4,5 cambia este comportamiento predeterminado en caso de que se produzcan excepciones inadvertidas.</span><span class="sxs-lookup"><span data-stu-id="939fa-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="939fa-133">Las excepciones no observadas siguen <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> provocando que se produzca el evento, pero, de forma predeterminada, el proceso no finaliza.</span><span class="sxs-lookup"><span data-stu-id="939fa-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="939fa-134">En su lugar, se omite la excepción una vez provocado el evento, independientemente de si un controlador de eventos observa la excepción.</span><span class="sxs-lookup"><span data-stu-id="939fa-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="939fa-135">En el .NET Framework 4,5, puede usar el [ \<elemento de > ThrowUnobservedTaskExceptions](throwunobservedtaskexceptions-element.md) en un archivo de configuración de la aplicación para habilitar el comportamiento de .NET Framework 4 de producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="939fa-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="939fa-136">También puede especificar el comportamiento de la excepción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="939fa-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="939fa-137">Estableciendo la variable `COMPlus_ThrowUnobservedTaskExceptions` de entorno (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="939fa-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="939fa-138">Estableciendo el valor DWORD del registro ThrowUnobservedTaskExceptions = 1 en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Clave NETFramework.</span><span class="sxs-lookup"><span data-stu-id="939fa-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="939fa-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="939fa-139">Example</span></span>  
 <span data-ttu-id="939fa-140">En el ejemplo siguiente se muestra cómo habilitar el inicio de excepciones en tareas mediante el uso de un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="939fa-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="939fa-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="939fa-141">Example</span></span>  
 <span data-ttu-id="939fa-142">En el ejemplo siguiente se muestra cómo se produce una excepción no observada desde una tarea.</span><span class="sxs-lookup"><span data-stu-id="939fa-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="939fa-143">El código debe ejecutarse como un programa lanzado para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="939fa-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="939fa-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="939fa-144">See also</span></span>

- [<span data-ttu-id="939fa-145">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="939fa-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="939fa-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="939fa-146">Configuration File Schema</span></span>](../index.md)
