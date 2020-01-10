---
title: Implementar .NET Framework y aplicaciones
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: b1ba9810b4b0d5a1688318db1093a9ce9bdf8fda
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716461"
---
# <a name="deploying-the-net-framework-and-applications"></a><span data-ttu-id="ca490-102">Implementar .NET Framework y aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ca490-102">Deploying the .NET Framework and Applications</span></span>

<span data-ttu-id="ca490-103">Este artículo le ayuda a empezar a implementar .NET Framework con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca490-103">This article helps you get started deploying the .NET Framework with your application.</span></span> <span data-ttu-id="ca490-104">La mayoría de la información está destinada a desarrolladores, OEM y administradores de empresa.</span><span class="sxs-lookup"><span data-stu-id="ca490-104">Most of the information is intended for developers, OEMs, and enterprise administrators.</span></span> <span data-ttu-id="ca490-105">Los usuarios que deseen instalar .NET Framework en sus equipos deben leer [Instalar .NET Framework](../install/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca490-105">Users who want to install the .NET Framework on their computers should read [Installing the .NET Framework](../install/index.md).</span></span>

## <a name="key-deployment-resources"></a><span data-ttu-id="ca490-106">Recursos de implementación clave</span><span class="sxs-lookup"><span data-stu-id="ca490-106">Key Deployment Resources</span></span>

<span data-ttu-id="ca490-107">Use los siguientes vínculos a otros temas de MSDN para obtener información específica sobre la implementación y mantenimiento de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca490-107">Use the following links to other MSDN topics for specific information about deploying and servicing the .NET Framework.</span></span>

<span data-ttu-id="ca490-108">**Instalación e implementación**</span><span class="sxs-lookup"><span data-stu-id="ca490-108">**Setup and deployment**</span></span>

- <span data-ttu-id="ca490-109">Información general para el instalador y la implementación:</span><span class="sxs-lookup"><span data-stu-id="ca490-109">General installer and deployment information:</span></span>

  - <span data-ttu-id="ca490-110">Opciones del instalador:</span><span class="sxs-lookup"><span data-stu-id="ca490-110">Installer options:</span></span>

    - [<span data-ttu-id="ca490-111">Instalador web</span><span class="sxs-lookup"><span data-stu-id="ca490-111">Web installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

    - [<span data-ttu-id="ca490-112">Instalador sin conexión</span><span class="sxs-lookup"><span data-stu-id="ca490-112">Offline installer</span></span>](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

  - <span data-ttu-id="ca490-113">Modos de instalación:</span><span class="sxs-lookup"><span data-stu-id="ca490-113">Installation modes:</span></span>

    - [<span data-ttu-id="ca490-114">Instalación silenciosa</span><span class="sxs-lookup"><span data-stu-id="ca490-114">Silent installation</span></span>](deployment-guide-for-developers.md#chaining_custom)

    - [<span data-ttu-id="ca490-115">Mostrar una interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="ca490-115">Displaying a UI</span></span>](deployment-guide-for-developers.md#chaining_default)

  - [<span data-ttu-id="ca490-116">Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ca490-116">Reducing system restarts during .NET Framework 4.5 installations</span></span>](reducing-system-restarts.md)

  - [<span data-ttu-id="ca490-117">Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ca490-117">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- <span data-ttu-id="ca490-118">Implementar .NET Framework con una aplicación cliente (para desarrolladores):</span><span class="sxs-lookup"><span data-stu-id="ca490-118">Deploying the .NET Framework with a client application (for developers):</span></span>

  - <span data-ttu-id="ca490-119">[Usar InstallShield](deployment-guide-for-developers.md#installshield-deployment) en un proyecto de instalación e implementación</span><span class="sxs-lookup"><span data-stu-id="ca490-119">[Using InstallShield](deployment-guide-for-developers.md#installshield-deployment) in a setup and deployment project</span></span>

  - [<span data-ttu-id="ca490-120">Usar una aplicación ClickOnce de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ca490-120">Using a Visual Studio ClickOnce application</span></span>](deployment-guide-for-developers.md#clickonce-deployment)

  - [<span data-ttu-id="ca490-121">Crear un paquete de instalación de WiX</span><span class="sxs-lookup"><span data-stu-id="ca490-121">Creating a WiX installation package</span></span>](deployment-guide-for-developers.md#wix)

  - [<span data-ttu-id="ca490-122">Usar un instalador personalizado</span><span class="sxs-lookup"><span data-stu-id="ca490-122">Using a custom installer</span></span>](deployment-guide-for-developers.md#chaining)

  - <span data-ttu-id="ca490-123">[Información adicional](deployment-guide-for-developers.md) para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="ca490-123">[Additional information](deployment-guide-for-developers.md) for developers</span></span>

- <span data-ttu-id="ca490-124">Implementar .NET Framework (para OEM y administradores):</span><span class="sxs-lookup"><span data-stu-id="ca490-124">Deploying the .NET Framework (for OEMs and administrators):</span></span>

  - [<span data-ttu-id="ca490-125">Windows Assessment and Deployment Kit (ADK)</span><span class="sxs-lookup"><span data-stu-id="ca490-125">Windows Assessment and Deployment Kit (ADK)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=254976)

  - [<span data-ttu-id="ca490-126">Guía del administrador</span><span class="sxs-lookup"><span data-stu-id="ca490-126">Administrator's guide</span></span>](guide-for-administrators.md)

<span data-ttu-id="ca490-127">**Mantenimiento**</span><span class="sxs-lookup"><span data-stu-id="ca490-127">**Servicing**</span></span>

- <span data-ttu-id="ca490-128">Para obtener información general, vea el [blog de .NET Framework](https://devblogs.microsoft.com/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="ca490-128">For general information, see the [.NET Framework blog](https://devblogs.microsoft.com/dotnet/).</span></span>

- [<span data-ttu-id="ca490-129">Detectar versiones</span><span class="sxs-lookup"><span data-stu-id="ca490-129">Detecting versions</span></span>](../migration-guide/how-to-determine-which-versions-are-installed.md)

- [<span data-ttu-id="ca490-130">Detectar Service Pack y actualizaciones</span><span class="sxs-lookup"><span data-stu-id="ca490-130">Detecting service packs and updates</span></span>](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="features-that-simplify-deployment"></a><span data-ttu-id="ca490-131">Características que simplifican la implementación</span><span class="sxs-lookup"><span data-stu-id="ca490-131">Features That Simplify Deployment</span></span>

<span data-ttu-id="ca490-132">.NET Framework proporciona algunas características básicas que facilitan la implementación de las aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="ca490-132">The .NET Framework provides a number of basic features that make it easier to deploy your applications:</span></span>

- <span data-ttu-id="ca490-133">Aplicaciones carentes de impacto.</span><span class="sxs-lookup"><span data-stu-id="ca490-133">No-impact applications.</span></span>

     <span data-ttu-id="ca490-134">Esta característica permite aislar la aplicación y eliminar conflictos de archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="ca490-134">This feature provides application isolation and eliminates DLL conflicts.</span></span> <span data-ttu-id="ca490-135">De forma predeterminada, los componentes no afectan a otras aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ca490-135">By default, components do not affect other applications.</span></span>

- <span data-ttu-id="ca490-136">Componentes privados predeterminados.</span><span class="sxs-lookup"><span data-stu-id="ca490-136">Private components by default.</span></span>

     <span data-ttu-id="ca490-137">De forma predeterminada, los componentes se implementan en el directorio de la aplicación y sólo son visibles para la aplicación en la que están incluidos.</span><span class="sxs-lookup"><span data-stu-id="ca490-137">By default, components are deployed to the application directory and are visible only to the containing application.</span></span>

- <span data-ttu-id="ca490-138">Uso compartido de código controlado.</span><span class="sxs-lookup"><span data-stu-id="ca490-138">Controlled code sharing.</span></span>

     <span data-ttu-id="ca490-139">El uso compartido de código no es el comportamiento predeterminado; para compartir código, es necesario que este quede explícitamente disponible para el uso compartido.</span><span class="sxs-lookup"><span data-stu-id="ca490-139">Code sharing requires you to explicitly make code available for sharing instead of being the default behavior.</span></span>

- <span data-ttu-id="ca490-140">Control de versiones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ca490-140">Side-by-side versioning.</span></span>

     <span data-ttu-id="ca490-141">Es posible que coexistan varias versiones de un componente o de una aplicación; el usuario puede elegir las versiones que desea utilizar, y Common Language Runtime impone la directiva de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="ca490-141">Multiple versions of a component or application can coexist, you can choose which versions to use, and the common language runtime enforces versioning policy.</span></span>

- <span data-ttu-id="ca490-142">Implementación y duplicación mediante XCOPY.</span><span class="sxs-lookup"><span data-stu-id="ca490-142">XCOPY deployment and replication.</span></span>

     <span data-ttu-id="ca490-143">Los componentes y aplicaciones autodescriptivos e independientes pueden implementarse sin entradas del Registro o dependencias.</span><span class="sxs-lookup"><span data-stu-id="ca490-143">Self-described and self-contained components and applications can be deployed without registry entries or dependencies.</span></span>

- <span data-ttu-id="ca490-144">Actualizaciones inmediatas.</span><span class="sxs-lookup"><span data-stu-id="ca490-144">On-the-fly updates.</span></span>

     <span data-ttu-id="ca490-145">Los administradores pueden utilizar servidores host, como ASP.NET, para actualizar programas de archivos DLL, incluso en equipos remotos.</span><span class="sxs-lookup"><span data-stu-id="ca490-145">Administrators can use hosts, such as ASP.NET, to update program DLLs, even on remote computers.</span></span>

- <span data-ttu-id="ca490-146">Integración con Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="ca490-146">Integration with the Windows Installer.</span></span>

     <span data-ttu-id="ca490-147">A la hora de implementar la aplicación, estarán disponibles las características de anuncio, edición, reparación e instalación a petición.</span><span class="sxs-lookup"><span data-stu-id="ca490-147">Advertisement, publishing, repair, and install-on-demand are all available when deploying your application.</span></span>

- <span data-ttu-id="ca490-148">Implementación de empresa.</span><span class="sxs-lookup"><span data-stu-id="ca490-148">Enterprise deployment.</span></span>

     <span data-ttu-id="ca490-149">Esta característica proporciona una distribución de software sencilla, que incluye el uso de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ca490-149">This feature provides easy software distribution, including using Active Directory.</span></span>

- <span data-ttu-id="ca490-150">Descarga y almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="ca490-150">Downloading and caching.</span></span>

     <span data-ttu-id="ca490-151">Las descargas incrementales reducen el tamaño de las mismas, y los componentes pueden aislarse a fin de que solo los use la aplicación para una implementación de bajo impacto.</span><span class="sxs-lookup"><span data-stu-id="ca490-151">Incremental downloads keep downloads smaller, and components can be isolated for use only by the application for low-impact deployment.</span></span>

- <span data-ttu-id="ca490-152">Código que no es de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="ca490-152">Partially trusted code.</span></span>

     <span data-ttu-id="ca490-153">La identidad no se basa en el usuario sino en el código y no aparece ningún cuadro de diálogo de certificado.</span><span class="sxs-lookup"><span data-stu-id="ca490-153">Identity is based on the code instead of the user, and no certificate dialog boxes appear.</span></span>

## <a name="packaging-and-distributing-net-framework-applications"></a><span data-ttu-id="ca490-154">Empaquetar y distribuir aplicaciones de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ca490-154">Packaging and Distributing .NET Framework Applications</span></span>

<span data-ttu-id="ca490-155">Parte de la información relacionada con el empaquetado y la implementación de .NET Framework se describe en otras secciones de la documentación.</span><span class="sxs-lookup"><span data-stu-id="ca490-155">Some of the packaging and deployment information for the .NET Framework is described in other sections of the documentation.</span></span> <span data-ttu-id="ca490-156">En esas secciones se proporciona información sobre los [ensamblados](../../standard/assembly/index.md), que son unidades autodescriptivas que no necesitan entradas del Registro, los [ensamblados con nombre seguro](../../standard/assembly/strong-named.md), que garantizan el carácter unívoco del nombre e impiden la simulación de este, y el [control de versiones de los ensamblados](../../standard/assembly/versioning.md), que aborda muchos de los problemas asociados a conflictos de archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="ca490-156">Those sections provide information about the self-describing units called [assemblies](../../standard/assembly/index.md), which require no registry entries, [strong-named assemblies](../../standard/assembly/strong-named.md), which ensure name uniqueness and prevent name spoofing, and [assembly versioning](../../standard/assembly/versioning.md), which addresses many of the problems associated with DLL conflicts.</span></span> <span data-ttu-id="ca490-157">En las siguientes secciones, se proporciona información sobre cómo se empaquetan y se distribuyen las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca490-157">The following sections provide information about packaging and distributing .NET Framework applications.</span></span>

### <a name="packaging"></a><span data-ttu-id="ca490-158">Empaquetado</span><span class="sxs-lookup"><span data-stu-id="ca490-158">Packaging</span></span>

<span data-ttu-id="ca490-159">.NET Framework proporciona las siguientes opciones para empaquetar aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="ca490-159">The .NET Framework provides the following options for packaging applications:</span></span>

- <span data-ttu-id="ca490-160">Como un solo ensamblado o como una colección de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ca490-160">As a single assembly or as a collection of assemblies.</span></span>

     <span data-ttu-id="ca490-161">Con esta opción, simplemente se emplean los archivos.dll o .exe tal y como se compilaron.</span><span class="sxs-lookup"><span data-stu-id="ca490-161">With this option, you simply use the .dll or .exe files as they were built.</span></span>

- <span data-ttu-id="ca490-162">Como archivos contenedores (CAB).</span><span class="sxs-lookup"><span data-stu-id="ca490-162">As cabinet (CAB) files.</span></span>

     <span data-ttu-id="ca490-163">Con esta opción, los archivos se comprimen en archivos .cab para disminuir el tiempo de distribución y descarga.</span><span class="sxs-lookup"><span data-stu-id="ca490-163">With this option, you compress files into .cab files to make distribution or download less time consuming.</span></span>

- <span data-ttu-id="ca490-164">Como un paquete de Microsoft Windows Installer o en otros formatos de instalación.</span><span class="sxs-lookup"><span data-stu-id="ca490-164">As a Windows Installer package or in other installer formats.</span></span>

     <span data-ttu-id="ca490-165">Con esta opción, se crean archivos .msi para usarlos con Windows Installer o se empaqueta la aplicación para utilizarla con otro instalador.</span><span class="sxs-lookup"><span data-stu-id="ca490-165">With this option, you create .msi files for use with the Windows Installer, or you package your application for use with some other installer.</span></span>

### <a name="distribution"></a><span data-ttu-id="ca490-166">Distribución</span><span class="sxs-lookup"><span data-stu-id="ca490-166">Distribution</span></span>

<span data-ttu-id="ca490-167">.NET Framework proporciona las siguientes opciones para distribuir aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="ca490-167">The .NET Framework provides the following options for distributing applications:</span></span>

- <span data-ttu-id="ca490-168">Utilizar XCOPY o FTP.</span><span class="sxs-lookup"><span data-stu-id="ca490-168">Use XCOPY or FTP.</span></span>

     <span data-ttu-id="ca490-169">Como las aplicaciones de tipo Common Language Runtime son autodescriptivas y no precisan entradas del Registro, se puede utilizar XCOPY o FTP simplemente para copiar la aplicación en un directorio adecuado.</span><span class="sxs-lookup"><span data-stu-id="ca490-169">Because common language runtime applications are self-describing and require no registry entries, you can use XCOPY or FTP to simply copy the application to an appropriate directory.</span></span> <span data-ttu-id="ca490-170">La aplicación puede entonces ejecutarse desde ese directorio.</span><span class="sxs-lookup"><span data-stu-id="ca490-170">The application can then be run from that directory.</span></span>

- <span data-ttu-id="ca490-171">Emplear descarga de código.</span><span class="sxs-lookup"><span data-stu-id="ca490-171">Use code download.</span></span>

     <span data-ttu-id="ca490-172">Si la aplicación se está distribuyendo a través de Internet o de una intranet corporativa, puede simplemente descargar el código en un equipo y ejecutar la aplicación allí mismo.</span><span class="sxs-lookup"><span data-stu-id="ca490-172">If you are distributing your application over the Internet or through a corporate intranet, you can simply download the code to a computer and run the application there.</span></span>

- <span data-ttu-id="ca490-173">Utilizar un programa de instalación como Windows Installer 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca490-173">Use an installer program such as Windows Installer 2.0.</span></span>

     <span data-ttu-id="ca490-174">Windows Installer 2.0 puede instalar, reparar o quitar ensamblados de .NET Framework de la memoria caché global de ensamblados y de directorios privados.</span><span class="sxs-lookup"><span data-stu-id="ca490-174">Windows Installer 2.0 can install, repair, or remove .NET Framework assemblies in the global assembly cache and in private directories.</span></span>

### <a name="installation-location"></a><span data-ttu-id="ca490-175">Ubicación de instalación</span><span class="sxs-lookup"><span data-stu-id="ca490-175">Installation Location</span></span>

<span data-ttu-id="ca490-176">Para determinar la ubicación donde se van a implementar los ensamblados de la aplicación para que el runtime los encuentre, vea [Cómo el motor en tiempo de ejecución ubica ensamblados](how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ca490-176">To determine where to deploy your application's assemblies so they can be found by the runtime, see [How the Runtime Locates Assemblies](how-the-runtime-locates-assemblies.md).</span></span>

<span data-ttu-id="ca490-177">Las cuestiones de seguridad pueden afectar también al modo en que se implementa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca490-177">Security considerations can also affect how you deploy your application.</span></span> <span data-ttu-id="ca490-178">Los permisos de seguridad se conceden al código administrado según la ubicación del código.</span><span class="sxs-lookup"><span data-stu-id="ca490-178">Security permissions are granted to managed code according to where the code is located.</span></span> <span data-ttu-id="ca490-179">Si se implementa una aplicación o un componente en una ubicación donde reciba poca confianza, como Internet, se verán limitadas las funciones de dicha aplicación o dicho componente.</span><span class="sxs-lookup"><span data-stu-id="ca490-179">Deploying an application or component to a location where it receives little trust, such as the Internet, limits what the application or component can do.</span></span> <span data-ttu-id="ca490-180">Para obtener más información sobre la implementación y la seguridad, vea [Conceptos básicos sobre la seguridad de acceso del código](../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="ca490-180">For more information about deployment and security considerations, see [Code Access Security Basics](../misc/code-access-security-basics.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ca490-181">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ca490-181">Related Topics</span></span>

|<span data-ttu-id="ca490-182">Title</span><span class="sxs-lookup"><span data-stu-id="ca490-182">Title</span></span>|<span data-ttu-id="ca490-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca490-183">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="ca490-184">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="ca490-184">How the Runtime Locates Assemblies</span></span>](how-the-runtime-locates-assemblies.md)|<span data-ttu-id="ca490-185">Describe la forma en que Common Language Runtime determina el ensamblado que se va a utilizar para llevar a cabo una solicitud de enlace.</span><span class="sxs-lookup"><span data-stu-id="ca490-185">Describes how the common language runtime determines which assembly to use to fulfill a binding request.</span></span>|
|[<span data-ttu-id="ca490-186">Procedimientos recomendados para cargar ensamblados</span><span class="sxs-lookup"><span data-stu-id="ca490-186">Best Practices for Assembly Loading</span></span>](best-practices-for-assembly-loading.md)|<span data-ttu-id="ca490-187">Aborda formas de evitar problemas de identidad de tipos que pueden causar errores como <xref:System.InvalidCastException> o <xref:System.MissingMethodException>, entre otros.</span><span class="sxs-lookup"><span data-stu-id="ca490-187">Discusses ways to avoid problems of type identity that can lead to <xref:System.InvalidCastException>, <xref:System.MissingMethodException>, and other errors.</span></span>|
|[<span data-ttu-id="ca490-188">Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ca490-188">Reducing System Restarts During .NET Framework 4.5 Installations</span></span>](reducing-system-restarts.md)|<span data-ttu-id="ca490-189">Describe el Administrador de reinicio, que evita, en la medida de lo posible, los reinicios del equipo y explica cómo pueden aprovecharlo las aplicaciones que instalan .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca490-189">Describes the Restart Manager, which prevents reboots whenever possible, and explains how applications that install the .NET Framework can take advantage of it.</span></span>|
|[<span data-ttu-id="ca490-190">Guía de implementación para administradores</span><span class="sxs-lookup"><span data-stu-id="ca490-190">Deployment Guide for Administrators</span></span>](guide-for-administrators.md)|<span data-ttu-id="ca490-191">Explica cómo un administrador del sistema puede implementar .NET Framework y sus dependencias del sistema en una red con Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="ca490-191">Explains how a system administrator can deploy the .NET Framework and its system dependencies across a network by using Microsoft Endpoint Configuration Manager.</span></span>|
|[<span data-ttu-id="ca490-192">Guía de implementación para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="ca490-192">Deployment Guide for Developers</span></span>](deployment-guide-for-developers.md)|<span data-ttu-id="ca490-193">Explica cómo los desarrolladores de software pueden instalar .NET Framework en los equipos de los usuarios con sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ca490-193">Explains how developers can install .NET Framework on their users' computers with their applications.</span></span>|
|[<span data-ttu-id="ca490-194">Implementar aplicaciones, servicios y componentes</span><span class="sxs-lookup"><span data-stu-id="ca490-194">Deploying Applications, Services, and Components</span></span>](/visualstudio/deployment/deploying-applications-services-and-components)|<span data-ttu-id="ca490-195">Describe las opciones de implementación de Visual Studio e incluye instrucciones para publicar una aplicación mediante las tecnologías ClickOnce y Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="ca490-195">Discusses deployment options in Visual Studio, including instructions for publishing an application using the ClickOnce and Windows Installer technologies.</span></span>|
|[<span data-ttu-id="ca490-196">Publicar aplicaciones ClickOnce</span><span class="sxs-lookup"><span data-stu-id="ca490-196">Publishing ClickOnce Applications</span></span>](/visualstudio/deployment/publishing-clickonce-applications)|<span data-ttu-id="ca490-197">Describe cómo empaquetar una aplicación de Windows Forms e implementarla con ClickOnce en los equipos cliente en una red.</span><span class="sxs-lookup"><span data-stu-id="ca490-197">Describes how to package a Windows Forms application and deploy it with ClickOnce to client computers on a network.</span></span>|
|[<span data-ttu-id="ca490-198">Empaquetar e implementar recursos</span><span class="sxs-lookup"><span data-stu-id="ca490-198">Packaging and Deploying Resources</span></span>](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|<span data-ttu-id="ca490-199">Describe el modelo de concentrador y de radio que .NET Framework usa para empaquetar e implementar los recursos; aborda las convenciones de nomenclatura de los recursos, el proceso de reserva y las alternativas de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="ca490-199">Describes the hub and spoke model that the .NET Framework uses to package and deploy resources; covers resource naming conventions, fallback process, and packaging alternatives.</span></span>|
|[<span data-ttu-id="ca490-200">Implementar una aplicación interoperativa</span><span class="sxs-lookup"><span data-stu-id="ca490-200">Deploying an Interop Application</span></span>](../interop/deploying-an-interop-application.md)|<span data-ttu-id="ca490-201">Explica cómo distribuir e instalar aplicaciones de interoperabilidad, que suelen incluir un ensamblado de cliente de .NET Framework, uno o varios ensamblados de interoperabilidad que representan diferentes bibliotecas de tipos COM, y uno o varios componentes COM registrados.</span><span class="sxs-lookup"><span data-stu-id="ca490-201">Explains how to ship and install interop applications, which typically include a .NET Framework client assembly, one or more interop assemblies representing distinct COM type libraries, and one or more registered COM components.</span></span>|
|[<span data-ttu-id="ca490-202">Cómo: Obtener el progreso del instalador de .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ca490-202">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>](how-to-get-progress-from-the-dotnet-installer.md)|<span data-ttu-id="ca490-203">Describe cómo iniciar y seguir en modo silencioso el proceso de instalación de .NET Framework, mientras se muestra la vista del progreso de la instalación.</span><span class="sxs-lookup"><span data-stu-id="ca490-203">Describes how to silently launch and track the .NET Framework setup process while showing your own view of the setup progress.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ca490-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca490-204">See also</span></span>

- [<span data-ttu-id="ca490-205">Guía de desarrollo</span><span class="sxs-lookup"><span data-stu-id="ca490-205">Development Guide</span></span>](../development-guide.md)
