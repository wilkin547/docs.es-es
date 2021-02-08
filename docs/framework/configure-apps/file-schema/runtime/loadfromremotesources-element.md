---
description: 'Más información acerca de: <loadFromRemoteSources> elemento'
title: <loadFromRemoteSources> (Elemento)
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: f5dcff1fb7b0393fe5896dd9d107461a3151f79a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782356"
---
# <a name="loadfromremotesources-element"></a><span data-ttu-id="0069f-103">Elemento \<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="0069f-103">\<loadFromRemoteSources> element</span></span>

<span data-ttu-id="0069f-104">Especifica si se debe conceder plena confianza a los ensamblados cargados desde orígenes remotos en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0069f-104">Specifies whether assemblies loaded from remote sources should be granted full trust in .NET Framework 4 and later.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0069f-105">Si se le dirigió a este artículo debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, consulte [Cómo: usar un ensamblado desde la web en Visual Studio](/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0069f-105">If you were directed to this article because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a><span data-ttu-id="0069f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0069f-106">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0069f-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0069f-107">Attributes and elements</span></span>

 <span data-ttu-id="0069f-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0069f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0069f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0069f-109">Attributes</span></span>  
  
|<span data-ttu-id="0069f-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="0069f-110">Attribute</span></span>|<span data-ttu-id="0069f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="0069f-111">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="0069f-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0069f-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="0069f-113">Especifica si se debe conceder plena confianza a un ensamblado que se carga desde un origen remoto.</span><span class="sxs-lookup"><span data-stu-id="0069f-113">Specifies whether an assembly that is loaded from a remote source should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0069f-114">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="0069f-114">enabled attribute</span></span>  
  
|<span data-ttu-id="0069f-115">Value</span><span class="sxs-lookup"><span data-stu-id="0069f-115">Value</span></span>|<span data-ttu-id="0069f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0069f-116">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="0069f-117">No conceda plena confianza a las aplicaciones de orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="0069f-117">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="0069f-118">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0069f-118">This is the default.</span></span>|  
|`true`|<span data-ttu-id="0069f-119">Conceda plena confianza a las aplicaciones desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="0069f-119">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0069f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0069f-120">Child elements</span></span>  

 <span data-ttu-id="0069f-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0069f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0069f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0069f-122">Parent elements</span></span>  
  
|<span data-ttu-id="0069f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="0069f-123">Element</span></span>|<span data-ttu-id="0069f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="0069f-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0069f-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0069f-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0069f-126">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0069f-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0069f-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0069f-127">Remarks</span></span>

<span data-ttu-id="0069f-128">En el .NET Framework 3,5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el código del ensamblado se ejecuta en confianza parcial con un conjunto de permisos concedidos que depende de la zona desde la que se carga.</span><span class="sxs-lookup"><span data-stu-id="0069f-128">In the .NET Framework 3.5 and earlier versions, if you load an assembly from a remote location, code in the assembly runs in partial trust with a grant set that depends on the zone from which it is loaded.</span></span> <span data-ttu-id="0069f-129">Por ejemplo, si carga un ensamblado desde un sitio web, se carga en la zona de Internet y se le concede el conjunto de permisos de Internet.</span><span class="sxs-lookup"><span data-stu-id="0069f-129">For example, if you load an assembly from a website, it is loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="0069f-130">En otras palabras, se ejecuta en un espacio aislado de Internet.</span><span class="sxs-lookup"><span data-stu-id="0069f-130">In other words, it executes in an Internet sandbox.</span></span>

<span data-ttu-id="0069f-131">A partir de la .NET Framework 4, la Directiva de seguridad de acceso del código (CAS) está deshabilitada y los ensamblados se cargan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0069f-131">Starting with the .NET Framework 4, code access security (CAS) policy is disabled and assemblies are loaded in full trust.</span></span> <span data-ttu-id="0069f-132">Normalmente, esto concedería plena confianza a los ensamblados cargados con el <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> método que anteriormente tenía un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="0069f-132">Ordinarily, this would grant full trust to assemblies loaded with the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method that previously had been sandboxed.</span></span> <span data-ttu-id="0069f-133">Para evitar esto, la capacidad de ejecutar código en los ensamblados cargados desde un origen remoto está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0069f-133">To prevent this, the ability to run code in assemblies loaded from a remote source is disabled by default.</span></span> <span data-ttu-id="0069f-134">De forma predeterminada, si intenta cargar un ensamblado remoto, <xref:System.IO.FileLoadException> se produce una con un mensaje de excepción similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0069f-134">By default, if you attempt to load a remote assembly, a <xref:System.IO.FileLoadException> with an exception message like the following is thrown:</span></span>

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

<span data-ttu-id="0069f-135">Para cargar el ensamblado y ejecutar su código, debe:</span><span class="sxs-lookup"><span data-stu-id="0069f-135">To load the assembly and execute its code, you must either:</span></span>

- <span data-ttu-id="0069f-136">Cree explícitamente un espacio aislado para el ensamblado (consulte [Cómo: ejecutar código de confianza parcial en un espacio aislado](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span><span class="sxs-lookup"><span data-stu-id="0069f-136">Explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).</span></span>

- <span data-ttu-id="0069f-137">Ejecute el código del ensamblado con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0069f-137">Run the assembly's code in full trust.</span></span> <span data-ttu-id="0069f-138">Para ello, configure el `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0069f-138">You do this by configuring the `<loadFromRemoteSources>` element.</span></span> <span data-ttu-id="0069f-139">Le permite especificar que los ensamblados que se ejecutan en confianza parcial en versiones anteriores del .NET Framework ahora se ejecutan en plena confianza en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0069f-139">It lets you specify that the assemblies that run in partial trust in earlier versions of the .NET Framework now run in full trust in the .NET Framework 4 and later versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0069f-140">Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="0069f-140">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="0069f-141">En su lugar, cree un espacio aislado <xref:System.AppDomain> en el que cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0069f-141">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>

<span data-ttu-id="0069f-142">El `enabled` atributo del `<loadFromRemoteSources>` elemento solo es efectivo cuando está deshabilitada la seguridad de acceso del código (CAS).</span><span class="sxs-lookup"><span data-stu-id="0069f-142">The `enabled` attribute for the `<loadFromRemoteSources>` element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="0069f-143">De forma predeterminada, la Directiva CAS está deshabilitada en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="0069f-143">By default, CAS policy is disabled in the .NET Framework 4 and later versions.</span></span> <span data-ttu-id="0069f-144">Si establece `enabled` en `true` , se concederá plena confianza a los ensamblados remotos.</span><span class="sxs-lookup"><span data-stu-id="0069f-144">If you set `enabled` to `true`, remote assemblies are granted full trust.</span></span>

<span data-ttu-id="0069f-145">Si `enabled` no se establece en `true` , <xref:System.IO.FileLoadException> se produce una excepción en cualquiera de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="0069f-145">If `enabled` is not set to `true`, a <xref:System.IO.FileLoadException> is thrown under the either of the following conditions:</span></span>

- <span data-ttu-id="0069f-146">El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en el .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="0069f-146">The sandboxing behavior of the current domain is different from its behavior in the .NET Framework 3.5.</span></span> <span data-ttu-id="0069f-147">Esto requiere que la Directiva de CAS esté deshabilitada y que el dominio actual no esté en un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="0069f-147">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>

- <span data-ttu-id="0069f-148">El ensamblado que se está cargando no es de la `MyComputer` zona.</span><span class="sxs-lookup"><span data-stu-id="0069f-148">The assembly being loaded is not from the `MyComputer` zone.</span></span>

<span data-ttu-id="0069f-149">Establecer el `<loadFromRemoteSources>` elemento en `true` evita que se produzca esta excepción.</span><span class="sxs-lookup"><span data-stu-id="0069f-149">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="0069f-150">Permite especificar que no se confíe en el Common Language Runtime para crear un espacio aislado de seguridad de los ensamblados cargados y que se puedan ejecutar con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0069f-150">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute in full trust.</span></span>

## <a name="notes"></a><span data-ttu-id="0069f-151">Notas</span><span class="sxs-lookup"><span data-stu-id="0069f-151">Notes</span></span>

- <span data-ttu-id="0069f-152">En el .NET Framework 4,5 y versiones posteriores, los ensamblados de recursos compartidos de red locales se ejecutan de forma predeterminada en plena confianza. no es necesario habilitar el `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0069f-152">In the .NET Framework 4.5 and later versions, assemblies on local network shares run in full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>

- <span data-ttu-id="0069f-153">Si se ha copiado una aplicación de la web, Windows la marca como una aplicación Web, aunque se encuentre en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="0069f-153">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="0069f-154">Puede cambiar esa designación cambiando sus propiedades de archivo, o puede usar el `<loadFromRemoteSources>` elemento para conceder plena confianza al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0069f-154">You can change that designation by changing its file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="0069f-155">Como alternativa, puede utilizar el <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> método para cargar un ensamblado local que el sistema operativo ha marcado como cargado desde Internet.</span><span class="sxs-lookup"><span data-stu-id="0069f-155">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>

- <span data-ttu-id="0069f-156">Puede obtener un <xref:System.IO.FileLoadException> en una aplicación que se ejecuta en una aplicación de Windows Virtual PC.</span><span class="sxs-lookup"><span data-stu-id="0069f-156">You may get a <xref:System.IO.FileLoadException> in an application that is running in a Windows Virtual PC application.</span></span> <span data-ttu-id="0069f-157">Esto puede ocurrir cuando se intenta cargar un archivo desde carpetas vinculadas en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="0069f-157">This can happen when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="0069f-158">También se puede producir al intentar cargar un archivo desde una carpeta vinculada a través de [servicios de escritorio remoto](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span><span class="sxs-lookup"><span data-stu-id="0069f-158">It can also occur when you try to load a file from a folder linked over [Remote Desktop Services](/windows/win32/termserv/terminal-services-portal) (Terminal Services).</span></span> <span data-ttu-id="0069f-159">Para evitar la excepción, establezca `enabled` en `true` .</span><span class="sxs-lookup"><span data-stu-id="0069f-159">To avoid the exception, set `enabled` to `true`.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="0069f-160">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="0069f-160">Configuration file</span></span>

<span data-ttu-id="0069f-161">Este elemento se utiliza normalmente en el archivo de configuración de la aplicación, pero se puede usar en otros archivos de configuración en función del contexto.</span><span class="sxs-lookup"><span data-stu-id="0069f-161">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="0069f-162">Para obtener más información, vea el artículo [uso más implícito de la Directiva CAS: loadFromRemoteSources](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) en el blog de seguridad de .net.</span><span class="sxs-lookup"><span data-stu-id="0069f-162">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) in the .NET Security blog.</span></span>  

## <a name="example"></a><span data-ttu-id="0069f-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0069f-163">Example</span></span>

<span data-ttu-id="0069f-164">En el ejemplo siguiente se muestra cómo conceder plena confianza a los ensamblados cargados desde orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="0069f-164">The following example shows how to grant full trust to assemblies loaded from remote sources.</span></span>

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a><span data-ttu-id="0069f-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="0069f-165">See also</span></span>

- [<span data-ttu-id="0069f-166">Usos más implícitos de la Directiva CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="0069f-166">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [<span data-ttu-id="0069f-167">Cómo: Ejecutar código de confianza parcial en un espacio aislado</span><span class="sxs-lookup"><span data-stu-id="0069f-167">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [<span data-ttu-id="0069f-168">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0069f-168">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0069f-169">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0069f-169">Configuration File Schema</span></span>](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
