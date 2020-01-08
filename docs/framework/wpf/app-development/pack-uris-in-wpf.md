---
title: Empaquetar URI en WPF
ms.date: 03/30/2017
helpviewer_keywords:
- pack URI scheme [WPF]
- loading embedded resources [WPF]
- URIs (Uniform Resource Identifiers)
- Uniform Resource Identifiers (URIs)
- loading non-resource files
- application management [WPF]
ms.assetid: 43adb517-21a7-4df3-98e8-09e9cdf764c4
ms.openlocfilehash: e20053c451d12c6a8493d5d7fcfc72fe3d3d764e
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636385"
---
# <a name="pack-uris-in-wpf"></a><span data-ttu-id="67c6e-102">Empaquetar URI en WPF</span><span class="sxs-lookup"><span data-stu-id="67c6e-102">Pack URIs in WPF</span></span>

<span data-ttu-id="67c6e-103">En Windows Presentation Foundation (WPF), los identificadores uniformes de recursos (URI) se usan para identificar y cargar archivos de muchas maneras, entre las que se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="67c6e-103">In Windows Presentation Foundation (WPF), uniform resource identifiers (URIs) are used to identify and load files in many ways, including the following:</span></span>

- <span data-ttu-id="67c6e-104">Especificar el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que se va a mostrar cuando se inicia una aplicación por primera vez.</span><span class="sxs-lookup"><span data-stu-id="67c6e-104">Specifying the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] to show when an application first starts.</span></span>

- <span data-ttu-id="67c6e-105">Cargando imágenes.</span><span class="sxs-lookup"><span data-stu-id="67c6e-105">Loading images.</span></span>

- <span data-ttu-id="67c6e-106">Navegando a páginas.</span><span class="sxs-lookup"><span data-stu-id="67c6e-106">Navigating to pages.</span></span>

- <span data-ttu-id="67c6e-107">Cargando archivos de datos no ejecutables.</span><span class="sxs-lookup"><span data-stu-id="67c6e-107">Loading non-executable data files.</span></span>

<span data-ttu-id="67c6e-108">Además, los URI se pueden usar para identificar y cargar archivos desde varias ubicaciones, incluidas las siguientes:</span><span class="sxs-lookup"><span data-stu-id="67c6e-108">Furthermore, URIs can be used to identify and load files from a variety of locations, including the following:</span></span>

- <span data-ttu-id="67c6e-109">Ensamblado actual.</span><span class="sxs-lookup"><span data-stu-id="67c6e-109">The current assembly.</span></span>

- <span data-ttu-id="67c6e-110">El ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-110">A referenced assembly.</span></span>

- <span data-ttu-id="67c6e-111">Una ubicación relativa a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="67c6e-111">A location relative to an assembly.</span></span>

- <span data-ttu-id="67c6e-112">El sitio de origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-112">The application's site of origin.</span></span>

<span data-ttu-id="67c6e-113">Para proporcionar un mecanismo coherente para identificar y cargar estos tipos de archivos desde estas ubicaciones, WPF aprovecha la extensibilidad del esquema de *pack uri*.</span><span class="sxs-lookup"><span data-stu-id="67c6e-113">To provide a consistent mechanism for identifying and loading these types of files from these locations, WPF leverages the extensibility of the *pack URI scheme*.</span></span> <span data-ttu-id="67c6e-114">En este tema se proporciona información general sobre el esquema, se explica cómo construir identificadores URI para una variedad de escenarios, se explican los URI absolutos y relativos y la resolución de identificadores URI, antes de mostrar cómo usar los URI del paquete de marcado y código.</span><span class="sxs-lookup"><span data-stu-id="67c6e-114">This topic provides an overview of the scheme, covers how to construct pack URIs for a variety of scenarios, discusses absolute and relative URIs and URI resolution, before showing how to use pack URIs from both markup and code.</span></span>

<a name="The_Pack_URI_Scheme"></a>

## <a name="the-pack-uri-scheme"></a><span data-ttu-id="67c6e-115">Esquema de Pack URI</span><span class="sxs-lookup"><span data-stu-id="67c6e-115">The Pack URI Scheme</span></span>

<span data-ttu-id="67c6e-116">El esquema de Pack URI se usa en la especificación de [convenciones de empaquetado abierto](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC), que describe un modelo para organizar e identificar el contenido.</span><span class="sxs-lookup"><span data-stu-id="67c6e-116">The pack URI scheme is used by the [Open Packaging Conventions](https://go.microsoft.com/fwlink/?LinkID=71255) (OPC) specification, which describes a model for organizing and identifying content.</span></span> <span data-ttu-id="67c6e-117">Los elementos clave de este modelo son paquetes y partes, donde un *paquete* es un contenedor lógico para una o más *partes*lógicas.</span><span class="sxs-lookup"><span data-stu-id="67c6e-117">The key elements of this model are packages and parts, where a *package* is a logical container for one or more logical *parts*.</span></span> <span data-ttu-id="67c6e-118">La figura siguiente ilustra este concepto.</span><span class="sxs-lookup"><span data-stu-id="67c6e-118">The following figure illustrates this concept.</span></span>

![Diagrama de paquete y partes](./media/pack-uris-in-wpf/wpf-package-parts-diagram.png)

<span data-ttu-id="67c6e-120">Para identificar elementos, la especificación de OPC aprovecha la extensibilidad de RFC 2396 (identificadores uniformes de recursos (URI): Sintaxis genérica) para definir el esquema de Pack URI.</span><span class="sxs-lookup"><span data-stu-id="67c6e-120">To identify parts, the OPC specification leverages the extensibility of RFC 2396 (Uniform Resource Identifiers (URI): Generic Syntax) to define the pack URI scheme.</span></span>

<span data-ttu-id="67c6e-121">El esquema especificado por un URI se define mediante su prefijo; http, FTP y file son ejemplos conocidos.</span><span class="sxs-lookup"><span data-stu-id="67c6e-121">The scheme that is specified by a URI is defined by its prefix; http, ftp, and file are well-known examples.</span></span> <span data-ttu-id="67c6e-122">El esquema de Pack URI usa "Pack" como su esquema y contiene dos componentes: autoridad y ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="67c6e-122">The pack URI scheme uses "pack" as its scheme, and contains two components: authority and path.</span></span> <span data-ttu-id="67c6e-123">A continuación se da el formato de un Pack URI.</span><span class="sxs-lookup"><span data-stu-id="67c6e-123">The following is the format for a pack URI.</span></span>

<span data-ttu-id="67c6e-124">*ruta* de/de la*autoridad* Pack://</span><span class="sxs-lookup"><span data-stu-id="67c6e-124">pack://*authority*/*path*</span></span>

<span data-ttu-id="67c6e-125">La *autoridad* especifica el tipo de paquete que contiene una parte, mientras que la *ruta de acceso* especifica la ubicación de un elemento dentro de un paquete.</span><span class="sxs-lookup"><span data-stu-id="67c6e-125">The *authority* specifies the type of package that a part is contained by, while the *path* specifies the location of a part within a package.</span></span>

<span data-ttu-id="67c6e-126">Este concepto se muestra en la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="67c6e-126">This concept is illustrated by the following figure:</span></span>

![Relación entre paquete, autoridad y ruta de acceso](./media/pack-uris-in-wpf/wpf-relationship-diagram.png)

<span data-ttu-id="67c6e-128">Los paquetes y los elementos son análogos a las aplicaciones y los archivos, donde una aplicación (paquete) puede incluir uno o más archivos (elementos), como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="67c6e-128">Packages and parts are analogous to applications and files, where an application (package) can include one or more files (parts), including:</span></span>

- <span data-ttu-id="67c6e-129">Archivos de recursos que se compilan en el ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-129">Resource files that are compiled into the local assembly.</span></span>

- <span data-ttu-id="67c6e-130">Archivos de recursos que se compilan en un ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-130">Resource files that are compiled into a referenced assembly.</span></span>

- <span data-ttu-id="67c6e-131">Archivos de recursos que se compilan en un ensamblado que hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-131">Resource files that are compiled into a referencing assembly.</span></span>

- <span data-ttu-id="67c6e-132">Archivos de contenido.</span><span class="sxs-lookup"><span data-stu-id="67c6e-132">Content files.</span></span>

- <span data-ttu-id="67c6e-133">Archivos de sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="67c6e-133">Site of origin files.</span></span>

<span data-ttu-id="67c6e-134">Para tener acceso a estos tipos de archivos, WPF admite dos entidades: application:///y siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="67c6e-134">To access these types of files, WPF supports two authorities: application:/// and siteoforigin:///.</span></span> <span data-ttu-id="67c6e-135">La autoridad application:/// identifica los archivos de datos de aplicación que se conocen en tiempo de compilación, incluidos los archivos de recursos y de contenido.</span><span class="sxs-lookup"><span data-stu-id="67c6e-135">The application:/// authority identifies application data files that are known at compile time, including resource and content files.</span></span> <span data-ttu-id="67c6e-136">La autoridad siteoforigin:/// identifica los archivos de sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="67c6e-136">The siteoforigin:/// authority identifies site of origin files.</span></span> <span data-ttu-id="67c6e-137">El ámbito de cada autoridad se muestra en la figura siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-137">The scope of each authority is shown in the following figure.</span></span>

![Diagrama de URI de paquete](./media/pack-uris-in-wpf/wpf-pack-uri-scheme.png)

> [!NOTE]
> <span data-ttu-id="67c6e-139">El componente de autoridad de un Pack URI es un identificador URI incrustado que apunta a un paquete y debe ajustarse a RFC 2396.</span><span class="sxs-lookup"><span data-stu-id="67c6e-139">The authority component of a pack URI is an embedded URI that points to a package and must conform to RFC 2396.</span></span> <span data-ttu-id="67c6e-140">Además, el carácter "/" se debe reemplazar por el carácter ",", y los caracteres reservados "%" y "?" deben incluirse en secuencias de escape.</span><span class="sxs-lookup"><span data-stu-id="67c6e-140">Additionally, the "/" character must be replaced with the "," character, and reserved characters such as "%" and "?" must be escaped.</span></span> <span data-ttu-id="67c6e-141">Consulte la especificación de OPC para detalles.</span><span class="sxs-lookup"><span data-stu-id="67c6e-141">See the OPC for details.</span></span>

<span data-ttu-id="67c6e-142">En las secciones siguientes se explica cómo construir Pack URI con estas dos autoridades junto con las rutas de acceso adecuadas para identificar los archivos de recursos, contenido y sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="67c6e-142">The following sections explain how to construct pack URIs using these two authorities in conjunction with the appropriate paths for identifying resource, content, and site of origin files.</span></span>

<a name="Resource_File_Pack_URIs___Local_Assembly"></a>

## <a name="resource-file-pack-uris"></a><span data-ttu-id="67c6e-143">Pack URI de archivos de recursos</span><span class="sxs-lookup"><span data-stu-id="67c6e-143">Resource File Pack URIs</span></span>

<span data-ttu-id="67c6e-144">Los archivos de recursos se configuran como elementos de `Resource` de MSBuild y se compilan en ensamblados.</span><span class="sxs-lookup"><span data-stu-id="67c6e-144">Resource files are configured as MSBuild `Resource` items and are compiled into assemblies.</span></span> <span data-ttu-id="67c6e-145">WPF admite la construcción de Pack URI que se pueden usar para identificar los archivos de recursos compilados en el ensamblado local o compilados en un ensamblado al que se hace referencia desde el ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-145">WPF supports the construction of pack URIs that can be used to identify resource files that are either compiled into the local assembly or compiled into an assembly that is referenced from the local assembly.</span></span>

<a name="Local_Assembly_Resource_File"></a>

### <a name="local-assembly-resource-file"></a><span data-ttu-id="67c6e-146">Archivo de recursos del ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-146">Local Assembly Resource File</span></span>

<span data-ttu-id="67c6e-147">El Pack URI de un archivo de recursos que se compila en el ensamblado local usa la siguiente autoridad y ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="67c6e-147">The pack URI for a resource file that is compiled into the local assembly uses the following authority and path:</span></span>

- <span data-ttu-id="67c6e-148">**Autoridad**: application:///.</span><span class="sxs-lookup"><span data-stu-id="67c6e-148">**Authority**: application:///.</span></span>

- <span data-ttu-id="67c6e-149">**Ruta de acceso**: nombre del archivo de recursos, incluida su ruta de acceso relativa a la carpeta raíz del proyecto de ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-149">**Path**: The name of the resource file, including its path, relative to the local assembly project folder root.</span></span>

<span data-ttu-id="67c6e-150">En el ejemplo siguiente se muestra el Pack URI de un archivo de recursos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en la raíz de la carpeta del proyecto del ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-150">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the local assembly's project folder.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="67c6e-151">En el ejemplo siguiente se muestra el Pack URI de un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en una subcarpeta de la carpeta del proyecto del ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-151">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the local assembly's project folder.</span></span>

`pack://application:,,,/Subfolder/ResourceFile.xaml`

<a name="Resource_File_Pack_URIs___Referenced_Assembly"></a>

### <a name="referenced-assembly-resource-file"></a><span data-ttu-id="67c6e-152">Archivo de recursos del ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-152">Referenced Assembly Resource File</span></span>

<span data-ttu-id="67c6e-153">El Pack URI de un archivo de recursos que se compila en un ensamblado al que se hace referencia usa la siguiente autoridad y ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="67c6e-153">The pack URI for a resource file that is compiled into a referenced assembly uses the following authority and path:</span></span>

- <span data-ttu-id="67c6e-154">**Autoridad**: application:///.</span><span class="sxs-lookup"><span data-stu-id="67c6e-154">**Authority**: application:///.</span></span>

- <span data-ttu-id="67c6e-155">**Ruta de acceso**: nombre de un archivo de recursos que se compila en un ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-155">**Path**: The name of a resource file that is compiled into a referenced assembly.</span></span> <span data-ttu-id="67c6e-156">La ruta de acceso debe tener el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="67c6e-156">The path must conform to the following format:</span></span>

  <span data-ttu-id="67c6e-157">*AssemblyShortName*{ *; Versión*] { *; PublicKey*]; componente/*ruta de acceso*</span><span class="sxs-lookup"><span data-stu-id="67c6e-157">*AssemblyShortName*{*;Version*]{*;PublicKey*];component/*Path*</span></span>

  - <span data-ttu-id="67c6e-158">**AssemblyShortName**: nombre corto del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-158">**AssemblyShortName**: the short name for the referenced assembly.</span></span>

  - <span data-ttu-id="67c6e-159">**;Version** [opcional]: versión del ensamblado al que se hace referencia y que contiene el archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="67c6e-159">**;Version** [optional]: the version of the referenced assembly that contains the resource file.</span></span> <span data-ttu-id="67c6e-160">Se usa cuando hay cargados dos o más ensamblados a los que se hace referencia con el mismo nombre corto.</span><span class="sxs-lookup"><span data-stu-id="67c6e-160">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="67c6e-161">**;PublicKey** [opcional]: clave pública que se usó para firmar el ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-161">**;PublicKey** [optional]: the public key that was used to sign the referenced assembly.</span></span> <span data-ttu-id="67c6e-162">Se usa cuando hay cargados dos o más ensamblados a los que se hace referencia con el mismo nombre corto.</span><span class="sxs-lookup"><span data-stu-id="67c6e-162">This is used when two or more referenced assemblies with the same short name are loaded.</span></span>

  - <span data-ttu-id="67c6e-163">**;component**: especifica que la referencia al ensamblado se hace desde el ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-163">**;component**: specifies that the assembly being referred to is referenced from the local assembly.</span></span>

  - <span data-ttu-id="67c6e-164">**/Path**: nombre del archivo de recursos, incluida su ruta de acceso relativa a la raíz de la carpeta del proyecto del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-164">**/Path**: the name of the resource file, including its path, relative to the root of the referenced assembly's project folder.</span></span>

<span data-ttu-id="67c6e-165">En el ejemplo siguiente se muestra el Pack URI de un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en la raíz de la carpeta del proyecto del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-165">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml`

<span data-ttu-id="67c6e-166">En el ejemplo siguiente se muestra el Pack URI de un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en una subcarpeta de la carpeta del proyecto del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-166">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in a subfolder of the referenced assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml`

<span data-ttu-id="67c6e-167">En el ejemplo siguiente se muestra el Pack URI de un archivo de recursos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que se encuentra en la carpeta raíz de una carpeta de proyecto de un ensamblado específico de la versión a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-167">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] resource file that is located in the root folder of a referenced, version-specific assembly's project folder.</span></span>

`pack://application:,,,/ReferencedAssembly;v1.0.0.1;component/ResourceFile.xaml`

<span data-ttu-id="67c6e-168">Tenga en cuenta que la sintaxis de Pack URI para los archivos de recursos de ensamblado a los que se hace referencia solo se puede usar con la autoridad application:///.</span><span class="sxs-lookup"><span data-stu-id="67c6e-168">Note that the pack URI syntax for referenced assembly resource files can be used only with the application:/// authority.</span></span> <span data-ttu-id="67c6e-169">Por ejemplo, no se admite lo siguiente en WPF.</span><span class="sxs-lookup"><span data-stu-id="67c6e-169">For example, the following is not supported in WPF.</span></span>

`pack://siteoforigin:,,,/SomeAssembly;component/ResourceFile.xaml`

<a name="Content_File_Pack_URIs"></a>

## <a name="content-file-pack-uris"></a><span data-ttu-id="67c6e-170">Pack URI de archivos de contenido</span><span class="sxs-lookup"><span data-stu-id="67c6e-170">Content File Pack URIs</span></span>

<span data-ttu-id="67c6e-171">El URI del paquete para un archivo de contenido usa la siguiente autoridad y ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="67c6e-171">The pack URI for a content file uses the following authority and path:</span></span>

- <span data-ttu-id="67c6e-172">**Autoridad**: application:///.</span><span class="sxs-lookup"><span data-stu-id="67c6e-172">**Authority**: application:///.</span></span>

- <span data-ttu-id="67c6e-173">**Ruta de acceso**: nombre del archivo de contenido, incluida su ruta de acceso relativa a la ubicación del sistema de archivos del ensamblado ejecutable principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-173">**Path**: The name of the content file, including its path relative to the file system location of the application's main executable assembly.</span></span>

<span data-ttu-id="67c6e-174">En el ejemplo siguiente se muestra el Pack URI de un archivo de contenido de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], que se encuentra en la misma carpeta que el ensamblado ejecutable.</span><span class="sxs-lookup"><span data-stu-id="67c6e-174">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in the same folder as the executable assembly.</span></span>

`pack://application:,,,/ContentFile.xaml`

<span data-ttu-id="67c6e-175">En el ejemplo siguiente se muestra el Pack URI de un archivo de contenido de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], que se encuentra en una subcarpeta relativa al ensamblado ejecutable de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-175">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] content file, located in a subfolder that is relative to the application's executable assembly.</span></span>

`pack://application:,,,/Subfolder/ContentFile.xaml`

> [!NOTE]
> <span data-ttu-id="67c6e-176">No se puede navegar por los archivos de contenido HTML.</span><span class="sxs-lookup"><span data-stu-id="67c6e-176">HTML content files cannot be navigated to.</span></span> <span data-ttu-id="67c6e-177">El esquema de URI solo admite la navegación a los archivos HTML que se encuentran en el sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="67c6e-177">The URI scheme only supports navigation to HTML files that are located at the site of origin.</span></span>

<a name="The_siteoforigin_____Authority"></a>

## <a name="site-of-origin-pack-uris"></a><span data-ttu-id="67c6e-178">Pack URI de sitio de origen</span><span class="sxs-lookup"><span data-stu-id="67c6e-178">Site of Origin Pack URIs</span></span>

<span data-ttu-id="67c6e-179">El URI del paquete para un archivo de sitio de origen usa la siguiente autoridad y ruta de acceso:</span><span class="sxs-lookup"><span data-stu-id="67c6e-179">The pack URI for a site of origin file uses the following authority and path:</span></span>

- <span data-ttu-id="67c6e-180">**Autoridad**: siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="67c6e-180">**Authority**: siteoforigin:///.</span></span>

- <span data-ttu-id="67c6e-181">**Ruta de acceso**: nombre del archivo de sitio de origen, incluida su ruta de acceso relativa a la ubicación desde donde se inició el ensamblado ejecutable.</span><span class="sxs-lookup"><span data-stu-id="67c6e-181">**Path**: The name of the site of origin file, including its path relative to the location from which the executable assembly was launched.</span></span>

<span data-ttu-id="67c6e-182">En el ejemplo siguiente se muestra el Pack URI para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de sitio de origen, almacenado en la ubicación desde la que se inicia el ensamblado ejecutable.</span><span class="sxs-lookup"><span data-stu-id="67c6e-182">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in the location from which the executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/SiteOfOriginFile.xaml`

<span data-ttu-id="67c6e-183">En el ejemplo siguiente se muestra el Pack URI para un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo de sitio de origen, almacenado en una subcarpeta relativa a la ubicación desde la que se inicia el ensamblado ejecutable de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-183">The following example shows the pack URI for a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] site of origin file, stored in subfolder that is relative to the location from which the application's executable assembly is launched.</span></span>

`pack://siteoforigin:,,,/Subfolder/SiteOfOriginFile.xaml`

<a name="Page_Files"></a>

## <a name="page-files"></a><span data-ttu-id="67c6e-184">Archivos de paginación</span><span class="sxs-lookup"><span data-stu-id="67c6e-184">Page Files</span></span>

<span data-ttu-id="67c6e-185">Los archivos XAML que se configuran como MSBuild `Page` elementos se compilan en ensamblados de la misma manera que los archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="67c6e-185">XAML files that are configured as MSBuild `Page` items are compiled into assemblies in the same way as resource files.</span></span> <span data-ttu-id="67c6e-186">Por consiguiente, los elementos de `Page` de MSBuild se pueden identificar mediante pack uri para los archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="67c6e-186">Consequently, MSBuild `Page` items can be identified using pack URIs for resource files.</span></span>

<span data-ttu-id="67c6e-187">Los tipos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos que se configuran normalmente como elementos`Page` de MSBuild tienen uno de los elementos siguientes como su elemento raíz:</span><span class="sxs-lookup"><span data-stu-id="67c6e-187">The types of [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files that are commonly configured as MSBuild`Page` items have one of the following as their root element:</span></span>

- <xref:System.Windows.Window?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Page?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.PageFunction%601?displayProperty=nameWithType>

- <xref:System.Windows.ResourceDictionary?displayProperty=nameWithType>

- <xref:System.Windows.Documents.FlowDocument?displayProperty=nameWithType>

- <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>

<a name="Absolute_vs_Relative_Pack_URIs"></a>

## <a name="absolute-vs-relative-pack-uris"></a><span data-ttu-id="67c6e-188">URI absolutos frente a packs relativos</span><span class="sxs-lookup"><span data-stu-id="67c6e-188">Absolute vs. Relative Pack URIs</span></span>

<span data-ttu-id="67c6e-189">Un URI de paquete completo incluye el esquema, la autoridad y la ruta de acceso, y se considera un URI de paquete absoluto.</span><span class="sxs-lookup"><span data-stu-id="67c6e-189">A fully qualified pack URI includes the scheme, the authority, and the path, and it is considered an absolute pack URI.</span></span> <span data-ttu-id="67c6e-190">Como simplificación de los desarrolladores, los elementos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] normalmente permiten establecer los atributos adecuados con un URI de paquete relativo, que incluye solo la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="67c6e-190">As a simplification for developers, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements typically allow you to set appropriate attributes with a relative pack URI, which includes only the path.</span></span>

<span data-ttu-id="67c6e-191">Por ejemplo, considere el siguiente Pack URI absoluto para un archivo de recursos en el ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-191">For example, consider the following absolute pack URI for a resource file in the local assembly.</span></span>

`pack://application:,,,/ResourceFile.xaml`

<span data-ttu-id="67c6e-192">El URI del Pack relativo que hace referencia a este archivo de recursos sería el siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-192">The relative pack URI that refers to this resource file would be the following.</span></span>

`/ResourceFile.xaml`

> [!NOTE]
> <span data-ttu-id="67c6e-193">Dado que los archivos de sitio de origen no están asociados a los ensamblados, solo se puede hacer referencia a ellos con identificadores URI absolutos.</span><span class="sxs-lookup"><span data-stu-id="67c6e-193">Because site of origin files are not associated with assemblies, they can only be referred to with absolute pack URIs.</span></span>

<span data-ttu-id="67c6e-194">De forma predeterminada, un URI de Pack relativo se considera relativo a la ubicación del marcado o código que contiene la referencia.</span><span class="sxs-lookup"><span data-stu-id="67c6e-194">By default, a relative pack URI is considered relative to the location of the markup or code that contains the reference.</span></span> <span data-ttu-id="67c6e-195">Sin embargo, si se usa una barra diagonal inversa inicial, la referencia del URI del Pack relativo se considera relativa a la raíz de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-195">If a leading backslash is used, however, the relative pack URI reference is then considered relative to the root of the application.</span></span> <span data-ttu-id="67c6e-196">Por ejemplo, considere la estructura de proyecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-196">For example, consider the following project structure.</span></span>

`App.xaml`

`Page2.xaml`

`\SubFolder`

`+ Page1.xaml`

`+ Page2.xaml`

<span data-ttu-id="67c6e-197">Si página1. XAML contiene un URI que hace referencia a \SubFolder\Page2.XAML *raíz*, la referencia puede usar el siguiente URI de módulo relativo.</span><span class="sxs-lookup"><span data-stu-id="67c6e-197">If Page1.xaml contains a URI that references *Root*\SubFolder\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`Page2.xaml`

<span data-ttu-id="67c6e-198">Si página1. XAML contiene un URI que hace referencia a \Page2.XAML *raíz*, la referencia puede usar el siguiente URI de módulo relativo.</span><span class="sxs-lookup"><span data-stu-id="67c6e-198">If Page1.xaml contains a URI that references *Root*\Page2.xaml, the reference can use the following relative pack URI.</span></span>

`/Page2.xaml`

<a name="Pack_URI_Resolution"></a>

## <a name="pack-uri-resolution"></a><span data-ttu-id="67c6e-199">Resolución de Pack URI</span><span class="sxs-lookup"><span data-stu-id="67c6e-199">Pack URI Resolution</span></span>

<span data-ttu-id="67c6e-200">El formato de los identificadores URI permite que los Pack URI de los distintos tipos de archivos tengan el mismo aspecto.</span><span class="sxs-lookup"><span data-stu-id="67c6e-200">The format of pack URIs makes it possible for pack URIs for different types of files to look the same.</span></span> <span data-ttu-id="67c6e-201">Por ejemplo, considere el siguiente Pack URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="67c6e-201">For example, consider the following absolute pack URI.</span></span>

`pack://application:,,,/ResourceOrContentFile.xaml`

<span data-ttu-id="67c6e-202">Este URI de paquete absoluto podría hacer referencia a un archivo de recursos en el ensamblado local o en un archivo de contenido.</span><span class="sxs-lookup"><span data-stu-id="67c6e-202">This absolute pack URI could refer to either a resource file in the local assembly or a content file.</span></span> <span data-ttu-id="67c6e-203">Lo mismo se cumple para el URI relativo siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-203">The same is true for the following relative URI.</span></span>

`/ResourceOrContentFile.xaml`

<span data-ttu-id="67c6e-204">Con el fin de determinar el tipo de archivo al que hace referencia un Pack URI, WPF resuelve los URI para los archivos de recursos en los ensamblados locales y los archivos de contenido mediante el uso de la heurística siguiente:</span><span class="sxs-lookup"><span data-stu-id="67c6e-204">In order to determine the type of file that a pack URI refers to, WPF resolves URIs for resource files in local assemblies and content files by using the following heuristics:</span></span>

1. <span data-ttu-id="67c6e-205">Sondear los metadatos de ensamblado para un atributo de <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> que coincida con el URI del paquete.</span><span class="sxs-lookup"><span data-stu-id="67c6e-205">Probe the assembly metadata for an <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute that matches the pack URI.</span></span>

2. <span data-ttu-id="67c6e-206">Si se encuentra el atributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, la ruta de acceso del Pack URI hace referencia a un archivo de contenido.</span><span class="sxs-lookup"><span data-stu-id="67c6e-206">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is found, the path of the pack URI refers to a content file.</span></span>

3. <span data-ttu-id="67c6e-207">Si no se encuentra el atributo <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute>, sondee los archivos de recursos de conjunto que se compilan en el ensamblado local.</span><span class="sxs-lookup"><span data-stu-id="67c6e-207">If the <xref:System.Windows.Resources.AssemblyAssociatedContentFileAttribute> attribute is not found, probe the set resource files that are compiled into the local assembly.</span></span>

4. <span data-ttu-id="67c6e-208">Si se encuentra un archivo de recursos que coincide con la ruta de acceso del Pack URI, la ruta de acceso del Pack URI hace referencia a un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="67c6e-208">If a resource file that matches the path of the pack URI is found, the path of the pack URI refers to a resource file.</span></span>

5. <span data-ttu-id="67c6e-209">Si no se encuentra el recurso, el <xref:System.Uri> creado internamente no es válido.</span><span class="sxs-lookup"><span data-stu-id="67c6e-209">If the resource is not found, the internally created <xref:System.Uri> is invalid.</span></span>

<span data-ttu-id="67c6e-210">La resolución de URI no se aplica a los URI que hacen referencia a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="67c6e-210">URI resolution does not apply for URIs that refer to the following:</span></span>

- <span data-ttu-id="67c6e-211">Archivos de contenido en ensamblados a los que se hace referencia: WPF no admite estos tipos de archivo.</span><span class="sxs-lookup"><span data-stu-id="67c6e-211">Content files in referenced assemblies: these file types are not supported by WPF.</span></span>

- <span data-ttu-id="67c6e-212">Archivos incrustados en ensamblados a los que se hace referencia: los URI que los identifican son únicos porque incluyen el nombre del ensamblado al que se hace referencia y el sufijo `;component`.</span><span class="sxs-lookup"><span data-stu-id="67c6e-212">Embedded files in referenced assemblies: URIs that identify them are unique because they include both the name of the referenced assembly and the `;component` suffix.</span></span>

- <span data-ttu-id="67c6e-213">Archivos de sitio de origen: los URI que los identifican son únicos porque son los únicos archivos que se pueden identificar mediante Pack URI que contienen la autoridad siteoforigin:///.</span><span class="sxs-lookup"><span data-stu-id="67c6e-213">Site of origin files: URIs that identify them are unique because they are the only files that can be identified by pack URIs that contain the siteoforigin:/// authority.</span></span>

<span data-ttu-id="67c6e-214">Una simplificación que la resolución de URI de paquete permite es que el código sea algo independiente de las ubicaciones de los archivos de recursos y de contenido.</span><span class="sxs-lookup"><span data-stu-id="67c6e-214">One simplification that pack URI resolution allows is for code to be somewhat independent of the locations of resource and content files.</span></span> <span data-ttu-id="67c6e-215">Por ejemplo, si tiene un archivo de recursos en el ensamblado local que se reconfigura para que sea un archivo de contenido, el URI del paquete del recurso sigue siendo el mismo, al igual que el código que usa el URI del paquete.</span><span class="sxs-lookup"><span data-stu-id="67c6e-215">For example, if you have a resource file in the local assembly that is reconfigured to be a content file, the pack URI for the resource remains the same, as does the code that uses the pack URI.</span></span>

<a name="Programming_with_Pack_URIs"></a>

## <a name="programming-with-pack-uris"></a><span data-ttu-id="67c6e-216">Programación con Pack URI</span><span class="sxs-lookup"><span data-stu-id="67c6e-216">Programming with Pack URIs</span></span>

<span data-ttu-id="67c6e-217">Muchas clases de WPF implementan propiedades que se pueden establecer con pack uri, entre los que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="67c6e-217">Many WPF classes implement properties that can be set with pack URIs, including:</span></span>

- <xref:System.Windows.Application.StartupUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Frame.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>

- <xref:System.Windows.Documents.Hyperlink.NavigateUri%2A?displayProperty=nameWithType>

- <xref:System.Windows.Window.Icon%2A?displayProperty=nameWithType>

- <xref:System.Windows.Controls.Image.Source%2A?displayProperty=nameWithType>

<span data-ttu-id="67c6e-218">Estas propiedades se pueden establecer tanto desde el marcado como desde el código.</span><span class="sxs-lookup"><span data-stu-id="67c6e-218">These properties can be set from both markup and code.</span></span> <span data-ttu-id="67c6e-219">En esta sección se muestran las construcciones básicas para ambos y, luego, se muestran ejemplos de escenarios comunes.</span><span class="sxs-lookup"><span data-stu-id="67c6e-219">This section demonstrates the basic constructions for both and then shows examples of common scenarios.</span></span>

<a name="Using_Pack_URIs_in_Markup"></a>

### <a name="using-pack-uris-in-markup"></a><span data-ttu-id="67c6e-220">Uso de los Pack URI en el marcado</span><span class="sxs-lookup"><span data-stu-id="67c6e-220">Using Pack URIs in Markup</span></span>

<span data-ttu-id="67c6e-221">Un Pack URI se especifica en el marcado estableciendo el elemento de un atributo con el Pack URI.</span><span class="sxs-lookup"><span data-stu-id="67c6e-221">A pack URI is specified in markup by setting the element of an attribute with the pack URI.</span></span> <span data-ttu-id="67c6e-222">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67c6e-222">For example:</span></span>

`<element attribute="pack://application:,,,/File.xaml" />`

<span data-ttu-id="67c6e-223">En la tabla 1 se muestran los distintos identificadores URI absolutos que puede especificar en el marcado.</span><span class="sxs-lookup"><span data-stu-id="67c6e-223">Table 1 illustrates the various absolute pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="67c6e-224">Tabla 1: Pack URI absolutos en el marcado</span><span class="sxs-lookup"><span data-stu-id="67c6e-224">Table 1: Absolute Pack URIs in Markup</span></span>

|<span data-ttu-id="67c6e-225">File</span><span class="sxs-lookup"><span data-stu-id="67c6e-225">File</span></span>|<span data-ttu-id="67c6e-226">URI de paquete absoluto</span><span class="sxs-lookup"><span data-stu-id="67c6e-226">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="67c6e-227">Archivo de recursos: ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-227">Resource file - local assembly</span></span>|`"pack://application:,,,/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-228">Archivo de recursos en subcarpeta: ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-228">Resource file in subfolder - local assembly</span></span>|`"pack://application:,,,/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-229">Archivo de recursos: ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-229">Resource file - referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-230">Archivo de recursos en subcarpeta del ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-230">Resource file in subfolder of referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-231">Archivo de recursos en el ensamblado al que se hace referencia con versiones</span><span class="sxs-lookup"><span data-stu-id="67c6e-231">Resource file in versioned referenced assembly</span></span>|`"pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-232">Archivo de contenido</span><span class="sxs-lookup"><span data-stu-id="67c6e-232">Content file</span></span>|`"pack://application:,,,/ContentFile.xaml"`|
|<span data-ttu-id="67c6e-233">Archivo de contenido en subcarpeta</span><span class="sxs-lookup"><span data-stu-id="67c6e-233">Content file in subfolder</span></span>|`"pack://application:,,,/Subfolder/ContentFile.xaml"`|
|<span data-ttu-id="67c6e-234">Archivo de sitio de origen</span><span class="sxs-lookup"><span data-stu-id="67c6e-234">Site of origin file</span></span>|`"pack://siteoforigin:,,,/SOOFile.xaml"`|
|<span data-ttu-id="67c6e-235">Archivo de sitio de origen en subcarpeta</span><span class="sxs-lookup"><span data-stu-id="67c6e-235">Site of origin file in subfolder</span></span>|`"pack://siteoforigin:,,,/Subfolder/SOOFile.xaml"`|

<span data-ttu-id="67c6e-236">En la tabla 2 se muestran los diversos identificadores URI relativos que se pueden especificar en el marcado.</span><span class="sxs-lookup"><span data-stu-id="67c6e-236">Table 2 illustrates the various relative pack URIs that you can specify in markup.</span></span>

<span data-ttu-id="67c6e-237">Tabla 2: Pack URI relativos en el marcado</span><span class="sxs-lookup"><span data-stu-id="67c6e-237">Table 2: Relative Pack URIs in Markup</span></span>

|<span data-ttu-id="67c6e-238">File</span><span class="sxs-lookup"><span data-stu-id="67c6e-238">File</span></span>|<span data-ttu-id="67c6e-239">URI de paquete relativo</span><span class="sxs-lookup"><span data-stu-id="67c6e-239">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="67c6e-240">Archivo de recursos en el ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-240">Resource file in local assembly</span></span>|`"/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-241">Archivo de recursos en subcarpeta del ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-241">Resource file in subfolder of local assembly</span></span>|`"/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-242">Archivo de recursos en el ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-242">Resource file in referenced assembly</span></span>|`"/ReferencedAssembly;component/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-243">Archivo de recursos en subcarpeta del ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-243">Resource file in subfolder of referenced assembly</span></span>|`"/ReferencedAssembly;component/Subfolder/ResourceFile.xaml"`|
|<span data-ttu-id="67c6e-244">Archivo de contenido</span><span class="sxs-lookup"><span data-stu-id="67c6e-244">Content file</span></span>|`"/ContentFile.xaml"`|
|<span data-ttu-id="67c6e-245">Archivo de contenido en subcarpeta</span><span class="sxs-lookup"><span data-stu-id="67c6e-245">Content file in subfolder</span></span>|`"/Subfolder/ContentFile.xaml"`|

<a name="Using_Pack_URIs_in_Code"></a>

### <a name="using-pack-uris-in-code"></a><span data-ttu-id="67c6e-246">Uso de los Pack URI en el código</span><span class="sxs-lookup"><span data-stu-id="67c6e-246">Using Pack URIs in Code</span></span>

<span data-ttu-id="67c6e-247">Para especificar un Pack URI en el código, cree una instancia de la clase <xref:System.Uri> y pase el URI del paquete como parámetro al constructor.</span><span class="sxs-lookup"><span data-stu-id="67c6e-247">You specify a pack URI in code by instantiating the <xref:System.Uri> class and passing the pack URI as a parameter to the constructor.</span></span> <span data-ttu-id="67c6e-248">Esto último se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-248">This is demonstrated in the following example.</span></span>

```csharp
Uri uri = new Uri("pack://application:,,,/File.xaml");
```

<span data-ttu-id="67c6e-249">De forma predeterminada, la clase <xref:System.Uri> considera que los URI Pack son absolutos.</span><span class="sxs-lookup"><span data-stu-id="67c6e-249">By default, the <xref:System.Uri> class considers pack URIs to be absolute.</span></span> <span data-ttu-id="67c6e-250">Por consiguiente, se produce una excepción cuando se crea una instancia de la clase <xref:System.Uri> con un Pack URI relativo.</span><span class="sxs-lookup"><span data-stu-id="67c6e-250">Consequently, an exception is raised when an instance of the <xref:System.Uri> class is created with a relative pack URI.</span></span>

```csharp
Uri uri = new Uri("/File.xaml");
```

<span data-ttu-id="67c6e-251">Afortunadamente, la sobrecarga <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> del constructor de clase <xref:System.Uri> acepta un parámetro de tipo <xref:System.UriKind> para permitirle especificar si un Pack URI es absoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="67c6e-251">Fortunately, the <xref:System.Uri.%23ctor%28System.String%2CSystem.UriKind%29> overload of the <xref:System.Uri> class constructor accepts a parameter of type <xref:System.UriKind> to allow you to specify whether a pack URI is either absolute or relative.</span></span>

```csharp
// Absolute URI (default)
Uri absoluteUri = new Uri("pack://application:,,,/File.xaml", UriKind.Absolute);
// Relative URI
Uri relativeUri = new Uri("/File.xaml",
                        UriKind.Relative);
```

<span data-ttu-id="67c6e-252">Solo debe especificar <xref:System.UriKind.Absolute> o <xref:System.UriKind.Relative> cuando esté seguro de que el URI del paquete proporcionado es uno o el otro.</span><span class="sxs-lookup"><span data-stu-id="67c6e-252">You should specify only <xref:System.UriKind.Absolute> or <xref:System.UriKind.Relative> when you are certain that the provided pack URI is one or the other.</span></span> <span data-ttu-id="67c6e-253">Si no conoce el tipo de Pack URI que se usa, por ejemplo, cuando un usuario escribe un Pack URI en tiempo de ejecución, use <xref:System.UriKind.RelativeOrAbsolute> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="67c6e-253">If you don't know the type of pack URI that is used, such as when a user enters a pack URI at run time, use <xref:System.UriKind.RelativeOrAbsolute> instead.</span></span>

```csharp
// Relative or Absolute URI provided by user via a text box
TextBox userProvidedUriTextBox = new TextBox();
Uri uri = new Uri(userProvidedUriTextBox.Text, UriKind.RelativeOrAbsolute);
```

<span data-ttu-id="67c6e-254">En la tabla 3 se muestran los diversos Pack URI relativos que se pueden especificar en el código mediante <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67c6e-254">Table 3 illustrates the various relative pack URIs that you can specify in code by using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="67c6e-255">Tabla 3: Pack URI absolutos en el código</span><span class="sxs-lookup"><span data-stu-id="67c6e-255">Table 3: Absolute Pack URIs in Code</span></span>

|<span data-ttu-id="67c6e-256">File</span><span class="sxs-lookup"><span data-stu-id="67c6e-256">File</span></span>|<span data-ttu-id="67c6e-257">URI de paquete absoluto</span><span class="sxs-lookup"><span data-stu-id="67c6e-257">Absolute pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="67c6e-258">Archivo de recursos: ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-258">Resource file - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-259">Archivo de recursos en subcarpeta: ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-259">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-260">Archivo de recursos: ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-260">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-261">Archivo de recursos en subcarpeta del ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-261">Resource file in subfolder of referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-262">Archivo de recursos en el ensamblado al que se hace referencia con versiones</span><span class="sxs-lookup"><span data-stu-id="67c6e-262">Resource file in versioned referenced assembly</span></span>|`Uri uri = new Uri("pack://application:,,,/ReferencedAssembly;v1.0.0.0;component/ResourceFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-263">Archivo de contenido</span><span class="sxs-lookup"><span data-stu-id="67c6e-263">Content file</span></span>|`Uri uri = new Uri("pack://application:,,,/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-264">Archivo de contenido en subcarpeta</span><span class="sxs-lookup"><span data-stu-id="67c6e-264">Content file in subfolder</span></span>|`Uri uri = new Uri("pack://application:,,,/Subfolder/ContentFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-265">Archivo de sitio de origen</span><span class="sxs-lookup"><span data-stu-id="67c6e-265">Site of origin file</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/SOOFile.xaml", UriKind.Absolute);`|
|<span data-ttu-id="67c6e-266">Archivo de sitio de origen en subcarpeta</span><span class="sxs-lookup"><span data-stu-id="67c6e-266">Site of origin file in subfolder</span></span>|`Uri uri = new Uri("pack://siteoforigin:,,,/Subfolder/SOOFile.xaml", UriKind.Absolute);`|

<span data-ttu-id="67c6e-267">En la tabla 4 se muestran los diversos Pack URI relativos que se pueden especificar en el código mediante <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67c6e-267">Table 4 illustrates the various relative pack URIs that you can specify in code using <xref:System.Uri?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="67c6e-268">Tabla 4: Pack URI relativos en el código</span><span class="sxs-lookup"><span data-stu-id="67c6e-268">Table 4: Relative Pack URIs in Code</span></span>

|<span data-ttu-id="67c6e-269">File</span><span class="sxs-lookup"><span data-stu-id="67c6e-269">File</span></span>|<span data-ttu-id="67c6e-270">URI de paquete relativo</span><span class="sxs-lookup"><span data-stu-id="67c6e-270">Relative pack URI</span></span>|
|----------|-------------------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="67c6e-271">Archivo de recursos: ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-271">Resource file - local assembly</span></span>|`Uri uri = new Uri("/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="67c6e-272">Archivo de recursos en subcarpeta: ensamblado local</span><span class="sxs-lookup"><span data-stu-id="67c6e-272">Resource file in subfolder - local assembly</span></span>|`Uri uri = new Uri("/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="67c6e-273">Archivo de recursos: ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-273">Resource file - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="67c6e-274">Archivo de recursos en subcarpeta: ensamblado al que se hace referencia</span><span class="sxs-lookup"><span data-stu-id="67c6e-274">Resource file in subfolder - referenced assembly</span></span>|`Uri uri = new Uri("/ReferencedAssembly;component/Subfolder/ResourceFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="67c6e-275">Archivo de contenido</span><span class="sxs-lookup"><span data-stu-id="67c6e-275">Content file</span></span>|`Uri uri = new Uri("/ContentFile.xaml", UriKind.Relative);`|
|<span data-ttu-id="67c6e-276">Archivo de contenido en subcarpeta</span><span class="sxs-lookup"><span data-stu-id="67c6e-276">Content file in subfolder</span></span>|`Uri uri = new Uri("/Subfolder/ContentFile.xaml", UriKind.Relative);`|

<a name="Common_Pack_URI_Scenarios"></a>

### <a name="common-pack-uri-scenarios"></a><span data-ttu-id="67c6e-277">Escenarios comunes de Pack URI</span><span class="sxs-lookup"><span data-stu-id="67c6e-277">Common Pack URI Scenarios</span></span>

<span data-ttu-id="67c6e-278">En las secciones anteriores se ha explicado cómo construir pack uri para identificar los archivos de recursos, contenido y sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="67c6e-278">The preceding sections have discussed how to construct pack URIs to identify resource, content, and site of origin files.</span></span> <span data-ttu-id="67c6e-279">En WPF, estas construcciones se utilizan de varias maneras, y las secciones siguientes cubren varios usos comunes.</span><span class="sxs-lookup"><span data-stu-id="67c6e-279">In WPF, these constructions are used in a variety of ways, and the following sections cover several common usages.</span></span>

<a name="Specifying_the_UI_to_Show_when_an_Application_Starts"></a>

#### <a name="specifying-the-ui-to-show-when-an-application-starts"></a><span data-ttu-id="67c6e-280">Especificación de la UI que se va a mostrar cuando una aplicación se inicia por primera vez</span><span class="sxs-lookup"><span data-stu-id="67c6e-280">Specifying the UI to Show When an Application Starts</span></span>

<span data-ttu-id="67c6e-281"><xref:System.Windows.Application.StartupUri%2A> especifica el primer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que se va a mostrar cuando se inicia una aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="67c6e-281"><xref:System.Windows.Application.StartupUri%2A> specifies the first [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to show when a WPF application is launched.</span></span> <span data-ttu-id="67c6e-282">En el caso de las aplicaciones independientes, el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] puede ser una ventana, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-282">For standalone applications, the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] can be a window, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/Copy of App.xaml#startupuriwindow)]

<span data-ttu-id="67c6e-283">Las aplicaciones independientes y las aplicaciones de explorador XAML (XBAP) también pueden especificar una página como la interfaz de usuario inicial, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-283">Standalone applications and XAML browser applications (XBAPs) can also specify a page as the initial UI, as shown in the following example.</span></span>

[!code-xaml[PackURIOverviewSnippets#StartupUriPage](~/samples/snippets/csharp/VS_Snippets_Wpf/PackURIOverviewSnippets/CS/App.xaml#startupuripage)]

<span data-ttu-id="67c6e-284">Si la aplicación es una aplicación independiente y se especifica una página con <xref:System.Windows.Application.StartupUri%2A>, WPF abre un <xref:System.Windows.Navigation.NavigationWindow> para hospedar la página.</span><span class="sxs-lookup"><span data-stu-id="67c6e-284">If the application is a standalone application and a page is specified with <xref:System.Windows.Application.StartupUri%2A>, WPF opens a <xref:System.Windows.Navigation.NavigationWindow> to host the page.</span></span> <span data-ttu-id="67c6e-285">En el caso de las XBAP, la página se muestra en el explorador del host.</span><span class="sxs-lookup"><span data-stu-id="67c6e-285">For XBAPs, the page is shown in the host browser.</span></span>

<a name="Navigating_to_a_Page"></a>

#### <a name="navigating-to-a-page"></a><span data-ttu-id="67c6e-286">Navegación a una página</span><span class="sxs-lookup"><span data-stu-id="67c6e-286">Navigating to a Page</span></span>

<span data-ttu-id="67c6e-287">En el ejemplo siguiente se muestra cómo navegar a una página.</span><span class="sxs-lookup"><span data-stu-id="67c6e-287">The following example shows how to navigate to a page.</span></span>

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

<span data-ttu-id="67c6e-288">Para obtener más información sobre las distintas maneras de navegar en WPF, consulte [información general sobre navegación](navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67c6e-288">For more information on the various ways to navigate in WPF, see [Navigation Overview](navigation-overview.md).</span></span>

<a name="Specifying_a_Window_Icon"></a>

#### <a name="specifying-a-window-icon"></a><span data-ttu-id="67c6e-289">Especificación de un icono de ventana</span><span class="sxs-lookup"><span data-stu-id="67c6e-289">Specifying a Window Icon</span></span>

<span data-ttu-id="67c6e-290">En el ejemplo siguiente se muestra cómo usar un identificador URI para especificar el icono de una ventana.</span><span class="sxs-lookup"><span data-stu-id="67c6e-290">The following example shows how to use a URI to specify a window's icon.</span></span>

[!code-xaml[WindowIconSnippets#WindowIconSetXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/WindowIconSnippets/XAML/MainWindow.xaml#windowiconsetxaml)]

<span data-ttu-id="67c6e-291">Para obtener más información, vea <xref:System.Windows.Window.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="67c6e-291">For more information, see <xref:System.Windows.Window.Icon%2A>.</span></span>

<a name="Loading_Image__Audio__and_Video_Files"></a>

#### <a name="loading-image-audio-and-video-files"></a><span data-ttu-id="67c6e-292">Carga de archivos de imagen, audio y vídeo</span><span class="sxs-lookup"><span data-stu-id="67c6e-292">Loading Image, Audio, and Video Files</span></span>

<span data-ttu-id="67c6e-293">WPF permite a las aplicaciones usar una amplia variedad de tipos de medios, los cuales se pueden identificar y cargar con pack uri, tal y como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="67c6e-293">WPF allows applications to use a wide variety of media types, all of which can be identified and loaded with pack URIs, as shown in the following examples.</span></span>

[!code-xaml[MediaPlayerVideoSample#VideoPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerVideoSample/CS/HomePage.xaml#videopackuriatsoo)]

[!code-xaml[MediaPlayerAudioSample#AudioPackURIAtSOO](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaPlayerAudioSample/CS/HomePage.xaml#audiopackuriatsoo)]

[!code-xaml[ImageSample#ImagePackURIContent](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageSample/CS/HomePage.xaml#imagepackuricontent)]

<span data-ttu-id="67c6e-294">Para obtener más información sobre cómo trabajar con contenido multimedia, vea [gráficos y multimedia](../graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="67c6e-294">For more information on working with media content, see [Graphics and Multimedia](../graphics-multimedia/index.md).</span></span>

<a name="Loading_a_Resource_Dictionary_from_the_Site_of_Origin"></a>

#### <a name="loading-a-resource-dictionary-from-the-site-of-origin"></a><span data-ttu-id="67c6e-295">Carga de un diccionario de recursos desde el sitio de origen</span><span class="sxs-lookup"><span data-stu-id="67c6e-295">Loading a Resource Dictionary from the Site of Origin</span></span>

<span data-ttu-id="67c6e-296">Los diccionarios de recursos (<xref:System.Windows.ResourceDictionary>) se pueden usar para admitir los temas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-296">Resource dictionaries (<xref:System.Windows.ResourceDictionary>) can be used to support application themes.</span></span> <span data-ttu-id="67c6e-297">Una forma de crear y administrar temas consiste en crear varios temas como diccionarios de recursos que están ubicados en el sitio de origen de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-297">One way to create and manage themes is to create multiple themes as resource dictionaries that are located at an application's site of origin.</span></span> <span data-ttu-id="67c6e-298">Esto permite agregar temas y actualizarlos sin tener que volver a compilar e implementar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="67c6e-298">This allows themes to be added and updated without recompiling and redeploying an application.</span></span> <span data-ttu-id="67c6e-299">Estos diccionarios de recursos se pueden identificar y cargar mediante pack uri, que se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="67c6e-299">These resource dictionaries can be identified and loaded using pack URIs, which is shown in the following example.</span></span>

[!code-xaml[ResourceDictionarySnippets#ResourceDictionaryPackURI](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourceDictionarySnippets/CS/App.xaml#resourcedictionarypackuri)]

<span data-ttu-id="67c6e-300">Para obtener información general sobre los temas de WPF, consulte [aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67c6e-300">For an overview of themes in WPF, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="67c6e-301">Vea también</span><span class="sxs-lookup"><span data-stu-id="67c6e-301">See also</span></span>

- [<span data-ttu-id="67c6e-302">Archivos de recursos, contenido y datos de aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="67c6e-302">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
