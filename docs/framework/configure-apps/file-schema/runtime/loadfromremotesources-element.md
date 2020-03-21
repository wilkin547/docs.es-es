---
title: <loadFromRemoteSources> (Elemento)
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154067"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="8575a-102">\<elemento> loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="8575a-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="8575a-103">Especifica si los ensamblados cargados desde orígenes remotos deben tener plena confianza en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8575a-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8575a-104">Si se le dirigió a este artículo debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, vea [Cómo: usar un ensamblado desde la Web en Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8575a-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="8575a-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8575a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8575a-106">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="8575a-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="8575a-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span><span class="sxs-lookup"><span data-stu-id="8575a-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8575a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8575a-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8575a-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8575a-109">Attributes and elements</span></span>
 <span data-ttu-id="8575a-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8575a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8575a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8575a-111">Attributes</span></span>  
  
|<span data-ttu-id="8575a-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="8575a-112">Attribute</span></span>|<span data-ttu-id="8575a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8575a-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8575a-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8575a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="8575a-115">Especifica si se debe conceder plena confianza a un ensamblado que se carga desde un origen remoto.</span><span class="sxs-lookup"><span data-stu-id="8575a-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8575a-116">atributo habilitado</span><span class="sxs-lookup"><span data-stu-id="8575a-116">enabled attribute</span></span>  
  
|<span data-ttu-id="8575a-117">Value</span><span class="sxs-lookup"><span data-stu-id="8575a-117">Value</span></span>|<span data-ttu-id="8575a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8575a-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8575a-119">No conceda plena confianza a las aplicaciones de orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="8575a-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="8575a-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8575a-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8575a-121">Conceda plena confianza a las aplicaciones de fuentes remotas.</span><span class="sxs-lookup"><span data-stu-id="8575a-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8575a-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8575a-122">Child elements</span></span>  
 <span data-ttu-id="8575a-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8575a-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8575a-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8575a-124">Parent elements</span></span>  
  
|<span data-ttu-id="8575a-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="8575a-125">Element</span></span>|<span data-ttu-id="8575a-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="8575a-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8575a-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8575a-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8575a-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8575a-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8575a-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8575a-129">Remarks</span></span>

<span data-ttu-id="8575a-130">En .NET Framework 3.5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código del ensamblado se ejecuta en confianza parcial con un conjunto de subvenciones que depende de la zona desde la que se carga.</span><span class="sxs-lookup"><span data-stu-id="8575a-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="8575a-131">Por ejemplo, si carga un ensamblado desde un sitio web, se carga en la zona de Internet y se le concede el conjunto de permisos de Internet.</span><span class="sxs-lookup"><span data-stu-id="8575a-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="8575a-132">En otras palabras, se ejecuta en un entorno limitado de Internet.</span><span class="sxs-lookup"><span data-stu-id="8575a-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="8575a-133">A partir de .NET Framework 4, la directiva de seguridad de acceso al código (CAS) está deshabilitada y los ensamblados se cargan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="8575a-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="8575a-134">Normalmente, esto concedería plena confianza a los <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> ensamblados cargados con el método que anteriormente se había aislado.</span><span class="sxs-lookup"><span data-stu-id="8575a-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="8575a-135">Para evitar esto, la capacidad de ejecutar código en ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8575a-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="8575a-136">De forma predeterminada, si intenta cargar <xref:System.IO.FileLoadException> un ensamblado remoto, se produce un mensaje con excepción como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="8575a-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="8575a-137">Para cargar el ensamblado y ejecutar su código, debe:</span><span class="sxs-lookup"><span data-stu-id="8575a-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="8575a-138">Cree explícitamente un entorno limitado para el ensamblado (consulte [Cómo: Ejecutar código](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)de confianza parcial en un espacio aislado ).</span><span class="sxs-lookup"><span data-stu-id="8575a-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="8575a-139">Ejecute el código del ensamblado con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="8575a-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="8575a-140">Para ello, configure `<loadFromRemoteSources>` el elemento.</span><span class="sxs-lookup"><span data-stu-id="8575a-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="8575a-141">Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores de .NET Framework ahora se ejecutan en plena confianza en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8575a-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8575a-142">Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="8575a-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="8575a-143">En su lugar, <xref:System.AppDomain> cree un espacio aislado en el que cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8575a-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="8575a-144">El `enabled` atributo `<loadFromRemoteSources>` del elemento solo es efectivo cuando se deshabilita la seguridad de acceso al código (CAS).</span><span class="sxs-lookup"><span data-stu-id="8575a-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="8575a-145">De forma predeterminada, la directiva CAS está deshabilitada en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8575a-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="8575a-146">Si establece `enabled` `true`en , se concede plena confianza a los ensamblados remotos.</span><span class="sxs-lookup"><span data-stu-id="8575a-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="8575a-147">Si `enabled` no se `true`establece <xref:System.IO.FileLoadException> en , a se lanza en cualquiera de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="8575a-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="8575a-148">El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="8575a-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="8575a-149">Esto requiere que la directiva CAS se deshabilite y que el dominio actual no se va en espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="8575a-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="8575a-150">El ensamblado que se `MyComputer` está cargando no es de la zona.</span><span class="sxs-lookup"><span data-stu-id="8575a-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="8575a-151">Establecer `<loadFromRemoteSources>` el `true` elemento para evitar que se produzca esta excepción.</span><span class="sxs-lookup"><span data-stu-id="8575a-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="8575a-152">Le permite especificar que no confía en Common Language Runtime para habilitar los ensamblados cargados para la seguridad y que se les puede permitir ejecutar con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="8575a-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="8575a-153">Notas</span><span class="sxs-lookup"><span data-stu-id="8575a-153">Notes</span></span>

- <span data-ttu-id="8575a-154">En .NET Framework 4.5 y versiones posteriores, los ensamblados de recursos compartidos de red local se ejecutan con plena confianza de forma predeterminada; no es necesario habilitar `<loadFromRemoteSources>` el elemento.</span><span class="sxs-lookup"><span data-stu-id="8575a-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="8575a-155">Si una aplicación se ha copiado de la web, Windows la marca como una aplicación web, incluso si reside en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="8575a-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="8575a-156">Puede cambiar esa designación cambiando sus `<loadFromRemoteSources>` propiedades de archivo o puede usar el elemento para conceder al ensamblado plena confianza.</span><span class="sxs-lookup"><span data-stu-id="8575a-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="8575a-157">Como alternativa, puede usar <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> el método para cargar un ensamblado local que el sistema operativo ha marcado como que se ha cargado desde la web.</span><span class="sxs-lookup"><span data-stu-id="8575a-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="8575a-158">Puede obtener <xref:System.IO.FileLoadException> un en una aplicación que se ejecuta en una aplicación de PC virtual de Windows.</span><span class="sxs-lookup"><span data-stu-id="8575a-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="8575a-159">Esto puede suceder cuando intenta cargar un archivo de carpetas vinculadas en el equipo de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="8575a-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="8575a-160">También puede ocurrir cuando intenta cargar un archivo desde una carpeta vinculada a través de Servicios de [Escritorio remoto](/windows/win32/termserv/terminal-services-portal) (Servicios de Terminal Server).</span><span class="sxs-lookup"><span data-stu-id="8575a-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="8575a-161">Para evitar la `enabled` excepción, establezca en `true`.</span><span class="sxs-lookup"><span data-stu-id="8575a-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="8575a-162">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8575a-162">Configuration file</span></span>

<span data-ttu-id="8575a-163">Este elemento se utiliza normalmente en el archivo de configuración de la aplicación, pero se puede utilizar en otros archivos de configuración en función del contexto.</span><span class="sxs-lookup"><span data-stu-id="8575a-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="8575a-164">Para obtener más información, vea el artículo [Usos más implícitos de la directiva CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) en el blog de seguridad de .NET.</span><span class="sxs-lookup"><span data-stu-id="8575a-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="8575a-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8575a-165">Example</span></span>

<span data-ttu-id="8575a-166">En el ejemplo siguiente se muestra cómo conceder plena confianza a los ensamblados cargados desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="8575a-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="8575a-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8575a-167">See also</span></span>

- [<span data-ttu-id="8575a-168">Usos más implícitos de la directiva CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="8575a-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="8575a-169">Cómo: Ejecutar código de confianza parcial en un espacio aislado</span><span class="sxs-lookup"><span data-stu-id="8575a-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="8575a-170">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="8575a-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8575a-171">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8575a-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
