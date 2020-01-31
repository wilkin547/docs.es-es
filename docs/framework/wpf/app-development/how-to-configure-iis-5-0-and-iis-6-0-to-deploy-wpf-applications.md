---
title: 'Cómo: Configurar IIS 5.0 e IIS 6.0 para implementar aplicaciones de WPF'
titleSuffix: ''
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
ms.openlocfilehash: d557ac6cd380edcbc93b5315f6356697817274bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740407"
---
# <a name="how-to-configure-iis-50-and-iis-60-to-deploy-wpf-applications"></a>Cómo: Configurar IIS 5.0 e IIS 6.0 para implementar aplicaciones de WPF

Puede implementar una aplicación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] desde la mayoría de los servidores Web, siempre y cuando estén configurados con los tipos MIME (Extensiones multipropósito de correo Internet) adecuados. De forma predeterminada, Microsoft Internet Information Services (IIS) 7,0 se configura con estos tipos MIME, pero Microsoft Internet Information Services (IIS) 5,0 y Microsoft Internet Information Services (IIS) 6,0 no.

En este tema se describe cómo configurar Microsoft Internet Information Services (IIS) 5,0 y Microsoft Internet Information Services (IIS) 6,0 para implementar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones.

> [!NOTE]
> Puede comprobar la cadena *UserAgent* en el registro para determinar si un sistema tiene .NET Framework instalado. Para obtener más información y un script que examina la cadena *UserAgent* para determinar si .NET Framework está instalado en un sistema, consulte [detectar si el .NET Framework 3,0 está instalado](how-to-detect-whether-the-net-framework-3-0-is-installed.md).

<a name="content_expiration"></a>

## <a name="adjust-the-content-expiration-setting"></a>Ajustar la configuración de la expiración del contenido

Debe ajustar el valor de la expiración del contenido a 1 minuto. En el procedimiento siguiente se describe cómo hacerlo con IIS.

1. Haga clic en el menú **Inicio**, seleccione **Herramientas administrativas** y, después, haga clic en **Administrador de Internet Information Services (IIS)** . También puede iniciar esta aplicación desde la línea de comandos con "%SystemRoot%\system32\inetsrv\iis.msc".

2. Expanda el árbol de IIS hasta que encuentre el nodo **sitio web predeterminado** .

3. Haga clic con el botón derecho en **Sitio web predeterminado** y seleccione **Propiedades** en el menú contextual.

4. Seleccione la pestaña **Encabezados HTTP** y haga clic en "Habilitar expiración de contenido".

5. Establezca el contenido para que expire transcurrido 1 minuto.

<a name="register_mime_types"></a>

## <a name="register-mime-types-and-file-extensions"></a>Registrar tipos MIME y extensiones de archivo

Debe registrar varios tipos MIME y extensiones de archivo para que el explorador del sistema del cliente pueda cargar el controlador correcto. Debe agregar los tipos siguientes:

|Comprobación de actualización|Tipo MIME|
|---------------|---------------|
|.manifest|application/manifest|
|.xaml|application/xaml+xml|
|.application|application/x-ms-application|
|.xbap|application/x-ms-xbap|
|.deploy|application/octet-stream|
|.xps|application/vnd.ms-xpsdocument|

> [!NOTE]
> No es necesario registrar los tipos MIME o las extensiones de archivo en los sistemas cliente. Se registran automáticamente al instalar Microsoft .NET Framework.

El siguiente ejemplo de Microsoft Visual Basic Scripting Edition (VBScript) agrega automáticamente los tipos MIME necesarios a IIS. Para usar el script, copie el código en un archivo .vbs de su servidor. A continuación, ejecute el archivo desde la línea de comandos o haga doble clic en el archivo en el explorador de Microsoft Windows para ejecutar el script.

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
> Ejecutar este script varias veces crea varias entradas de asignación MIME en la metabase de Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0.

Después de ejecutar este script, es posible que no vea tipos MIME adicionales en Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0 Microsoft Management Console (MMC). Sin embargo, estos tipos MIME se han agregado a la metabase de Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0. El siguiente script mostrará todos los tipos MIME en la metabase de Microsoft Internet Information Services (IIS) 5,0 o Microsoft Internet Information Services (IIS) 6,0.

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
