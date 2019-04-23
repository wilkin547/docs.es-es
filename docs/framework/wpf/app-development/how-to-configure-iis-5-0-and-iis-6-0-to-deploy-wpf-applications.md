---
title: Procedimiento Configurar IIS 5.0 e IIS 6.0 para implementar aplicaciones de WPF
ms.date: 03/30/2017
helpviewer_keywords:
- MIME types [WPF], registering
- adjusting content expiration setting [WPF]
- registering file extensions [WPF]
- deploying applications [WPF]
- applications [WPF], deploying
- Web servers [WPF], configuring to deploy WPF applications
- configuring Web servers to deploy WPF applications [WPF]
- content expiration setting [WPF], adjusting
- file extensions [WPF], registering
- registering MIME types [WPF]
ms.assetid: c6e8c2cb-9ba2-4e75-a0d5-180ec9639433
ms.openlocfilehash: 6fa00c4ced8c05d056703560e5740689c6dcfe39
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973673"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a><span data-ttu-id="a7b8f-102">Procedimiento Configurar IIS 5.0 e IIS 6.0 para implementar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a7b8f-102">How to: Configure IIS 5.0 and IIS 6.0 to Deploy WPF Applications</span></span>

<span data-ttu-id="a7b8f-103">Puede implementar una aplicación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] desde la mayoría de los servidores web, siempre que estén configurados con los tipos [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] adecuados.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-103">You can deploy a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application from most Web servers, as long as they are configured with the appropriate [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] types.</span></span> <span data-ttu-id="a7b8f-104">De manera predeterminada, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] se configura con estos tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)], pero [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] y [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] no.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-104">By default, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] is configured with these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types, but [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] are not.</span></span>

<span data-ttu-id="a7b8f-105">En este tema se describe cómo configurar [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] y [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] para implementar aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-105">This topic describes how to configure [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] and [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] to deploy [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>

> [!NOTE]
> <span data-ttu-id="a7b8f-106">Puede comprobar el *UserAgent* cadena en el registro para determinar si un sistema tiene instalado .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-106">You can check the *UserAgent* string in the registry to determine whether a system has .NET Framework installed.</span></span> <span data-ttu-id="a7b8f-107">Para obtener detalles y un script que examina la *UserAgent* cadena para determinar si .NET Framework está instalada en un sistema, consulte [detectar si .NET Framework 3.0 está instalada la](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span><span class="sxs-lookup"><span data-stu-id="a7b8f-107">For details and a script that examines the *UserAgent* string to determine whether .NET Framework is installed on a system, see [Detect Whether the .NET Framework 3.0 Is Installed](how-to-detect-whether-the-net-framework-3-0-is-installed.md).</span></span>

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a><span data-ttu-id="a7b8f-108">Ajustar la configuración de la expiración del contenido</span><span class="sxs-lookup"><span data-stu-id="a7b8f-108">Adjust the Content Expiration Setting</span></span>

<span data-ttu-id="a7b8f-109">Debe ajustar el valor de la expiración del contenido a 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-109">You should adjust the content expiration setting to 1 minute.</span></span> <span data-ttu-id="a7b8f-110">En el siguiente procedimiento se indica cómo hacerlo con [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-110">The following procedure outlines how to do this with [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span>

1. <span data-ttu-id="a7b8f-111">Haga clic en el menú **Inicio**, seleccione **Herramientas administrativas** y, después, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-111">Click the **Start** menu, point to **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="a7b8f-112">También puede iniciar esta aplicación desde la línea de comandos con "%SystemRoot%\system32\inetsrv\iis.msc".</span><span class="sxs-lookup"><span data-stu-id="a7b8f-112">You can also launch this application from the command line with "%SystemRoot%\system32\inetsrv\iis.msc".</span></span>

2. <span data-ttu-id="a7b8f-113">Expanda el árbol de [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] hasta encontrar el nodo **Sitio web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-113">Expand the [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] tree until you find the **Default Web site** node.</span></span>

3. <span data-ttu-id="a7b8f-114">Haga clic con el botón derecho en **Sitio web predeterminado** y seleccione **Propiedades** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-114">Right-click **Default Web site** and select **Properties** from the context menu.</span></span>

4. <span data-ttu-id="a7b8f-115">Seleccione la pestaña **Encabezados HTTP** y haga clic en "Habilitar expiración de contenido".</span><span class="sxs-lookup"><span data-stu-id="a7b8f-115">Select the **HTTP Headers** tab and click "Enable Content Expiration".</span></span>

5. <span data-ttu-id="a7b8f-116">Establezca el contenido para que expire transcurrido 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-116">Set the content to expire after 1 minute.</span></span>

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a><span data-ttu-id="a7b8f-117">Registrar tipos MIME y extensiones de archivo</span><span class="sxs-lookup"><span data-stu-id="a7b8f-117">Register MIME Types and File Extensions</span></span>

<span data-ttu-id="a7b8f-118">Debe registrar varios tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] y extensiones de archivo para que el explorador del sistema cliente pueda cargar el controlador correcto.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-118">You must register several [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types and file extensions so that the browser on the client's system can load the correct handler.</span></span> <span data-ttu-id="a7b8f-119">Debe agregar los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7b8f-119">You need to add the following types:</span></span>

|<span data-ttu-id="a7b8f-120">Extensión</span><span class="sxs-lookup"><span data-stu-id="a7b8f-120">Extension</span></span>|<span data-ttu-id="a7b8f-121">Tipo MIME</span><span class="sxs-lookup"><span data-stu-id="a7b8f-121">MIME Type</span></span>|
|---------------|---------------|
|<span data-ttu-id="a7b8f-122">.manifest</span><span class="sxs-lookup"><span data-stu-id="a7b8f-122">.manifest</span></span>|<span data-ttu-id="a7b8f-123">application/manifest</span><span class="sxs-lookup"><span data-stu-id="a7b8f-123">application/manifest</span></span>|
|<span data-ttu-id="a7b8f-124">.xaml</span><span class="sxs-lookup"><span data-stu-id="a7b8f-124">.xaml</span></span>|<span data-ttu-id="a7b8f-125">application/xaml+xml</span><span class="sxs-lookup"><span data-stu-id="a7b8f-125">application/xaml+xml</span></span>|
|<span data-ttu-id="a7b8f-126">.application</span><span class="sxs-lookup"><span data-stu-id="a7b8f-126">.application</span></span>|<span data-ttu-id="a7b8f-127">application/x-ms-application</span><span class="sxs-lookup"><span data-stu-id="a7b8f-127">application/x-ms-application</span></span>|
|<span data-ttu-id="a7b8f-128">.xbap</span><span class="sxs-lookup"><span data-stu-id="a7b8f-128">.xbap</span></span>|<span data-ttu-id="a7b8f-129">application/x-ms-xbap</span><span class="sxs-lookup"><span data-stu-id="a7b8f-129">application/x-ms-xbap</span></span>|
|<span data-ttu-id="a7b8f-130">.deploy</span><span class="sxs-lookup"><span data-stu-id="a7b8f-130">.deploy</span></span>|<span data-ttu-id="a7b8f-131">application/octet-stream</span><span class="sxs-lookup"><span data-stu-id="a7b8f-131">application/octet-stream</span></span>|
|<span data-ttu-id="a7b8f-132">.xps</span><span class="sxs-lookup"><span data-stu-id="a7b8f-132">.xps</span></span>|<span data-ttu-id="a7b8f-133">application/vnd.ms-xpsdocument</span><span class="sxs-lookup"><span data-stu-id="a7b8f-133">application/vnd.ms-xpsdocument</span></span>|

> [!NOTE]
> <span data-ttu-id="a7b8f-134">No necesita registrar los tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] ni las extensiones de archivo en los sistemas cliente.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-134">You do not need to register [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types or file extensions on client systems.</span></span> <span data-ttu-id="a7b8f-135">Se registran automáticamente al instalar Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-135">They are registered automatically when you install Microsoft .NET Framework.</span></span>

<span data-ttu-id="a7b8f-136">El siguiente ejemplo de Microsoft Visual Basic Scripting Edition (VBScript) agrega automáticamente el necesario [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] tipos [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-136">The following Microsoft Visual Basic Scripting Edition (VBScript) sample automatically adds the necessary [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types to [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].</span></span> <span data-ttu-id="a7b8f-137">Para usar el script, copie el código en un archivo .vbs de su servidor.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-137">To use the script, copy the code to a .vbs file on your server.</span></span> <span data-ttu-id="a7b8f-138">Después, ejecute el script mediante la ejecución del archivo desde la línea de comandos o haga doble clic en él desde [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-138">Then, run the script by running the file from the command line or double-clicking the file in [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].</span></span>

```vb
' This script adds the necessary Windows Presentation Foundation MIME types
' to an IIS Server.
' To use this script, just double-click or execute it from a command line.
' Running this script multiple times results in multiple entries in the IIS MimeMap.

Dim MimeMapObj, MimeMapArray, MimeTypesToAddArray, WshShell, oExec
Const ADS_PROPERTY_UPDATE = 2

' Set the MIME types to be added
MimeTypesToAddArray = Array(".manifest", "application/manifest", ".xaml", _
    "application/xaml+xml", ".application", "application/x-ms-application", _
    ".deploy", "application/octet-stream", ".xbap", "application/x-ms-xbap", _
    ".xps", "application/vnd.ms-xpsdocument")

' Get the MimeMap object
Set MimeMapObj = GetObject("IIS://LocalHost/MimeMap")

' Call AddMimeType for every pair of extension/MIME type
For counter = 0 to UBound(MimeTypesToAddArray) Step 2
    AddMimeType MimeTypesToAddArray(counter), MimeTypesToAddArray(counter+1)
Next

' Create a Shell object
Set WshShell = CreateObject("WScript.Shell")

' Stop and Start the IIS Service
Set oExec = WshShell.Exec("net stop w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = WshShell.Exec("net start w3svc")
Do While oExec.Status = 0
    WScript.Sleep 100
Loop

Set oExec = Nothing

' Report status to user
WScript.Echo "Windows Presentation Foundation MIME types have been registered."

' AddMimeType Sub
Sub AddMimeType (Ext, MType)

    ' Get the mappings from the MimeMap property.
    MimeMapArray = MimeMapObj.GetEx("MimeMap")

    ' Add a new mapping.
    i = UBound(MimeMapArray) + 1
    ReDim Preserve MimeMapArray(i)
    Set MimeMapArray(i) = CreateObject("MimeMap")
    MimeMapArray(i).Extension = Ext
    MimeMapArray(i).MimeType = MType
    MimeMapObj.PutEx ADS_PROPERTY_UPDATE, "MimeMap", MimeMapArray
    MimeMapObj.SetInfo

End Sub
```

> [!NOTE]
> <span data-ttu-id="a7b8f-139">Si ejecuta este script varias veces, se crean varias entradas de asignación [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] en la metabase de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-139">Running this script multiple times creates multiple [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] map entries in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>

<span data-ttu-id="a7b8f-140">Después de haber ejecutado este script, puede que no vea los tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] adicionales de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-140">After you have run this script, you may not see additional [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types from the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)].</span></span> <span data-ttu-id="a7b8f-141">En cambio, estos tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] se han agregado a la metabase de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-141">However, these [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types have been added to the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span> <span data-ttu-id="a7b8f-142">El script siguiente mostrará todos los tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] en la metabase de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7b8f-142">The following script will display all the [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] types in the [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] or [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] metabase.</span></span>

```vb
' This script lists the MIME types for an IIS Server.
' To use this script, just double-click or execute it from a command line
' by calling cscript.exe

dim mimeMapEntry, allMimeMaps

' Get the MimeMap object.
Set mimeMapEntry = GetObject("IIS://localhost/MimeMap")
allMimeMaps = mimeMapEntry.GetEx("MimeMap")

' Display the mappings in the table.
For Each mimeMap In allMimeMaps
    WScript.Echo(mimeMap.MimeType & " (" & mimeMap.Extension + ")")
Next
```

<span data-ttu-id="a7b8f-143">Guarde el script como un archivo `.vbs` (por ejemplo, `DiscoverIISMimeTypes.vbs`) y ejecútelo desde el símbolo del sistema usando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7b8f-143">Save the script as a `.vbs` file (for example, `DiscoverIISMimeTypes.vbs`) and run it from the command prompt using the following command:</span></span>

```console
cscript DiscoverIISMimeTypes.vbs
```
