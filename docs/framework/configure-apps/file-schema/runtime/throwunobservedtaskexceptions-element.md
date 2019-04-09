---
title: <ThrowUnobservedTaskExceptions> Elemento
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
ms.openlocfilehash: cdce2181490d32212cd2629e98267e43bbe0d334
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189409"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="15177-102">\<ThrowUnobservedTaskExceptions > elemento</span><span class="sxs-lookup"><span data-stu-id="15177-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="15177-103">Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="15177-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="15177-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="15177-104">\<configuration></span></span>  
<span data-ttu-id="15177-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="15177-105">\<runtime></span></span>  
<span data-ttu-id="15177-106">\<ThrowUnobservedTaskExceptions></span><span class="sxs-lookup"><span data-stu-id="15177-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15177-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15177-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15177-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15177-108">Attributes and Elements</span></span>  
 <span data-ttu-id="15177-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="15177-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15177-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="15177-110">Attributes</span></span>  
  
|<span data-ttu-id="15177-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="15177-111">Attribute</span></span>|<span data-ttu-id="15177-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="15177-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="15177-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="15177-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="15177-114">Especifica si las excepciones no controladas de tarea deben finalizar el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="15177-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="15177-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="15177-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="15177-116">Valor</span><span class="sxs-lookup"><span data-stu-id="15177-116">Value</span></span>|<span data-ttu-id="15177-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="15177-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="15177-118">No termina el proceso en ejecución para una excepción no controlada de tareas.</span><span class="sxs-lookup"><span data-stu-id="15177-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="15177-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="15177-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="15177-120">Finaliza el proceso en ejecución para una excepción no controlada de tareas.</span><span class="sxs-lookup"><span data-stu-id="15177-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15177-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15177-121">Child Elements</span></span>  
 <span data-ttu-id="15177-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="15177-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15177-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15177-123">Parent Elements</span></span>  
  
|<span data-ttu-id="15177-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="15177-124">Element</span></span>|<span data-ttu-id="15177-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="15177-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="15177-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="15177-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="15177-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="15177-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="15177-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15177-128">Remarks</span></span>  
 <span data-ttu-id="15177-129">Si una excepción que está asociada con un <xref:System.Threading.Tasks.Task> no ha observado, no hay ningún <xref:System.Threading.Tasks.Task.Wait%2A> operación, el elemento primario no está conectado y el <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> propiedad no se ha leído la excepción de la tarea se considera inadvertida.</span><span class="sxs-lookup"><span data-stu-id="15177-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="15177-130">En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], de manera predeterminada, si un <xref:System.Threading.Tasks.Task> que tiene un inadvertido excepción es la recolección, finalizador inicia una excepción y termina el proceso.</span><span class="sxs-lookup"><span data-stu-id="15177-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="15177-131">La terminación del proceso viene determinada por el tiempo de finalización y de recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="15177-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="15177-132">Para facilitar a los desarrolladores escribir código asincrónico basado en tareas, el [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] cambia este comportamiento predeterminado para las excepciones no observadas.</span><span class="sxs-lookup"><span data-stu-id="15177-132">To make it easier for developers to write asynchronous code based on tasks, the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="15177-133">Excepciones inadvertidas provocan que el <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> evento, pero de forma predeterminada, el proceso no finaliza.</span><span class="sxs-lookup"><span data-stu-id="15177-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="15177-134">En su lugar, se omite la excepción después de que se genera el evento, independientemente de si un controlador de eventos observa la excepción.</span><span class="sxs-lookup"><span data-stu-id="15177-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="15177-135">En el [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], puede usar el [ \<ThrowUnobservedTaskExceptions > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) en un archivo de configuración para habilitar la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] comportamiento de producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="15177-135">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="15177-136">También puede especificar el comportamiento de excepción en una de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="15177-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
-   <span data-ttu-id="15177-137">Estableciendo la variable de entorno `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="15177-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
-   <span data-ttu-id="15177-138">Estableciendo el valor DWORD del Registro valor ThrowUnobservedTaskExceptions = 1 en el HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Tecla NETFramework.</span><span class="sxs-lookup"><span data-stu-id="15177-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15177-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15177-139">Example</span></span>  
 <span data-ttu-id="15177-140">El ejemplo siguiente muestra cómo habilitar el inicio de excepciones en tareas mediante el uso de un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15177-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="15177-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15177-141">Example</span></span>  
 <span data-ttu-id="15177-142">El ejemplo siguiente muestra cómo se produce una excepción no observada de una tarea.</span><span class="sxs-lookup"><span data-stu-id="15177-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="15177-143">El código debe ejecutarse como un programa de lanzamiento para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="15177-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="15177-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="15177-144">See also</span></span>

- [<span data-ttu-id="15177-145">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="15177-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="15177-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="15177-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
