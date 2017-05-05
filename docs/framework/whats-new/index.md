---
title: Novedades de .NET Framework | Microsoft Docs
ms.custom: 
ms.date: 05/02/2017
ms.prod: .net-framework-4.6
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
caps.latest.revision: 292
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: adb9c30b6dc52ea17410423fd76c938e258549eb
ms.openlocfilehash: 7f83abf73931117d563ec1d609aae5764adfb57d
ms.lasthandoff: 05/02/2017

---
# <a name="what39s-new-in-the-net-framework"></a>Novedades de .NET Framework
<a name="introduction"></a> En este artículo se resumen las nuevas características y mejoras en las siguientes versiones de .NET Framework:  
  
 [.NET Framework 4.7](#v47)   
 [.NET Framework 4.6.2](#v462)   
 [.NET Framework 4.6.1](#v461)   
 [.NET 2015 y .NET Framework 4.6](#v46)   
 [.NET Framework 4.5.2](#v452)   
 [.NET Framework 4.5.1](#v451)   
 [.NET Framework 4.5](#core)  
  
 Este artículo no proporciona información completa sobre cada una de las características nuevas y puede estar sujeto a cambios. Para obtener información general sobre .NET Framework, vea [Introducción](http://msdn.microsoft.com/library/c693fd34-88fe-4d90-b332-19eeadf3b7e7). Para conocer las plataformas compatibles, vea [Requisitos de sistema](~/docs/framework/get-started/system-requirements.md). Para obtener vínculos de descarga e instrucciones de instalación, vea [Instalar](../../../docs/framework/install/guide-for-developers.md).  
  
> [!NOTE]
>  El equipo de .NET Framework también publica características fuera de banda con NuGet para expandir la compatibilidad con la plataforma e introducir nuevas funciones (como colecciones invariables y tipos de vector habilitados para SIMD). Para obtener más información, vea [Las API y las bibliotecas de clases adicionales](http://msdn.microsoft.com/library/cf2d9006-b631-4e5d-81cd-20aab78c60f1) y [.NET Framework y versiones fuera de banda](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). Vea una [lista completa de paquetes NuGet](http://blogs.msdn.com/b/dotnet/p/nugetpackages.aspx) para .NET Framework o suscríbase a [nuestra fuente](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).  
  
<a name="v47"></a>   
## <a name="introducing-the-net-framework-47"></a>Introducción a .NET Framework 4.7  
 .NET Framework 4.7 se basa en la versión 4.6, 4.6.1 y 4.6.2 de .NET Framework e incorpora muchas correcciones y varias características nuevas, sin dejar de ser un producto muy estable.  

### <a name="downloading-and-installing-the-net-framework-47"></a>Descarga e instalación de .NET Framework 4.7
 
Puede descargar .NET Framework 4.7 de las siguientes ubicaciones:  
  
- [Instalador web de .NET Framework 4.7](http://go.microsoft.com/fwlink/?LinkId=825299)  
  
- [Instalador sin conexión de .NET Framework 4.7](http://go.microsoft.com/fwlink/?LinkId=825303)  
  
.NET Framework 4.7 puede instalarse en Windows 10, Windows 8.1, Windows 7 y las plataformas de servidor correspondientes a partir de Windows Server 2008 R2 SP1. Puede instalar .NET Framework 4.7 mediante el instalador web o el instalador sin conexión. La manera recomendada para la mayoría de los usuarios es usar el programa de instalación web.  
  
Puede usar como destino .NET Framework 4.7 en Visual Studio 2012 o posterior instalando el [Paquete de desarrollador de .NET Framework 4.7](http://go.microsoft.com/fwlink/?LinkId=825319).  
  
### <a name="whats-new-in-the-net-framework-47"></a>Novedades de .NET Framework 4.7

.NET Framework 4.7 incluye nuevas características en las áreas siguientes:

- [Principal](#Core47)
- [Redes](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

Para una lista de las nuevas API agregadas a .NET Framework 4.7, consulte [.NET Framework 4.7 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) (Cambios de API de .NET Framework 4.7) en GitHub. Para una lista de las mejoras de características y correcciones de errores en .NET Framework 4.7, consulte [.NET Framework 4.7 List of Changes](http://gutithub.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) (Lista de cambios de .NET Framework 4.7) en GitHub.  Para más información, vea [Announcing .NET Framework 4.7](https://blogs.msdn.microsoft.com/dotnet/2017/04/05/announcing-the-net-framework-4-7/) (Anuncio de .NET Framework 4.7) en el Blog de .NET.
  
<a name="Core47" />
### <a name="core"></a>Principal ###

.NET Framework 4.7 mejora la serialización mediante <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Funcionalidad mejorada con criptografía de curva elíptica (ECC)***

En .NET Framework 4.7, se agregaron métodos `ImportParameters(ECParameters)` a las clases <xref:System.Security.Cryptography.ECDsa> y <xref:System.Security.Cryptography.ECDiffieHellman> para permitir que un objeto represente una clave ya establecida. También se agregó un método `ExportParameters(Boolean)` para exportar la clave mediante parámetros de curva explícitos.

.NET Framework 4.7 también agrega compatibilidad con curvas adicionales (incluido el conjunto de curvas Brainpool) y tiene definiciones predefinidas agregadas para facilidad de creación a través de los nuevos métodos Factory Method <xref:System.Security.Cryptography.ECDsa.Create%2A> y <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

Puede ver un [ejemplo de las mejoras de criptografía de .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e) en GitHub.

**Mayor compatibilidad para caracteres de control mediante DataContractJsonSerializer**

.NET Framework 4.7, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serializa los caracteres de control de conformidad con la norma ECMAScript 6. Este comportamiento está habilitado de manera predeterminada para aplicaciones que tienen .NET Framework 4.7 como destino y es una característica opcional para las aplicaciones que se ejecutan en .NET Framework 4.7 pero tienen como destino una versión anterior de .NET Framework. Para más información, consulte [Cambios de redestinación en .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />
### <a name="networking"></a>Redes ###

.NET Framework 4.7 agregue la siguiente característica relacionada con la red:

**Compatibilidad predeterminada del sistema operativo con protocolos TLS***

La pila TLS, usada por <xref:System.Net.Security.SslStream?displayProperty=fullName>, y componentes que se encuentran por encima de la pila, como HTTP, FTP y SMTP, permiten que los desarrolladores use los protocolos TLS predeterminados compatibles con el sistema operativo. Ya no es necesario que los desarrolladores codifiquen una versión de TLS de forma rígida.

<a name="ASP-NET47" />
### <a name="aspnet"></a>ASP.NET ###

En .NET Framework 4.7, ASP.NET incluye las siguientes características nuevas:

**Extensibilidad de caché de objetos**

A partir de .NET Framework 4.7, ASP.NET agrega un nuevo conjunto de API que permiten que los desarrolladores reemplacen las implementaciones predeterminadas de ASP.NET por la supervisión de memoria y el almacenamiento en caché de objetos en memoria. Ahora los desarrolladores pueden reemplazar cualquiera de los siguientes tres componentes si la implementación de ASP.NET no es adecuada:

- **Almacén de caché de objetos**. En la nueva sección de configuración de proveedores de caché, los desarrolladores pueden insertar implementaciones nuevas de una caché de objetos para una aplicación de ASP.NET mediante la nueva interfaz **ICacheStoreProvider**.
 
- **Supervisión de memoria**. El monitor de memoria predeterminado de ASP.NET notifica a las aplicaciones cuando se ejecutan cerca del límite de bytes privado configurado para el proceso o cuando queda poca RAM física total disponible en la máquina. Las notificaciones se activan cuando se está cerca de estos límites. En el caso de algunas aplicaciones, las notificaciones se activan demasiado cerca de los límites configurados como para permitir reacciones que sean útiles. Ahora los desarrolladores pueden escribir sus propios monitores de memoria que reemplacen el monitor predeterminado con la propiedad <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=fullName>.

- **Reacciones por límite de memoria**. De manera predeterminada, ASP.NET intenta recortar la caché de objetos y llama periódicamente a <xref:System.GC.Collect%2A?displayProperty=fullName> cuando se está cerca del límite de proceso de bytes privados. En algunas aplicaciones, la frecuencia de llamadas a <xref:System.GC.Collect%2A?displayProperty=fullName> o la cantidad de caché que se recorta no son suficientes. Ahora los desarrolladores puede reemplazar o complementar el comportamiento predeterminado si suscriben las implementaciones de **IObserver** al monitor de memoria de la aplicación.

<a name="wcf47" />
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF) ###

Windows Communication Foundation (WFC) agrega las siguientes características y cambios:

**Capacidad de configurar las opciones de seguridad de mensaje predeterminadas en TLS 1.1 o TLS 1.2**

A partir de .NET Framework 4.7, WCF le permite configurar TSL 1.1 o TLS 1.2 además de SSL 3.0 y TSL 1.0 como el protocolo de seguridad de mensajes predeterminado. Esta es una configuración opcional; para habilitarla, debe agregar la entrada siguiente al archivo de configuración de la aplicación:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" /> 
</runtime>
```

**Confiabilidad mejorada de las aplicaciones WFC y la serialización WCF**

WCF incluye varios cambios de código que eliminan condiciones de carrera, por lo que se mejora el rendimiento y la confiabilidad de las opciones de serialización. Se incluyen los siguientes:

- Mayor compatibilidad para combinar código asincrónico y sincrónico en las llamadas a **SocketConnection.BeginRead** y **SocketConnection.Read**.
- Confiabilidad mejorada cuando se anula una conexión con **SharedConnectionListener** y **DuplexChannelBinder**.
- Confiabilidad mejorada de las operaciones de serialización cuando se llama al método [FormatterServices.GetSerializableMembers](assetId:///System.Runtime.Serialization.FormatterServices.GetSerializableMembers(System.Type??qualifyHint=True&autoUpgrade=False).
- Confiabilidad mejorada cuando se elimina un objeto waiter mediante una llamada al método **ChannelSynchronizer.RemoveWaiter**.  

<a name="wf47" />
### <a name="windows-forms"></a>Windows Forms ###

En .NET Framework 4.7, Windows Forms mejora la compatibilidad con monitores con valores altos de PPP.

**Compatibilidad con valores altos de PPP**

A partir de las aplicaciones que tienen .NET Framework 4.7 como destino, .NET Framework cuenta con compatibilidad con valores altos de PPP y PPP dinámicos. La compatibilidad con valores altos de PPP mejora el diseño y la apariencia de los formularios y controles en monitores con valores altos de PPP. PPP dinámicos cambia el diseño y la apariencia de los formularios y controles cuando el usuario cambia los PPP o el factor de escala de visualización de una aplicación en ejecución.

Compatibilidad con valores altos de PPP es una característica opcional que se configura definiendo una sección [\<System.Windows.Forms.ConfigurationSection>](Windows%20Forms%20Configuration%20Section.md) en el archivo de configuración de la aplicación. Para más información sobre cómo agregar compatibilidad con valores altos de PPP y PPP dinámicos a la aplicación de Windows Forms, consulte [Compatibilidad con valores altos de PPP en Windows Forms](High%20DPI%20Support%20In%20Windows%20Forms.md).  

<a name="WPF47"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

En .NET Framework 4.7, WPF incluye las siguientes mejoras:

**Compatibilidad con una pila de entrada táctil o de lápiz basada en mensajes WM_POINTER de Windows**

Ahora tiene la opción de usar una pila de entrada táctil o de lápiz basada en [mensajes WM_POINTER](https://msdn.microsoft.com/library/windows/desktop/hh454903(v=vs.85).aspx) en lugar de Windows Ink Services Platform (WISP). Se trata de una característica opcional de .NET Framework. Para más información, consulte [Cambios de redestinación en .NET Framework 4.7](Retargeting%20Changes%20in%20the%20.NET%20Framework%204.7.md).

**Nueva implementación para API de impresión de WPF**

Las API de impresión de WPF en la clase [System.Printing.PrintQueue](assetId:///T:System.Printing.PrintQueue?qualifyHint=True&autoUpgrade=True) llaman a la [API Print Document Package](https://msdn.microsoft.com/library/windows/desktop/hh448418(v=vs.85).aspx) de Windows en lugar de a la [API XPS Print](https://msdn.microsoft.com/library/windows/desktop/ff686814(v=vs.85).aspx) en desuso. Para ver el impacto que este cambio tiene en la compatibilidad de aplicaciones, consulte [Cambios de redestinación en .NET Framework 4.7](Retargeting%20Changes%20in%20the%20.NET%20Framework%204.7.md). 

<a name="v462"></a>   
## <a name="whats-new-in-the-net-framework-462"></a>Novedades de .NET Framework 4.6.2  
.NET Framework 4.6.2 incluye nuevas características en las áreas siguientes:  
  
-   [ASP.NET](#ASPNET462)  
  
-   [Categorías de caracteres](#Strings)  
  
-   [Criptografía](#Crypto462)  
  
-   [SqlClient](#SQLClient)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF462)  
  
-   [Windows Workflow Foundation (WF)](#WF462)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Conversión de aplicaciones de Windows Forms y WPF a aplicaciones de UWP](#UWPConvert)  
  
-   [Mejoras en la depuración](#Debug462)  
  
 Para una lista de las nuevas API agregadas a .NET Framework 4.6.2, consulte los [cambios de API de .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) en GitHub. Para una lista de las mejoras de características y correcciones de errores en .NET Framework 4.6.2, consulte [.NET Framework 4.6.2 List of Changes](http://go.microsoft.com/fwlink/?LinkId=708778) (Lista de cambios de .NET Framework 4.6.2) en GitHub.  Para obtener más información, vea [Announcing .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) (Anuncio de .NET Framework 4.6.2) en el Blog de .NET.  
  
<a name="ASPNET462"></a>   
### <a name="aspnet"></a>ASP.NET  
 En .NET Framework 4.6.2, ASP.NET incluye las siguientes mejoras:  
  
 **Compatibilidad mejorada para los mensajes de error localizado de validadores de anotación de datos**  
 Los validadores de anotación de datos permiten realizar la validación agregando uno o varios atributos a una propiedad de clase. El elemento [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True) del atributo define el texto del mensaje de error si se produce un error de validación. A partir de .NET Framework 4.6.2, ASP.NET facilita la tarea de localizar mensajes de error. Los mensajes de error se localizarán si:  
  
1.  Se proporciona [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True) en el atributo de validación.  
  
2.  El archivo de recursos está almacenado en la carpeta App_LocalResources.  
  
3.  El nombre del archivo de recursos localizados tiene la forma `DataAnnotation.Localization.{`*nombre*`}.resx`, donde *nombre* es un nombre de referencia cultural en el formato *códigoDeIdioma*`-`*códigoDePaís/Región* o *códigoDeIdioma*.  
  
4.  El nombre de clave del recurso es la cadena asignada al atributo [ValidationAttribute.ErrorMessage](assetId:///P:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage?qualifyHint=True&autoUpgrade=True) y su valor es el mensaje de error localizado.  
  
 Por ejemplo, el siguiente atributo de anotación de datos define el mensaje de error de la referencia cultural predeterminada para una clasificación no válida.  
  
```csharp  
  
public class RatingInfo  
{  
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]  
   [Display(Name = "Your Rating")]  
   public int Rating { get; set; }  
}  
  
```  
  
```vb  
  
Public Class RatingInfo  
   \<Required(ErrorMessage = "The rating must be between 1 and 10.")>  
   \<Display(Name = "Your Rating")>  
   Public Property Rating As Integer = 1  
End Class  
  
```  
  
 A continuación, puede crear un archivo de recursos DataAnnotation.Localization.fr.resx cuya clave sea la cadena del mensaje de error y cuyo valor sea el mensaje de error localizado. El archivo debe encontrarse en la carpeta `App.LocalResources`. Por ejemplo, a continuación se muestra la clave y su valor en un mensaje de error localizado en idioma francés (fr):  
  
|Name|Valor|  
|----------|-----------|  
|La clasificación debe estar entre 1 y 10.|La note doit être comprise entre 1 et 10.|  
  
 A continuación, este archivo puede  
  
 Además, la localización de anotaciones de datos es extensible. Los desarrolladores pueden conectar su propio proveedor de localizador de cadenas mediante la implementación de la interfaz [IStringLocalizerProvider](assetId:///T:System.Web.Globalization.IStringLocalizerProvider?qualifyHint=False&autoUpgrade=True) para almacenar la cadena de localización en un lugar distinto de un archivo de recursos.  
  
 **Compatibilidad asincrónica con proveedores de almacenes de estados de sesión**  
 Actualmente, ASP.NET permite el uso de métodos de devolución de tareas con proveedores de almacenes de estados de sesión, lo que permite que las aplicaciones ASP.NET aprovechen las ventajas de escalabilidad de la asincronía. Para admitir operaciones asincrónicas con proveedores de almacenes de estados de sesión, ASP.NET incluye una nueva interfaz [System.Web.SessionState.ISessionStateModule](assetId:///T:System.Web.SessionState.ISessionStateModule?qualifyHint=True&autoUpgrade=True) que se hereda de [IHttpModule](assetId:///T:System.Web.IHttpModule?qualifyHint=False&autoUpgrade=True) y permite a los desarrolladores implementar sus propios módulos de estados de sesión y proveedores de almacenes de sesión asincrónica. La interfaz se define de la siguiente manera:  
  
```csharp  
  
public interface ISessionStateModule : IHttpModule {  
    void ReleaseSessionState(HttpContext context);  
    Task ReleaseSessionStateAsync(HttpContext context);  
}  
  
```  
  
 Además, la clase [SessionStateUtility](assetId:///T:System.Web.SessionState.SessionStateUtility?qualifyHint=False&autoUpgrade=True) incluye dos nuevos métodos, [IsSessionStateReadOnly](assetId:///M:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly(System.Web.HttpContext)?qualifyHint=False&autoUpgrade=True) y [IsSessionStateRequired](assetId:///M:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired(System.Web.HttpContext)?qualifyHint=False&autoUpgrade=True), que se pueden usar para admitir operaciones asincrónicas.  
  
 **Compatibilidad asincrónica con proveedores de caché de resultados**  
 A partir de .NET Framework 4.6.2, pueden usarse métodos de devolución de tarea con proveedores de caché de resultados para proporcionar las ventajas de escalabilidad de la asincronía.  Los proveedores que implementan estos métodos reducen el bloqueo de subprocesos en un servidor web y mejoran la escalabilidad de un servicio de ASP.NET.  
  
 Se han agregado las API siguientes para ofrecer compatibilidad con proveedores de caché de resultados asincrónicos:  
  
-   La clase [System.Web.Caching.OutputCacheProviderAsync](assetId:///T:System.Web.Caching.OutputCacheProviderAsync?qualifyHint=True&autoUpgrade=True), que hereda de [System.Web.Caching.OutputCacheProvider](assetId:///T:System.Web.Caching.OutputCacheProvider?qualifyHint=True&autoUpgrade=True) y permite a los desarrolladores implementar un proveedor de caché de resultados asincrónico.  
  
-   La clase [OutputCacheUtility](assetId:///T:System.Web.Caching.OutputCacheUtility?qualifyHint=False&autoUpgrade=True), que proporciona métodos auxiliares para configurar la caché de resultados.  
  
-   18 métodos nuevos en la clase [System.Web.HttpCachePolicy](assetId:///T:System.Web.HttpCachePolicy?qualifyHint=True&autoUpgrade=True). Estos incluyen [GetCacheability](assetId:///M:System.Web.HttpCachePolicy.GetCacheability?qualifyHint=False&autoUpgrade=True), [GetCacheExtensions](assetId:///M:System.Web.HttpCachePolicy.GetCacheExtensions?qualifyHint=False&autoUpgrade=True), [GetETag](assetId:///M:System.Web.HttpCachePolicy.GetETag?qualifyHint=False&autoUpgrade=True), [GetETagFromFileDependencies](assetId:///M:System.Web.HttpCachePolicy.GetETagFromFileDependencies?qualifyHint=False&autoUpgrade=True), [GetMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetMaxAge?qualifyHint=False&autoUpgrade=True), [GetMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetMaxAge?qualifyHint=False&autoUpgrade=True), [GetNoStore](assetId:///M:System.Web.HttpCachePolicy.GetNoStore?qualifyHint=False&autoUpgrade=True), [GetNoTransforms](assetId:///M:System.Web.HttpCachePolicy.GetNoTransforms?qualifyHint=False&autoUpgrade=True), [GetOmitVaryStar](assetId:///M:System.Web.HttpCachePolicy.GetOmitVaryStar?qualifyHint=False&autoUpgrade=True), [GetProxyMaxAge](assetId:///M:System.Web.HttpCachePolicy.GetProxyMaxAge?qualifyHint=False&autoUpgrade=True), [GetRevalidation](assetId:///M:System.Web.HttpCachePolicy.GetRevalidation?qualifyHint=False&autoUpgrade=True), [GetUtcLastModified](assetId:///M:System.Web.HttpCachePolicy.GetUtcLastModified?qualifyHint=False&autoUpgrade=True), [GetVaryByCustom](assetId:///M:System.Web.HttpCachePolicy.GetVaryByCustom?qualifyHint=False&autoUpgrade=True), [HasSlidingExpiration](assetId:///M:System.Web.HttpCachePolicy.HasSlidingExpiration?qualifyHint=False&autoUpgrade=True) y [IsValidUntilExpires](assetId:///M:System.Web.HttpCachePolicy.IsValidUntilExpires?qualifyHint=False&autoUpgrade=True).  
  
-   2 métodos nuevos en la clase [System.Web.HttpCacheVaryByContentEncodings](assetId:///T:System.Web.HttpCacheVaryByContentEncodings?qualifyHint=True&autoUpgrade=True): [GetContentEncodings](assetId:///M:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings?qualifyHint=False&autoUpgrade=True) y [SetContentEncodings](assetId:///M:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   2 métodos nuevos en la clase [System.Web.HttpCacheVaryByHeaders](assetId:///T:System.Web.HttpCacheVaryByHeaders?qualifyHint=True&autoUpgrade=True): [GetHeaders](assetId:///M:System.Web.HttpCacheVaryByHeaders.GetHeaders?qualifyHint=False&autoUpgrade=True) y [SetHeaders](assetId:///M:System.Web.HttpCacheVaryByHeaders.SetHeaders(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   2 métodos nuevos en la clase [System.Web.HttpCacheVaryByParams](assetId:///T:System.Web.HttpCacheVaryByParams?qualifyHint=True&autoUpgrade=True): [GetParams](assetId:///M:System.Web.HttpCacheVaryByParams.GetParams?qualifyHint=False&autoUpgrade=True) y [SetParams](assetId:///M:System.Web.HttpCacheVaryByParams.SetParams(System.String[])?qualifyHint=False&autoUpgrade=True).  
  
-   En la clase [System.Web.Caching.AggregateCacheDependency](assetId:///T:System.Web.Caching.AggregateCacheDependency?qualifyHint=True&autoUpgrade=True), el método [GetFileDependencies](assetId:///M:System.Web.Caching.AggregateCacheDependency.GetFileDependencies?qualifyHint=False&autoUpgrade=True).  
  
-   En la clase [CacheDependency](assetId:///T:System.Web.Caching.CacheDependency?qualifyHint=False&autoUpgrade=True), el método [GetFileDependencies](assetId:///M:System.Web.Caching.CacheDependency.GetFileDependencies?qualifyHint=False&autoUpgrade=True).  
  
<a name="Strings"></a>   
### <a name="character-categories"></a>Categorías de caracteres  
 Los caracteres de .NET Framework 4.6.2 se clasifican según el [estándar Unicode, versión 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/). En .NET Framework 4.6 y .NET Framework 4.6.1, los caracteres están clasificados según las categorías de caracteres Unicode 6.3.  
  
 La compatibilidad con Unicode 8.0 está limitada a la clasificación de caracteres mediante la clase [CharUnicodeInfo](assetId:///T:System.Globalization.CharUnicodeInfo?qualifyHint=False&autoUpgrade=True) y a los tipos y los métodos que se basan en ella. Entre ellos se incluyen la clase [StringInfo](assetId:///T:System.Globalization.StringInfo?qualifyHint=False&autoUpgrade=True), el método sobrecargado [Char.GetUnicodeCategory](assetId:///M:System.Char.GetUnicodeCategory(System.Char)?qualifyHint=True&autoUpgrade=True) y las [clases de caracteres](../Topic/Character%20Classes%20in%20Regular%20Expressions.md) reconocidas por el motor de expresiones regulares de .NET Framework.  La comparación y la ordenación de caracteres y cadenas no se ven afectadas por este cambio y siguen dependiendo del sistema operativo subyacente o, en el caso de los sistemas Windows 7, de los datos de caracteres proporcionados por .NET Framework.  
  
 Para realizar cambios en las categorías de caracteres de Unicode 6.0 a Unicode 7.0, consulte la página sobre [el estándar Unicode, versión 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) en el sitio web de The Unicode Consortium. Para realizar cambios de caracteres de Unicode 7.0 a Unicode 8.0, consulte la página sobre [el estándar Unicode, versión 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) en el sitio web de The Unicode Consortium.  
  
<a name="Crypto462"></a>   
### <a name="cryptography"></a>Criptografía  
 **Compatibilidad con certificados X509 que contienen DSA de FIPS 186-3**  
 .NET Framework 4.6.2 agrega compatibilidad con certificados X509 de DSA (algoritmo de firma digital) cuyas claves superan el límite de 1024 bits de FIPS 186-2.  
  
 Además de admitir los tamaños de clave más grandes de FIPS 186-3, .NET Framework 4.6.2 permite calcular firmas con la familia SHA-2 de algoritmos hash (SHA256, SHA384 y SHA512). La compatibilidad con FIPS 186-3 la proporciona la nueva clase [System.Security.Cryptography.DSACng](assetId:///T:System.Security.Cryptography.DSACng?qualifyHint=True&autoUpgrade=True).  
  
 Para conservar los cambios recientes en la clase [RSA](assetId:///T:System.Security.Cryptography.RSA?qualifyHint=False&autoUpgrade=True) de .NET Framework 4.6 y la clase [ECDsa](assetId:///T:System.Security.Cryptography.ECDsa?qualifyHint=False&autoUpgrade=True) de .NET Framework 4.6.1, la clase base abstracta [DSA](assetId:///T:System.Security.Cryptography.DSA?qualifyHint=False&autoUpgrade=True) de .NET Framework 4.6.2 tiene métodos adicionales que permiten que los llamadores usen esta funcionalidad sin conversión. Puede llamar al método de extensión [DSACertificateExtensions.GetDSAPrivateKey](assetId:///M:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?qualifyHint=True&autoUpgrade=True) para firmar los datos, como se muestra en el ejemplo siguiente.  
  
```csharp  
  
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPrivateKey())  
    {  
        return dsa.SignData(data, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```vb  
  
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()  
    Using DSA As DSA = cert.GetDSAPrivateKey()  
        Return DSA.SignData(data, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 También puede llamar al método de extensión [DSACertificateExtensions.GetDSAPublicKey](assetId:///M:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)?qualifyHint=True&autoUpgrade=True) para comprobar los datos firmados, como se muestra en el ejemplo siguiente.  
  
```csharp  
  
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)  
{  
    using (DSA dsa = cert.GetDSAPublicKey())  
    {  
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);  
    }  
}  
  
```  
  
```  
  
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean  
    Using dsa As DSA = cert.GetDSAPublicKey()  
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)  
    End Using  
End Function  
  
```  
  
 **Mayor claridad para las entradas en rutinas de derivación de claves ECDiffieHellman**  
 .NET Framework 3.5 incluía compatibilidad para el acuerdo de claves Diffie-Hellman de curva elíptica con tres rutinas diferentes de función de derivación de claves (KDF). Las entradas en las rutinas y las propias rutinas se configuraban mediante propiedades en el objeto [ECDiffieHellmanCng](assetId:///T:System.Security.Cryptography.ECDiffieHellmanCng?qualifyHint=False&autoUpgrade=True). Pero como no todas las rutinas leían todas las propiedades de entrada, esto podía provocar confusión al desarrollador.  
  
 Para solucionarlo en .NET Framework 4.6.2, se han agregado los tres métodos siguientes a la clase base [ECDiffieHellman](assetId:///T:System.Security.Cryptography.ECDiffieHellman?qualifyHint=False&autoUpgrade=True) para manifestar con mayor claridad estas rutinas KDF y sus entradas:  
  
|Método ECDiffieHellman|Descripción|  
|----------------------------|-----------------|  
|[DeriveKeyFromHash(ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Security.Cryptography.HashAlgorithmName,System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Deriva el material de clave mediante la fórmula<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> donde *x* es el resultado calculado del algoritmo de Diffie-Hellman de curva elíptica.|  
|[DeriveKeyFromHmac(ECDiffieHellmanPublicKey, HashAlgorithmName, Byte\[\], Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Security.Cryptography.HashAlgorithmName,System.Byte[],System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Deriva el material de clave mediante la fórmula<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> donde *x* es el resultado calculado del algoritmo de Diffie-Hellman de curva elíptica.|  
|[DeriveKeyTls(ECDiffieHellmanPublicKey, Byte\[\], Byte\[\])](assetId:///M:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls(System.Security.Cryptography.ECDiffieHellmanPublicKey,System.Byte[],System.Byte[])?qualifyHint=False&autoUpgrade=False)|Deriva el material de clave mediante el algoritmo de derivación de función pseudoaleatoria (PRF) de TLS.|  
  
 **Compatibilidad con el cifrado simétrico de clave persistente**  
 La biblioteca de criptografía (CNG) de Windows agrega compatibilidad para almacenar claves simétricas persistentes y para usar claves simétricas almacenadas en el hardware, y .NET Framework 4.6.2 hace posible que los desarrolladores usen esta característica.  Como el concepto de nombres de clave y proveedores de clave depende de la implementación, el uso de esta característica obliga a emplear el constructor de los tipos de la implementación concreta, en lugar del enfoque de fábrica preferido (por ejemplo, llamar a `Aes.Create`).  
  
 Existe compatibilidad con el cifrado simétrico de clave persistente para los algoritmos AES ([AesCng](assetId:///T:System.Security.Cryptography.AesCng?qualifyHint=False&autoUpgrade=True)) y 3DES ([TripleDESCng](assetId:///T:System.Security.Cryptography.TripleDESCng?qualifyHint=False&autoUpgrade=True)). Por ejemplo:  
  
```csharp  
  
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)  
{  
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))  
    {  
        aes.IV = iv;  
  
        // Using the zero-argument overload is required to make use of the persisted key  
        using (ICryptoTransform encryptor = aes.CreateEncryptor())  
        {  
            if (!encryptor.CanTransformMultipleBlocks)  
            {  
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");  
            }  
  
            return encryptor.TransformFinalBlock(data, 0, data.Length);  
        }  
    }  
}  
  
```  
  
```vb  
  
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()  
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)  
        Aes.IV = iv  
  
        ' Using the zero-argument overload Is required to make use of the persisted key  
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()  
            If Not encryptor.CanTransformMultipleBlocks Then  
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")  
            End If  
            Return encryptor.TransformFinalBlock(data, 0, data.Length)  
        End Using  
    End Using  
End Function  
  
```  
  
 **Compatibilidad con SignedXml para hash SHA-2**  
 .NET Framework 4.6.2 agrega compatibilidad con la clase [SignedXml](assetId:///T:System.Security.Cryptography.Xml.SignedXml?qualifyHint=False&autoUpgrade=True) para los métodos de firma PKCS#1 RSA-SHA256, RSA-SHA384 y RSA-SHA512, y para los algoritmos de resumen de referencia SHA256, SHA384 y SHA512.  
  
 Todas las constantes URI se exponen en [SignedXml](xref:System.Security.Cryptography.Xml.SignedXml?qualifyHint=False&autoUpgrade=True):  
  
|Campo SignedXml|Constante|  
|---------------------|--------------|  
|[XmlDsigSHA256Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmlenc#sha256"|  
|[XmlDsigRSASHA256Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|  
|[XmlDsigSHA384Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#sha384"|  
|[XmlDsigRSASHA384Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|  
|[XmlDsigSHA512Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmlenc#sha512"|  
|[XmlDsigRSASHA512Url](assetId:///F:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url?qualifyHint=False&autoUpgrade=True)|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|  
  
 Todos los programas que hayan registrado un controlador [SignatureDescription](assetId:///T:System.Security.Cryptography.SignatureDescription?qualifyHint=False&autoUpgrade=True) personalizado en [CryptoConfig](assetId:///T:System.Security.Cryptography.CryptoConfig?qualifyHint=False&autoUpgrade=True) para agregar compatibilidad para estos algoritmos seguirán funcionando como antes, pero como ahora hay valores predeterminados de la plataforma, ya no es necesario el registro de [CryptoConfig](assetId:///T:System.Security.Cryptography.CryptoConfig?qualifyHint=False&autoUpgrade=True).  
  
<a name="SQLClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 El proveedor de datos .NET Framework para SQL Server ([System.Data.SqlClient](assetId:///N:System.Data.SqlClient?qualifyHint=True&autoUpgrade=True)) incluye las siguientes funciones nuevas en .NET Framework 4.6.2:  
  
 **Agrupación de conexiones y tiempos de espera con bases de datos SQL de Azure**  
 Cuando se habilita la agrupación de conexiones y se produce un error de tiempo de espera u otro tipo de error de inicio de sesión, se almacena en caché una excepción que se produce en todos los intentos de conexión posteriores que se realicen en un plazo de entre 5 segundos y 1 minuto.  Para obtener más información, vea [Agrupación de conexiones en SQL Server (ADO.NET)](../Topic/SQL%20Server%20Connection%20Pooling%20\(ADO.NET\).md).  
  
 Este comportamiento no es el deseable al conectarse a bases de datos SQL de Azure, ya que en los intentos de conexión se pueden producir errores transitorios que normalmente se recuperan rápidamente. Para optimizar la experiencia de reintento de conexión, se elimina el comportamiento del período de bloqueo del grupo de conexiones cuando se produce un error en las conexiones a bases de datos SQL de Azure.  
  
 La adición de la nueva palabra clave `PoolBlockingPeriod` permite seleccionar el período de bloqueo más adecuado para la aplicación. Estos valores incluyen:  
  
 `Auto`  
 El período de bloqueo del grupo de conexiones para una aplicación que se conecta a una base de datos SQL de Azure está deshabilitado, mientras que el período de bloqueo del grupo de conexiones para una aplicación que se conecta a cualquier otra instancia de SQL Server está habilitado. Este es el valor predeterminado. Si el nombre del punto de conexión del servidor termina de alguna de las siguientes maneras, se considera que se trata de bases de datos SQL de Azure:  
  
-   .database.windows.net  
  
-   .database.chinacloudapi.cn  
  
-   .database.usgovcloudapi.net  
  
-   .database.cloudapi.de  
  
 `AlwaysBlock`  
 El período de bloqueo del grupo de conexión siempre está habilitado.  
  
 `NeverBlock`  
 El período de bloqueo del grupo de conexión siempre está deshabilitado.  
  
 **Mejoras para Always Encrypted**  
 SQLClient presenta dos mejoras para Always Encrypted:  
  
-   Para mejorar el rendimiento de las consultas con parámetros en las columnas de una base de datos cifrada, ahora se almacenan en caché los metadatos de cifrado de los parámetros de consulta. Con la propiedad [SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled](assetId:///P:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled?qualifyHint=True&autoUpgrade=True) establecida en `true` (el valor predeterminado), si se llama varias veces a la misma consulta, el cliente recupera metadatos de parámetros del servidor una única vez.  
  
-   Ahora, las entradas de clave de cifrado de columna incluidas en la caché de claves se expulsan después de un intervalo de tiempo configurable, que se establece mediante la propiedad [SqlConnection.ColumnEncryptionKeyCacheTtl](assetId:///P:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl?qualifyHint=True&autoUpgrade=True).  
  
<a name="WCF"></a>   
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 En .NET Framework 4.6.2, Windows Communication Foundation se ha mejorado en las áreas siguientes:  
  
 **Compatibilidad con la seguridad de transporte de WCF para los certificados almacenados con CNG**  
 La seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows. En .NET Framework 4.6.2, esta compatibilidad está limitada al uso de certificados con una clave pública que tenga un exponente con una longitud no superior a 32 bits. Cuando una aplicación tiene .NET Framework 4.6.2 como destino, esta característica está activada de forma predeterminada.  
  
 En el caso de las aplicaciones que tengan como destino .NET Framework 4.6.1 y versiones anteriores, pero se ejecuten en .NET Framework 4.6.2 o versiones posteriores, esta característica se puede activar agregando la siguiente línea a la sección [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) del archivo app.config o web.config.  
  
```xml  
  
<AppContextSwitchOverrides  
    value="Switch.System.ServiceModel.DisableCngCertificates=false"  
/>  
  
```  
  
 Esto también se puede hacer mediante programación con código similar al siguiente:  
  
```csharp  
  
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";  
AppContext.SetSwitch(disableCngCertificates, false);  
  
```  
  
```vb  
  
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"  
AppContext.SetSwitch(disableCngCertificates, False)  
  
```  
  
 **Mejor compatibilidad para varias reglas de ajuste al horario de verano mediante la clase DataContractJsonSerializer**  
 Los clientes pueden usar una opción de configuración de la aplicación para determinar si la clase [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True) admite varias reglas de ajuste para una sola zona horaria. Esta característica es opcional. Para habilitarla, agregue la siguiente opción de configuración al archivo app.config:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />  
</runtime>  
  
```  
  
 Cuando esta característica está habilitada, un objeto [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True) usa el tipo [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) en lugar del tipo [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True) para deserializar los datos de fecha y hora. [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) admite varias reglas de ajuste, lo que permite trabajar con datos históricos de zona horaria, mientras que [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True) no las admite.  
  
 Para más información sobre la estructura [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) y los ajustes de zona horaria, consulte [Información general sobre zonas horarias](../Topic/Time%20Zone%20Overview.md).  
  
 **Compatibilidad para conservar una hora UTC al serializar y deserializar con la clase XMLSerializer**  
 Normalmente, cuando la clase [XmlSerializer](assetId:///T:System.Xml.Serialization.XmlSerializer?qualifyHint=False&autoUpgrade=True) se usa para serializar un valor [DateTime](assetId:///T:System.DateTime?qualifyHint=False&autoUpgrade=True) UTC, crea una cadena de tiempo serializada que conserva la fecha y la hora, pero da por supuesto que la hora es local.  Por ejemplo, si crea una instancia de fecha y hora UTC llamando al código siguiente:  
  
```csharp  
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);  
```  
  
```vb  
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)  
```  
  
 el resultado es la cadena de tiempo serializada "03:00:00.0000000-08:00" para un sistema con ocho horas con retraso con respecto a la hora UTC.  Además, los valores serializados siempre se deserializan como valores de fecha y hora locales.  
  
 Puede usar una opción de configuración de la aplicación para determinar si [XmlSerializer](assetId:///T:System.Xml.Serialization.XmlSerializer?qualifyHint=False&autoUpgrade=True) conserva la información de zona horaria UTC al serializar y deserializar valores [DateTime](assetId:///T:System.DateTime?qualifyHint=False&autoUpgrade=True):  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides   
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />  
</runtime>  
  
```  
  
 Cuando esta característica está habilitada, un objeto [DataContractJsonSerializer](assetId:///T:System.Runtime.Serialization.Json.DataContractJsonSerializer?qualifyHint=False&autoUpgrade=True) usa el tipo [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) en lugar del tipo [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True) para deserializar los datos de fecha y hora. [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) admite varias reglas de ajuste, lo que permite trabajar con datos históricos de zona horaria, mientras que [TimeZone](assetId:///T:System.TimeZone?qualifyHint=False&autoUpgrade=True) no las admite.  
  
 Para más información sobre la estructura [TimeZoneInfo](assetId:///T:System.TimeZoneInfo?qualifyHint=False&autoUpgrade=True) y los ajustes de zona horaria, consulte [Información general sobre zonas horarias](../Topic/Time%20Zone%20Overview.md).  
  
 **Mejor coincidencia de NetNamedPipeBinding**  
 WCF tiene una nueva opción de la aplicación que se puede establecer en las aplicaciones cliente para garantizar que siempre se conecten al servicio que escucha en el URI que mejor coincida con el que solicitan. Con esta opción de la aplicación establecida en `false` (valor predeterminado), es posible que los clientes que usan [NetNamedPipeBinding](assetId:///T:System.ServiceModel.NetNamedPipeBinding?qualifyHint=False&autoUpgrade=True) intenten conectarse a un servicio que escucha en un URI que es una subcadena del URI solicitado.  
  
 Por ejemplo, un cliente intenta conectarse a un servicio que escucha en `net.pipe://localhost/Service1`, pero un servicio diferente en ese equipo que se ejecuta con privilegios de administrador escucha en `net.pipe://localhost`. Con esta opción de la aplicación establecida en `false`, el cliente intentará conectarse al servicio incorrecto. Después de establecer la opción de la aplicación en `true`, el cliente siempre se conectará al mejor servicio.  
  
> [!NOTE]
>  Los clientes que usan [NetNamedPipeBinding](assetId:///T:System.ServiceModel.NetNamedPipeBinding?qualifyHint=False&autoUpgrade=True) encuentran servicios basados en la dirección base del servicio (si existe) en lugar de la dirección del punto de conexión completo. Para garantizar que esta opción siempre funcione, el servicio debe usar una dirección base única.  
  
 Para habilitar este cambio, agregue la siguiente opción de la aplicación al archivo App.config o Web.config de la aplicación cliente:  
  
```xml  
  
<configuration>  
    <appSettings>  
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />  
    </appSettings>  
</configuration>  
  
```  
  
 **SSL 3.0 no es el protocolo predeterminado**  
 Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, SSL 3.0 ya no es el protocolo predeterminado para negociar una conexión segura. En la mayoría de los casos, esto no debería afectar a las aplicaciones existentes, porque TLS 1.0 está incluido en la lista de protocolos para NetTcp. Todos los clientes deberían poder negociar una conexión usando como mínimo TLS 1.0.      Si se requiere Ssl3, use uno de los siguientes mecanismos de configuración para agregarlo a la lista de protocolos negociados.  
  
-   La propiedad [SslStreamSecurityBindingElement.SslProtocols](assetId:///P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?qualifyHint=True&autoUpgrade=True)  
  
-   La propiedad [TcpTransportSecurity.SslProtocols](assetId:///P:System.ServiceModel.TcpTransportSecurity.SslProtocols?qualifyHint=True&autoUpgrade=True)  
  
-   La sección [\<transport>](../Topic/%3Ctransport%3E%20of%20%3CnetTcpBinding%3E.md) de la sección [\<netTcpBinding>](../Topic/%3CnetTcpBinding%3E.md)  
  
-   La sección [\<sslStreamSecurity>](../Topic/%3CsslStreamSecurity%3E.md) de la sección [\<customBinding>](../Topic/%3CcustomBinding%3E.md)  
  
<a name="WPF462"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 En .NET Framework 4.6.2, Windows Presentation Foundation se ha mejorado en las áreas siguientes:  
  
 **Ordenación de grupos**  
 Ahora, una aplicación que use un objeto [CollectionView](assetId:///T:System.Windows.Data.CollectionView?qualifyHint=False&autoUpgrade=True) para agrupar los datos puede declarar explícitamente cómo ordenar los grupos. La ordenación explícita resuelve el problema de la ordenación no intuitiva que se produce cuando una aplicación agrega o elimina grupos dinámicamente, o cuando cambia el valor de las propiedades de elementos implicadas en la agrupación. También puede mejorar el rendimiento del proceso de creación de grupos, ya que mueve las comparaciones de las propiedades de agrupación de la ordenación de la colección completa a la ordenación de los grupos.  
  
 Para admitir la ordenación de grupos, las nuevas propiedades [GroupDescription.SortDescriptions](assetId:///P:System.ComponentModel.GroupDescription.SortDescriptions?qualifyHint=True&autoUpgrade=True) y [GroupDescription.CustomSort](assetId:///P:System.ComponentModel.GroupDescription.CustomSort?qualifyHint=True&autoUpgrade=True) describen cómo ordenar la colección de grupos generada por el objeto [GroupDescription](assetId:///T:System.ComponentModel.GroupDescription?qualifyHint=False&autoUpgrade=True). Esto es análogo a la forma en que las propiedades [ListCollectionView](assetId:///T:System.Windows.Data.ListCollectionView?qualifyHint=False&autoUpgrade=True) con el mismo nombre describen cómo se ordenan los elementos de datos.  
  
 Dos nuevas propiedades estáticas de la clase [PropertyGroupDescription](assetId:///T:System.Windows.Data.PropertyGroupDescription?qualifyHint=False&autoUpgrade=True), [CompareNameAscending](assetId:///P:System.Windows.Data.PropertyGroupDescription.CompareNameAscending?qualifyHint=False&autoUpgrade=True) y [CompareNameDescending](assetId:///P:System.Windows.Data.PropertyGroupDescription.CompareNameDescending?qualifyHint=False&autoUpgrade=True), se pueden usar para los casos más comunes.  
  
 Por ejemplo, el siguiente código XAML agrupa los datos por edad, ordena los grupos de edad en orden ascendente y agrupa los elementos de cada grupo de edad por apellido.  
  
```xaml  
  
<GroupDescriptions>  
     \<PropertyGroupDescription   
         PropertyName=”Age”   
         CustomSort=   
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>  
     </PropertyGroupDescription>  
</GroupDescriptions>  
  
<SortDescriptions>  
     \<SortDescription PropertyName=”LastName”/>  
</SortDescriptions>  
  
```  
  
 **Compatibilidad con teclado en pantalla**  
 La compatibilidad con teclado en pantalla permite el seguimiento del foco en aplicaciones WPF, ya que invoca y descarta automáticamente el nuevo teclado en pantalla de Windows 10 cuando un control que acepta entrada de texto recibe la entrada táctil.  
  
 En versiones anteriores de .NET Framework, las aplicaciones WPF no pueden optar por el seguimiento del foco sin deshabilitar la compatibilidad con lápiz o movimiento táctil en WPF.  Como resultado, las aplicaciones WPF deben elegir entre compatibilidad táctil completa en WPF o basarse en la promoción del mouse de Windows.  
  
 **PPP por monitor**  
 Para admitir la reciente proliferación de entornos con valores altos o híbridos de PPP para las aplicaciones WPF, WPF en .NET Framework 4.6.2 habilita el reconocimiento de monitor. Consulte [los ejemplos y la guía para desarrolladores](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) en GitHub para obtener más información sobre cómo activar el reconocimiento de PPP por monitor en la aplicación WPF.  
  
 En versiones anteriores de .NET Framework, las aplicaciones WPF tienen habilitado el reconocimiento de PPP del sistema. En otras palabras, el sistema operativo escala la interfaz de usuario de la aplicación según corresponda, en función del valor de PPP del monitor en el que se representa la aplicación. ,  
  
 Para aplicaciones que se ejecutan en .NET Framework 4.6.2, puede deshabilitar los cambios de PPP por monitor en las aplicaciones WPF. Para ello, agregue una instrucción de configuración en la sección [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) del archivo de configuración de la aplicación de la siguiente manera:  
  
```xml  
  
<runtime>  
   \<AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>  
</runtime>  
  
```  
  
<a name="WF462"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 En .NET Framework 4.6.2, Windows Workflow Foundation se ha mejorado en las áreas siguientes:  
  
 **Compatibilidad con expresiones de C# e IntelliSense en el Diseñador de WF rehospedado**  
 A partir de .NET Framework 4.5, WF admite expresiones de C# en el diseñador de Visual Studio y en los flujos de trabajo de código. El Diseñador de flujo de trabajo rehospedado es una característica clave de WF que permite que el Diseñador de flujo de trabajo esté en una aplicación fuera de Visual Studio (por ejemplo, en WPF).  Windows Workflow Foundation permite admitir expresiones de C# e IntelliSense en el Diseñador de flujo de trabajo rehospedado. Para obtener más información, consulte el [blog de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).  
  
 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`  
 En las versiones de .NET Framework anteriores a .NET Framework 4.6.2, IntelliSense del Diseñador de WF se interrumpe cuando un cliente vuelve a compilar un proyecto de flujo de trabajo desde Visual Studio. Aunque la compilación del proyecto es correcta, los tipos de flujo de trabajo no se encuentran en el diseñador y en la ventana **Lista de errores** aparecen advertencias de IntelliSense que indican los tipos de flujo de trabajo que faltan. .NET Framework 4.6.2 soluciona este problema y hace que IntelliSense esté disponible.  
  
 **Las aplicaciones V1 de flujo de trabajo con seguimiento del flujo de trabajo ahora se ejecutan en modo FIPS**  
 Los equipos que tienen habilitado el modo de cumplimiento de FIPS ahora pueden ejecutar correctamente una aplicación de versión 1 de flujo de trabajo con el seguimiento del flujo de trabajo habilitado. Para habilitar este escenario, debe realizar el cambio siguiente en el archivo app.config:  
  
```xml  
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />  
```  
  
 Si este escenario no está habilitado, al ejecutar la aplicación se sigue generando una excepción con el mensaje "Esta implementación no forma parte de los algoritmos criptográficos validados por Windows Platform FIPS".  
  
 **Mejoras en el flujo de trabajo al usar la actualización dinámica con el Diseñador de flujo de trabajo de Visual Studio**  
 El Diseñador de flujo de trabajo, el Diseñador de actividad de diagrama de flujo y otros diseñadores de actividad de flujo de trabajo ahora cargan y muestran correctamente los flujos de trabajo que se han guardado después de llamar al método [DynamicUpdateServices.PrepareForUpdate](assetId:///M:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate(System.Activities.Activity)?qualifyHint=True&autoUpgrade=True). En versiones de .NET Framework anteriores a .NET Framework 4.6.2, la carga de un archivo XAML en Visual Studio para un flujo de trabajo guardado después de llamar a [DynamicUpdateServices.PrepareForUpdate](assetId:///M:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate(System.Activities.Activity)?qualifyHint=True&autoUpgrade=True) puede producir los problemas siguientes:  
  
-   El Diseñador de flujo de trabajo no se puede cargar el archivo XAML correctamente (cuando [ViewStateData.Id](assetId:///P:System.Activities.Presentation.ViewState.ViewStateData.Id?qualifyHint=True&autoUpgrade=True) se encuentra al final de la línea).  
  
-   El Diseñador de actividad de diagrama de flujo u otros diseñadores de actividad de flujo de trabajo pueden mostrar todos los objetos en sus ubicaciones predeterminadas en lugar de los valores de la propiedad adjunta.  
  
<a name="ClickOnce"></a>   
### <a name="clickonce"></a>ClickOnce  
 Se ha actualizado ClickOnce para que admita TLS 1.1 y TLS 1.2 además del protocolo 1.0, que ya se admite. ClickOnce detecta automáticamente qué protocolo se requiere; no es necesario realizar ningún paso adicional en la aplicación ClickOnce para habilitar la compatibilidad con TLS 1.1 y 1.2.  
  
<a name="UWPConvert"></a>   
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Conversión de aplicaciones de Windows Forms y WPF a aplicaciones de UWP  
 Windows ahora ofrece funciones para llevar aplicaciones existentes de escritorio de Windows, incluidas aplicaciones de Windows Forms y WPF, a la Plataforma universal de Windows (UWP). Esta tecnología actúa como un puente, ya que permite migrar gradualmente su base de código existente a UWP, lo que lleva su aplicación a todos los dispositivos Windows 10.  
  
 Las aplicaciones de escritorio convertidas obtienen una identidad de aplicación similar a la identidad de aplicación de las aplicaciones de UWP, lo que hace que las API de UWP sean accesibles para habilitar características como iconos dinámicos y notificaciones. La aplicación sigue comportándose como antes y se ejecuta como una aplicación de plena confianza. Una vez convertida la aplicación, se puede agregar un proceso de contenedor de la aplicación al proceso de plena confianza existente para agregar una interfaz de usuario adaptable. Cuando todas las funciones se hayan movido al proceso de contenedor de la aplicación, se puede quitar el proceso de plena confianza y la nueva aplicación de UWP estará disponible para todos los dispositivos Windows 10.  
  
<a name="Debug462"></a>   
### <a name="debugging-improvements"></a>Mejoras en la depuración  
 La *API de depuración no administrada* se ha mejorado en .NET Framework 4.6.2 para que realice análisis adicionales cuando se inicie una excepción [NullReferenceException](assetId:///T:System.NullReferenceException?qualifyHint=False&autoUpgrade=True), de modo que sea posible determinar qué variable de una sola línea de código fuente es `null`.   Para admitir este escenario, se han agregado las API siguientes a la API de depuración no administrada.  
  
-   Las interfaces [ICorDebugCode4](../Topic/ICorDebugCode4%20Interface.md), [ICorDebugVariableHome](../Topic/ICorDebugVariableHome%20Interface.md) e [ICorDebugVariableHomeEnum](../Topic/ICorDebugVariableHomeEnum%20Interface.md), que exponen las ubicaciones nativas de las variables administradas. Esto permite a los depuradores realizar un análisis de flujo de código cuando se produce una excepción [NullReferenceException](assetId:///T:System.NullReferenceException?qualifyHint=False&autoUpgrade=True) y trabajar hacia atrás para determinar la variable administrada que se corresponde con la ubicación nativa que era `null`.  
  
-   El método [ICorDebugType2::GetTypeID](../Topic/ICorDebugType2::GetTypeID%20Method.md) proporciona una asignación para ICorDebugType a [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md), lo que permite al depurador obtener un valor [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md) sin una instancia de ICorDebugType. Después, las API existentes en [COR_TYPEID](../Topic/COR_TYPEID%20Structure.md) pueden usarse para determinar el diseño de clase del tipo.  
  
<a name="v461"></a>   
## <a name="whats-new-in-the-net-framework-461"></a>Novedades de .NET Framework 4.6.1  
 .NET Framework 4.6.1 incluye nuevas características en las áreas siguientes:  
  
-   [Criptografía](#Crypto)  
  
-   [ADO.NET](#ADO.NET461)  
  
-   [Windows Presentation Foundation (WPF)](#WPF461)  
  
-   [Windows Workflow Foundation](#WWF461)  
  
-   [Generación de perfiles](#Profile461)  
  
-   [NGen](#NGEN461)  
  
 Para más información sobre .NET Framework 4.6.1, consulte los temas siguientes:  
  
-   La [lista de cambios de .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=622964)  
  
-   [Compatibilidad de aplicaciones en 4.6.1](../Topic/Application%20Compatibility%20in%20the%20.NET%20Framework%204.6.1.md)  
  
-   [Diferencia de la API de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=622989) (en GitHub)  
  
<a name="Crypto"></a>   
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Cifrado: compatibilidad con certificados X509 que contienen ECDSA  
 La versión 4.6 de .NET Framework agrega compatibilidad con RSACng para certificados X509. .NET Framework 4.6.1 agrega compatibilidad para certificados X509 ECDSA (Elliptic Curve Digital Signature Algorithm).  
  
 ECDSA ofrece un mejor rendimiento y es un algoritmo de cifrado más seguro que RSA, lo que lo convierte en una excelente elección cuando están en juego la escalabilidad y el rendimiento de la seguridad de capa de transporte (TLS). La implementación de .NET Framework encapsula las llamadas en funciones de Windows existentes.  
  
 El ejemplo de código siguiente muestra lo fácil que es generar una firma para una secuencia de bytes mediante la nueva compatibilidad para certificados X509 de ECDSA incluidos en .NET Framework 4.6.1.  
  
<!-- TODO: review snippet reference  [!CODE [whatsnew.461.crypto#1](../CodeSnippet/VS_Snippets_CLR/whatsnew.461.crypto#1)]  -->  
  
 Esto ofrece un contraste marcado para el código necesario para generar una firma en .NET Framework 4.6.  
  
<!-- TODO: review snippet reference  [!CODE [whatsnew.461.crypto#2](../CodeSnippet/VS_Snippets_CLR/whatsnew.461.crypto#2)]  -->  
  
<a name="ADO.NET461"></a>   
### ADO.NET Se agregó lo siguiente a ADO.NET:  
  
 Compatibilidad con Always Encrypted para claves protegidas por hardware  
 ADO.NET ahora permite almacenar claves maestras de la columna Always Encrypted de forma nativa en módulos de seguridad de hardware (HSM). Con esta compatibilidad, los clientes pueden aprovechar las claves asimétricas almacenadas en HSM sin tener que escribir proveedores de almacenes de clave maestra de la columna personalizada ni registrarlos en las aplicaciones.  
  
 Los clientes necesitan instalar el proveedor CSP proporcionado por el fabricante HSM o los proveedores de almacén de claves de CNG en los servidores de aplicación o en los equipos cliente para tener acceso a los datos que Always Encrypted ha protegido con las claves maestras de columna almacenadas en un HSM.  
  
 Mejora del comportamiento de la conexión de [MultiSubnetFailover](assetId:///P:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover?qualifyHint=False&autoUpgrade=True) para AlwaysOn  
 SqlClient ahora proporciona automáticamente una conexión más rápida a un grupo de disponibilidad AlwaysOn (AG). Detecta de forma transparente si la aplicación se conecta a un grupo de disponibilidad AlwaysOn (AG) en una subred diferente y detecta rápidamente el servidor activo actual y proporciona una conexión al servidor. Antes de esta versión, una aplicación tenía que establecer la cadena de conexión para incluir `“MultisubnetFailover=true”` e indicar que se conecta a un grupo de disponibilidad AlwaysOn. Sin establecer la palabra clave de conexión en `true`, una aplicación podría experimentar un tiempo de espera mientras se conecta a un grupo de disponibilidad AlwaysOn. Con esta versión, la aplicación ya *no* necesita establecer [MultiSubnetFailover](assetId:///P:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover?qualifyHint=False&autoUpgrade=True) en `true`. Para obtener más información sobre la compatibilidad de SqlClient con grupos de disponibilidad AlwaysOn, vea [Compatibilidad de SqlClient para alta disponibilidad y recuperación ante desastres](../Topic/SqlClient%20Support%20for%20High%20Availability,%20Disaster%20Recovery.md).  
  
<a name="WPF461"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 Windows Presentation Foundation incluye una serie de mejoras y cambios.  
  
 Rendimiento mejorado  
 Se corrigió el retraso de activación de eventos de función táctil en .NET Framework 4.6.1. Además, al escribir un control [RichTextBox](assetId:///T:System.Windows.Controls.RichTextBox?qualifyHint=False&autoUpgrade=True) ya no se bloquea el subproceso de representación durante la entrada rápida.  
  
 Mejoras en el corrector ortográfico  
 El corrector ortográfico en WPF se ha actualizado en Windows 8.1 y en versiones posteriores para aprovechar la compatibilidad del sistema operativo con la corrección ortográfica de idiomas adicionales.  No hay ningún cambio en la funcionalidad en las versiones de Windows anteriores a Windows 8.1.  
  
 Como en versiones anteriores de .NET Framework, el idioma de un control [TextBox](assetId:///T:System.Windows.Controls.TextBox?qualifyHint=False&autoUpgrade=True) o un bloque [RichTextBox](assetId:///T:System.Windows.Controls.RichTextBox?qualifyHint=False&autoUpgrade=True) se detecta mediante la búsqueda de información en el orden siguiente:  
  
-   `xml:lang`, si está presente.  
  
-   Idioma de entrada actual.  
  
-   Referencia cultural del subproceso actual.  
  
 Para obtener más información sobre la compatibilidad de idioma en WPF, vea la [entrada de blog de WPF sobre las características de .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkID=691819).  
  
 Compatibilidad adicional con diccionarios personalizados por el usuario  
 En .NET Framework 4.6.1, WPF reconoce los diccionarios personalizados que se registran de forma global. Esta funcionalidad está disponible además de la posibilidad de registrarlos por control.  
  
 En versiones anteriores de WPF, los diccionarios personalizados no reconocían palabras excluidas ni listas de autocorrección. Ahora se admiten en Windows 8.1 y Windows 10 mediante el uso de archivos que se pueden colocar en el directorio `%AppData%\Microsoft\Spelling\<language tag>`.  Las reglas siguientes se aplican a estos archivos:  
  
-   Los archivos deben tener las extensiones .dic (para palabras agregadas), .exc (para las palabras excluidas) o .acl (para la autocorrección).  
  
-   Los archivos deben ser texto sin formato UTF-16 LE que comienza con la marca BOM (Byte Order Mark).  
  
-   Cada línea debe constar de una palabra (en las listas de palabras agregadas y excluidas) o un par de autocorrección con las palabras separadas por una barra vertical ("|") (en la lista de palabras de Autocorrección).  
  
-   Estos archivos se consideran de solo lectura y el sistema no los modifica.  
  
> [!NOTE]
>  Estos nuevos formatos de archivos no son compatibles directamente con las API de corrección ortográfica de WPF, y los diccionarios personalizados proporcionados a WPF en las aplicaciones deben continuar usando los archivos .lex.  
  
 Muestras  
 Hay una serie de [ejemplos de WPF](https://msdn.microsoft.com/library/ms771633.aspx) en MSDN. Más de 200 de los ejemplos más populares (según su utilización) se moverán a un [repositorio de GitHub de código abierto](https://github.com/Microsoft/WPF-Samples). Ayúdenos a mejorar nuestros ejemplos enviando una solicitud de extracción o abriendo un [problema de GitHub](https://github.com/Microsoft/WPF-Samples/issues).  
  
 Extensiones de DirectX  
 WPF incluye un [paquete NuGet](http://go.microsoft.com/fwlink/?LinkID=691342) que proporciona nuevas implementaciones de [D3DImage](assetId:///T:System.Windows.Interop.D3DImage?qualifyHint=False&autoUpgrade=True) que facilitan la tarea de interoperar con contenido DX10 y Dx11. El código para este paquete se ha abierto y está disponible [en GitHub](https://github.com/Microsoft/WPFDXInterop).  
  
<a name="WWF461"></a>   
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: transacciones  
 El método [Transaction.EnlistPromotableSinglePhase](assetId:///Overload:System.Transactions.Transaction.EnlistPromotableSinglePhase?qualifyHint=True&autoUpgrade=True) ahora puede usar un administrador de transacciones distribuidas que no sea MSDTC para promocionar la transacción. Para ello, especifique un identificador GUID de promoción de transacción a la nueva sobrecarga [Transaction.EnlistPromotableSinglePhase(IPromotableSinglePhaseNotification, Guid)](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification,System.Guid)?qualifyHint=True&autoUpgrade=False). Si esta operación se realiza correctamente, hay limitaciones de las capacidades de la transacción. Una vez que se activa un promotor de transacciones que no sea MSDTC, los métodos siguientes inician una [TransactionPromotionException](assetId:///T:System.Transactions.TransactionPromotionException?qualifyHint=False&autoUpgrade=True) porque estos métodos requieren promoción a MSDTC:  
  
-   [Transaction.EnlistDurable](assetId:///Overload:System.Transactions.Transaction.EnlistDurable?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetDtcTransaction](assetId:///M:System.Transactions.TransactionInterop.GetDtcTransaction(System.Transactions.Transaction)?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetExportCookie](assetId:///M:System.Transactions.TransactionInterop.GetExportCookie(System.Transactions.Transaction,System.Byte[])?qualifyHint=True&autoUpgrade=True)  
  
-   [TransactionInterop.GetTransmitterPropagationToken](assetId:///M:System.Transactions.TransactionInterop.GetTransmitterPropagationToken(System.Transactions.Transaction)?qualifyHint=True&autoUpgrade=True)  
  
 Una vez que se activa un promotor de transacciones que no sea MSDTC, debe usarse para futuras inscripciones duraderas a través de los protocolos que define. El [GUID](assetId:///T:System.Guid?qualifyHint=False&autoUpgrade=True) del promotor de transacción puede obtenerse con la propiedad [PromoterType](assetId:///P:System.Transactions.Transaction.PromoterType?qualifyHint=False&autoUpgrade=True). Cuando se promueve la transacción, el promotor de transacciones proporciona una matriz [Byte](assetId:///T:System.Byte?qualifyHint=False&autoUpgrade=True) que representa el token promocionado. Una aplicación puede obtener el token promocionado de una transacción promocionada que no sea de MSDTC con el método [GetPromotedToken](assetId:///M:System.Transactions.Transaction.GetPromotedToken?qualifyHint=False&autoUpgrade=True).  
  
 Los usuarios de la nueva sobrecarga [Transaction.EnlistPromotableSinglePhase(IPromotableSinglePhaseNotification, Guid)](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification,System.Guid)?qualifyHint=True&autoUpgrade=False) deben seguir una secuencia de llamada específica para que la operación de promoción se lleve a cabo correctamente. Estas reglas están registradas en la documentación del método.  
  
<a name="Profile461"></a>   
### <a name="profiling"></a>Generación de perfiles  
 La API de generación de perfiles no administrada se ha mejorado como se indica a continuación:  
  
 Mejor compatibilidad para tener acceso a archivos PDB en la interfaz [ICorProfilerInfo7](../Topic/ICorProfilerInfo7%20Interface.md)  
 En ASP.Net 5, cada vez es más común que los ensamblados se compilen en memoria mediante Roslyn. Para desarrolladores que crean herramientas de generación de perfiles, esto significa que los PDB serializados históricamente en disco ya no estén presentes. Las herramientas del generador de perfiles suelen usar archivos PDB para asignar código a las líneas de código fuente para tareas como el análisis de rendimiento de línea por línea o de cobertura de código. La interfaz [ICorProfilerInfo7](../Topic/ICorProfilerInfo7%20Interface.md) ahora incluye dos nuevos métodos, [ICorProfilerInfo7::GetInMemorySymbolsLength](../Topic/ICorProfilerInfo7::GetInMemorySymbolsLength%20Method.md) e [ICorProfilerInfo7::ReadInMemorySymbols](../Topic/ICorProfilerInfo7::ReadInMemorySymbols.md), para proporcionar estas herramientas del generador de perfiles con acceso a los datos de PDB en memoria. Usando las nuevas API, un generador de perfiles puede obtener el contenido de un PDB en memoria como una matriz de bytes y luego procesarlo o serializarlo en el disco.  
  
 Mejor instrumentación con la interfaz ICorProfiler  
 Los generadores de perfiles que utilizan la funcionalidad ReJit de la API `ICorProfiler` para la instrumentación dinámica ahora pueden modificar algunos metadatos. Anteriormente dichas herramientas podían instrumentar IL en cualquier momento, pero los metadatos solo se podían modificar en tiempo de carga del módulo. Dado que IL hace referencia a los metadatos, esto limita los tipos de instrumentación que se podían hacer. Hemos solucionado algunos de esos límites agregando el método [ICorProfilerInfo7::ApplyMetaData](../Topic/ICorProfilerInfo7::ApplyMetaData%20Method.md) para admitir un subconjunto de ediciones de metadatos después de que el módulo se cargue, en particular agregando nuevos registros `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec` y `UserString`. Este cambio permite una mayor variedad de instrumentación sobre la marcha.  
  
<a name="NGEN461"></a>   
### <a name="native-image-generator-ngen-pdbs"></a>PDB del generador de imágenes nativas (NGEN)  
 El seguimiento de eventos de varios equipos permite a los clientes generar perfiles de un programa en la máquina A y mirar los datos de generación de perfiles con la asignación de la línea de origen en la máquina B. Al usar versiones anteriores de .NET Framework, el usuario copiaría todos los módulos y las imágenes nativas de la máquina con generación de perfiles a la máquina de análisis que contiene el archivo PDB de IL para crear la asignación de código fuente a nativo. Aunque este proceso puede funcionar bien cuando los archivos son relativamente pequeños, como en aplicaciones de teléfono, los archivos pueden ser muy grandes en sistemas de escritorio y requieren mucho tiempo para copiarse.  
  
 Con los archivos PDB de NGen, NGen puede crear un archivo PDB que contenga la asignación de IL a nativo sin una dependencia del archivo PDB de IL. En nuestro escenario de seguimiento de eventos de varias máquinas, todo lo que se necesita es copiar la imagen nativa PDB generada por la máquina A a la máquina B y utilizar [Depurar API de acceso de interfaz](https://docs.microsoft.com/en-us/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) para leer la asignación de origen al IL del archivo PDB de IL y la asignación del IL a nativo del archivo PDB de imágenes nativas. La combinación de ambas asignaciones permite asignar código fuente a nativo. Dado que el PDB de imagen nativa es mucho menor que todos los módulos y las imágenes nativas, el proceso de copiar de la máquina A a la máquina B es mucho más rápido.  
  
<a name="v46"></a>   
## <a name="whats-new-in-net-2015"></a>Novedades de .NET 2015  
 .NET 2015 presenta .NET Framework 4.6 y .NET Core. Algunas características nuevas se aplican a ambos, y otras son específicas de .NET Framework 4.6 o .NET Core.  
  
-   **ASP.NET 5**  
  
     .NET Framework 2015 incluye ASP.NET 5, que es una plataforma .NET eficiente para la compilación de aplicaciones modernas basadas en la nube. La plataforma es modular, por lo que puede incluir solo aquellas características que se necesitan en la aplicación. Puede hospedarse en IIS o autohospedarse en un proceso personalizado y se pueden ejecutar aplicaciones con diferentes versiones de .NET Framework en el mismo servidor. Incluye un nuevo sistema de configuración de entorno que está diseñado para la implementación de la nube.  
  
     MVC, Web API y Web Pages están unificados en un marco único llamado MVC 6. Las aplicaciones de ASP.NET 5 se compilan con las nuevas herramientas de Visual Studio 2015. Las aplicaciones existentes funcionarán en el nuevo .NET Framework; sin embargo, para compilar una aplicación que use MVC 6 o SignalR 3, debe usar el sistema de proyectos de Visual Studio 2015.  
  
     Para obtener información, vea [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).  
  
-   **Actualizaciones de ASP.NET**  
  
    -   **API basada en tareas para el vaciado de respuestas asincrónicas**  
  
         Ahora, ASP.NET proporciona una API sencilla basada en tareas para el vaciado de respuestas asincrónicas, [HttpResponse.FlushAsync](assetId:///M:System.Web.HttpResponse.FlushAsync?qualifyHint=True&autoUpgrade=True), que permite vaciar las respuestas de forma asincrónica con el soporte `async/await` de su lenguaje.  
  
    -   `Model binding supports task-returning methods`  
  
         ASP.NET agregó en .NET Framework 4.5 la característica Enlace de modelos, que habilita un enfoque extensible y centrado en el código en las operaciones de datos basadas en CRUD de las páginas de formularios Web Forms y los controles de usuario. Ahora el sistema Enlace de modelos es compatible con los métodos de enlace de modelos que devuelven [Task](assetId:///T:System.Threading.Tasks.Task?qualifyHint=False&autoUpgrade=True). Esta característica permite que los desarrolladores de formularios Web Forms aprovechen las ventajas que presenta la escalabilidad de la asincronía con la facilidad del sistema de enlace de datos al usar las versiones más recientes de ORM, incluido Entity Framework.  
  
         El enlace de modelos asincrónicos se controla con la opción de configuración `aspnet:EnableAsyncModelBinding`.  
  
        ```  
  
        <appSettings>  
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />  
        </appSettings>  
  
        ```  
  
         En las aplicaciones que tienen como destino .NET Framework 4.6, el valor predeterminado es `true`. En las aplicaciones que se ejecutan en .NET Framework 4.6 y que tienen como destino una versión anterior de .NET Framework, el valor predeterminado es `false`. Se puede habilitar estableciendo la opción de configuración en `true`.  
  
    -   **Compatibilidad con HTTP/2 (Windows 10)**  
  
         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) es una nueva versión del protocolo HTTP que proporciona un uso mucho mejor de la conexión (menos recorridos de ida y vuelta entre el cliente y el servidor), lo que permite una latencia más baja para los usuarios al cargar páginas web.  Las páginas web (no de servicios) aprovechan HTTP/2 al máximo, porque el protocolo se optimizó para la solicitud de varios artefactos como parte de una sola experiencia. La compatibilidad para HTTP/2 se agregó a ASP.NET en .NET Framework 4.6. Como la funcionalidad de red existe en varios niveles, se necesitaban nuevas características en Windows, IIS y ASP.NET para habilitar HTTP/2. Debe ejecutar Windows 10 para usar HTTP/2 con ASP.NET.  
  
         También se admite HTTP/2, y está activado de forma predeterminada en las aplicaciones de la Plataforma universal de Windows (UWP) de Windows 10 que usan la API [System.Net.Http.HttpClient](assetId:///T:System.Net.Http.HttpClient?qualifyHint=True&autoUpgrade=True).  
  
         Para proporcionar una forma de usar la característica [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) en aplicaciones de ASP.NET, se agregó un método nuevo con dos sobrecargas, [PushPromise(String)](assetId:///M:System.Web.HttpResponse.PushPromise(System.String)?qualifyHint=False&autoUpgrade=False) y [PushPromise(String, String, NameValueCollection)](assetId:///M:System.Web.HttpResponse.PushPromise(System.String,System.String,System.Collections.Specialized.NameValueCollection)?qualifyHint=False&autoUpgrade=False), a la clase [HttpResponse](assetId:///T:System.Web.HttpResponse?qualifyHint=False&autoUpgrade=True).  
  
        > [!NOTE]
        >  Mientras que ASP.NET 5 admite HTTP/2, la compatibilidad con la característica PUSH PROMISE aún no se ha agregado.  
  
         El explorador y el servidor web (IIS en Windows) hacen todo el trabajo. No tiene que hacer el trabajo más farragoso para los usuarios.  
  
         La mayoría de [los principales navegadores admiten HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), por lo que probablemente los usuarios se beneficiarán de la compatibilidad con HTTP/2 si el servidor lo admite.  
  
    -   **Compatibilidad con el Protocolo de enlace de tokens**  
  
         Google y Microsoft colaboraron en un nuevo sistema de autenticación llamado [Protocolo de enlace de tokens](https://github.com/TokenBinding/Internet-Drafts). La premisa es que los tokens de autenticación (en la memoria caché del navegador) pueden ser robados y usados por delincuentes para acceder a recursos seguros (por ejemplo, su cuenta bancaria) sin necesidad de contraseña ni de otra información privilegiada. El nuevo protocolo tiene como objetivo mitigar este problema.  
  
         El Protocolo de enlace de tokens se implementará en Windows 10 como una característica del explorador. Las aplicaciones de ASP.NET participarán en el protocolo para validar la legitimidad de los tokens de autenticación. Las implementaciones de cliente y de servidor establecen la protección de extremo a extremo especificada por el protocolo.  
  
    -   **Algoritmos hash de cadena aleatoria**  
  
         En .NET Framework 4.5, se introdujo [un algoritmo hash de cadena aleatorio](https://msdn.microsoft.com/library/jj152924.aspx). pero no era compatible con ASP.NET porque algunas características de ASP.NET dependían de un código hash estable. En .NET Framework 4.6 ya se admiten los algoritmos hash de cadena aleatoria. Para habilitar esta característica, use la opción de configuración `aspnet:UseRandomizedStringHashAlgorithm`.  
  
        ```  
  
        <appSettings>  
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />  
        </appSettings>  
  
        ```  
  
-   **ADO.NET**  
  
     ADO .NET ahora es compatible con la característica Always Encrypted disponible en SQL Server 2016 Community Technology Preview 2 (CTP2). Con Always Encrypted, SQL Server puede realizar operaciones en los datos cifrados y, lo mejor de todo, es que la clave de cifrado reside, junto con la aplicación, en el entorno de confianza del cliente y no en el servidor. Always Encrypted protege los datos del cliente para que los administradores de bases de datos no tengan acceso a los datos de texto sin formato. El cifrado y descifrado de datos ocurre de forma transparente en el nivel de controlador, lo que minimiza los cambios que deben realizarse en las aplicaciones existentes. Para obtener más información, vea [Always Encrypted (motor de base de datos)](https://msdn.microsoft.com/library/mt163865\(v=sql.130\).aspx) y [Always Encrypted (desarrollo de cliente)](https://msdn.microsoft.com/library/mt147923\(v=sql.130\).aspx).  
  
-   **Compilador JIT de 64 bits para código administrado**  
  
     .NET Framework 4.6 incluye una nueva versión del compilador JIT de 64 bits (llamado originalmente RyuJIT). El nuevo compilador de 64 bits proporciona importantes mejoras de rendimiento con respecto al antiguo compilador JIT de 64 bits. El nuevo compilador de 64 bits está habilitado para los procesos de 64 bits que se ejecutan en .NET Framework 4.6. La aplicación se ejecutará en un proceso de 64 bits si se ha compilado como aplicación de 64 bits o AnyCPU y se está ejecutando en un sistema operativo de 64 bits. Aunque se hayan tomado precauciones para efectuar la transición al nuevo compilador de la manera más transparente posible, es posible que se produzcan cambios en el comportamiento. Nos gustaría que se pusiera en contacto con nosotros si encuentra algún problema al usar el nuevo compilador JIT. Póngase en contacto con nosotros a través de [Microsoft Connect](http://connect.microsoft.com/) si detecta algún problema que pueda estar relacionado con el nuevo compilador JIT de 64 bits.  
  
     El nuevo compilador JIT de 64 bits también incluye características de aceleración SIMD de hardware al acoplarse con tipos habilitados para SIMD en el espacio de nombres [System.Numerics](assetId:///N:System.Numerics?qualifyHint=False&autoUpgrade=True), que pueden conseguir notables mejoras en el rendimiento.  
  
-   **Mejoras en el cargador de ensamblados**  
  
     Ahora el cargador de ensamblados usa la memoria de un modo más eficaz al descargar ensamblados de IL después de cargar una imagen NGEN correspondiente. Este cambio reduce la memoria virtual, que es bastante útil en las aplicaciones de 32 bits de gran tamaño (por ejemplo, Visual Studio), y también guarda la memoria física.  
  
-   **Cambios en la biblioteca de clases base**  
  
     Se agregaron muchas nuevas API a .NET Framework 4.6 para habilitar escenarios clave. Incluyen los siguientes cambios y adiciones:  
  
    -   **Implementaciones de IReadOnlyCollection\<T>**  
  
         Las colecciones adicionales implementan [IReadOnlyCollection\<T>](assetId:///T:System.Collections.Generic.IReadOnlyCollection`1?qualifyHint=False&autoUpgrade=True) como [Queue<T\>](assetId:///T:System.Collections.Generic.Queue`1?qualifyHint=False&autoUpgrade=True) y [Stack\<T>](assetId:///T:System.Collections.Generic.Stack`1?qualifyHint=False&autoUpgrade=True).  
  
    -   **CultureInfo.CurrentCulture y CultureInfo.CurrentUICulture**  
  
         Las propiedades [CultureInfo.CurrentCulture](assetId:///P:System.Globalization.CultureInfo.CurrentCulture?qualifyHint=True&autoUpgrade=True) y [CultureInfo.CurrentUICulture](assetId:///P:System.Globalization.CultureInfo.CurrentUICulture?qualifyHint=True&autoUpgrade=True) ahora son de lectura y escritura, en lugar de solo lectura. Si asigna un nuevo objeto [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True) a estas propiedades, también cambian la referencia cultural del subproceso actual definida por la propiedad `Thread.CurrentThread.CurrentCulture` y la referencia cultural del subproceso de la interfaz usuario actual definida por las propiedades `Thread.CurrentThread.CurrentUICulture`.  
  
    -   **Mejoras en la recolección de elementos no utilizados (GC)**  
  
         La clase [GC](assetId:///T:System.GC?qualifyHint=False&autoUpgrade=True) ahora incluye los métodos [TryStartNoGCRegion](assetId:///M:System.GC.TryStartNoGCRegion(System.Int64)?qualifyHint=False&autoUpgrade=True) y [EndNoGCRegion](assetId:///M:System.GC.EndNoGCRegion?qualifyHint=False&autoUpgrade=True) que permiten impedir la recolección de elementos no usados durante la ejecución de una ruta crítica.  
  
         Una nueva sobrecarga del método [GC.Collect(Int32, GCCollectionMode, Boolean, Boolean)](assetId:///M:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean,System.Boolean)?qualifyHint=True&autoUpgrade=False) permite controlar si el montón del objeto pequeño y el montón del objeto grande se exploran y compactan o si solo se exploran.  
  
    -   **Tipos habilitados para SIMD**  
  
         El espacio de nombres [System.Numerics](assetId:///N:System.Numerics?qualifyHint=False&autoUpgrade=True) incluye ahora varios tipos habilitados para SIMD, como [Matrix3x2](assetId:///T:System.Numerics.Matrix3x2?qualifyHint=False&autoUpgrade=True), [Matrix4x4](assetId:///T:System.Numerics.Matrix4x4?qualifyHint=False&autoUpgrade=True), [Plane](assetId:///T:System.Numerics.Plane?qualifyHint=False&autoUpgrade=True), [Quaternion](assetId:///T:System.Numerics.Quaternion?qualifyHint=False&autoUpgrade=True), [Vector2](assetId:///T:System.Numerics.Vector2?qualifyHint=False&autoUpgrade=True), [Vector3](assetId:///T:System.Numerics.Vector3?qualifyHint=False&autoUpgrade=True) y [Vector4](assetId:///T:System.Numerics.Vector4?qualifyHint=False&autoUpgrade=True).  
  
         Como el nuevo compilador JIT de 64 bits también incluye características de aceleración de hardware SIMD, hay mejoras de rendimiento considerablemente importantes al usar los tipos habilitados para SIMD con el nuevo compilador JIT de 64 bits.  
  
    -   **Actualizaciones de criptografía**  
  
         La API [System.Security.Cryptography](assetId:///N:System.Security.Cryptography?qualifyHint=True&autoUpgrade=True) se está actualizando para admitir la [API de criptografía de CNG de Windows](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx). Las versiones anteriores de .NET Framework se basaban completamente en una [versión anterior de las API de criptografía de Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) como base para la implementación de [System.Security.Cryptography](assetId:///N:System.Security.Cryptography?qualifyHint=True&autoUpgrade=True). Recibimos solicitudes para admitir la API de CNG, ya que admite [algoritmos de criptografía modernos](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), que son importantes para determinadas categorías de aplicaciones.  
  
         .NET Framework 4.6 incluye las siguientes mejoras para admitir las API de criptografía de CNG de Windows:  
  
        -   Un conjunto de métodos de extensión para los certificados X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` y `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, que devuelven, siempre que sea posible, una implementación basada en CNG en lugar de una implementación basada en CAPI (algunas tarjetas inteligentes, entre otros, siguen necesitando CAPI, mientras que las API controlan la reserva).  
  
        -   La clase [System.Security.Cryptography.RSACng](assetId:///T:System.Security.Cryptography.RSACng?qualifyHint=True&autoUpgrade=True), que proporciona una implementación de CNG del algoritmo RSA.  
  
        -   Mejoras en la API de RSA, de modo que las acciones habituales ya no necesitan ninguna conversión. Por ejemplo, el cifrado de datos con un objeto [X509Certificate2](assetId:///T:System.Security.Cryptography.X509Certificates.X509Certificate2?qualifyHint=False&autoUpgrade=True) necesita un código similar al siguiente en las versiones anteriores de .NET Framework.  
  
<!-- TODO: review snippet reference              [!CODE [WhatsNew.Casting#1](../CodeSnippet/VS_Snippets_CLR/whatsnew.casting#1)]  -->  
  
             Code that uses the new cryptography APIs in the .NET Framework 4.6 can be rewritten as follows to avoid the cast.  
  
<!-- TODO: review snippet reference              [!CODE [WhatsNew.Casting#2](../CodeSnippet/VS_Snippets_CLR/whatsnew.casting#2)]  -->  
  
    -   **Compatibilidad con la conversión de fechas y horas a o desde la hora de Unix**  
  
         Se agregaron los siguientes métodos nuevos a la estructura [DateTimeOffset](assetId:///T:System.DateTimeOffset?qualifyHint=False&autoUpgrade=True) para admitir la conversión de valores de fecha y hora a la hora de Unix o desde esta:  
  
        -   [DateTimeOffset.FromUnixTimeSeconds](assetId:///M:System.DateTimeOffset.FromUnixTimeSeconds(System.Int64)?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.FromUnixTimeMilliseconds](assetId:///M:System.DateTimeOffset.FromUnixTimeMilliseconds(System.Int64)?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.ToUnixTimeSeconds](assetId:///M:System.DateTimeOffset.ToUnixTimeSeconds?qualifyHint=True&autoUpgrade=True)  
  
        -   [DateTimeOffset.ToUnixTimeMilliseconds](assetId:///M:System.DateTimeOffset.ToUnixTimeMilliseconds?qualifyHint=True&autoUpgrade=True)  
  
    -   **Modificadores de compatibilidad**  
  
         La nueva clase [AppContext](assetId:///T:System.AppContext?qualifyHint=False&autoUpgrade=True) agrega una nueva característica de compatibilidad que permite a los autores de bibliotecas proporcionar a sus usuarios un mecanismo uniforme para cancelar la participación de la nueva funcionalidad. Establece un contrato flexible entre los componentes para poder comunicar una solicitud de cancelación de la participación. Esta capacidad normalmente es importante cuando se realiza un cambio en la funcionalidad existente. Por el contrario, la nueva funcionalidad participa de forma implícita.  
  
         Con [AppContext](assetId:///T:System.AppContext?qualifyHint=False&autoUpgrade=True), las bibliotecas definen y exponen modificadores de compatibilidad, mientras que el código que depende de ellas puede configurar dichos modificadores para que afecten al comportamiento de la biblioteca. De forma predeterminada, las bibliotecas proporcionan la nueva funcionalidad y solo la modifican (es decir, ofrecen la funcionalidad anterior) si el modificador está establecido.  
  
         Una aplicación (o una biblioteca) puede declarar el valor de un modificador (que es siempre un valor [booleano](assetId:///T:System.Boolean?qualifyHint=False&autoUpgrade=True)) que define una biblioteca dependiente. El modificador siempre es implícitamente `false`. Cuando el modificador se establece en `true`, se habilita. Cuando el modificador se establece explícitamente en `false`, proporciona el nuevo comportamiento.  
  
        ```csharp  
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);  
        ```  
  
         La biblioteca debe comprobar si un consumidor declaró el valor del conmutador y, después, actuar en consecuencia.  
  
        ```  
  
        if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))   
        {  
           // This is the case where the switch value was not set by the application.   
           // The library can choose to get the value of shouldThrow by other means.   
           // If no overrides nor default values are specified, the value should be 'false'.   
           // A false value implies the latest behavior.  
        }  
  
           // The library can use the value of shouldThrow to throw exceptions or not.  
           if (shouldThrow)   
           {  
              // old code  
           }  
           else {  
              // new code  
           }  
        }  
  
        ```  
  
         Es conveniente usar un formato coherente para los modificadores porque son un contrato formal que expone una biblioteca. Las siguientes son dos formatos obvios.  
  
        -   *Modificador*.*espacio de nombres*.*nombre del modificador*  
  
        -   *Modificador*.*biblioteca*.*nombre del modificador*  
  
    -   **Cambios en el modelo asincrónico basado en tareas (TAP)**  
  
         Para las aplicaciones que tienen como destino .NET Framework 4.6, los objetos [Task](assetId:///T:System.Threading.Tasks.Task?qualifyHint=False&autoUpgrade=True) y [Task\<TResult>](assetId:///T:System.Threading.Tasks.Task`1?qualifyHint=False&autoUpgrade=True) heredan la referencia cultural y la referencia cultural de interfaz de usuario del subproceso que realiza la llamada. No se ve afectado el comportamiento de las aplicaciones que tienen como destino las versiones anteriores de .NET Framework o que no especifican una versión concreta de .NET Framework. Para más información, consulte la sección "Referencia cultural y operaciones asincrónicas basadas en tareas" del tema sobre la clase [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True).  
  
         La clase [System.Threading.AsyncLocal\<T>](assetId:///T:System.Threading.AsyncLocal`1?qualifyHint=True&autoUpgrade=True) le permite representar datos de ambiente locales de un flujo de control asincrónico determinado, por ejemplo, un método `async`. Se puede usar para conservar los datos en todos los subprocesos. También puede definir un método de devolución de llamada que se le notifique al cambiar los datos de ambiente, ya sea porque se ha cambiado la propiedad [AsyncLocal<T\>.Value](assetId:///P:System.Threading.AsyncLocal`1.Value?qualifyHint=True&autoUpgrade=True) de forma explícita o porque el subproceso ha encontrado una transición de contexto.  
  
         Se agregaron tres prácticos métodos, [Task.CompletedTask](assetId:///P:System.Threading.Tasks.Task.CompletedTask?qualifyHint=True&autoUpgrade=True), [Task.FromCanceled](assetId:///M:System.Threading.Tasks.Task.FromCanceled(System.Threading.CancellationToken)?qualifyHint=True&autoUpgrade=True) y [Task.FromException](assetId:///M:System.Threading.Tasks.Task.FromException(System.Exception)?qualifyHint=True&autoUpgrade=True), al patrón asincrónico basado en tareas (TAP) para que devuelva las tareas completadas en un estado determinado.  
  
         La clase [NamedPipeClientStream](assetId:///T:System.IO.Pipes.NamedPipeClientStream?qualifyHint=False&autoUpgrade=True) ahora admite la comunicación asincrónica con su nuevo método [ConnectAsync](assetId:///M:System.IO.Pipes.NamedPipeClientStream.ConnectAsync?qualifyHint=False&autoUpgrade=True). .  
  
    -   **EventSource ahora permite escribir en el Registro de eventos**  
  
         Ahora puede usar la clase [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True) para registrar mensajes administrativos u operativos en el registro de eventos, además de cualquier sesión ETW existente que se haya creado en el equipo. Anteriormente, tenía que usar el paquete de NuGet Microsoft.Diagnostics.Tracing.EventSource para poder aprovechar esta funcionalidad, que ahora está integrada en .NET Framework 4.6.  
  
         El paquete de NuGet y .NET Framework 4.6 se han actualizado con las siguientes características:  
  
        -   **Eventos dinámicos**  
  
             Permite eventos definidos "sobre la marcha" sin crear métodos de eventos.  
  
        -   **Cargas enriquecidas**  
  
             Permite que las matrices y clases con atributos especiales, así como los tipos primitivos, se pasen como carga  
  
        -   **Seguimiento de actividad**  
  
             Hace que los eventos de inicio y de detención etiqueten eventos entre ellos con un identificador que representa todas las actividades actualmente activas.  
  
         Para admitir estas características, se ha agregado el método [Write](assetId:///M:System.Diagnostics.Tracing.EventSource.Write(System.String)?qualifyHint=False&autoUpgrade=True) sobrecargado a la clase [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True).  
  
-   **Windows Presentation Foundation (WPF)**  
  
    -   **Mejoras en el HDPI**  
  
         Se mejoró la compatibilidad con HDPI en WPF en .NET Framework 4.6. Se han hecho cambios en el redondeo del diseño para reducir las instancias de recorte en los controles que contienen bordes. De forma predeterminada, esta característica está activada únicamente si [TargetFrameworkAttribute](assetId:///T:System.Runtime.Versioning.TargetFrameworkAttribute?qualifyHint=False&autoUpgrade=True) está establecido en .NET 4.6.  Las aplicaciones que tienen como destino versiones anteriores de .NET Framework y que se ejecutan en .NET Framework 4.6 pueden participar en el nuevo comportamiento agregando la siguiente línea a la sección [\<runtime>](../Topic/%3Cruntime%3E%20Element.md) del archivo app.config:  
  
        ```  
  
        <AppContextSwitchOverrides  
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"  
        />  
  
        ```  
  
         Actualmente, las ventanas de WPF que ocupan varios monitores con diferentes valores de PPP (configuración de varios PPP) se representan completamente sin regiones oscurecidas. Puede deshabilitar este comportamiento agregando la siguiente línea a la sección `<appSettings>` del archivo app.config:  
  
        ```  
  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
  
        ```  
  
         Se ha agregado compatibilidad para cargar automáticamente el cursor derecho según la configuración de PPP a [System.Windows.Input.Cursor](assetId:///T:System.Windows.Input.Cursor?qualifyHint=True&autoUpgrade=True).  
  
    -   **Mejor si es táctil**  
  
         Los informes de los clientes en [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) acerca del comportamiento impredecible de la función táctil se han tratado en .NET Framework 4.6. Ahora, el umbral de doble punteo de las aplicaciones de WPF y de la Tienda Windows es el mismo en Windows 8.1 y versiones superiores.  
  
    -   **Compatibilidad con las ventanas secundarias transparentes**  
  
         En .NET Framework 4.6, WPF admite las ventanas secundarias transparentes en Windows 8.1 y versiones superiores, de manera que puede crear ventanas secundarias transparentes y no rectangulares en las ventanas de nivel superior. Puede habilitar esta característica estableciendo la propiedad [HwndSourceParameters.UsesPerPixelTransparency](assetId:///P:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency?qualifyHint=True&autoUpgrade=True) en `true`.  
  
-   **Windows Communication Foundation (WCF)**  
  
    -   **Compatibilidad con SSL**  
  
         WCF ahora admite la versión con SSL TLS 1.1 y TLS 1.2, además de SSL 3.0 y TLS 1.0, al usar NetTcp con la autenticación de cliente y la seguridad de transporte. Ahora se puede seleccionar el protocolo que se quiere usar o bien deshabilitar protocolos antiguos menos seguros; para ello, establezca la propiedad [SslProtocols](assetId:///P:System.ServiceModel.TcpTransportSecurity.SslProtocols?qualifyHint=False&autoUpgrade=True) o agregue lo siguiente a un archivo de configuración.  
  
        ```  
        <netTcpBinding>  
           <binding>  
              <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                 <transport clientCredentialType="None|Windows|Certificate"  
                            protectionLevel="None|Sign|EncryptAndSign"  
                            sslProtocols="Ssl3|Tls1|Tls11|Tls12">  
                    </transport>  
              </security>  
           </binding>  
        </netTcpBinding>  
  
        ```  
  
    -   **Enviar mensajes con diferentes conexiones HTTP**  
  
         Ahora WCF permite que los usuarios se aseguren de que se han enviado determinados mensajes con diferentes conexiones HTTP subyacentes. Existen dos modos para hacer esto:  
  
        -   **Usar un prefijo de nombre de grupo de conexión**  
  
             Los usuarios pueden especificar una cadena que WCF usará como prefijo del nombre del grupo de conexión. Se envían dos mensajes con prefijos diferentes por distintas conexiones HTTP subyacentes. Establezca el prefijo agregando un par clave-valor a la propiedad [Message.Properties](assetId:///P:System.ServiceModel.Channels.Message.Properties?qualifyHint=True&autoUpgrade=True) del mensaje. La clave es "httpTransporteConexiónGrupoNombrePrefijo"; el valor es el prefijo deseado.  
  
        -   **Usar distintos generadores de canales**  
  
             Los usuarios también pueden habilitar una característica que garantiza que los mensajes enviados por canales creados por distintos generadores de canales usen diferentes conexiones HTTP subyacentes. Para habilitar esta característica, los usuarios deben establecer el siguiente valor `appSetting` en `true`:  
  
            ```  
  
            <appSettings>  
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />  
            </appSettings>  
  
            ```  
  
-   **Windows Workflow Foundation (WWF)**  
  
     Ahora puede especificar los segundos durante los que un servicio de flujo de trabajo retendrá una solicitud de operación fuera de servicio cuando haya un marcador que no sea de protocolo pendiente antes de que expire la solicitud. Un marcador "no de protocolo" es un marcador que no está relacionado con las actividades de recepción pendientes. Algunas actividades crean marcadores no de protocolo dentro de su implementación, por lo que es posible que no sea obvio que exista un marcador no de protocolo. Entre ellas se encuentran Estado y Selección. Si tiene un servicio de flujo de trabajo implementado con un equipo de estado o que contiene una actividad de selección, lo más probable es que tenga marcadores no de protocolo. Especifique el intervalo agregando una línea como la siguiente a la sección `appSettings` del archivo app.config:  
  
    ```  
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>  
    ```  
  
     El valor predeterminado es de 60 segundos. Si `value` se establece en 0, las solicitudes fuera de servicio se rechazan inmediatamente con un error que contiene un texto similar a este:  
  
    ```Output  
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.   
    ```  
  
     Este es el mismo mensaje que aparece si recibe un mensaje de operación fuera de servicio y no hay ningún marcador que no sea de protocolo.  
  
     Si el valor del elemento `FilterResumeTimeoutInSeconds` es distinto de cero, hay marcadores no de protocolo y el intervalo de tiempo de espera expira, se produce un error en la operación con un mensaje de tiempo de espera.  
  
-   **Transacciones**  
  
     Ahora puede incluir el identificador de transacción distribuida para la transacción que provocó que se produjera una excepción derivada de [TransactionException](assetId:///T:System.Transactions.TransactionException?qualifyHint=False&autoUpgrade=True). Para ello, agregue la siguiente clave a la sección `appSettings` del archivo app.config:  
  
    ```  
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>   
    ```  
  
     El valor predeterminado es `false`.  
  
-   **Redes**  
  
    -   **Reutilización del socket**  
  
         Windows 10 incluye un nuevo algoritmo de red de alta escalabilidad que optimiza los recursos del equipo con la reutilización de los puertos locales para las conexiones TCP salientes. .NET Framework 4.6 es compatible con este algoritmo y permite que las aplicaciones de .NET aprovechen el nuevo comportamiento. En versiones anteriores de Windows había un límite de conexiones simultáneas artificial (normalmente de 16.384, el tamaño predeterminado del intervalo de puertos dinámicos) y esto podía limitar la escalabilidad de un servicio provocando el agotamiento de puertos durante la carga.  
  
         Se agregaron dos API nuevas a .NET Framework 4.6 para permitir la reutilización de puertos, lo que elimina de forma eficaz el límite de 64 K de las conexiones simultáneas:  
  
        -   El valor de enumeración [SocketOptionName.ReuseUnicastPort](assetId:///T:System.Net.Sockets.SocketOptionName?qualifyHint=True&autoUpgrade=True).  
  
        -   La propiedad [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True).  
  
         De forma predeterminada, la propiedad [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True) es `false`, a menos que el valor `HWRPortReuseOnSocketBind` de la clave del Registro `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` se establezca en 0x1. Para habilitar la reutilización del puerto local en las conexiones HTTP, establezca la propiedad [ServicePointManager.ReusePort](assetId:///P:System.Net.ServicePointManager.ReusePort?qualifyHint=True&autoUpgrade=True) en `true`. Esto hace que todas las conexiones de socket TCP salientes de [HttpClient](assetId:///T:System.Net.Http.HttpClient?qualifyHint=False&autoUpgrade=True) y [HttpWebRequest](assetId:///T:System.Net.HttpWebRequest?qualifyHint=False&autoUpgrade=True) usen una nueva opción de socket de Windows 10, [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), que permite la reutilización del puerto local.  
  
         Los desarrolladores que crean una aplicación solo de sockets pueden especificar la opción [SocketOptionName.ReuseUnicastPort](assetId:///T:System.Net.Sockets.SocketOptionName?qualifyHint=True&autoUpgrade=True) al llamar a un método (como [Socket.SetSocketOption](assetId:///M:System.Net.Sockets.Socket.SetSocketOption(System.Net.Sockets.SocketOptionLevel,System.Net.Sockets.SocketOptionName,System.Byte[])?qualifyHint=True&autoUpgrade=True)) para que los sockets de salida reutilicen los puertos locales durante el enlace.  
  
    -   **Compatibilidad con nombres de dominio internacionales y PunyCode**  
  
         Se agregó una nueva propiedad, [IdnHost](assetId:///P:System.Uri.IdnHost?qualifyHint=False&autoUpgrade=True), a la clase [Uri](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True) para ofrecer una mejor compatibilidad con los nombres de dominio internacionales y PunyCode.  
  
-   **Cambio de tamaño en controles de Windows Forms**  
  
     Esta característica se expandió en .NET Framework 4.6 para incluir los tipos [DomainUpDown](assetId:///T:System.Windows.Forms.DomainUpDown?qualifyHint=False&autoUpgrade=True), [NumericUpDown](assetId:///T:System.Windows.Forms.NumericUpDown?qualifyHint=False&autoUpgrade=True), [DataGridViewComboBoxColumn](assetId:///T:System.Windows.Forms.DataGridViewComboBoxColumn?qualifyHint=False&autoUpgrade=True), [DataGridViewColumn](assetId:///T:System.Windows.Forms.DataGridViewColumn?qualifyHint=False&autoUpgrade=True) y [ToolStripSplitButton](assetId:///T:System.Windows.Forms.ToolStripSplitButton?qualifyHint=False&autoUpgrade=True) y el rectángulo especificado en la propiedad [Bounds](assetId:///P:System.Drawing.Design.PaintValueEventArgs.Bounds?qualifyHint=False&autoUpgrade=True) cuando se dibuja un [UITypeEditor](assetId:///T:System.Drawing.Design.UITypeEditor?qualifyHint=False&autoUpgrade=True).  
  
     Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):  
  
    ```  
  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
  
    ```  
  
-   **Compatibilidad para codificaciones de páginas de códigos**  
  
     .NET Core admite principalmente las codificaciones Unicode y, de forma predeterminada, proporciona compatibilidad limitada para las codificaciones de páginas de códigos. Puede agregar compatibilidad para codificaciones de páginas de códigos disponibles en .NET Framework pero que no se admiten en .NET Core registrando codificaciones de páginas de código con el método [Encoding.RegisterProvider](assetId:///M:System.Text.Encoding.RegisterProvider(System.Text.EncodingProvider)?qualifyHint=True&autoUpgrade=True). Para más información, consulte la documentación sobre la clase [System.Text.CodePagesEncodingProvider](xref:System.Text.CodePagesEncodingProvider).  
  
-   **.NET Native**  
  
     Las aplicaciones de Windows para Windows 10 que tienen como destino .NET Core y están escritas en C# o Visual Basic pueden aprovechar una nueva tecnología que compila las aplicaciones en código nativo en lugar de IL. Generan aplicaciones que se caracterizan por un inicio y tiempos de ejecución más rápidos. Para obtener más información, consulte [Compilar aplicaciones con .NET Native](../Topic/Compiling%20Apps%20with%20.NET%20Native.md). Para obtener información general sobre .NET Native en la que se examina cómo difiere de la compilación JIT y de NGEN, y lo que eso conlleva para el código, vea [.NET Native y compilación](../Topic/.NET%20Native%20and%20Compilation.md).  
  
     Las aplicaciones se compilan en código nativo de forma predeterminada cuando se compilan con Visual Studio 2015. Para obtener más información, vea [Introducción a .NET Native](../Topic/Getting%20Started%20with%20.NET%20Native.md).  
  
     Para admitir la depuración de aplicaciones .NET Native, se agregó una serie de interfaces y enumeraciones nuevas a la API de depuración no administrada. Para obtener más información, consulte el tema [Depuración (Referencia de la API no administrada)](../Topic/Debugging%20\(Unmanaged%20API%20Reference\).md).  
  
-   **Paquetes de .NET Framework de código abierto**  
  
     Los paquetes de .NET Core como las colecciones invariables, [las API de SIMD](http://go.microsoft.com/fwlink/?LinkID=518639) y las API para redes, por ejemplo, las que se encuentran en el espacio de nombres [System.Net.Http](assetId:///N:System.Net.Http?qualifyHint=False&autoUpgrade=True), ahora están disponibles como paquetes de código abierto en [GitHub](https://github.com/). Para acceder al código, vea [NetFx en GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Para obtener más información y saber cómo contribuir a estos paquetes, vea [.NET Core y código abierto](../Topic/.NET%20Core%20and%20Open-Source.md) y la [página principal de .NET en GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).  
  
 [Volver al principio](#introduction)  
  
<a name="v452"></a>   
## <a name="whats-new-in-the-net-framework-452"></a>Novedades de .NET Framework 4.5.2  
  
-   **Nuevas API para aplicaciones de ASP.NET.** Los nuevos métodos [HttpResponse.AddOnSendingHeaders](assetId:///M:System.Web.HttpResponse.AddOnSendingHeaders(System.Action{System.Web.HttpContext})?qualifyHint=True&autoUpgrade=True) y [HttpResponseBase.AddOnSendingHeaders](assetId:///M:System.Web.HttpResponseBase.AddOnSendingHeaders(System.Action{System.Web.HttpContextBase})?qualifyHint=True&autoUpgrade=True) le permiten inspeccionar y modificar los encabezados de respuesta y el código de estado mientras que la respuesta se vacía a la aplicación del cliente. Considere usar estos métodos en lugar de los eventos [PreSendRequestHeaders](assetId:///E:System.Web.HttpApplication.PreSendRequestHeaders?qualifyHint=False&autoUpgrade=True) y [PreSendRequestContent](assetId:///E:System.Web.HttpApplication.PreSendRequestContent?qualifyHint=False&autoUpgrade=True); son más eficaces y confiables.  
  
     El método [HostingEnvironment.QueueBackgroundWorkItem](assetId:///M:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem(System.Action{System.Threading.CancellationToken})?qualifyHint=True&autoUpgrade=True) permite programar pequeños elementos de trabajo en segundo plano. ASP.NET realiza un seguimiento de estos elementos y evita que IIS termine el proceso de trabajo de manera abrupta hasta que se completen todos los elementos de trabajo en segundo plano. Este método no se puede invocar desde fuera del dominio de una aplicación administrada de ASP.NET.  
  
     Las nuevas propiedades [HttpResponse.HeadersWritten](assetId:///P:System.Web.HttpResponse.HeadersWritten?qualifyHint=True&autoUpgrade=False) y [HttpResponseBase.HeadersWritten](assetId:///P:System.Web.HttpResponseBase.HeadersWritten?qualifyHint=True&autoUpgrade=False) devuelven valores booleanos que indican si se escribieron los encabezados de respuesta. Puede usar estas propiedades para comprobar si se realizan correctamente las llamadas a las API como [HttpResponse.StatusCode](assetId:///P:System.Web.HttpResponse.StatusCode?qualifyHint=True&autoUpgrade=True) (que generan excepciones si se han escrito los encabezados).  
  
-   **Cambio de tamaño en controles de Windows Forms** Esta característica se ha ampliado. Ahora se puede usar el valor de PPP del sistema para cambiar el tamaño de componentes de los siguientes controles adicionales (por ejemplo, la flecha desplegable en cuadros combinados):  
  
     [ComboBox](assetId:///T:System.Windows.Forms.ComboBox?qualifyHint=False&autoUpgrade=True)   
     [ToolStripComboBox](assetId:///T:System.Windows.Forms.ToolStripComboBox?qualifyHint=False&autoUpgrade=True)   
     [ToolStripMenuItem](assetId:///T:System.Windows.Forms.ToolStripMenuItem?qualifyHint=False&autoUpgrade=True)   
     [Cursor](assetId:///T:System.Windows.Forms.Cursor?qualifyHint=False&autoUpgrade=True)   
     [DataGridView](assetId:///T:System.Windows.Forms.DataGridView?qualifyHint=False&autoUpgrade=True)   
     [DataGridViewComboBoxColumn](assetId:///T:System.Windows.Forms.DataGridViewComboBoxColumn?qualifyHint=False&autoUpgrade=True)  
  
     Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
-   **Nueva característica de flujo de trabajo.** Un administrador de recursos que usa el método [EnlistPromotableSinglePhase](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification)?qualifyHint=False&autoUpgrade=True) (y, por lo tanto, implementa la interfaz [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True)) puede usar el nuevo método [Transaction.PromoteAndEnlistDurable](assetId:///M:System.Transactions.Transaction.PromoteAndEnlistDurable(System.Guid,System.Transactions.IPromotableSinglePhaseNotification,System.Transactions.ISinglePhaseNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True) para pedir lo siguiente:  
  
    -   Promocionar la transacción a una transacción de MSDTC (Coordinador de transacciones distribuidas de Microsoft).  
  
    -   Reemplace [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True) por un elemento [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True), que es una inscripción duradera que admite confirmaciones de una sola fase.  
  
     Esto puede realizarse en el mismo dominio de la aplicación y no requiere que ningún código sin administrar adicional interactúe con MSDTC para realizar la promoción. Solo puede llamarse al nuevo método cuando haya una llamada pendiente de [System.Transactions](assetId:///N:System.Transactions?qualifyHint=True&autoUpgrade=True) al método [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True)`Promote` implementado por la inscripción duradera.  
  
-   **Mejoras de generación de perfiles.** Las siguientes API de generación de perfiles no administradas proporcionan una generación de perfiles más sólida:  
  
     [Estructura COR_PRF_ASSEMBLY_REFERENCE_INFO](../Topic/COR_PRF_ASSEMBLY_REFERENCE_INFO%20Structure.md)   
     [Enumeración COR_PRF_HIGH_MONITOR](../Topic/COR_PRF_HIGH_MONITOR%20Enumeration.md)   
     [Método GetAssemblyReferences](../Topic/ICorProfilerCallback6::GetAssemblyReferences%20Method.md)   
     [Método GetEventMask2](../Topic/ICorProfilerInfo5::GetEventMask2%20Method.md)   
     [Método SetEventMask2](../Topic/ICorProfilerInfo5::SetEventMask2%20Method.md)   
     [Método AddAssemblyReference](../Topic/ICorProfilerAssemblyReferenceProvider::AddAssemblyReference%20Method.md)  
  
     Las implementaciones de `ICorProfiler` anteriores eran compatibles con la carga diferida de ensamblados dependientes. Las nuevas API de generación de perfiles requieren que los ensamblados dependientes insertados por el generador de perfiles se carguen inmediatamente, en lugar de cargarse cuando la aplicación se haya inicializado por completo. Este cambio no afecta a los usuarios de las API de `ICorProfiler` existentes.  
  
-   **Mejoras en la depuración.** Las API de depuración no administradas proporcionan una mejor integración con un generador de perfiles. Ahora se puede acceder a metadatos insertados por el generador de perfiles, así como a variables locales y código producidos por solicitudes de ReJIT del compilador en la depuración de volcados.  
  
     [Método SetWriteableMetadataUpdateMode](../Topic/ICorDebugProcess7::SetWriteableMetadataUpdateMode%20Method.md)   
     [Método EnumerateLocalVariablesEx](../Topic/ICorDebugILFrame4::EnumerateLocalVariablesEx%20Method.md)   
     [Método GetLocalVariableEx](../Topic/ICorDebugILFrame4::GetLocalVariableEx%20Method.md)   
     [Método GetCodeEx](../Topic/ICorDebugILFrame4::GetCodeEx%20Method.md)   
     [Método GetActiveReJitRequestILCode](../Topic/ICorDebugFunction3::GetActiveReJitRequestILCode%20Method.md)   
     [Método GetInstrumentedILMap](../Topic/ICorDebugILCode2::GetInstrumentedILMap%20Method.md)  
  
-   **Cambios en el seguimiento de eventos.** .NET Framework 4.5.2 permite realizar el seguimiento de actividades fuera del proceso, basado en Seguimiento de eventos para Windows (ETW), para una mayor área expuesta. Esto permite a los proveedores de Administración avanzada de energía (APM) proporcionar herramientas sencillas que realicen un seguimiento preciso de solicitudes y actividades individuales en distintos subprocesos.  Estos eventos solo se desencadenan cuando son habilitados por los controladores de ETW; por lo tanto, los cambios no afectan a código de ETW escrito anteriormente o a código que se ejecute cuando ETW esté deshabilitado.  
  
-   **Promover una transacción y convertirla en una inscripción duradera**  
  
     [Transaction.PromoteAndEnlistDurable](assetId:///M:System.Transactions.Transaction.PromoteAndEnlistDurable(System.Guid,System.Transactions.IPromotableSinglePhaseNotification,System.Transactions.ISinglePhaseNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True) es una API nueva que se ha agregado a .NET Framework 4.5.2 y 4.6:  
  
    ```  
  
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,  
                                              IPromotableSinglePhaseNotification promotableNotification,  
                                              ISinglePhaseNotification enlistmentNotification,  
                                              EnlistmentOptions enlistmentOptions)  
  
    ```  
  
     El método se puede usar con una inscripción creada previamente por [Transaction.EnlistPromotableSinglePhase](assetId:///M:System.Transactions.Transaction.EnlistPromotableSinglePhase(System.Transactions.IPromotableSinglePhaseNotification)?qualifyHint=True&autoUpgrade=True) en respuesta al método [ITransactionPromoter.Promote](assetId:///M:System.Transactions.ITransactionPromoter.Promote?qualifyHint=True&autoUpgrade=True). Pide a `System.Transactions` que promueva la transacción a una transacción MSDTC y que "convierta" la inscripción que se puede promover en una inscripción duradera. Una vez que el método finalice correctamente, `System.Transactions` dejará de hacer referencia a la interfaz [IPromotableSinglePhaseNotification](assetId:///T:System.Transactions.IPromotableSinglePhaseNotification?qualifyHint=False&autoUpgrade=True) y cualquier futura notificación llegará a través de la interfaz [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True) provista. La inscripción en cuestión debe actuar como inscripción duradera y admitir el registro y la recuperación de transacciones. Consulte [Transaction.EnlistDurable](assetId:///M:System.Transactions.Transaction.EnlistDurable(System.Guid,System.Transactions.IEnlistmentNotification,System.Transactions.EnlistmentOptions)?qualifyHint=True&autoUpgrade=True) para obtener detalles. Además, la inscripción debe admitir [ISinglePhaseNotification](assetId:///T:System.Transactions.ISinglePhaseNotification?qualifyHint=False&autoUpgrade=True).  *Solo* se puede llamar a este método al procesar una llamada [ITransactionPromoter.Promote](assetId:///M:System.Transactions.ITransactionPromoter.Promote?qualifyHint=True&autoUpgrade=True). Si no es el caso, se inicia una excepción [TransactionException](assetId:///T:System.Transactions.TransactionException?qualifyHint=False&autoUpgrade=True).  
  
 [Volver al principio](#introduction)  
  
<a name="v451"></a>   
## <a name="whats-new-in-the-net-framework-451"></a>Novedades de .NET Framework 4.5.1  
 **Actualizaciones de abril de 2014**:  
  
-   [Visual Studio 2013 Update 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) incluye actualizaciones para las plantillas de la Biblioteca de clases portable para garantizar la compatibilidad en los escenarios siguientes:  
  
    -   Puede usar las API de Windows en tiempo de ejecución en bibliotecas portables cuyo destino sea Windows 8.1, Windows Phone 8.1 y Windows Phone Silverlight 8.1.  
  
    -   Puede incluir XAML (tipos de Windows.UI.XAML) en las bibliotecas portables cuyo destino es Windows 8.1 o Windows Phone 8.1. Se admiten las siguientes plantillas de XAML: página en blanco, diccionario de recursos, control basado en modelo y control de usuario.  
  
    -   Se puede crear un componente de Windows en tiempo de ejecución portable (archivo .winmd) para usarlo en aplicaciones de la Tienda que tengan como destino Windows 8.1 y Windows Phone 8.1.  
  
    -   Puede cambiar el destino de una biblioteca de clases de la Tienda Windows o la Tienda de Windows Phone como biblioteca de clases portable.  
  
     Para obtener más información sobre estos cambios, vea [Biblioteca de clases portable](../Topic/Cross-Platform%20Development%20with%20the%20Portable%20Class%20Library.md).  
  
-   El conjunto de contenido de .NET Framework ahora incluye documentación para .NET Native, que es una tecnología de precompilación para crear e implementar aplicaciones de Windows. .NET Native compila aplicaciones directamente en código nativo, en lugar de hacerlo en un lenguaje intermedio (IL), lo que mejora el rendimiento. Para obtener información detallada, vea [Compilar aplicaciones con .NET Native](../Topic/Compiling%20Apps%20with%20.NET%20Native.md).  
  
-   [.NET Framework Reference Source](http://referencesource.microsoft.com/) proporciona una nueva experiencia de navegación y mejores funciones. Ahora puede navegar en línea por el código fuente de .NET Framework, [descargar la referencia](http://referencesource.microsoft.com/download.html) para visualizarlo sin conexión y examinar los orígenes (incluidas revisiones y actualizaciones) durante la depuración. Para obtener más información, vea la entrada de blog [A new look for .NET Reference Source](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx) (Un nuevo aspecto para el origen de referencia de .NET).  
  
 Estas son las principales características nuevas y mejoras realizadas en .NET Framework 4.5.1:  
  
-   Redirección automática de enlace de ensamblados. A partir de Visual Studio 2013, cuando se compila una aplicación cuyo destino es .NET Framework 4.5.1, se pueden agregar al archivo de configuración de la aplicación redirecciones de enlace si la aplicación o sus componentes hacen referencia a varias versiones del mismo ensamblado. Esta característica también se puede habilitar en proyectos que tienen como destino versiones anteriores de .NET Framework. Para obtener más información, vea [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../Topic/How%20to:%20Enable%20and%20Disable%20Automatic%20Binding%20Redirection.md).  
  
-   Capacidad de recopilar información de diagnóstico para ayudar a los desarrolladores a mejorar el rendimiento de las aplicaciones de servidor y en la nube. Para más información, consulte los métodos [WriteEventWithRelatedActivityId](assetId:///M:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId(System.Int32,System.Guid,System.Object[])?qualifyHint=False&autoUpgrade=True) y [WriteEventWithRelatedActivityIdCore](assetId:///M:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore(System.Int32,System.Guid*,System.Int32,System.Diagnostics.Tracing.EventSource.EventData*)?qualifyHint=False&autoUpgrade=True) en la clase [EventSource](assetId:///T:System.Diagnostics.Tracing.EventSource?qualifyHint=False&autoUpgrade=True).  
  
-   Capacidad de compactar explícitamente el montón de objetos grandes (LOH) durante la recolección de elementos no utilizados. Para más información, consulte la propiedad [GCSettings.LargeObjectHeapCompactionMode](assetId:///P:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?qualifyHint=True&autoUpgrade=True).  
  
-   Mejoras adicionales de rendimiento como, por ejemplo, la suspensión de la aplicación ASP.NET, mejoras de JIT con varios núcleos o reducción del tiempo de inicio de la aplicación tras una actualización de .NET Framework. Para obtener información detallada, vea las entradas de blog relativas al [anuncio de .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx) y la [suspensión de aplicaciones ASP.NET](http://blogs.msdn.com/b/dotnet/archive/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting.aspx).  
  
 Las mejoras en Windows Forms son las siguientes:  
  
-   Cambio de tamaño en controles de Windows Forms. Puede usar el valor de PPP del sistema para cambiar el tamaño de los componentes de controles (por ejemplo, los iconos que aparecen en una cuadrícula de propiedades); para ello, active esta opción con una entrada en el archivo de configuración de la aplicación (app.config). Actualmente, esta característica es compatible con los siguientes controles de Windows Forms:  
  
     [PropertyGrid](assetId:///T:System.Windows.Forms.PropertyGrid?qualifyHint=False&autoUpgrade=True)   
     [TreeView](assetId:///T:System.Windows.Forms.TreeView?qualifyHint=False&autoUpgrade=True)   
     Algunos aspectos de [DataGridView](assetId:///T:System.Windows.Forms.DataGridView?qualifyHint=False&autoUpgrade=True) (consulte las [características nuevas de 4.5.2](#v452) para conocer los controles compatibles adicionales)  
  
     Para activar esta característica, agregue un nuevo elemento \<appSettings> al archivo de configuración (app.config) y establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
 Algunas de las mejoras realizadas durante la depuración de las aplicaciones de .NET Framework en Visual Studio 2013 son:  
  
-   Valores devueltos en el depurador de Visual Studio. Al depurar una aplicación administrada en Visual Studio 2013, en la ventana Automático se muestran los valores y tipos devueltos de los métodos. Esta información está disponible para el escritorio, la Tienda Windows y las aplicaciones Windows Phone. Para obtener más información, vea [Examinar los valores devueltos de llamadas a métodos](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) en MSDN Library.  
  
-   Editar y continuar en aplicaciones de 64 bits. Visual Studio 2013 admite la característica Editar y continuar en aplicaciones administradas de 64 bits para el escritorio, la Tienda Windows y Windows Phone. Las limitaciones existentes siguen en vigor para las aplicaciones de 32 bits y 64 bits (vea la última sección del artículo [Cambios admitidos en el código (C#)](http://msdn.microsoft.com/library/ms164927\(v=vs.120\).aspx)).  
  
-   Depuración asincrónica. Para facilitar la depuración de aplicaciones asincrónicas en Visual Studio 2013, la pila de llamadas oculta el código de infraestructura proporcionado por los compiladores para permitir la programación asincrónica y, además, encadena los principales marcos lógicos para que pueda seguir la ejecución lógica del programa con mayor claridad. La ventana Tareas reemplaza a la ventana Tareas paralelas, donde se muestran las tareas relacionadas con un punto de interrupción determinado, así como las demás tareas que actualmente están activas o programadas en la aplicación. Puede obtener más información sobre esta característica en la sección "Async-aware debugging" (Depuración asincrónica) de la publicación sobre [el anuncio de .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
-   Mayor compatibilidad con las excepciones de los componentes de Windows en tiempo de ejecución. En Windows 8.1, las excepciones que se inician en aplicaciones de la Tienda Windows conservan información sobre el error que provocó la excepción, incluso entre diferentes lenguajes. Puede obtener más información sobre esta característica en la sección "Windows Store app development" (Desarrollo de aplicaciones de la Tienda Windows) de la publicación del [anuncio de .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
 A partir de Visual Studio 2013, puede usar la [herramienta de optimización guiada por perfiles administrados (Mpgo.exe)](../Topic/Mpgo.exe%20\(Managed%20Profile%20Guided%20Optimization%20Tool\).md) para optimizar las aplicaciones de Tienda Windows 8.x, así como las aplicaciones de escritorio.  
  
 Para conocer las nuevas características de ASP.NET 4.5.1, vea [ASP.NET 4.5.1 y Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) en el sitio de ASP.NET.  
  
 [Volver al principio](#introduction)  
  
<a name="core"></a>   
## <a name="whats-new-in-the-net-framework-45"></a>Novedades de .NET Framework 4.5  
  
### <a name="core-new-features-and-improvements"></a>Principales características nuevas y mejoras  
  
-   Capacidad para reducir los reinicios del sistema mediante la detección y cierre de las aplicaciones de .NET Framework 4 durante la implementación. Vea [Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5](../Topic/Reducing%20System%20Restarts%20During%20.NET%20Framework%204.5%20Installations.md).  
  
-   Compatibilidad con matrices mayores de 2 gigabytes (GB) en plataformas de 64 bits. Esta característica se puede habilitar en el archivo de configuración de la aplicación. Consulte el elemento [\<gcAllowVeryLargeObjects>](../Topic/%3CgcAllowVeryLargeObjects%3E%20Element.md), donde también se indican otras restricciones de tamaño de objeto y de tamaño de matriz.  
  
-   Mayor rendimiento a través de la recolección de elementos no utilizados en segundo plano en el caso de los servidores. Cuando se usa la recolección de elementos no utilizados de los servidores en .NET Framework 4.5, se habilita automáticamente la recolección de elementos no utilizados en segundo plano. Vea la sección sobre la recolección de elementos no utilizados en segundo plano de los servidores del tema [Fundamentals of Garbage Collection](../Topic/Fundamentals%20of%20Garbage%20Collection.md) (Fundamentos de la recolección de elementos no utilizados).  
  
-   Compilación Just-in-time (JIT) en segundo plano, que se encuentra disponible opcionalmente en los procesadores de varios núcleos para mejorar el rendimiento de la aplicación. Consulte [ProfileOptimization](assetId:///T:System.Runtime.ProfileOptimization?qualifyHint=False&autoUpgrade=True).  
  
-   Capacidad para limitar el tiempo durante el cual el motor de expresiones regulares intentará resolver una expresión regular antes de agotar el tiempo de espera. Consulte la propiedad [Regex.MatchTimeout](assetId:///P:System.Text.RegularExpressions.Regex.MatchTimeout?qualifyHint=True&autoUpgrade=True).  
  
-   Capacidad para definir la referencia cultural predeterminada de un dominio de aplicación. Consulte la clase [CultureInfo](assetId:///T:System.Globalization.CultureInfo?qualifyHint=False&autoUpgrade=True).  
  
-   Compatibilidad de la consola con la codificación Unicode (UTF-16). Consulte la clase [Console](assetId:///T:System.Console?qualifyHint=False&autoUpgrade=True).  
  
-   Compatibilidad con el control de versiones de ordenación cultural de cadenas y datos de comparación. Consulte la clase [SortVersion](assetId:///T:System.Globalization.SortVersion?qualifyHint=False&autoUpgrade=True).  
  
-   Mayor rendimiento al recuperar recursos. Vea [Empaquetar e implementar recursos](../Topic/Packaging%20and%20Deploying%20Resources%20in%20Desktop%20Apps.md).  
  
-   Mejoras en la compresión Zip para reducir el tamaño de un archivo comprimido. Consulte el espacio de nombres [System.IO.Compression](assetId:///N:System.IO.Compression?qualifyHint=True&autoUpgrade=True).  
  
-   Capacidad de personalizar un contexto de reflexión para invalidar el comportamiento predeterminado de reflexión a través de la clase [CustomReflectionContext](assetId:///T:System.Reflection.Context.CustomReflectionContext?qualifyHint=False&autoUpgrade=True).  
  
-   Compatibilidad con la versión 2008 del estándar de internacionalización de nombres de dominio de las aplicaciones (IDNA) cuando se usa la clase [System.Globalization.IdnMapping](assetId:///T:System.Globalization.IdnMapping?qualifyHint=True&autoUpgrade=True) en Windows 8.  
  
-   Delegación de comparación de cadenas en el sistema operativo, que implementa Unicode 6.0, cuando se usa .NET Framework en Windows 8. Al ejecutarse en otras plataformas, .NET Framework incluye sus propios datos de comparación de cadenas, que implementan Unicode 5.x. Consulte la clase [String](assetId:///T:System.String?qualifyHint=False&autoUpgrade=True) y la sección Comentarios de la clase [SortVersion](assetId:///T:System.Globalization.SortVersion?qualifyHint=False&autoUpgrade=True).  
  
-   Capacidad para calcular los códigos hash de cadenas en cada dominio de aplicación. Vea el elemento [\<UseRandomizedStringHashAlgorithm>](../Topic/%3CUseRandomizedStringHashAlgorithm%3E%20Element.md).  
  
-   Compatibilidad con la reflexión de tipos dividida entre las clases [Type](assetId:///T:System.Type?qualifyHint=False&autoUpgrade=True) y [TypeInfo](assetId:///T:System.Reflection.TypeInfo?qualifyHint=False&autoUpgrade=True). Vea [Reflection in the .NET Framework for Windows Store Apps](../Topic/Reflection%20in%20the%20.NET%20Framework%20for%20Windows%20Store%20Apps.md) (Reflexión en .NET Framework para aplicaciones de la Tienda Windows).  
  
### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)  
 En .NET Framework 4.5, Managed Extensibility Framework (MEF) cuenta con las siguientes características nuevas:  
  
-   Compatibilidad con los tipos genéricos.  
  
-   Modelo de programación basado en convenciones que permite crear elementos basándose en convenciones de nomenclatura en lugar de en atributos.  
  
-   Ámbitos múltiples.  
  
-   Un subconjunto de MEF que puede usar cuando cree aplicaciones de la Tienda Windows 8.x. Este subconjunto está disponible como un [paquete descargable](http://go.microsoft.com/fwlink/?LinkId=256238) en la galería de NuGet. Para instalar el paquete, abra el proyecto en Visual Studio, elija **Administrar paquetes de NuGet** en el menú **Proyecto** y busque en línea el paquete `Microsoft.Composition`.  
  
 Para obtener más información, vea [Managed Extensibility Framework (MEF)](../Topic/Managed%20Extensibility%20Framework%20\(MEF\).md).  
  
### <a name="asynchronous-file-operations"></a>Operaciones de archivo asincrónicas  
 En .NET Framework 4.5, se agregaron nuevas características asincrónicas a los lenguajes C# y Visual Basic. Estas características agregan un modelo basado en tareas para realizar operaciones asincrónicas. Para utilizar este nuevo modelo, use los métodos asincrónicos de las clases de E/S. Vea [E/S de archivos asincrónica](../Topic/Asynchronous%20File%20I-O.md).  
  
<a name="tools"></a>   
### <a name="tools"></a>Herramientas  
 En .NET Framework 4.5, el generador de archivos de recursos (Resgen.exe) permite crear un archivo .resw para su uso en aplicaciones de la Tienda Windows 8.x desde un archivo .resources incrustado en un ensamblado de .NET Framework. Para obtener más información, vea [Resgen.exe (Resource File Generator)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) (Resgen.exe [generador de archivos de recursos]).  
  
 La optimización guiada por perfiles administrados (Mpgo.exe) permite mejorar el tiempo de inicio de la aplicación, la utilización de la memoria (el tamaño del espacio de trabajo) y el rendimiento mediante la optimización de los ensamblados de imagen nativos. La herramienta de línea de comandos genera datos de perfil para los ensamblados nativos de aplicación de la imagen. Vean [Mpgo.exe (Managed Profile Guided Optimization Tool)](../Topic/Mpgo.exe%20\(Managed%20Profile%20Guided%20Optimization%20Tool\).md) (Mpgo.exe [herramienta de optimización guiada por perfiles administrados]). A partir de Visual Studio 2013, puede usar la Mpgo.exe para optimizar las aplicaciones de Tienda Windows 8.x, así como las aplicaciones de escritorio.  
  
<a name="parallel"></a>   
### <a name="parallel-computing"></a>Informática en paralelo  
 .NET Framework 4.5 cuenta con varias características y mejoras nuevas para el procesamiento informático en paralelo. Entre estas se incluyen un rendimiento mejorado, mayor control, mejor compatibilidad con la programación asincrónica, una nueva biblioteca de flujo de datos y mejor compatibilidad para la depuración y el análisis de rendimiento en paralelo. Vea la entrada [What’s New for Parallelism in .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) (Novedades de paralelismo en .NET 4.5) de la sección sobre Programación en paralelo del blog sobre .NET.  
  
<a name="web"></a>   
### <a name="web"></a>Web  
 ASP.NET 4.5 y 4.5.1 incorporan el enlace de modelos de formularios Web Forms, compatibilidad con WebSocket, controladores asincrónicos, mejoras de rendimiento y muchas otras características. Para obtener más información, vea los siguientes recursos:  
  
-   [ASP.NET 4.5 y Visual Studio 2012](../Topic/ASP.NET%20Core%20and%20Visual%20Studio%202015.md) en MSDN Library.  
  
-   [ASP.NET 4.5.1 y Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) en el sitio de ASP.NET.  
  
<a name="networking"></a>   
### <a name="networking"></a>Redes  
 .NET Framework 4.5 proporciona una nueva interfaz de programación para aplicaciones HTTP. Para más información, consulte los nuevos espacios de nombres [System.Net.Http](assetId:///N:System.Net.Http?qualifyHint=True&autoUpgrade=True) y [System.Net.Http.Headers](assetId:///N:System.Net.Http.Headers?qualifyHint=True&autoUpgrade=True).  
  
 También se incluye compatibilidad con una nueva interfaz de programación para aceptar e interactuar con una conexión WebSocket mediante el objeto [HttpListener](assetId:///T:System.Net.HttpListener?qualifyHint=False&autoUpgrade=True) existente y las clases relacionadas. Para más información, consulte el nuevo espacio de nombres [System.Net.WebSockets](assetId:///N:System.Net.WebSockets?qualifyHint=False&autoUpgrade=True) y la clase [HttpListener](assetId:///T:System.Net.HttpListener?qualifyHint=False&autoUpgrade=True).  
  
 Además, .NET Framework 4.5 incluye las siguientes mejoras de red:  
  
-   Compatibilidad de URI conforme a RFC. Para más información, consulte [URI](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True) y las clases relacionadas.  
  
-   Compatibilidad con el análisis de nombres de dominio internacionalizados (IDN). Para más información, consulte [URI](assetId:///T:System.Uri?qualifyHint=False&autoUpgrade=True) y las clases relacionadas.  
  
-   Compatibilidad con la internacionalización de direcciones de correo electrónico (EAI). Para más información, consulte el espacio de nombres [System.Net.Mail](assetId:///N:System.Net.Mail?qualifyHint=False&autoUpgrade=True).  
  
-   Compatibilidad mejorada de IPv6. Para más información, consulte el espacio de nombres [System.Net.NetworkInformation](assetId:///N:System.Net.NetworkInformation?qualifyHint=False&autoUpgrade=True).  
  
-   Compatibilidad con el socket de modo dual. Para más información, consulte las clases [Socket](assetId:///T:System.Net.Sockets.Socket?qualifyHint=False&autoUpgrade=True) y [TcpListener](assetId:///T:System.Net.Sockets.TcpListener?qualifyHint=False&autoUpgrade=True).  
  
<a name="client"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 En .NET Framework 4.5, Windows Presentation Foundation (WPF) contiene cambios y mejoras en las áreas siguientes:  
  
-   El nuevo control [Barra de herramientas](assetId:///T:System.Windows.Controls.Ribbon.Ribbon?qualifyHint=False&autoUpgrade=True), que permite implementar una interfaz de usuario en forma de cinta que incluye una barra de herramientas de acceso rápido, un menú de aplicación y pestañas.  
  
-   La nueva interfaz [INotifyDataErrorInfo](assetId:///T:System.ComponentModel.INotifyDataErrorInfo?qualifyHint=False&autoUpgrade=True), que admite la validación de datos sincrónica y asincrónica.  
  
-   Nuevas características para las clases [VirtualizingPanel](assetId:///T:System.Windows.Controls.VirtualizingPanel?qualifyHint=False&autoUpgrade=True) y [Dispatcher](assetId:///T:System.Windows.Threading.Dispatcher?qualifyHint=False&autoUpgrade=True).  
  
-   Rendimiento mejorado al mostrar conjuntos grandes de datos agrupados y al acceder a colecciones en subprocesos que no son de interfaz de usuario.  
  
-   Enlace de datos a propiedades estáticas, enlace de datos a tipos personalizados que implementan la interfaz [ICustomTypeProvider](assetId:///T:System.Reflection.ICustomTypeProvider?qualifyHint=False&autoUpgrade=True) y recuperación de información de enlace de datos desde una expresión de enlace.  
  
-   Reposición de los datos a medida que cambian los valores (modelado dinámico).  
  
-   Capacidad de comprobar si el contexto de datos de un contenedor de elementos está desconectado.  
  
-   Capacidad de establecer la cantidad de tiempo que debe transcurrir entre los cambios de propiedad y las actualizaciones del origen de datos.  
  
-   Compatibilidad mejorada para implementar patrones de eventos débiles. Además, los eventos ahora pueden aceptar extensiones de marcado.  
  
<a name="windows_communication_foundation"></a>   
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
 En .NET Framework 4.5, se han agregado las características siguientes para facilitar la creación y el mantenimiento de aplicaciones de Windows Communication Foundation (WCF):  
  
-   Simplificación de los archivos de configuración generados.  
  
-   Compatibilidad con el desarrollo del contrato en primer lugar.  
  
-   Capacidad de configurar el modo de compatibilidad de ASP.NET más fácilmente.  
  
-   Cambios en los valores de propiedad de transporte predeterminados para reducir las probabilidades de tener que establecerlos.  
  
-   Actualizaciones de la clase [XmlDictionaryReaderQuotas](assetId:///T:System.Xml.XmlDictionaryReaderQuotas?qualifyHint=False&autoUpgrade=True) para reducir la probabilidad de tener que configurar manualmente cuotas para los lectores de diccionarios XML.  
  
-   Validación de los archivos de configuración de WCF por parte de Visual Studio dentro del proceso de compilación, para que se puedan detectar errores de configuración antes de ejecutar la aplicación.  
  
-   Nueva compatibilidad con streaming asincrónico.  
  
-   Nueva asignación del protocolo HTTPS para facilitar la exposición de un extremo a través de HTTPS con Internet Information Services (IIS).  
  
-   Capacidad de generar metadatos en un solo documento WSDL anexando `?singleWSDL` a la dirección URL del servicio.  
  
-   Compatibilidad con Websockets para permitir una comunicación bidireccional verdadera a través de los puertos 80 y 443 con características de rendimiento similares a las del transporte TCP.  
  
-   Compatibilidad para configurar servicios en el código.  
  
-   Información sobre herramientas del editor XML.  
  
-   Compatibilidad con almacenamiento en caché de [ChannelFactory](assetId:///T:System.ServiceModel.ChannelFactory?qualifyHint=False&autoUpgrade=True).  
  
-   Compatibilidad con la compresión de codificadores binarios.  
  
-   Compatibilidad con un transporte UDP que permite a los desarrolladores escribir servicios que utilizan mensajería de tipo "desencadenar y omitir”. Un cliente envía un mensaje a un servicio y no espera ninguna respuesta de él.  
  
-   Capacidad de admitir varios modos de autenticación en un único extremo de WCF mediante el uso de transporte HTTP y seguridad de transporte.  
  
-   Compatibilidad con los servicios WCF que utilizan nombres de dominio internacionalizados (IDN).  
  
 Para obtener más información, vea [Novedades de Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).  
  
<a name="windows_workflow_foundation"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 Se agregaron varias características nuevas a Windows Workflow Foundation (WF) en .NET Framework 4.5, incluidas las siguientes:  
  
-   Flujos de trabajo de máquina de estados, que se incluyeron primero como parte de .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](http://go.microsoft.com/fwlink/?LinkID=215092)). Esta actualización incluía varias clases y actividades nuevas que permitían a los desarrolladores crear flujos de trabajo de máquina de estados. Estas clases y actividades se actualizaron para .NET Framework 4.5 con el objeto de incluir:  
  
    -   Capacidad de establecer puntos de interrupción en estados  
  
    -   Capacidad de copiar y pegar transiciones en el Diseñador de flujo de trabajo  
  
    -   Compatibilidad del diseñador para la creación de transiciones de desencadenador compartidas  
  
    -   Actividades para crear flujos de trabajo de máquina de estados, incluidas: [StateMachine](assetId:///T:System.Activities.Statements.StateMachine?qualifyHint=False&autoUpgrade=True), [State](assetId:///T:System.Activities.Statements.State?qualifyHint=False&autoUpgrade=True) y [Transition](assetId:///T:System.Activities.Statements.Transition?qualifyHint=False&autoUpgrade=True).  
  
-   Características mejoradas del Diseñador de flujo de trabajo, como las siguientes:  
  
    -   Funcionalidades de búsqueda de flujo de trabajo mejoradas en Visual Studio, incluidas **Búsqueda rápida** y **Buscar en archivos**.  
  
    -   Capacidad de crear automáticamente una actividad Secuencia cuando una segunda actividad secundaria se agrega a una actividad del contenedor y para incluir ambas actividades en la actividad Secuencia.  
  
    -   Compatibilidad con el movimiento panorámico, que permite cambiar la parte visible de un flujo de trabajo sin usar las barras de desplazamiento.  
  
    -   Una nueva vista **Esquema del documento**, en la que se muestran los componentes de un flujo de trabajo en una vista de esquema con forma de árbol y que le permite seleccionar un componente en la vista **Esquema del documento**.  
  
    -   Capacidad de agregar anotaciones a las actividades.  
  
    -   Capacidad de definir y consumir delegados de actividad mediante el Diseñador de flujo de trabajo.  
  
    -   Conexión e inserción automáticas para actividades y transiciones en los flujos de trabajo de máquina de estados y diagrama de flujo.  
  
-   Almacenamiento de la información de estado de vista de un flujo de trabajo en un único elemento del archivo XAML, para poder encontrar y editar fácilmente la información de estado de vista.  
  
-   Una actividad de contenedor NoPersistScope para evitar que se conserven las actividades secundarias.  
  
-   Compatibilidad con expresiones de C#:  
  
    -   Los proyectos de flujo de trabajo que usan Visual Basic utilizarán las expresiones de Visual Basic, y los proyectos de flujo de trabajo de C# utilizarán las expresiones de C#.  
  
    -   Los proyectos de flujo de trabajo de C# creados en Visual Studio 2010 y que tengan expresiones de Visual Basic son compatibles con los proyectos de flujo de trabajo de C# que usan expresiones de C#.  
  
-   Mejoras del control de versiones:  
  
    -   La nueva clase [WorkflowIdentity](assetId:///T:System.Activities.WorkflowIdentity?qualifyHint=False&autoUpgrade=True), que proporciona una asignación entre una instancia de flujo de trabajo guardada y su definición de flujo de trabajo.  
  
    -   Ejecución en paralelo de varias versiones de flujo de trabajo en el mismo host, incluido [WorkflowServiceHost](assetId:///T:System.ServiceModel.Activities.WorkflowServiceHost?qualifyHint=False&autoUpgrade=True).  
  
    -   En la actualización dinámica, la capacidad de modificar la definición de una instancia de flujo de trabajo guardada.  
  
-   Desarrollo de servicios de flujo de trabajo de contrato en primer lugar, que proporciona compatibilidad para generar automáticamente actividades que busquen coincidencias en un contrato de servicio existente.  
  
 Para obtener más información, vea [Novedades de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).  
  
<a name="tailored"></a>   
### <a name="net-for-windows-8x-store-apps"></a>.NET para aplicaciones de la Tienda Windows 8.x  
 Las aplicaciones de la Tienda Windows 8.x están diseñadas para factores de forma específicos y aprovechan la eficacia del sistema operativo Windows. Un subconjunto de .NET Framework 4.5 o 4.5.1 está disponible para compilar aplicaciones de la Tienda Windows 8.x para Windows mediante C# o Visual Basic. Este subconjunto se denomina .NET para aplicaciones de la Tienda Windows 8.x y se explica en una [introducción](http://go.microsoft.com/fwlink/?LinkId=228491) del Centro de desarrollo de Windows.  
  
<a name="portable"></a>   
### <a name="portable-class-libraries"></a>Bibliotecas de clases portables  
 El proyecto de Biblioteca de clases portable de Visual Studio 2012 (y versiones posteriores) permite escribir y compilar ensamblados administrados capaces de funcionar en múltiples plataformas de .NET Framework. Un proyecto de Biblioteca de clases portable le permite elegir las plataformas de destino (como Windows Phone y .NET para aplicaciones de la Tienda Windows 8.x). Los tipos y miembros disponibles en el proyecto se restringen automáticamente a los tipos y miembros comunes de estas plataformas. Para obtener más información, consulte [Biblioteca de clases portable](../Topic/Cross-Platform%20Development%20with%20the%20Portable%20Class%20Library.md).  
  
## <a name="see-also"></a>Vea también  
 [.NET Framework y versiones fuera de banda](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Novedades de Visual Studio 2013](http://msdn.microsoft.com/library/bb386063\(v=vs.120\).aspx)   
 [ASP.NET 4.5.1 y herramientas web para Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)   
 [ASP.NET y Visual Studio para Web](../Topic/ASP.NET%20and%20Visual%20Studio%20for%20Web.md)   
 [Novedades de Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173)   
 [Novedades de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176)   
 [What's New in Visual C++](http://msdn.microsoft.com/library/hh409293\(v=vs.120\).aspx) (Novedades de Visual C++)

