---
title: "Esquema de los archivos de configuración de .NET Framework"
ms.custom: 
ms.date: 05/01/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4af28280de24f3e25362f18985c209b1a2f29523
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="configuration-file-schema-for-the-net-framework"></a><span data-ttu-id="49c6b-102">Esquema de los archivos de configuración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="49c6b-102">Configuration file schema for the .NET Framework</span></span>

<span data-ttu-id="49c6b-103">Los archivos de configuración son archivos XML estándar que se pueden utilizar para cambiar configuraciones y establecer directivas para las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="49c6b-103">Configuration files are standard XML files that you can use to change settings and set policies for your apps.</span></span> <span data-ttu-id="49c6b-104">El esquema de configuración de .NET Framework se compone de elementos que se pueden usar en los archivos de configuración para controlar el comportamiento de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="49c6b-104">The .NET Framework configuration schema consists of elements that you can use in configuration files to control the behavior of your apps.</span></span> <span data-ttu-id="49c6b-105">La tabla de contenido de esta sección refleja la jerarquía de esquema para el inicio, el tiempo de ejecución, la red y otros tipos de valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="49c6b-105">The table of contents for this section reflects the schema hierarchy for startup, runtime, network, and other types of configuration settings.</span></span>

<span data-ttu-id="49c6b-106">Para obtener información sobre los tipos, el formato y la ubicación de los archivos de configuración, vea el artículo [Configuring Apps](~/docs/framework/configure-apps/index.md) (Configurar aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="49c6b-106">For information about the types, format, and location of configuration files, see the article [Configuring Apps](~/docs/framework/configure-apps/index.md).</span></span> <span data-ttu-id="49c6b-107">Familiarícese con XML para editar los archivos de configuración directamente.</span><span class="sxs-lookup"><span data-stu-id="49c6b-107">Familiarize yourself with XML if you want to edit the configuration files directly.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49c6b-108">En los atributos y etiquetas XML de los archivos de configuración se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="49c6b-108">XML tags and attributes in configuration files are case-sensitive.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="49c6b-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="49c6b-109">In this section</span></span>

<span data-ttu-id="49c6b-110">[**\<configuration>** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) (Elemento <configuration>): describe el elemento `<configuration>`, que es el elemento de nivel superior de todos los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="49c6b-110">[**\<configuration>** Element](~/docs/framework/configure-apps/file-schema/configuration-element.md) Describes the `<configuration>` element, which is the top-level element for all configuration files.</span></span>

<span data-ttu-id="49c6b-111">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) (Elemento <assemblyBinding>): especifica la directiva de enlace del ensamblado en el nivel de configuración.</span><span class="sxs-lookup"><span data-stu-id="49c6b-111">[**\<assemblyBinding>** Element](~/docs/framework/configure-apps/file-schema/assemblybinding-element-for-configuration.md) Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="49c6b-112">[**\<linkedConfiguration>** Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) (Elemento <linkedConfiguration>): especifica un archivo de configuración para incluirlo.</span><span class="sxs-lookup"><span data-stu-id="49c6b-112">[**\<linkedConfiguration>** Element](~/docs/framework/configure-apps/file-schema/linkedconfiguration-element.md) Specifies a configuration file to include.</span></span>

<span data-ttu-id="49c6b-113">[Startup Settings Schema](~/docs/framework/configure-apps/file-schema/startup/index.md) (Esquema de la configuración de inicio): describe los elementos que especifican la versión de Common Language Runtime que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="49c6b-113">[Startup Settings Schema](~/docs/framework/configure-apps/file-schema/startup/index.md) Describes the elements that specify which version of the common language runtime to use.</span></span>

<span data-ttu-id="49c6b-114">[Runtime Settings Schema](~/docs/framework/configure-apps/file-schema/runtime/index.md) (Esquema de la configuración del tiempo de ejecución): describe los elementos que configuran el enlace del ensamblado y el comportamiento del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49c6b-114">[Runtime Settings Schema](~/docs/framework/configure-apps/file-schema/runtime/index.md) Describes the elements that configure assembly binding and runtime behavior.</span></span>

<span data-ttu-id="49c6b-115">[Network Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) (Esquema de la configuración de red): describe los elementos que especifican cómo se conecta .NET Framework a Internet.</span><span class="sxs-lookup"><span data-stu-id="49c6b-115">[Network Settings Schema](~/docs/framework/configure-apps/file-schema/network/index.md) Describes the elements that specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="49c6b-116">[Cryptography Settings Schema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) (Esquema de la configuración de criptografía): describe los elementos que asignan nombres de algoritmo descriptivos a las clases que implementan algoritmos criptográficos.</span><span class="sxs-lookup"><span data-stu-id="49c6b-116">[Cryptography Settings Schema](~/docs/framework/configure-apps/file-schema/cryptography/index.md) Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

<span data-ttu-id="49c6b-117">[Configuration Sections Schema](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) (Esquema de secciones de configuración): describe los elementos necesarios para crear y usar las secciones de configuración de valores personalizados.</span><span class="sxs-lookup"><span data-stu-id="49c6b-117">[Configuration Sections Schema](~/docs/framework/configure-apps/file-schema/configuration-sections-schema.md) Describes the elements used to create and use configuration sections for custom settings.</span></span>

<span data-ttu-id="49c6b-118">[Trace and Debug Settings Schema](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) (Esquema de la configuración de seguimiento y depuración): describe los elementos que especifican los modificadores y agentes de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="49c6b-118">[Trace and Debug Settings Schema](~/docs/framework/configure-apps/file-schema/trace-debug/index.md) Describes the elements that specify trace switches and listeners.</span></span>

<span data-ttu-id="49c6b-119">[Compiler and Language Provider Settings Schema](~/docs/framework/configure-apps/file-schema/compiler/index.md) (Esquema de configuración de compilador y proveedor de lenguaje): describe los elementos que especifican la configuración del compilador para los proveedores de lenguaje disponibles.</span><span class="sxs-lookup"><span data-stu-id="49c6b-119">[Compiler and Language Provider Settings Schema](~/docs/framework/configure-apps/file-schema/compiler/index.md) Describes the elements that specify compiler configuration for available language providers.</span></span>

<span data-ttu-id="49c6b-120">[Application Settings Schema](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) (Esquema de la configuración de la aplicación): describe los elementos que permiten que una aplicación de formularios Windows Forms o ASP.NET almacene y recupere los valores del ámbito de usuario y del ámbito de aplicación.</span><span class="sxs-lookup"><span data-stu-id="49c6b-120">[Application Settings Schema](~/docs/framework/configure-apps/file-schema/application-settings-schema.md) Describes the elements that enable a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span>

<span data-ttu-id="49c6b-121">[App Settings Schema](~/docs/framework/configure-apps/file-schema/appsettings/index.md) (Esquema de configuración de aplicaciones): contiene valores de configuración de aplicación personalizados, como rutas de acceso de archivo, direcciones URL del servicio Web XML o cualquier otra información de configuración personalizada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="49c6b-121">[App Settings Schema](~/docs/framework/configure-apps/file-schema/appsettings/index.md) Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

<span data-ttu-id="49c6b-122">[Web Settings Schema](~/docs/framework/configure-apps/file-schema/web/index.md) (Esquema de configuración web): describe todos los elementos del esquema de configuración web, que incluye elementos para configurar cómo funciona ASP.NET con una aplicación host como IIS.</span><span class="sxs-lookup"><span data-stu-id="49c6b-122">[Web Settings Schema](~/docs/framework/configure-apps/file-schema/web/index.md) All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="49c6b-123">Se usa en los archivos *Aspnet.config*.</span><span class="sxs-lookup"><span data-stu-id="49c6b-123">Used in *Aspnet.config* files.</span></span>

<span data-ttu-id="49c6b-124">[Windows Forms Configuration Schema](winforms/index.md) (Esquema de configuración de Windows Forms): todos los elementos de la sección de configuración de aplicaciones de Windows Forms, incluidas personalizaciones como la compatibilidad con varios monitores y valores altos de PPP.</span><span class="sxs-lookup"><span data-stu-id="49c6b-124">[Windows Forms Configuration Schema](winforms/index.md) All elements in the Windows Forms application configuration section, which includes customizations such as multi-monitor and high DPI support.</span></span>

<span data-ttu-id="49c6b-125">[WCF Configuration Schema](~/docs/framework/configure-apps/file-schema/wcf/index.md) (Esquema de configuración de WCF): todos los elementos que permiten configurar el servicio WCF y las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="49c6b-125">[WCF Configuration Schema](~/docs/framework/configure-apps/file-schema/wcf/index.md) All elements that enable you to configure WCF service and client applications.</span></span>

<span data-ttu-id="49c6b-126">[WCF Directive Syntax](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) (Sintaxis de directivas WCF): describe la directiva `@ServiceHost`, que define atributos específicos de página usados por el compilador .svc.</span><span class="sxs-lookup"><span data-stu-id="49c6b-126">[WCF Directive Syntax](~/docs/framework/configure-apps/file-schema/wcf-directive/index.md) Describes the `@ServiceHost` directive, which defines page-specific attributes used by the .svc compiler.</span></span>

<span data-ttu-id="49c6b-127">[WIF Configuration Schema](windows-identity-foundation/index.md) (Esquema de configuración de WIF): todos los elementos del esquema de configuración de Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="49c6b-127">[WIF Configuration Schema](windows-identity-foundation/index.md) All elements of the Windows Identity Foundation (WIF) configuration schema.</span></span>

## <a name="related-sections"></a><span data-ttu-id="49c6b-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="49c6b-128">Related sections</span></span>

<span data-ttu-id="49c6b-129">[Remoting Settings Schema](http://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) (Esquema de configuración de la comunicación remota): describe los elementos que configuran las aplicaciones cliente y servidor que implementan la comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="49c6b-129">[Remoting Settings Schema](http://msdn.microsoft.com/library/dc2d1e62-9af7-4ca1-99fd-98b93bb4db9e) Describes the elements that configure client and server applications that implement remoting.</span></span>

<span data-ttu-id="49c6b-130">[ASP.NET Settings Schema](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) (Esquema de configuración de ASP.NET): describe los elementos que controlan el comportamiento de las aplicaciones web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="49c6b-130">[ASP.NET Settings Schema](http://msdn.microsoft.com/library/b5ysx397\(v=vs.100\).aspx) Describes the elements that control the behavior of ASP.NET Web applications.</span></span>

<span data-ttu-id="49c6b-131">[Web Services Settings Schema](http://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e) (Esquema de configuración de los servicios Web): describe los elementos que controlan el comportamiento de los servicios web ASP.NET y sus clientes.</span><span class="sxs-lookup"><span data-stu-id="49c6b-131">[Web Services Settings Schema](http://msdn.microsoft.com/library/f84d6d55-1add-4eb7-ae46-33df5833ea2e) Describes the elements that control the behavior of ASP.NET Web services and their clients.</span></span>

<span data-ttu-id="49c6b-132">[Configuring .NET Framework Apps](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) (Configurar aplicaciones de .NET Framework): describe cómo configurar la seguridad, el enlace del ensamblado y la comunicación remota de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49c6b-132">[Configuring .NET Framework Apps](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42) Describes how to configure security, assembly binding, and remoting in the .NET Framework.</span></span>
