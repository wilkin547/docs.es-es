---
title: <loadFromRemoteSources> (Elemento)
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: 454314bf1002a9648f669cc708c8ac42461fccaf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452271"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="3a906-102">\<elemento > loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="3a906-102">\<loadFromRemoteSources> element</span></span>
<span data-ttu-id="3a906-103">Especifica si se debe conceder plena confianza a los ensamblados cargados desde orígenes remotos en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3a906-103">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a906-104">Si se le dirigió a este artículo debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, consulte [Cómo: usar un ensamblado desde la web en Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3a906-104">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
<span data-ttu-id="3a906-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a906-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a906-106">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a906-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3a906-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<loadFromRemoteSources >**</span><span class="sxs-lookup"><span data-stu-id="3a906-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a906-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a906-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a906-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a906-109">Attributes and elements</span></span>
 <span data-ttu-id="3a906-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a906-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a906-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a906-111">Attributes</span></span>  
  
|<span data-ttu-id="3a906-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="3a906-112">Attribute</span></span>|<span data-ttu-id="3a906-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a906-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3a906-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3a906-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3a906-115">Especifica si se debe conceder plena confianza a un ensamblado que se carga desde un origen remoto.</span><span class="sxs-lookup"><span data-stu-id="3a906-115">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3a906-116">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="3a906-116">enabled attribute</span></span>  
  
|<span data-ttu-id="3a906-117">Value</span><span class="sxs-lookup"><span data-stu-id="3a906-117">Value</span></span>|<span data-ttu-id="3a906-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a906-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3a906-119">No conceda plena confianza a las aplicaciones de orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="3a906-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="3a906-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3a906-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="3a906-121">Conceda plena confianza a las aplicaciones desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="3a906-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a906-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a906-122">Child elements</span></span>  
 <span data-ttu-id="3a906-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a906-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a906-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a906-124">Parent elements</span></span>  
  
|<span data-ttu-id="3a906-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a906-125">Element</span></span>|<span data-ttu-id="3a906-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a906-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3a906-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a906-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3a906-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3a906-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a906-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3a906-129">Remarks</span></span>

<span data-ttu-id="3a906-130">En el .NET Framework 3,5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código del ensamblado se ejecuta en confianza parcial con un conjunto de permisos concedidos que depende de la zona desde la que se carga.</span><span class="sxs-lookup"><span data-stu-id="3a906-130">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="3a906-131">Por ejemplo, si carga un ensamblado desde un sitio web, se carga en la zona de Internet y se le concede el conjunto de permisos de Internet.</span><span class="sxs-lookup"><span data-stu-id="3a906-131">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="3a906-132">En otras palabras, se ejecuta en un espacio aislado de Internet.</span><span class="sxs-lookup"><span data-stu-id="3a906-132">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="3a906-133">A partir de la .NET Framework 4, la Directiva de seguridad de acceso del código (CAS) está deshabilitada y los ensamblados se cargan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="3a906-133">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="3a906-134">Normalmente, esto concedería plena confianza a los ensamblados cargados con el método de <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> que anteriormente tenía un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="3a906-134">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="3a906-135">Para evitar esto, la capacidad de ejecutar código en los ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3a906-135">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="3a906-136">De forma predeterminada, si intenta cargar un ensamblado remoto, se produce una <xref:System.IO.FileLoadException> con un mensaje de excepción similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a906-136">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

<span data-ttu-id="3a906-137">Para cargar el ensamblado y ejecutar su código, debe:</span><span class="sxs-lookup"><span data-stu-id="3a906-137">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="3a906-138">Cree explícitamente un espacio aislado para el ensamblado (consulte [Cómo: ejecutar código de confianza parcial en un espacio aislado](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="3a906-138">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="3a906-139">Ejecute el código del ensamblado con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="3a906-139">Run the assembly's code in full trust.</span></span> <span data-ttu-id="3a906-140">Para ello, configure el elemento `<loadFromRemoteSources>`.</span><span class="sxs-lookup"><span data-stu-id="3a906-140">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="3a906-141">Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores del .NET Framework ahora se ejecutan en plena confianza en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3a906-141">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a906-142">Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a906-142">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="3a906-143">En su lugar, cree un <xref:System.AppDomain> en espacio aislado en el que cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3a906-143">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="3a906-144">El atributo `enabled` del elemento `<loadFromRemoteSources>` solo es efectivo cuando está deshabilitada la seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="3a906-144">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="3a906-145">De forma predeterminada, la Directiva CAS está deshabilitada en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3a906-145">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="3a906-146">Si establece `enabled` en `true`, se concederá plena confianza a los ensamblados remotos.</span><span class="sxs-lookup"><span data-stu-id="3a906-146">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="3a906-147">Si `enabled` no se establece en `true`, se produce una <xref:System.IO.FileLoadException> en cualquiera de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="3a906-147">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="3a906-148">El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en el .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="3a906-148">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="3a906-149">Esto requiere que la Directiva de CAS esté deshabilitada y que el dominio actual no esté en un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="3a906-149">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="3a906-150">El ensamblado que se está cargando no es de la zona `MyComputer`.</span><span class="sxs-lookup"><span data-stu-id="3a906-150">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="3a906-151">Establecer el elemento de `<loadFromRemoteSources>` en `true` impide que se inicie esta excepción.</span><span class="sxs-lookup"><span data-stu-id="3a906-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="3a906-152">Permite especificar que no se confíe en el Common Language Runtime para crear un espacio aislado de seguridad de los ensamblados cargados y que se puedan ejecutar con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="3a906-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="3a906-153">Notas</span><span class="sxs-lookup"><span data-stu-id="3a906-153">Notes</span></span>

- <span data-ttu-id="3a906-154">En el .NET Framework 4,5 y versiones posteriores, los ensamblados de recursos compartidos de red locales se ejecutan de forma predeterminada en plena confianza. no es necesario habilitar el elemento `<loadFromRemoteSources>`.</span><span class="sxs-lookup"><span data-stu-id="3a906-154">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="3a906-155">Si se ha copiado una aplicación de la web, Windows la marca como una aplicación Web, aunque se encuentre en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="3a906-155">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="3a906-156">Puede cambiar esa designación cambiando sus propiedades de archivo, o puede usar el elemento `<loadFromRemoteSources>` para conceder plena confianza al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3a906-156">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="3a906-157">Como alternativa, puede utilizar el método <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> para cargar un ensamblado local que el sistema operativo ha marcado como cargado desde Internet.</span><span class="sxs-lookup"><span data-stu-id="3a906-157">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="3a906-158">Puede obtener un <xref:System.IO.FileLoadException> en una aplicación que se ejecuta en una aplicación de Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="3a906-158">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="3a906-159">Esto puede ocurrir cuando se intenta cargar un archivo desde carpetas vinculadas en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="3a906-159">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="3a906-160">También se puede producir al intentar cargar un archivo desde una carpeta vinculada a través de [servicios de escritorio remoto](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span><span class="sxs-lookup"><span data-stu-id="3a906-160">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="3a906-161">Para evitar la excepción, establezca `enabled` en `true`.</span><span class="sxs-lookup"><span data-stu-id="3a906-161">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="3a906-162">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="3a906-162">Configuration file</span></span>

<span data-ttu-id="3a906-163">Este elemento se utiliza normalmente en el archivo de configuración de la aplicación, pero se puede usar en otros archivos de configuración en función del contexto.</span><span class="sxs-lookup"><span data-stu-id="3a906-163">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="3a906-164">Para obtener más información, vea el artículo [uso más implícito de la Directiva CAS: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) en el blog de seguridad de .net.</span><span class="sxs-lookup"><span data-stu-id="3a906-164">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="3a906-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a906-165">Example</span></span>

<span data-ttu-id="3a906-166">En el ejemplo siguiente se muestra cómo conceder plena confianza a los ensamblados cargados desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="3a906-166">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="3a906-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a906-167">See also</span></span>

- [<span data-ttu-id="3a906-168">Usos más implícitos de la Directiva CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="3a906-168">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="3a906-169">Cómo: Ejecutar código de confianza parcial en un espacio aislado</span><span class="sxs-lookup"><span data-stu-id="3a906-169">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="3a906-170">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3a906-170">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3a906-171">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3a906-171">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
