---
title: "Cambios de redestinación en .NET Framework 4.7 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes,.NET Framework
- retargeting changes,.NET Framework 4.7
- application compatibility
ms.assetid: d98bf1e3-0017-4933-8e7b-191ac3542fcc
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2881049ee490bf0abdd8b2f0651ca3703ccae76a
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-47"></a>Cambios de redestinación en .NET Framework 4.7

En casos poco frecuentes, los cambios de redestinación pueden afectar a las aplicaciones que se vuelven a compilar para .NET Framework 4.7. No afectan a los binarios que tienen como destino una versión anterior de .NET Framework pero que se ejecutan en la versión 4.7. .NET Framework 4.7 incluye cambios de redestinación en las áreas siguientes:  

-   [Principal](#Core)  
-   [ASP.NET](#asp) 
-   [Windows Communication Foundation (WCF)](#WCF)  
-   [Windows Presentation Foundation (WPF)](#WPF)
 
 La columna de ámbito de las tablas siguientes especifica la importancia de cada cambio:  
  
-   Principal. Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código. Observe que ninguno de los cambios de redestinación pertenecen a esta categoría.  
  
-   Secundario. Cambio que afecta a un pequeño número de aplicaciones o que requiere ligeras modificaciones en el código.  
  
-   Avanzado. Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.  
  
-   Transparente. Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.  
  
## <a name="a-namecore--core"></a><a name="Core" /> Principal

| Característica | Cambio | Impacto | Ámbito |
|----|----|----|----|
|<xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> | Las aplicaciones que tienen como destino .NET Framework 4.6.2 y versiones anteriores esperan que el valor asignado a esta propiedad sea un < xref:System.IntPtr > en la ubicación especificada en la memoria donde se encuentra el valor HWND.<br/></br>A partir de las aplicaciones que tienen como destino NET Framework 4.7, una aplicación de Windows Forms puede establecer el valor de esta propiedad con un código como el siguiente: <br/><br/>` cspParameters.ParentWindowHandle = form.Handle; ` | Las aplicaciones que encuentren conveniente este cambio de comportamiento pueden rechazar el nuevo comportamiento. De forma similar, las aplicaciones que tengan como destino versiones anteriores de .NET Framework, pero que se ejecuten en .NET Framework 4.7 pueden incluirse en el comportamiento nuevo. Para más información, vea [Mitigación: CspParameters.ParentWindowHandle espera HWND](../../../docs/framework/migration-guide/mitigation-cspparameters-parentwindowhandle-expects-an-hwnd.md). | Secundaria |
| Serialización mediante el elemento < xref:System.Runtime.Serialization.Json.DataContractJsonSerializer > | A partir de las aplicaciones dirigidas a .NET Framework 4.7, la serialización de los caracteres de control con < xref:System.Runtime.Serialization.Json.DataContractJsonSerializer > es ahora compatible con ECMAScript V6 y V8 | Este cambio se ajusta al estándar ECMAScript y debería tener poca repercusión. Si es así, hay un modificador de compatibilidad disponible para restaurar el comportamiento anterior. Para más información, vea [Mitigación: Serialización del caracteres de control con DataContractJsonSerializer](../../../docs/framework/migration-guide/mitigation-serialization-control-characters.md)  | Borde |

## <a name="a-nameasp--aspnet"></a><a name="asp" /> ASP.NET

| Característica  |Cambio  |Impacto | Ámbito | 
---------|---------|---------|-----|
Límite de solicitudes simultáneas por sesión | En .NET Framework 4.6.2 y versiones anteriores, ASP.NET ejecuta solicitudes con el mismos elemento <xref:System.Web.SessionState.HttpSessionState.SessionID%2A> de forma secuencial, y ASP.NET siempre emite el elemento <xref:System.Web.SessionState.HttpSessionState.SessionID%2A> a través de una cookie de forma predeterminada. Si una página tarda mucho tiempo en cargarse y presiona <kbd>F5</kbd> en el explorador, el rendimiento del explorador descenderá significativamente.<br/><br/>A partir de .NET Framework 4.7, un contador realiza un seguimiento de las solicitudes en cola y finaliza las solicitudes cuando superan un límite especificado. El valor predeterminado es 50. Si el se alcanza el límite, se registrará una advertencia en el registro de eventos y se podrá grabar una respuesta HTTP 500 en el registro de IIS.|Este cambio puede mejorar el rendimiento global del servidor.<br/><br/>Para restaurar el comportamiento anterior, puede agregar la siguiente configuración al archivo web.config para rechazar el nuevo comportamiento.<br/><br/>`<appSettings>`<br/>&nbsp;&nbsp;&nbsp;`<add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>`<br/>`</appSettings>` | Borde |

## <a name="a-namewcf--windows-communication-foundation"></a><a name="WCF" /> Windows Communication Foundation

| Característica  |Cambio  |Impacto | Ámbito | 
---------|---------|---------|-----|
| Seguridad de los mensajes en WCF | Las aplicaciones que se ejecuten en .NET Framework 4.7 o superior podrán usar TLS 1.1 y TLS 1.2 en la seguridad de los mensajes e WCF a través de los ajustes de configuración de la aplicación. Se trata de una característica opcional; de forma predeterminada, la compatibilidad con TLS 1.1 y TLS 1.2 en la seguridad de los mensajes en WCF está deshabilitada. | El comportamiento predeterminado de la seguridad de los mensajes en WCF permanece sin cambios. <br/><br/> Para habilitar la compatibilidad con TLS 1.1 y TLS 1.2, agregue el siguiente ajuste de configuración a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo `app.config` o `web.config`:  <br/><br/>`<runtime>` <br/> &nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;`<br/>&nbsp;&nbsp;&nbsp;`Switch.System.Net.DontEnableSchUseStrongCrypto=false" />`<br/>`</runtime>` | Borde |         

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> Windows Presentation Foundation (WPF)  

| Característica | Cambio | Impacto | Ámbito |
|---|---|---|---|
| La ubicación del espacio del control <xref:System.Windows.Controls.Grid> en columnas de estrella | A partir de las aplicaciones que se dirigen a .NET Framework 4.7, WPF reemplaza el algoritmo que el control <xref:System.Windows.Controls.Grid> utiliza para asignar espacio a \*-columns.md) | Para las aplicaciones que se dirigen a la versiones de .NET Framework que empiezan por .NET Framework 4.7, este cambio afecta a la anchura real asignada a las columnas \* en un número de casos. Si este cambio es un cambio no deseado, el algoritmo anterior puede seguir aplicándose mediante la adición de una entrada al archivo de configuración de la aplicación. Para más información, vea [Mitigación: Asignación del espacio del control de cuadrícula a columnas de estrella](../../../docs/framework/migration-guide/mitigation-grid-control.md). | Secundaria |
| <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> | En aplicaciones que tienen como destino .NET Framework 4.6.2 y versiones anteriores, un error en la excepción que controla el código para el método <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> provocó que apareciera el elemento [NullReferenceException](assetId:///T:System.NullReferenceException] en lugar de la excepción prevista (como [DirectoryNotFoundException](assetId:///T:System.IO.DirectoryNotFoundException) o [FileNotFoundException](assetId:///T:System.IO.FileNotFoundException)).<br/><br/>A partir de las aplicaciones que tienen como destino .NET Framework 4.7, se muestra la excepción correcta.  | Las aplicaciones que tienen como destino .NET Framework 4.7 y que depende del control del elemento [NullReferenceException](assetId:///T:System.NullReferenceException) pueden restaurar el comportamiento anterior agregando el siguiente ajuste de configuración a la sección [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo `app.config`: <br/><br/>`<runtime>`<br/>&nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true"/>`<br/>`</runtime>`| Borde | 
| Compatibilidad opcional con una pila de lápiz/entrada táctil basada en `WM_POINTER` | A partir de las aplicaciones que se dirigen a .NET Framework 4.7, WPF proporciona compatibilidad para una entrada táctil opcional basada en `WM_POINTER.  | Se trata de una característica opcional que está disponible en sistemas de Windows a partir de Windows 10 Creators Update. Las aplicaciones de WPF que no incluyen explícitamente compatibilidad con el lápiz o la entrada táctil basados en el puntero no se ven afectadas. Para más información, vea [Mitigación: Compatibilidad del lápiz y la entrada táctil basados en el puntero](../Topic/Mitigation:%20Pointer-based%20Touch%20and%20Stylus%20Support.md). | Borde |
| Clase [PrintQueue](assetId:///T:System.Printing.PrintQueue) | A partir de .NET Framework 4.7, las API de impresión de WPF que usan [PrintQueue](assetId:///T:System.Printing.PrintQueue) de forma predeterminada llaman a la API del paquete de documentos de impresión de Windows en lugar de a la API de impresión de XPS que ahora está en desuso.<br/><br/>La pila de impresión antigua continúa funcionando como antes en versiones anteriores de Windows. | Ni los usuarios ni los desarrolladores deberían percibir cambios en el comportamiento o el uso de la API. <br/><br/>Para usar la pila antigua en Windows 10 Creators Update, establezca el valor `UseXpsOMPrinting` `REG_DWORD` de la clave de registro `HKEY_CURRENT_USER\Software\Microsoft.NETFramework\Windows Presentation Foundation\Printing` en 1. | Borde | 
## <a name="see-also"></a>Vea también
[Compatibilidad de aplicaciones en .NET Framework 4.7](Application%20Compatibility%20in%20the%20.NET%20Framework%204.7.md)

