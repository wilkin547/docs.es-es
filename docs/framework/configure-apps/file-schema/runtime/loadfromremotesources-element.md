---
title: '&lt;loadFromRemoteSources&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13b42405a0faf721c46476aadaa0cff8163883c1
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="cffe5-102">&lt;loadFromRemoteSources&gt; Element</span><span class="sxs-lookup"><span data-stu-id="cffe5-102">&lt;loadFromRemoteSources&gt; Element</span></span>
<span data-ttu-id="cffe5-103">Especifica si los ensamblados de orígenes remotos se deben conceder plena confianza.</span><span class="sxs-lookup"><span data-stu-id="cffe5-103">Specifies whether assemblies from remote sources should be granted full trust.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cffe5-104">Si llega a este tema debido a un mensaje de error en la lista de errores del proyecto de Visual Studio o un error de compilación, consulte [Cómo: usar un ensamblado desde el Web en Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span><span class="sxs-lookup"><span data-stu-id="cffe5-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="cffe5-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cffe5-105">\<configuration></span></span>  
<span data-ttu-id="cffe5-106">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="cffe5-106">\<runtime></span></span>  
<span data-ttu-id="cffe5-107">\<loadFromRemoteSources></span><span class="sxs-lookup"><span data-stu-id="cffe5-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cffe5-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cffe5-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cffe5-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cffe5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cffe5-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cffe5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cffe5-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="cffe5-111">Attributes</span></span>  
  
|<span data-ttu-id="cffe5-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="cffe5-112">Attribute</span></span>|<span data-ttu-id="cffe5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cffe5-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="cffe5-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="cffe5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="cffe5-115">Especifica si un ensamblado que se carga desde orígenes remotos se debe conceder plena confianza.</span><span class="sxs-lookup"><span data-stu-id="cffe5-115">Specifies whether an assembly that is loaded from remote sources should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cffe5-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="cffe5-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="cffe5-117">Valor</span><span class="sxs-lookup"><span data-stu-id="cffe5-117">Value</span></span>|<span data-ttu-id="cffe5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="cffe5-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="cffe5-119">¿Concede plena confianza a las aplicaciones de orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="cffe5-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="cffe5-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cffe5-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="cffe5-121">Conceder plena confianza a las aplicaciones de orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="cffe5-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cffe5-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cffe5-122">Child Elements</span></span>  
 <span data-ttu-id="cffe5-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cffe5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cffe5-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cffe5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cffe5-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cffe5-125">Element</span></span>|<span data-ttu-id="cffe5-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="cffe5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cffe5-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cffe5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cffe5-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cffe5-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cffe5-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cffe5-129">Remarks</span></span>  
 <span data-ttu-id="cffe5-130">En la versión de .NET Framework 3.5 y versiones anteriores, si carga un ensamblado desde una ubicación remota, el ensamblado se ejecutaba con confianza parcial con un conjunto de permisos que dependía de la zona en la que se cargó.</span><span class="sxs-lookup"><span data-stu-id="cffe5-130">In the .NET Framework version 3.5 and earlier versions, if you loaded an assembly from a remote location, the assembly would run partially trusted with a grant set that depended on the zone in which it was loaded.</span></span> <span data-ttu-id="cffe5-131">Por ejemplo, si carga un ensamblado desde un sitio Web, se ha cargado en la zona de Internet y le concede el conjunto de permisos de Internet.</span><span class="sxs-lookup"><span data-stu-id="cffe5-131">For example, if you loaded an assembly from a website, it was loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="cffe5-132">En otras palabras, ejecuta en un espacio aislado de Internet.</span><span class="sxs-lookup"><span data-stu-id="cffe5-132">In other words, it executed in an Internet sandbox.</span></span> <span data-ttu-id="cffe5-133">Si intenta ejecutar ese ensamblado en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores, se produce una excepción, debe crear explícitamente un espacio aislado para el ensamblado (vea [Cómo: ejecutar código de confianza parcial en un espacio aislado](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), o se ejecuta con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="cffe5-133">If you try to run that assembly in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later versions, an exception is thrown; you must either explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), or run it in full trust.</span></span>  
  
 <span data-ttu-id="cffe5-134">El `<loadFromRemoteSources>` elemento le permite especificar que los ensamblados que se hubieran producido confianza parcial en versiones anteriores de .NET Framework deben ejecutar como de plena confianza en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="cffe5-134">The `<loadFromRemoteSources>` element lets you specify that the assemblies that would have run partially trusted in earlier versions of the .NET Framework are to be run fully trusted in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="cffe5-135">De forma predeterminada, los ensamblados remotos no se ejecutan en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="cffe5-135">By default, remote assemblies do not run in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span> <span data-ttu-id="cffe5-136">Para ejecutar un ensamblado remoto, debe ejecutar como de plena confianza o crear un espacio aislado <xref:System.AppDomain> en el que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="cffe5-136">To run a remote assembly, you must either run it as fully trusted or create a sandboxed <xref:System.AppDomain> in which to run it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cffe5-137">En el [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], ensamblados a los recursos compartidos de red local se ejecutan como de plena confianza de forma predeterminada; no es necesario habilitar la `<loadFromRemoteSources>` elemento.</span><span class="sxs-lookup"><span data-stu-id="cffe5-137">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], assemblies on local network shares are run as full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cffe5-138">Si una aplicación se ha copiado desde el sitio web, se marca por Windows como una aplicación web, incluso si se encuentra en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="cffe5-138">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="cffe5-139">Puede cambiar esa designación cambiando las propiedades del archivo, o puede usar el `<loadFromRemoteSources>` elemento que se va a conceder el ensamblado de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="cffe5-139">You can change that designation by changing the file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="cffe5-140">Como alternativa, puede utilizar el <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> método para cargar un ensamblado local que el sistema operativo haya marcado como se ha cargado desde la web.</span><span class="sxs-lookup"><span data-stu-id="cffe5-140">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>  
  
 <span data-ttu-id="cffe5-141">El `enabled` de atributo para este elemento es efectivo únicamente cuando la seguridad de acceso del código (CAS) está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="cffe5-141">The `enabled` attribute for this element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="cffe5-142">De forma predeterminada, la directiva CAS está deshabilitada en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="cffe5-142">By default, CAS policy is disabled in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="cffe5-143">Si establece `enabled` a `true`, aplicaciones remotas gozan de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="cffe5-143">If you set `enabled` to `true`, remote applications are granted full trust.</span></span>  
  
 <span data-ttu-id="cffe5-144">Si `<loadFromRemoteSources>``enabled` no está establecido en `true`, se produce una excepción en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="cffe5-144">If `<loadFromRemoteSources>``enabled` is not set to `true`, an exception is thrown under the following conditions:</span></span>  
  
-   <span data-ttu-id="cffe5-145">El comportamiento de espacio aislado del dominio actual es diferente de su comportamiento en el [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cffe5-145">The sandboxing behavior of the current domain is different from its behavior in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span> <span data-ttu-id="cffe5-146">Esto requiere la directiva de entidades emisoras de certificados que se deshabilite y el dominio actual no sea en un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="cffe5-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>  
  
-   <span data-ttu-id="cffe5-147">No es el ensamblado que se va a cargar desde el `MyComputer` zona.</span><span class="sxs-lookup"><span data-stu-id="cffe5-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cffe5-148">Es posible que obtenga un <xref:System.IO.FileLoadException> en una aplicación de Windows Virtual PC cuando se intenta cargar un archivo desde carpetas vinculadas en el equipo que hospeda.</span><span class="sxs-lookup"><span data-stu-id="cffe5-148">You may get a <xref:System.IO.FileLoadException> in a Windows Virtual PC application when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="cffe5-149">Este error también puede producirse al intentar cargar un archivo desde una carpeta vinculada sobre [servicios de escritorio remoto](http://go.microsoft.com/fwlink/?LinkId=182775) (servicios de Terminal Server).</span><span class="sxs-lookup"><span data-stu-id="cffe5-149">This error may also occur when you try to load a file from a folder linked over [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="cffe5-150">Para evitar la excepción, establezca `enabled` a `true`.</span><span class="sxs-lookup"><span data-stu-id="cffe5-150">To avoid the exception, set `enabled` to `true`.</span></span>  
  
 <span data-ttu-id="cffe5-151">Establecer el `<loadFromRemoteSources>` elemento `true` impide que se produzca esta excepción.</span><span class="sxs-lookup"><span data-stu-id="cffe5-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="cffe5-152">Le permite especificar que no se basa en common language runtime para el espacio aislado los ensamblados cargados por seguridad y que se pueden ejecutar como de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="cffe5-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute as full trust.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cffe5-153">Si el ensamblado no debe ejecutarse con plena confianza, no establezca este elemento de configuración.</span><span class="sxs-lookup"><span data-stu-id="cffe5-153">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="cffe5-154">En su lugar, cree un espacio aislado <xref:System.AppDomain> en el que se va a cargar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cffe5-154">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="cffe5-155">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="cffe5-155">Configuration File</span></span>  
 <span data-ttu-id="cffe5-156">Este elemento se utiliza normalmente en el archivo de configuración de aplicación, pero puede utilizarse en otros archivos de configuración según el contexto.</span><span class="sxs-lookup"><span data-stu-id="cffe5-156">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="cffe5-157">Para obtener más información, vea el artículo [más implícita usa de la directiva CAS: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) en el blog de seguridad de. NET.</span><span class="sxs-lookup"><span data-stu-id="cffe5-157">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cffe5-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cffe5-158">Example</span></span>  
 <span data-ttu-id="cffe5-159">En el ejemplo siguiente se muestra cómo conceder plena confianza a las aplicaciones de orígenes remotos.</span><span class="sxs-lookup"><span data-stu-id="cffe5-159">The following example shows how to grant full trust to applications from remote sources.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cffe5-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="cffe5-160">See Also</span></span>  
 [<span data-ttu-id="cffe5-161">Los usos más implícitos de directiva CAS: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="cffe5-161">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [<span data-ttu-id="cffe5-162">Cómo: Ejecutar código de confianza parcial en un espacio aislado</span><span class="sxs-lookup"><span data-stu-id="cffe5-162">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="cffe5-163">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="cffe5-163">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="cffe5-164">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="cffe5-164">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
