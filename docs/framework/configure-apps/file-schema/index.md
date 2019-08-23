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
ms.openlocfilehash: c3b5518b4b86c2e6f47825d552f49579c5ac0a6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921021"
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="497a4-102">Esquema de los archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="497a4-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="497a4-103">Los archivos de configuración son archivos XML estándar que se pueden utilizar para cambiar configuraciones y establecer directivas para las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="497a4-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="497a4-104">El esquema de configuración de .NET Framework se compone de elementos que se pueden usar en los archivos de configuración para controlar el comportamiento de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="497a4-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="497a4-105">La tabla de contenido de esta sección refleja la jerarquía de esquema para el inicio, el tiempo de ejecución, la red y otros tipos de valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="497a4-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="497a4-106">Para obtener información sobre los tipos, el formato y la ubicación de los archivos de configuración, vea el artículo [Configuring Apps](../index.md) (Configurar aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="497a4-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](../index.md).</span></span> <span data-ttu-id="497a4-107">Familiarícese con XML para editar los archivos de configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="497a4-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="497a4-108">En los atributos y etiquetas XML de los archivos de configuración se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="497a4-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="497a4-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="497a4-109">In this section</span></span>

<span data-ttu-id="497a4-110">[ **\<configuration>** Element](configuration-element.md) (Elemento <configuration>): describe el elemento `<configuration>`, que es el elemento de nivel superior de todos los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="497a4-110">[**\<configuration>** Element](configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="497a4-111">[ **\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md) (Elemento <assemblyBinding>): especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="497a4-111">[**\<assemblyBinding>** Element](assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="497a4-112">[ **\<linkedConfiguration>** Element](linkedconfiguration-element.md) (Elemento <linkedConfiguration>): especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="497a4-112">[**\<linkedConfiguration>** Element](linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="497a4-113">[Startup Settings Schema](./startup/index.md) (Esquema de la configuración de inicio): describe los elementos que especifican la versión de Common Language Runtime que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="497a4-113">[Startup Settings Schema](./startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="497a4-114">[Runtime Settings Schema](./runtime/index.md) (Esquema de la configuración del tiempo de ejecución): describe los elementos que configuran el enlace del ensamblado y el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="497a4-114">[Runtime Settings Schema](./runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="497a4-115">[Network Settings Schema](./network/index.md) (Esquema de la configuración de red): describe los elementos que especifican cómo se conecta .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="497a4-115">[Network Settings Schema](./network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="497a4-116">[Cryptography Settings Schema](./cryptography/index.md) (Esquema de la configuración de criptografía): describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="497a4-116">[Cryptography Settings Schema](./cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="497a4-117">[Configuration Sections Schema](configuration-sections-schema.md) (Esquema de secciones de configuración): describe los elementos necesarios para crear y usar las secciones de configuración de valores personalizados.</span><span class="sxs-lookup"><span data-stu-id="497a4-117">[Configuration Sections Schema](configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="497a4-118">[Trace and Debug Settings Schema](./trace-debug/index.md) (Esquema de la configuración de seguimiento y depuración): describe los elementos que especifican los modificadores y agentes de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="497a4-118">[Trace and Debug Settings Schema](./trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="497a4-119">[Compiler and Language Provider Settings Schema](./compiler/index.md) (Esquema de configuración de compilador y proveedor de lenguaje): describe los elementos que especifican la configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="497a4-119">[Compiler and Language Provider Settings Schema](./compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="497a4-120">[Application Settings Schema](application-settings-schema.md) (Esquema de la configuración de la aplicación): describe los elementos que permiten que una aplicación de formularios Windows Forms o ASP.NET almacene y recupere los valores del ámbito de usuario y del ámbito de aplicación.</span><span class="sxs-lookup"><span data-stu-id="497a4-120">[Application Settings Schema](application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="497a4-121">[App Settings Schema](./appsettings/index.md) (Esquema de configuración de aplicaciones): contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="497a4-121">[App Settings Schema](./appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="497a4-122">[Web Settings Schema](./web/index.md) (Esquema de configuración web): describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="497a4-122">[Web Settings Schema](./web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="497a4-123">Se usa en los archivos *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="497a4-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="497a4-124">[Windows Forms Configuration Schema](winforms/index.md) (Esquema de configuración de Windows Forms): todos los elementos de la sección de configuración de aplicaciones de Windows Forms, incluidas personalizaciones como la compatibilidad con varios monitores y valores altos de PPP.</span><span class="sxs-lookup"><span data-stu-id="497a4-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="497a4-125">[WCF Configuration Schema](./wcf/index.md) (Esquema de configuración de WCF): todos los elementos que permiten configurar el servicio WCF y las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="497a4-125">[WCF Configuration Schema](./wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="497a4-126">[WCF Directive Syntax](./wcf-directive/index.md) (Sintaxis de directivas WCF): describe la directiva `@ServiceHost`, que define atributos específicos de página usados por el compilador .svc.</span><span class="sxs-lookup"><span data-stu-id="497a4-126">[WCF Directive Syntax](./wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="497a4-127">[WIF Configuration Schema](windows-identity-foundation/index.md) (Esquema de configuración de WIF): todos los elementos del esquema de configuración de Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="497a4-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="497a4-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="497a4-128">Related sections</span></span>

<span data-ttu-id="497a4-129">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) (Esquema de configuración de la comunicación remota): describe los elementos que configuran las aplicaciones cliente y servidor que implementan la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="497a4-129">[Remoting Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100)) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="497a4-130">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) (Esquema de configuración de ASP.NET): describe los elementos que controlan el comportamiento de las aplicaciones web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="497a4-130">[ASP.NET Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="497a4-131">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) (Esquema de configuración de los servicios Web): describe los elementos que controlan el comportamiento de los servicios web ASP.NET y sus clientes.</span><span class="sxs-lookup"><span data-stu-id="497a4-131">[Web Services Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100)) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="497a4-132">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) (Configurar aplicaciones de .NET Framework): describe cómo configurar la seguridad, el enlace del ensamblado y la comunicación remota de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="497a4-132">[Configuring .NET Framework Apps](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kza1yk3a(v=vs.100)) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
