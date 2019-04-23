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
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>Procedimiento Configurar IIS 5.0 e IIS 6.0 para implementar aplicaciones de WPF

Puede implementar una aplicación de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] desde la mayoría de los servidores web, siempre que estén configurados con los tipos [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] adecuados. De manera predeterminada, [!INCLUDE[TLA#tla_iis70](../../../../includes/tlasharptla-iis70-md.md)] se configura con estos tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)], pero [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] y [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] no.

En este tema se describe cómo configurar [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] y [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] para implementar aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

> [!NOTE]
> Puede comprobar el *UserAgent* cadena en el registro para determinar si un sistema tiene instalado .NET Framework. Para obtener detalles y un script que examina la *UserAgent* cadena para determinar si .NET Framework está instalada en un sistema, consulte [detectar si .NET Framework 3.0 está instalada la](how-to-detect-whether-the-net-framework-3-0-is-installed.md).

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a>Ajustar la configuración de la expiración del contenido

Debe ajustar el valor de la expiración del contenido a 1 minuto. En el siguiente procedimiento se indica cómo hacerlo con [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)].

1. Haga clic en el menú **Inicio**, seleccione **Herramientas administrativas** y, después, haga clic en **Administrador de Internet Information Services (IIS)**. También puede iniciar esta aplicación desde la línea de comandos con "%SystemRoot%\system32\inetsrv\iis.msc".

2. Expanda el árbol de [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)] hasta encontrar el nodo **Sitio web predeterminado**.

3. Haga clic con el botón derecho en **Sitio web predeterminado** y seleccione **Propiedades** en el menú contextual.

4. Seleccione la pestaña **Encabezados HTTP** y haga clic en "Habilitar expiración de contenido".

5. Establezca el contenido para que expire transcurrido 1 minuto.

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a>Registrar tipos MIME y extensiones de archivo

Debe registrar varios tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] y extensiones de archivo para que el explorador del sistema cliente pueda cargar el controlador correcto. Debe agregar los tipos siguientes:

|Extensión|Tipo MIME|
|---------------|---------------|
|.manifest|application/manifest|
|.xaml|application/xaml+xml|
|.application|application/x-ms-application|
|.xbap|application/x-ms-xbap|
|.deploy|application/octet-stream|
|.xps|application/vnd.ms-xpsdocument|

> [!NOTE]
> No necesita registrar los tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] ni las extensiones de archivo en los sistemas cliente. Se registran automáticamente al instalar Microsoft .NET Framework.

El siguiente ejemplo de Microsoft Visual Basic Scripting Edition (VBScript) agrega automáticamente el necesario [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] tipos [!INCLUDE[TLA2#tla_iis5](../../../../includes/tla2sharptla-iis5-md.md)]. Para usar el script, copie el código en un archivo .vbs de su servidor. Después, ejecute el script mediante la ejecución del archivo desde la línea de comandos o haga doble clic en él desde [!INCLUDE[TLA#tla_winexpl](../../../../includes/tlasharptla-winexpl-md.md)].

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
> Si ejecuta este script varias veces, se crean varias entradas de asignación [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] en la metabase de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].

Después de haber ejecutado este script, puede que no vea los tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] adicionales de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)] [!INCLUDE[TLA#tla_mmc](../../../../includes/tlasharptla-mmc-md.md)]. En cambio, estos tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] se han agregado a la metabase de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)]. El script siguiente mostrará todos los tipos [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] en la metabase de [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] o [!INCLUDE[TLA#tla_iis60](../../../../includes/tlasharptla-iis60-md.md)].

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

Guarde el script como un archivo `.vbs` (por ejemplo, `DiscoverIISMimeTypes.vbs`) y ejecútelo desde el símbolo del sistema usando el comando siguiente:

```console
cscript DiscoverIISMimeTypes.vbs
```
