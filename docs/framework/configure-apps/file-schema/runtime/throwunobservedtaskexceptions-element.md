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
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="8b2f8-102">\<Elemento de> ThrowUnobservedTaskExceptions</span><span class="sxs-lookup"><span data-stu-id="8b2f8-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="8b2f8-103">Especifica si las excepciones de tareas no controladas deben finalizar un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
<span data-ttu-id="8b2f8-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8b2f8-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="8b2f8-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="8b2f8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span><span class="sxs-lookup"><span data-stu-id="8b2f8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2f8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b2f8-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b2f8-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8b2f8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8b2f8-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b2f8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8b2f8-110">Attributes</span></span>  
  
|<span data-ttu-id="8b2f8-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="8b2f8-111">Attribute</span></span>|<span data-ttu-id="8b2f8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b2f8-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8b2f8-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8b2f8-114">Especifica si las excepciones de tarea no controladas deben terminar el proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8b2f8-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="8b2f8-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8b2f8-116">Value</span><span class="sxs-lookup"><span data-stu-id="8b2f8-116">Value</span></span>|<span data-ttu-id="8b2f8-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b2f8-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8b2f8-118">No termina el proceso de ejecución para una excepción de tarea no controlada.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="8b2f8-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8b2f8-120">Termina el proceso de ejecución para una excepción de tarea no controlada.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b2f8-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8b2f8-121">Child Elements</span></span>  
 <span data-ttu-id="8b2f8-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b2f8-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8b2f8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8b2f8-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b2f8-124">Element</span></span>|<span data-ttu-id="8b2f8-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b2f8-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8b2f8-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8b2f8-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="8b2f8-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8b2f8-128">Remarks</span></span>  
 <span data-ttu-id="8b2f8-129">Si no se ha <xref:System.Threading.Tasks.Task> observado una excepción asociada <xref:System.Threading.Tasks.Task.Wait%2A> a una, no hay ninguna <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> operación, el elemento primario no está asociado y la propiedad no se leyó la excepción de tarea se considera que no se observa.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="8b2f8-130">En .NET Framework 4, de <xref:System.Threading.Tasks.Task> forma predeterminada, si se recopila una excepción no observada, el finalizador produce una excepción y finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="8b2f8-131">La terminación del proceso viene determinada por el momento de la recolección y finalización de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="8b2f8-132">Para facilitar a los desarrolladores escribir código asincrónico basado en tareas, .NET Framework 4.5 cambia este comportamiento predeterminado para las excepciones no observadas.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="8b2f8-133">Las excepciones no observadas siguen provocando que se genere el <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> evento, pero de forma predeterminada, el proceso no finaliza.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="8b2f8-134">En su lugar, la excepción se omite después de que se genera el evento, independientemente de si un controlador de eventos observa la excepción.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="8b2f8-135">En .NET Framework 4.5, puede usar el [ \<elemento de> ThrowUnobservedTaskExceptions](throwunobservedtaskexceptions-element.md) en un archivo de configuración de aplicación para habilitar el comportamiento de .NET Framework 4 de producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="8b2f8-136">También puede especificar el comportamiento de excepción de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="8b2f8-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="8b2f8-137">Estableciendo la `COMPlus_ThrowUnobservedTaskExceptions` variable`set COMPlus_ThrowUnobservedTaskExceptions=1`de entorno ( ).</span><span class="sxs-lookup"><span data-stu-id="8b2f8-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="8b2f8-138">Al establecer el valor DWORD del Registro ThrowUnobservedTaskExceptions\\, en el HKEY_LOCAL_MACHINE,SOFTWARE, Microsoft . Clave NETFramework.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b2f8-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b2f8-139">Example</span></span>  
 <span data-ttu-id="8b2f8-140">En el ejemplo siguiente se muestra cómo habilitar el lanzamiento de excepciones en tareas mediante un archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="8b2f8-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8b2f8-141">Example</span></span>  
 <span data-ttu-id="8b2f8-142">En el ejemplo siguiente se muestra cómo se produce una excepción no observada desde una tarea.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="8b2f8-143">El código debe ejecutarse como un programa liberado para que funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b2f8-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8b2f8-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b2f8-144">See also</span></span>

- [<span data-ttu-id="8b2f8-145">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="8b2f8-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8b2f8-146">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8b2f8-146">Configuration File Schema</span></span>](../index.md)
