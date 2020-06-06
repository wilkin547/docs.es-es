---
title: Esquema de los archivos de configuración de .NET Framework
ms.date: 05/01/2017
helpviewer_keywords:
- .NET Framework application configuration, configuration schema
- machine configuration files
- application configuration files, schema
- app.config files, schema
- schema configuration settings
- schemas, configuration settings
- enterprisesec.config files
- well-formed XML
- enterprisesec configuration files
- security.config files
- security [.NET Framework], configuration files
- application development [.NET Framework], schema
- XML tags
- container tags
- machine.config files
- configuration schema [.NET Framework]
- configuration settings [.NET Framework], applications
- configuration file reference [.NET Framework]
ms.assetid: 69003d39-dc8a-460c-a6be-e6d93e690b38
ms.openlocfilehash: 35ed53fc480e218df595794f80af2458f3ecec38
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73039161"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="eb20f-102">Esquema de los archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eb20f-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="eb20f-103">Los archivos de configuración son archivos XML estándar que se pueden utilizar para cambiar configuraciones y establecer directivas para las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb20f-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="eb20f-104">El esquema de configuración de .NET Framework se compone de elementos que se pueden usar en los archivos de configuración para controlar el comportamiento de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eb20f-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="eb20f-105">La tabla de contenido de esta sección refleja la jerarquía de esquema para el inicio, el tiempo de ejecución, la red y otros tipos de valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="eb20f-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="eb20f-106">Para obtener información sobre los tipos, el formato y la ubicación de los archivos de configuración, vea [Configurar aplicaciones](../index.md).</span><span class="sxs-lookup"><span data-stu-id="eb20f-106">For information about the types, format, and location of configuration files, see [Configure apps](../index.md).</span></span> <span data-ttu-id="eb20f-107">Familiarícese con XML para editar los archivos de configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="eb20f-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb20f-108">En los atributos y etiquetas XML de los archivos de configuración se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="eb20f-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="eb20f-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eb20f-109">In this section</span></span>

<span data-ttu-id="eb20f-110">[**\<configuration>** Element](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-110">[**\<configuration>** Element](configuration-element.md)</span></span>\
<span data-ttu-id="eb20f-111">Elemento de nivel superior para todos los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="eb20f-111">The top-level element for all configuration files.</span></span>

<span data-ttu-id="eb20f-112">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-112">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="eb20f-113">Especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="eb20f-113">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="eb20f-114">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-114">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md)</span></span>\
<span data-ttu-id="eb20f-115">Especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="eb20f-115">Specifies a configuration file to include.</span></span>

<span data-ttu-id="eb20f-116">[Esquema de configuración de inicio](./startup/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-116">[Startup Settings Schema](./startup/index.md)</span></span>\
<span data-ttu-id="eb20f-117">Elementos que especifican la versión de Common Language Runtime que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="eb20f-117">Elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="eb20f-118">[Esquema de configuración en tiempo de ejecución](./runtime/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-118">[Runtime Settings Schema](./runtime/index.md)</span></span>\
<span data-ttu-id="eb20f-119">Elementos que configuran el enlace de ensamblado y el comportamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="eb20f-119">Elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="eb20f-120">[Esquema de configuración de red](./network/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-120">[Network Settings Schema](./network/index.md)</span></span>\
<span data-ttu-id="eb20f-121">Elementos que especifican cómo se conecta el .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="eb20f-121">Elements that specify how the .NET Framework connects to the internet.</span></span>

<span data-ttu-id="eb20f-122">[Esquema de configuración de criptografía](./cryptography/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-122">[Cryptography Settings Schema](./cryptography/index.md)</span></span>\
<span data-ttu-id="eb20f-123">Elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="eb20f-123">Elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="eb20f-124">[Esquema de secciones de configuración](configuration-sections-schema.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-124">[Configuration Sections Schema](configuration-sections-schema.md)</span></span>\
<span data-ttu-id="eb20f-125">Elementos usados para crear y usar secciones de configuración para la configuración personalizada.</span><span class="sxs-lookup"><span data-stu-id="eb20f-125">Elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="eb20f-126">[Esquema de configuración de seguimiento y depuración](./trace-debug/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-126">[Trace and Debug Settings Schema](./trace-debug/index.md)</span></span>\
<span data-ttu-id="eb20f-127">Elementos que especifican modificadores y agentes de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb20f-127">Elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="eb20f-128">[Esquema de configuración de proveedor de lenguaje y compilador](./compiler/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-128">[Compiler and Language Provider Settings Schema](./compiler/index.md)</span></span>\
<span data-ttu-id="eb20f-129">Elementos que especifican la configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="eb20f-129">Elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="eb20f-130">[Esquema de configuración de la aplicación](application-settings-schema.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-130">[Application Settings Schema](application-settings-schema.md)</span></span>\
<span data-ttu-id="eb20f-131">Elementos que permiten a una aplicación Windows Forms o ASP.NET almacenar y recuperar valores de ámbito de aplicación y de ámbito de usuario.</span><span class="sxs-lookup"><span data-stu-id="eb20f-131">Elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="eb20f-132">[Esquema de configuración de la aplicación](./appsettings/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-132">[App Settings Schema](./appsettings/index.md)</span></span>\
<span data-ttu-id="eb20f-133">Contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="eb20f-133">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="eb20f-134">[Esquema de configuración Web](./web/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-134">[Web Settings Schema](./web/index.md)</span></span>\
<span data-ttu-id="eb20f-135">Elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="eb20f-135">Elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="eb20f-136">Se usa en los archivos *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="eb20f-136">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="eb20f-137">[Windows Forms esquema de configuración](winforms/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-137">[Windows Forms Configuration Schema](winforms/index.md)</span></span>\
<span data-ttu-id="eb20f-138">Todos los elementos de la sección de configuración de la aplicación Windows Forms, que incluye personalizaciones como la compatibilidad con varios monitores y con un alto valor de PPP.</span><span class="sxs-lookup"><span data-stu-id="eb20f-138">All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high-DPI support.</span></span>

<span data-ttu-id="eb20f-139">[Esquema de configuración de WCF](./wcf/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-139">[WCF Configuration Schema](./wcf/index.md)</span></span>\
<span data-ttu-id="eb20f-140">Todos los elementos que le permiten configurar el servicio WCF y las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="eb20f-140">All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="eb20f-141">[Sintaxis de directivas WCF](./wcf-directive/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-141">[WCF Directive Syntax](./wcf-directive/index.md)</span></span>\
<span data-ttu-id="eb20f-142">Describe la `@ServiceHost` Directiva, que define los atributos específicos de la página utilizados por el compilador. SVC.</span><span class="sxs-lookup"><span data-stu-id="eb20f-142">Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="eb20f-143">[Esquema de configuración de WIF](windows-identity-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="eb20f-143">[WIF Configuration Schema](windows-identity-foundation/index.md)</span></span>\
<span data-ttu-id="eb20f-144">Todos los elementos del esquema de configuración de Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="eb20f-144">All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="eb20f-145">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="eb20f-145">Related sections</span></span>

<span data-ttu-id="eb20f-146">[Esquema de configuración de comunicación remota](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20f-146">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span>\
<span data-ttu-id="eb20f-147">Describe los elementos que configuran las aplicaciones cliente y servidor que implementa la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="eb20f-147">Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="eb20f-148">[Esquema de configuración de ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20f-148">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span>\
<span data-ttu-id="eb20f-149">Describe los elementos que controlan el comportamiento de las aplicaciones web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="eb20f-149">Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="eb20f-150">[Esquema de configuración de servicios Web](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20f-150">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span>\
<span data-ttu-id="eb20f-151">Describe los elementos que controlan el comportamiento de servicios Web de ASP.NET y sus clientes.</span><span class="sxs-lookup"><span data-stu-id="eb20f-151">Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="eb20f-152">[Configuración de .NET Framework aplicaciones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb20f-152">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100))</span></span>\
<span data-ttu-id="eb20f-153">Describe cómo configurar la seguridad, el enlace del ensamblado y la comunicación remota de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb20f-153">Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
