---
title: <loadFromRemoteSources> (Elemento)
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ebb32a74f5413f9c927a84ababf2d60d20e0b024
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269697"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="a56fa-102">\<loadFromRemoteSources > elemento</span><span class="sxs-lookup"><span data-stu-id="a56fa-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="a56fa-103">Especifica si los ensamblados cargados desde orígenes remotos se deben conceder plena confianza en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a56fa-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="a56fa-104">Si llega a este tema debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, véase [Cómo: Usar un ensamblado desde la Web en Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="a56fa-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="a56fa-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a56fa-105">\<configuration></span></span>  
<span data-ttu-id="a56fa-106">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a56fa-106">\<runtime></span></span>  
<span data-ttu-id="a56fa-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="a56fa-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a56fa-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a56fa-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a56fa-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a56fa-109">Attributes and elements</span></span>
 <span data-ttu-id="a56fa-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a56fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a56fa-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a56fa-111">Attributes</span></span>  
  
|<span data-ttu-id="a56fa-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="a56fa-112">Attribute</span></span>|<span data-ttu-id="a56fa-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a56fa-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a56fa-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a56fa-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="a56fa-115">Especifica si un ensamblado que se carga desde un origen remoto se debe conceder plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a56fa-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a56fa-116">atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a56fa-116">enabled attribute</span></span>  
  
|<span data-ttu-id="a56fa-117">Valor</span><span class="sxs-lookup"><span data-stu-id="a56fa-117">Value</span></span>|<span data-ttu-id="a56fa-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a56fa-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a56fa-119">No conceda a plena confianza a las aplicaciones desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="a56fa-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="a56fa-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a56fa-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a56fa-121">Conceder plena confianza a las aplicaciones desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="a56fa-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a56fa-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a56fa-122">Child elements</span></span>  
 <span data-ttu-id="a56fa-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a56fa-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a56fa-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a56fa-124">Parent elements</span></span>  
  
|<span data-ttu-id="a56fa-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="a56fa-125">Element</span></span>|<span data-ttu-id="a56fa-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="a56fa-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a56fa-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a56fa-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a56fa-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a56fa-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a56fa-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a56fa-129">Remarks</span></span>

<span data-ttu-id="a56fa-130">En .NET Framework 3.5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código en el ensamblado se ejecuta en confianza parcial con un conjunto de permisos que depende de la zona desde la que se carga.</span><span class="sxs-lookup"><span data-stu-id="a56fa-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="a56fa-131">Por ejemplo, si carga un ensamblado desde un sitio Web, se cargan en la zona de Internet y a conceder el conjunto de permisos de Internet.</span><span class="sxs-lookup"><span data-stu-id="a56fa-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="a56fa-132">En otras palabras, ejecuta en un espacio aislado de Internet.</span><span class="sxs-lookup"><span data-stu-id="a56fa-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="a56fa-133">A partir de .NET Framework 4, se deshabilita la directiva de seguridad (CA) de acceso de código y los ensamblados se cargan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a56fa-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="a56fa-134">Normalmente, esto podría conceder plena confianza a los ensamblados cargados con los <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> método que anteriormente había sido en espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="a56fa-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="a56fa-135">Para evitar esto, la capacidad para ejecutar código en los ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a56fa-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="a56fa-136">De forma predeterminada, si intenta cargar un ensamblado remoto, un <xref:System.IO.FileLoadException> con un mensaje de excepción que se produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a56fa-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="a56fa-137">Para cargar el ensamblado y ejecutar su código, debe:</span><span class="sxs-lookup"><span data-stu-id="a56fa-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="a56fa-138">Cree explícitamente un espacio aislado para el ensamblado (vea [Cómo: Ejecutar código de confianza parcial en un recinto](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="a56fa-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="a56fa-139">Ejecutar código de ensamblado de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a56fa-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="a56fa-140">Ello, configure el `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a56fa-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="a56fa-141">Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores de .NET Framework ahora se ejecutan con plena confianza en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a56fa-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a56fa-142">Si el ensamblado no se ejecutará con plena confianza, no establezca este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="a56fa-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="a56fa-143">En su lugar, cree un espacio aislado <xref:System.AppDomain> en el que se va a cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a56fa-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="a56fa-144">El `enabled` atributo para el `<loadFromRemoteSources>` elemento es efectiva únicamente cuando seguridad de acceso del código (CAS) está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a56fa-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="a56fa-145">De forma predeterminada, la directiva CAS está deshabilitada en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a56fa-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="a56fa-146">Si establece `enabled` a `true`, ensamblados remotos gozan de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a56fa-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="a56fa-147">Si `enabled` no está establecido en `true`, un <xref:System.IO.FileLoadException> se produce en cualquiera de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a56fa-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="a56fa-148">El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="a56fa-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="a56fa-149">Esto requiere la directiva CAS va a deshabilitar y el dominio actual que no sea espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="a56fa-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="a56fa-150">El ensamblado que se está cargando no es de la `MyComputer` zona.</span><span class="sxs-lookup"><span data-stu-id="a56fa-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="a56fa-151">Establecer el `<loadFromRemoteSources>` elemento `true` impide que se produzca esta excepción.</span><span class="sxs-lookup"><span data-stu-id="a56fa-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="a56fa-152">Permite especificar que no se basa en common language runtime para el espacio aislado los ensamblados cargados por seguridad, y que puede ser pueden ejecutarse en plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a56fa-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="a56fa-153">Notas</span><span class="sxs-lookup"><span data-stu-id="a56fa-153">Notes</span></span>

- <span data-ttu-id="a56fa-154">En .NET Framework 4.5 y versiones posteriores, los ensamblados de recursos compartidos de red local se ejecutan con plena confianza de forma predeterminada; no es necesario que habilitar el `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="a56fa-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="a56fa-155">Si una aplicación se ha copiado desde la web, se marca por Windows como una aplicación web, incluso si se encuentra en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a56fa-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="a56fa-156">Puede cambiar esa designación cambiando sus propiedades de archivo, o puede usar el `<loadFromRemoteSources>` elemento que se va a conceder el ensamblado de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a56fa-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="a56fa-157">Como alternativa, puede usar el <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> método para cargar un ensamblado local que el sistema operativo ha marcado como cargado desde la web.</span><span class="sxs-lookup"><span data-stu-id="a56fa-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="a56fa-158">Es posible que obtenga un <xref:System.IO.FileLoadException> en una aplicación que se ejecuta en una aplicación de Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="a56fa-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="a56fa-159">Esto puede ocurrir cuando se intenta cargar un archivo de carpetas vinculadas en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="a56fa-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="a56fa-160">También puede producirse cuando intenta cargar un archivo desde una carpeta vinculada sobre [servicios de escritorio remoto](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span><span class="sxs-lookup"><span data-stu-id="a56fa-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="a56fa-161">Para evitar la excepción, establezca `enabled` a `true`.</span><span class="sxs-lookup"><span data-stu-id="a56fa-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="a56fa-162">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a56fa-162">Configuration file</span></span>

<span data-ttu-id="a56fa-163">Este elemento se utiliza normalmente en el archivo de configuración de aplicación, pero se puede usar en otros archivos de configuración según el contexto.</span><span class="sxs-lookup"><span data-stu-id="a56fa-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="a56fa-164">Para obtener más información, vea el artículo [más implícita usa de la directiva CAS: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) en el blog de seguridad. NET.</span><span class="sxs-lookup"><span data-stu-id="a56fa-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="a56fa-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a56fa-165">Example</span></span>

<span data-ttu-id="a56fa-166">El ejemplo siguiente muestra cómo conceder plena confianza a los ensamblados cargados desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="a56fa-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="a56fa-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="a56fa-167">See also</span></span>

- [<span data-ttu-id="a56fa-168">Los usos más implícitos de la directiva CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="a56fa-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [<span data-ttu-id="a56fa-169">Cómo: Ejecutar código de confianza parcial en un espacio aislado</span><span class="sxs-lookup"><span data-stu-id="a56fa-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="a56fa-170">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a56fa-170">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a56fa-171">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a56fa-171">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
