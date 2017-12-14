---
title: "Novedades de .NET Framework"
ms.custom: updateeachrelease
ms.date: 05/02/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53205ca9fd304d1dd1c76c5d6952d78634c5b231
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
---
# <a name="whats-new-in-the-net-framework"></a>Novedades de .NET Framework
<a name="introduction"></a> En este artículo se resumen las nuevas características y mejoras en las siguientes versiones de .NET Framework:  
 
[.NET Framework 4.7.1](#v471)    
[.NET Framework 4.7](#v47)   
[.NET Framework 4.6.2](#v462)   
[.NET Framework 4.6.1](#v461)   
[.NET 2015 y .NET Framework 4.6](#v46)   
[.NET Framework 4.5.2](#v452)   
[.NET Framework 4.5.1](#v451)   
[.NET Framework 4.5](#core)   

Este artículo no proporciona información completa sobre cada una de las características nuevas y puede estar sujeto a cambios. Para obtener información general sobre .NET Framework, vea [Introducción](../../../docs/framework/get-started/index.md). Para conocer las plataformas compatibles, vea [Requisitos de sistema](~/docs/framework/get-started/system-requirements.md). Para obtener vínculos de descarga e instrucciones de instalación, vea [Instalar](../../../docs/framework/install/guide-for-developers.md).

> [!NOTE]
> El equipo de .NET Framework también publica características fuera de banda con NuGet para expandir la compatibilidad con la plataforma e introducir nuevas funciones (como colecciones invariables y tipos de vector habilitados para SIMD). Para obtener más información, vea [Las API y las bibliotecas de clases adicionales](../additional-apis/index.md) y [.NET Framework y versiones fuera de banda](~/docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). Vea una [lista completa de paquetes NuGet](https://blogs.msdn.microsoft.com/dotnet/p/nugetpackages/) para .NET Framework o suscríbase a [nuestra fuente](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).

<a name="v471"></a> 
## <a name="introducing-the-net-framework-471"></a>Introducción a .NET Framework 4.7.1

.NET Framework 4.7.1 se basa en la versión 4.6, 4.6.1, 4.6.2 y 4.7 de .NET Framework e incorpora muchas correcciones y varias características nuevas, sin dejar de ser un producto muy estable.

### <a name="downloading-and-installing-the-net-framework-471"></a>Descarga e instalación de .NET Framework 4.7.1
 
Puede descargar .NET Framework 4.7.1 de las siguientes ubicaciones:

- [Instalador web de .NET Framework 4.7.1](http://go.microsoft.com/fwlink/?LinkId=852095)

- [Instalador sin conexión de .NET Framework 4.7.1](http://go.microsoft.com/fwlink/?LinkId=852107)

.NET Framework 4.7.1 puede instalarse en Windows 10, Windows 8.1, Windows 7 SP1 y las plataformas de servidor correspondientes a partir de Windows Server 2008 R2 SP1. Puede instalar .NET Framework 4.7.1 mediante el instalador web o el instalador sin conexión. La manera recomendada para la mayoría de los usuarios es usar el programa de instalación web.

Puede usar como destino .NET Framework 4.7.1 en Visual Studio 2012 o posterior mediante la instalación del [Paquete de desarrollador de .NET Framework 4.7.1](http://go.microsoft.com/fwlink/?LinkId=852105). 

### <a name="whats-new-in-the-net-framework-471"></a>Novedades de .NET Framework 4.7.1

.NET Framework 4.7.1 incluye nuevas características en las áreas siguientes:
 
- [Principal](#core471)
- [Common Language Runtime (CLR)](#clr)
- [Redes](#net471)
- [ASP.NET](#asp-net471) 

Además, un aspecto muy importante de .NET Framework 4.7.1 es mejorar la accesibilidad, lo que permite que una aplicación proporcione una experiencia adecuada para los usuarios de tecnología de asistencia. Para obtener información sobre las mejoras de accesibilidad en .NET Framework 4.7.1, vea [Novedades de accesibilidad en .NET Framework](whats-new-in-accessibility.md). 

<a name="core471" />
#### <a name="core"></a>Principal

**Compatibilidad con .NET Standard 2.0**

[.NET Standard](~/docs/standard/net-standard.md) define un conjunto de API que debe estar disponible en cada implementación de .NET que cumple con esa versión de Standard. .NET Framework 4.7.1 es totalmente compatible con .NET Standard 2.0 y agrega [unas doscientas API](https://github.com/dotnet/standard/blob/master/netstandard/src/ApiCompatBaseline.net461.txt) definidas en .NET Standard 2.0 y que no se encuentran en .NET Framework 4.6.1, 4.6.2 y 4.7. (Tenga en cuenta que estas versiones de .NET Framework son compatibles con .NET Standard 2.0 solo si también se implementan los archivos de compatibilidad adicionales de .NET Standard en el sistema de destino). Para más información, vea "BCL - .NET Standard 2.0 Support" (BCL: compatibilidad con .NET Standard 2.0) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features) (Características del compilador y del tiempo de ejecución de NET Framework 4.7.1).

**Compatibilidad con los generadores de configuración**

Los generadores de configuración permiten a los desarrolladores insertar y crear valores de configuración de forma dinámica para aplicaciones en tiempo de ejecución. Se pueden usar generadores de configuración personalizados para modificar datos existentes de una sección de configuración o para crear una sección de configuración totalmente desde cero. Sin los generadores de configuración, los archivos .config son estáticos y sus valores se definen algún tiempo antes de que se inicie la aplicación.

Para crear un generador de configuración personalizado, derive el generador de la clase <xref:System.Configuration.ConfigurationBuilder> abstracta y reemplace sus métodos <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> y <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType>. También debe definir los generadores en el archivo .config. Para más información, vea la sección "Configuration Builders" (Generadores de configuración) en la entrada de blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features) (Características de configuración y ASP.NET en .NET Framework 4.7.1). 

**Detección de características en tiempo de ejecución**

La clase <xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=fullName> proporciona un mecanismo para determinar si se admite una característica predefinida en una determinada implementación de .NET en tiempo de compilación o en tiempo de ejecución. En tiempo de compilación, un compilador puede comprobar si existe un campo especificado para determinar si se admite la característica; si es así, puede emitir código que aprovecha las ventajas de la característica. En tiempo de ejecución, una aplicación puede llamar al método <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> antes de emitir el código en tiempo de ejecución. Para obtener más información, vea [Add helper method to describe features supported by the runtime](https://github.com/dotnet/corefx/issues/17116) (Adición de un método auxiliar para describir características admitidas en tiempo de ejecución).

**Los tipos value tuple son serializables**

A partir de .NET Framework 4.7.1, <xref:System.ValueTuple?displayProperty=fullName> y sus tipos genéricos asociados se marcan como [serializables](xref:System.SerializableAttribute), lo que permite la serialización binaria. Esto facilita la migración de tipos tuple, como <xref:System.Tuple%603> y <xref:System.Tuple%604>, a tipos value tuple. Para más información, vea "Compiler -- ValueTuple is Serializable" (Compilador: ValueTuple serializable) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features) (Características del compilador y del tiempo de ejecución de .NET Framework 4.7.1).

**Compatibilidad con referencias de solo lectura**

.NET Framework 4.7.1 agrega <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=fullName>. Los compiladores de lenguaje utilizan este atributo para marcar los miembros que tienen parámetros o tipos de valor devuelto con referencias de solo lectura. Para más información, vea "Compiler -- Support for ReadOnlyReferences" (Compilador: compatibilidad con referencias de solo lectura) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features) (Características del compilador y del tiempo de ejecución de NET Framework 4.7.1). Para obtener información sobre los valores devueltos de referencia, vea [Ref return values and ref locals (C# Guide)](~/docs/csharp/programming-guide/classes-and-structs/ref-returns.md) [Valores devueltos y variables locales de tipo ref (Guía de C#)] y [Ref return values (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md) [Valores devueltos tipo ref (Visual Basic)].

<a name="clr" />
#### <a name="common-language-runtime-clr"></a>Common Language Runtime (CLR)

**Mejoras de rendimiento de la recolección de elementos no utilizados**

Los cambios en la recolección de elementos no utilizados en .NET Framework 4.7.1 mejoran el rendimiento general, sobre todo para las asignaciones del montón de objetos grandes. En .NET Framework 4.7.1, se usan bloqueos independientes para las asignaciones de montón de objetos pequeños y de montón de objetos grandes, lo que permite que se realicen las asignaciones de montón de objetos grandes cuando la operación de GC en segundo plano (BGC) rastrea el montón de objetos pequeños. Como resultado, las aplicaciones que realizan un número elevado de asignaciones de montón de objetos grandes deben observar una reducción de la contención del bloqueo de asignación y un rendimiento mejorado. Para más información, vea la sección "Runtime - GC Performance Improvements" (Tiempo de ejecución: mejoras de rendimiento de GC) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/28/net-framework-4-7-1-runtime-and-compiler-features/) (Características del compilador y del tiempo de ejecución de NET Framework 4.7.1). 

**Compatibilidad con archivos PDB portátiles**

A partir de .NET Framework 4.7.1 se admiten los archivos PDB portátiles. Mientras que los archivos PDB estándar solo son compatibles con Windows, los archivos PDB portátiles se pueden crear y leer en todas las plataformas. En la mayoría de los casos, el formato de archivo es transparente en una aplicación que se ejecuta en una implementación de .NET particular. Una excepción es una aplicación que emite un ensamblado en tiempo de ejecución de forma dinámica; en este caso, la capacidad de emitir un archivo PDB portátil puede ofrecer una mejora de rendimiento y reducir el consumo de memoria de la aplicación. 

Puede determinar en tiempo de ejecución si los archivos PDB portátiles son compatibles en la implementación de .NET actual al pasar la cadena "PortablePdb" al método <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported(System.String)?displayProperty=nameWithType> antes de emitir el ensamblado.  
 
<a name="net471"/>
#### <a name="networking"></a>Redes

**Compatibilidad de SHA-2 con Message.HashAlgorithm**

En .NET Framework 4.7 y en versiones anteriores, la propiedad <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> solo admitía los valores <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> y <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType>. A partir de .NET Framework 4.7.1, también se admiten <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType> y <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType>. Si este valor se usa realmente, depende de MSMQ, ya que la propia instancia <xref:System.Messaging.Message> no tiene ninguna función hash, sino que solo pasa los valores a MSMQ. Para más información, vea la sección "SHA-2 support for Message.HashAlgorithm" (Compatibilidad de SHA-2 con Message.HashAlgorithm) en la entrada de blog [.NET Framework 2 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features/) (Características de configuración y ASP.NET en .NET Framework 4.7.1).

<a name="asp-net471" />
#### <a name="aspnet"></a>ASP.NET

**Pasos de ejecución en aplicaciones ASP.NET**

ASP.NET procesa las solicitudes en una canalización predefinida que incluye veintitrés eventos. ASP.NET ejecuta cada controlador de eventos como un paso de ejecución. En las versiones de ASP.NET hasta .NET Framework 4.7, ASP.NETno puede permitir el flujo del contexto de ejecución debido al cambio entre subprocesos nativos y administrados. En su lugar, ASP.NET solo crea un flujo selectivo de <xref:System.Web.HttpContext>. A partir de .NET Framework 4.7.1, el método <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> también permite que los módulos restauren los datos de ambiente. Esta característica está orientada a las bibliotecas que tratan sobre el seguimiento, la generación de perfiles, el diagnóstico o las transacciones, que, por ejemplo, abordan el flujo de ejecución de la aplicación. Para más información, vea la sección "ASP.NET Execution Step Feature" (Característica de pasos de ejecución de ASP.NET) en la entrada de blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features) (Características de configuración y ASP.NET en .NET Framework 4.7.1). 

**Análisis HttpCookie de ASP.NET**

.NET Framework 4.7.1 incluye un nuevo método, <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>, que ofrece una forma estandarizada para crear un objeto <xref:System.Web.HttpCookie> a partir de una cadena y asignar con precisión los valores de cookie, como la fecha de expiración y la ruta de acceso. Para más información, vea la sección "ASP.NET HttpCookie parsing" (Análisis HttpCookie de ASP.NET) en la entrada de blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://blogs.msdn.microsoft.com/dotnet/2017/09/13/net-framework-4-7-1-asp-net-and-configuration-features) (Características de configuración y ASP.NET en .NET Framework 4.7.1). 

**Compatibilidad con opciones hash SHA-2 para las credenciales de autenticación de formularios de ASP.NET**

En .NET Framework 4.7 y versiones anteriores, ASP.NET permitía a los desarrolladores almacenar las credenciales de usuario con contraseñas a las que se les ha aplicado el algoritmo hash en archivos de configuración que usan MD5 o SHA1. A partir de .NET Framework 4.7.1, ASP.NET también admite nuevas opciones hash SHA-2 seguras, como SHA256, SHA384 y SHA512. SHA1 sigue siendo la opción predeterminada, aunque se puede definir un algoritmo hash no predeterminado en el archivo de configuración web. Por ejemplo:

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47"></a> 
### <a name="whats-new-in-the-net-framework-47"></a>Novedades de .NET Framework 4.7

.NET Framework 4.7 incluye nuevas características en las áreas siguientes:

- [Principal](#Core47)
- [Redes](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

Para una lista de las nuevas API agregadas a .NET Framework 4.7, consulte [.NET Framework 4.7 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) (Cambios de API de .NET Framework 4.7) en GitHub. Para una lista de las mejoras de características y correcciones de errores en .NET Framework 4.7, consulte [.NET Framework 4.7 List of Changes](http://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) (Lista de cambios de .NET Framework 4.7) en GitHub.  Para más información, vea [Announcing .NET Framework 4.7](https://blogs.msdn.microsoft.com/dotnet/2017/04/05/announcing-the-net-framework-4-7/) (Anuncio de .NET Framework 4.7) en el blog de .NET.

<a name="Core47" />
#### <a name="core"></a>Principal

.NET Framework 4.7 mejora la serialización con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Funcionalidad mejorada con criptografía de curva elíptica (ECC)***

En .NET Framework 4.7, los métodos `ImportParameters(ECParameters)` se han agregado a las clases <xref:System.Security.Cryptography.ECDsa> y <xref:System.Security.Cryptography.ECDiffieHellman> para permitir que un objeto represente una clave establecida previamente. También se agregó un método `ExportParameters(Boolean)` para exportar la clave mediante parámetros de curva explícitos.

.NET Framework 4.7 también admite las curvas adicionales, incluido el conjunto de curvas Brainpool, e incluye definiciones predefinidas agregadas para facilitar la creación a través de los nuevos patrones de diseño Factory Method <xref:System.Security.Cryptography.ECDsa.Create%2A> y <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

Puede ver un [ejemplo de las mejoras de criptografía de .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e) en GitHub.

**Mayor compatibilidad para caracteres de control mediante DataContractJsonSerializer**

En .NET Framework 4.7, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serializa los caracteres de control en conformidad con el estándar ECMAScript 6. Este comportamiento está habilitado de manera predeterminada para aplicaciones que tienen .NET Framework 4.7 como destino y es una característica opcional para las aplicaciones que se ejecutan en .NET Framework 4.7 pero tienen como destino una versión anterior de .NET Framework. Para más información, consulte [Cambios de redestinación en .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />
#### <a name="networking"></a>Redes

.NET Framework 4.7 agregue la siguiente característica relacionada con la red:

**Compatibilidad predeterminada del sistema operativo con protocolos TLS***

La pila TLS, que la usan <xref:System.Net.Security.SslStream?displayProperty=nameWithType> y los componentes que se encuentran por encima de la pila, como HTTP, FTP y SMTP, permite a los desarrolladores usar los protocolos TLS predeterminados compatibles con el sistema operativo. Ya no es necesario que los desarrolladores codifiquen una versión de TLS de forma rígida.

<a name="ASP-NET47" />
#### <a name="aspnet"></a>ASP.NET

En .NET Framework 4.7, ASP.NET incluye las siguientes características nuevas:

**Extensibilidad de caché de objetos**

A partir de .NET Framework 4.7, ASP.NET agrega un nuevo conjunto de API que permiten que los desarrolladores reemplacen las implementaciones predeterminadas de ASP.NET por la supervisión de memoria y el almacenamiento en caché de objetos en memoria. Ahora los desarrolladores pueden reemplazar cualquiera de los siguientes tres componentes si la implementación de ASP.NET no es adecuada:

- **Almacén de caché de objetos**. En la nueva sección de configuración de proveedores de caché, los desarrolladores pueden insertar implementaciones nuevas de una caché de objetos para una aplicación de ASP.NET mediante la nueva interfaz **ICacheStoreProvider**.
 
- **Supervisión de memoria**. El monitor de memoria predeterminado de ASP.NET notifica a las aplicaciones cuando se ejecutan cerca del límite de bytes privado configurado para el proceso o cuando queda poca RAM física total disponible en la máquina. Las notificaciones se activan cuando se está cerca de estos límites. En el caso de algunas aplicaciones, las notificaciones se activan demasiado cerca de los límites configurados como para permitir reacciones que sean útiles. Los desarrolladores ahora pueden usar la propiedad <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType> para escribir sus propios monitores de memoria y, así, reemplazar el predeterminado.

- **Reacciones por límite de memoria**. De forma predeterminada, ASP.NET intenta recortar la caché de objetos y llama periódicamente a <xref:System.GC.Collect%2A?displayProperty=nameWithType> cuando se está cerca del límite de proceso de bytes privados. En algunas aplicaciones, la frecuencia de llamadas a <xref:System.GC.Collect%2A?displayProperty=nameWithType> o la cantidad de caché que se recorta no son suficientes. Ahora los desarrolladores puede reemplazar o complementar el comportamiento predeterminado si suscriben las implementaciones de **IObserver** al monitor de memoria de la aplicación.

<a name="wcf47" />
#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

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
- Confiabilidad mejorada de las operaciones de serialización al llamar al método <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType>.
- Confiabilidad mejorada cuando se elimina un objeto waiter mediante una llamada al método **ChannelSynchronizer.RemoveWaiter**.

<a name="wf47" />
#### <a name="windows-forms"></a>Windows Forms

En .NET Framework 4.7, Windows Forms mejora la compatibilidad con monitores con valores altos de PPP.

**Compatibilidad con valores altos de PPP**

A partir de las aplicaciones que tienen .NET Framework 4.7 como destino, .NET Framework cuenta con compatibilidad con valores altos de PPP y PPP dinámicos. La compatibilidad con valores altos de PPP mejora el diseño y la apariencia de los formularios y controles en monitores con valores altos de PPP. PPP dinámicos cambia el diseño y la apariencia de los formularios y controles cuando el usuario cambia los PPP o el factor de escala de visualización de una aplicación en ejecución.

Compatibilidad con valores altos de PPP es una característica opcional que se configura definiendo una sección [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) en el archivo de configuración de la aplicación. Para más información sobre cómo agregar compatibilidad con valores altos de PPP y PPP dinámicos a la aplicación de Windows Forms, consulte [Compatibilidad con valores altos de PPP en Windows Forms](../winforms/high-dpi-support-in-windows-forms.md).

<a name="WPF47"></a> 
#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

En .NET Framework 4.7, WPF incluye las siguientes mejoras:

**Compatibilidad con una pila de entrada táctil o de lápiz basada en mensajes WM_POINTER de Windows**

Ahora tiene la opción de usar una pila de entrada táctil o de lápiz basada en [mensajes WM_POINTER](https://msdn.microsoft.com/library/windows/desktop/hh454903.aspx) en lugar de Windows Ink Services Platform (WISP). Se trata de una característica opcional de .NET Framework. Para más información, consulte [Cambios de redestinación en .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

**Nueva implementación para API de impresión de WPF**

Las API de impresión de WPF de la clase <xref:System.Printing.PrintQueue?displayProperty=nameWithType> llaman a la [API Print Document Package](https://msdn.microsoft.com/library/windows/desktop/hh448418(v=vs.85).aspx) de Windows en lugar de a la [API XPS Print](https://msdn.microsoft.com/library/windows/desktop/ff686814(v=vs.85).aspx), que está en desuso. Para ver el impacto que este cambio tiene en la compatibilidad de aplicaciones, consulte [Cambios de redestinación en .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md). 

<a name="v462"></a> 
## <a name="whats-new-in-the-net-framework-462"></a>Novedades de .NET Framework 4.6.2

[!INCLUDE[net_v462](../../../includes/net-v462-md.md)] incluye nuevas características en las áreas siguientes:

- [ASP.NET](#ASPNET462)

- [Categorías de caracteres](#Strings)

- [Criptografía](#Crypto462)

- [SqlClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#ClickOnce)

- [Conversión de aplicaciones de Windows Forms y WPF a aplicaciones de UWP](#UWPConvert)

- [Mejoras en la depuración](#Debug462)

Para una lista de las nuevas API agregadas a .NET Framework 4.6.2, consulte los [cambios de API de .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) en GitHub. Para una lista de las mejoras de características y correcciones de errores en .NET Framework 4.6.2, consulte [.NET Framework 4.6.2 List of Changes](http://go.microsoft.com/fwlink/?LinkId=708778) (Lista de cambios de .NET Framework 4.6.2) en GitHub.  Para obtener más información, vea [Announcing .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) (Anuncio de .NET Framework 4.6.2) en el blog de .NET.

<a name="ASPNET462"></a> 
### <a name="aspnet"></a>ASP.NET
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ASP.NET incluye las siguientes mejoras:

 **Compatibilidad mejorada para los mensajes de error localizado de validadores de anotación de datos** Los validadores de anotación de datos permiten realizar la validación mediante la adición de uno o varios atributos a una propiedad de clase. El elemento <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> del atributo define el texto del mensaje de error si se produce un error de validación. A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ASP.NET facilita la tarea de localizar mensajes de error. Los mensajes de error se localizarán si:

1.  Se proporciona <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> en el atributo de validación.

2.  El archivo de recursos está almacenado en la carpeta App_LocalResources.

3.  El nombre del archivo de recursos localizados tiene la forma `DataAnnotation.Localization.{`*nombre*`}.resx`, donde *nombre* es un nombre de referencia cultural en el formato *códigoDeIdioma*`-`*códigoDePaís/Región* o *códigoDeIdioma*.

4.  El nombre de clave del recurso es la cadena asignada al atributo <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> y su valor es el mensaje de error localizado.

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
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

 A continuación, puede crear un archivo de recursos DataAnnotation.Localization.fr.resx cuya clave sea la cadena del mensaje de error y cuyo valor sea el mensaje de error localizado. El archivo debe encontrarse en la carpeta `App.LocalResources`. Por ejemplo, a continuación se muestra la clave y su valor en un mensaje de error localizado en idioma francés (fr):

| Name                                 | Valor                                     |
| ------------------------------------ | ----------------------------------------- |
| La clasificación debe estar entre 1 y 10. | La note doit être comprise entre 1 et 10. |

 A continuación, este archivo puede

 Además, la localización de anotaciones de datos es extensible. Los desarrolladores pueden conectar su propio proveedor de localizador de cadenas mediante la implementación de la interfaz <xref:System.Web.Globalization.IStringLocalizerProvider> para almacenar la cadena de localización en un lugar distinto de un archivo de recursos.

 **Compatibilidad asincrónica con proveedores de almacenes de estados de sesión** Actualmente, ASP.NET permite el uso de métodos de devolución de tareas con proveedores de almacenes de estados de sesión, lo que permite que las aplicaciones ASP.NET aprovechen las ventajas de escalabilidad de la asincronía. Para admitir operaciones asincrónicas con proveedores de almacenes de estados de sesión, ASP.NET incluye una nueva interfaz, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>, que se hereda de <xref:System.Web.IHttpModule> y permite a los desarrolladores implementar sus propios módulos de estados de sesión y proveedores de almacenes de sesión asincrónica. La interfaz se define de la siguiente manera:

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

 Además, la clase <xref:System.Web.SessionState.SessionStateUtility> incluye dos nuevos métodos, <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> y <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, que se pueden usar para admitir operaciones asincrónicas.

 **Compatibilidad asincrónica con proveedores de caché de resultados** A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], pueden usarse métodos de devolución de tareas con proveedores de caché de resultados para proporcionar las ventajas de escalabilidad de la asincronía.  Los proveedores que implementan estos métodos reducen el bloqueo de subprocesos en un servidor web y mejoran la escalabilidad de un servicio de ASP.NET.

 Se han agregado las API siguientes para ofrecer compatibilidad con proveedores de caché de resultados asincrónicos:

- La clase <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType>, que se hereda de <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> y permite a los desarrolladores implementar un proveedor de caché de resultados asincrónicos.

- La clase <xref:System.Web.Caching.OutputCacheUtility>, que proporciona métodos auxiliares para configurar la caché de resultados.

- 18 métodos nuevos en la clase <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType>. Entre estos se incluyen <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A> y <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.

- 2 métodos nuevos en la clase <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> y <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.

- 2 métodos nuevos en la clase <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> y <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.

- 2 métodos nuevos en la clase <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> y <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.

- En la clase <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType>, el método <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A>.

- En la clase <xref:System.Web.Caching.CacheDependency>, el método <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A>.

<a name="Strings"></a> 
### <a name="character-categories"></a>Categorías de caracteres
 Los caracteres de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] se clasifican según el [estándar Unicode, versión 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/). En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], los caracteres están clasificados según las categorías de caracteres Unicode 6.3.

 La compatibilidad con Unicode 8.0 está limitada a la clasificación de caracteres mediante la clase <xref:System.Globalization.CharUnicodeInfo> y a los tipos y los métodos que se basan en ella. Entre ellos se incluyen la clase <xref:System.Globalization.StringInfo>, el método sobrecargado <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> y las [clases de caracteres](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) reconocidas por el motor de expresiones regulares de .NET Framework.  La comparación y la ordenación de caracteres y cadenas no se ven afectadas por este cambio y siguen dependiendo del sistema operativo subyacente o, en el caso de los sistemas Windows 7, de los datos de caracteres proporcionados por .NET Framework.

 Para realizar cambios en las categorías de caracteres de Unicode 6.0 a Unicode 7.0, consulte la página sobre [el estándar Unicode, versión 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) en el sitio web de The Unicode Consortium. Para realizar cambios de caracteres de Unicode 7.0 a Unicode 8.0, consulte la página sobre [el estándar Unicode, versión 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) en el sitio web de The Unicode Consortium.

<a name="Crypto462"></a> 
### <a name="cryptography"></a>Criptografía
 **Compatibilidad con certificados X509 que contienen DSA de FIPS 186-3** [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] agrega compatibilidad con certificados X509 de DSA (algoritmo de firma digital) cuyas claves superan el límite de 1024 bits de FIPS 186-2.

 Además de admitir los tamaños de clave más grandes de FIPS 186-3, [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] permite calcular firmas con la familia SHA-2 de algoritmos hash (SHA256, SHA384 y SHA512). La compatibilidad con FIPS 186-3 se proporciona mediante la nueva clase <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType>.

 Para conservar los cambios recientes en la clase <xref:System.Security.Cryptography.RSA> de .NET Framework 4.6 y la clase <xref:System.Security.Cryptography.ECDsa> de .NET Framework 4.6.1, la clase base abstracta <xref:System.Security.Cryptography.DSA> de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] tiene métodos adicionales que permiten que los llamadores usen esta funcionalidad sin conversión. Puede llamar al método de extensión <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> para firmar los datos, como se muestra en el ejemplo siguiente.

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

 También puede llamar al método de extensión <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> para comprobar los datos firmados, como se muestra en el ejemplo siguiente.

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

 **Mayor claridad para las entradas en rutinas de derivación de claves ECDiffieHellman** .NET Framework 3.5 incluía compatibilidad con el acuerdo de claves Diffie-Hellman de curva elíptica con tres rutinas diferentes de función de derivación de claves (KDF). Las entradas en las rutinas y las propias rutinas se configuraban mediante propiedades en el objeto <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Pero como no todas las rutinas leían todas las propiedades de entrada, esto podía provocar confusión al desarrollador.

 Para solucionarlo en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], se han agregado los tres métodos siguientes a la clase base <xref:System.Security.Cryptography.ECDiffieHellman> para representar con mayor claridad estas rutinas KDF y sus entradas:

|Método ECDiffieHellman|Descripción|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante la fórmula<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> donde *x* es el resultado calculado del algoritmo de Diffie-Hellman de curva elíptica.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante la fórmula<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> donde *x* es el resultado calculado del algoritmo de Diffie-Hellman de curva elíptica.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante el algoritmo de derivación de función pseudoaleatoria (PRF) de TLS.|

 **Compatibilidad con el cifrado simétrico de clave persistente** La biblioteca de criptografía (CNG) de Windows agrega compatibilidad para almacenar claves simétricas persistentes y para usar claves simétricas almacenadas en hardware, y [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] hace posible que los desarrolladores usen esta característica.  Como el concepto de nombres de clave y proveedores de clave depende de la implementación, el uso de esta característica obliga a emplear el constructor de los tipos de la implementación concreta, en lugar del enfoque de fábrica preferido (por ejemplo, llamar a `Aes.Create`).

 Existe compatibilidad con el cifrado simétrico de clave persistente para los algoritmos AES (<xref:System.Security.Cryptography.AesCng>) y 3DES (<xref:System.Security.Cryptography.TripleDESCng>). Por ejemplo:

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

 **Compatibilidad de SignedXml con el algoritmo hash SHA-2** [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] agrega compatibilidad con la clase <xref:System.Security.Cryptography.Xml.SignedXml> para los métodos de firma RSA-SHA256, RSA-SHA384 y RSA-SHA512 PKCS#1, y para los algoritmos de resumen de referencia SHA256, SHA384 y SHA512.

 Todas las constantes URI se exponen en <xref:System.Security.Cryptography.Xml.SignedXml>:

|Campo SignedXml|Constante|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|

 Todos los programas que hayan registrado un controlador <xref:System.Security.Cryptography.SignatureDescription> personalizado en <xref:System.Security.Cryptography.CryptoConfig> para agregar compatibilidad para estos algoritmos seguirán funcionando como antes, pero como ahora hay valores predeterminados de la plataforma, ya no es necesario el registro de <xref:System.Security.Cryptography.CryptoConfig>.

<a name="SQLClient"></a> 
### <a name="sqlclient"></a>SqlClient
 El proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>) incluye las siguientes características nuevas en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:

 **Agrupación de conexiones y tiempos de espera con bases de datos SQL de Azure** Cuando se habilita la agrupación de conexiones y se produce un error de tiempo de espera u otro tipo de error de inicio de sesión, se almacena en caché una excepción que se produce en todos los intentos de conexión posteriores que se realicen en un plazo de entre 5 segundos y 1 minuto.  Para obtener más información, vea [Agrupación de conexiones en SQL Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).

 Este comportamiento no es el deseable al conectarse a bases de datos SQL de Azure, ya que en los intentos de conexión se pueden producir errores transitorios que normalmente se recuperan rápidamente. Para optimizar la experiencia de reintento de conexión, se elimina el comportamiento del período de bloqueo del grupo de conexiones cuando se produce un error en las conexiones a bases de datos SQL de Azure.

 La adición de la nueva palabra clave `PoolBlockingPeriod` permite seleccionar el período de bloqueo más adecuado para la aplicación. Estos valores incluyen:

 `Auto` El período de bloqueo del grupo de conexiones para una aplicación que se conecta a una base de datos SQL de Azure está deshabilitado, mientras que el período de bloqueo del grupo de conexiones para una aplicación que se conecta a cualquier otra instancia de SQL Server está habilitado. Este es el valor predeterminado. Si el nombre del punto de conexión del servidor termina de alguna de las siguientes maneras, se considera que se trata de bases de datos SQL de Azure:

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

 `AlwaysBlock` El período de bloqueo del grupo de conexión siempre está habilitado.

 `NeverBlock` El período de bloqueo del grupo de conexión siempre está deshabilitado.

 **Mejoras para Always Encrypted** SQLClient presenta dos mejoras para Always Encrypted:

- Para mejorar el rendimiento de las consultas con parámetros en las columnas de una base de datos cifrada, ahora se almacenan en caché los metadatos de cifrado de los parámetros de consulta. Con la propiedad <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> establecida en `true` (que es el valor predeterminado), si se llama varias veces a la misma consulta, el cliente recupera los metadatos de parámetros del servidor una sola vez.

- Ahora, las entradas de clave de cifrado de columna incluidas en la caché de claves se expulsan después de un intervalo de tiempo configurable, que se establece mediante la propiedad <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType>.

<a name="WCF"></a> 
### <a name="windows-communication-foundation"></a>Windows Communication Foundation
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Communication Foundation se ha mejorado en las áreas siguientes:

 **Compatibilidad con la seguridad de transporte de WCF para los certificados almacenados con CNG** La seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows. En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], esta compatibilidad está limitada al uso de certificados con una clave pública que tenga un exponente con una longitud no superior a 32 bits. Cuando una aplicación tiene [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] como destino, esta característica está activada de forma predeterminada.

 En el caso de las aplicaciones que tengan como destino [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] o versiones anteriores, pero se ejecuten en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], esta característica se puede activar agregando la siguiente línea a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config o web.config.

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

 **Mejor compatibilidad para varias reglas de ajuste al horario de verano mediante la clase DataContractJsonSerializer** Los clientes pueden usar una opción de configuración de la aplicación para determinar si la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite varias reglas de ajuste para una sola zona horaria. Esta característica es opcional. Para habilitarla, agregue la siguiente opción de configuración al archivo app.config:

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

Cuando se habilita esta característica, un objeto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> usa el tipo <xref:System.TimeZoneInfo> en lugar del tipo <xref:System.TimeZone> para deserializar los datos de fecha y hora. <xref:System.TimeZoneInfo> admite varias reglas de ajuste, lo que permite trabajar con datos históricos de zona horaria, mientras que <xref:System.TimeZone> no las admite.

Para obtener más información sobre la estructura <xref:System.TimeZoneInfo> y los ajustes de zona horaria, consulte [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md).

**Compatibilidad para conservar una hora UTC al serializar y deserializar con la clase XMLSerializer** Normalmente, cuando la clase <xref:System.Xml.Serialization.XmlSerializer> se usa para serializar un valor <xref:System.DateTime> UTC, esta crea una cadena de tiempo serializada que conserva la fecha y la hora, pero da por supuesto que la hora es local.  Por ejemplo, si crea una instancia de fecha y hora UTC llamando al código siguiente:

```csharp
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);
```

```vb
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)
```

El resultado es la cadena de tiempo serializada "03:00:00.0000000-08:00" para un sistema con ocho horas con retraso con respecto a la hora UTC.  Además, los valores serializados siempre se deserializan como valores de fecha y hora locales.

 Puede usar una opción de configuración de la aplicación para determinar si <xref:System.Xml.Serialization.XmlSerializer> conserva la información de zona horaria UTC al serializar y deserializar valores <xref:System.DateTime>:

```xml 
<runtime>
     <AppContextSwitchOverrides 
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />
</runtime>
```

Cuando se habilita esta característica, un objeto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> usa el tipo <xref:System.TimeZoneInfo> en lugar del tipo <xref:System.TimeZone> para deserializar los datos de fecha y hora. <xref:System.TimeZoneInfo> admite varias reglas de ajuste, lo que permite trabajar con datos históricos de zona horaria, mientras que <xref:System.TimeZone> no las admite.

Para obtener más información sobre la estructura <xref:System.TimeZoneInfo> y los ajustes de zona horaria, consulte [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md).

 **Mejor coincidencia de NetNamedPipeBinding** WCF tiene una nueva opción de la aplicación que se puede establecer en las aplicaciones cliente para garantizar que siempre se conecten al servicio que escucha en el URI que mejor coincida con el que solicitan. Con esta opción de la aplicación establecida en `false` (valor predeterminado), es posible que los clientes que usan <xref:System.ServiceModel.NetNamedPipeBinding> intenten conectarse a un servicio que escucha en un URI que es una subcadena del URI solicitado.

 Por ejemplo, un cliente intenta conectarse a un servicio que escucha en `net.pipe://localhost/Service1`, pero un servicio diferente en ese equipo que se ejecuta con privilegios de administrador escucha en `net.pipe://localhost`. Con esta opción de la aplicación establecida en `false`, el cliente intentará conectarse al servicio incorrecto. Después de establecer la opción de la aplicación en `true`, el cliente siempre se conectará al mejor servicio.

> [!NOTE]
>  Los clientes que usan <xref:System.ServiceModel.NetNamedPipeBinding> encuentran servicios basados en la dirección base del servicio (si existe) en lugar de la dirección del punto de conexión completo. Para garantizar que esta opción siempre funcione, el servicio debe usar una dirección base única.

 Para habilitar este cambio, agregue la siguiente opción de la aplicación al archivo App.config o Web.config de la aplicación cliente:

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

 **SSL 3.0 no es el protocolo predeterminado** Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, SSL 3.0 ya no es el protocolo predeterminado para negociar una conexión segura. En la mayoría de los casos, esto no debería afectar a las aplicaciones existentes, porque TLS 1.0 está incluido en la lista de protocolos para NetTcp. Todos los clientes deberían poder negociar una conexión usando como mínimo TLS 1.0. Si se requiere Ssl3, use uno de los siguientes mecanismos de configuración para agregarlo a la lista de protocolos negociados.

- La propiedad <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType>

- La propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>

- La sección [\<transport>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) de la sección [\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)

- La sección [\<sslStreamSecurity>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) de la sección [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

<a name="WPF462"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Presentation Foundation se ha mejorado en las áreas siguientes:

 **Ordenación de grupos** Ahora, una aplicación que use un objeto <xref:System.Windows.Data.CollectionView> para agrupar los datos puede declarar explícitamente cómo ordenar los grupos. La ordenación explícita resuelve el problema de la ordenación no intuitiva que se produce cuando una aplicación agrega o elimina grupos dinámicamente, o cuando cambia el valor de las propiedades de elementos implicadas en la agrupación. También puede mejorar el rendimiento del proceso de creación de grupos, ya que mueve las comparaciones de las propiedades de agrupación de la ordenación de la colección completa a la ordenación de los grupos.

 Para admitir la ordenación de grupos, las nuevas propiedades <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> y <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> describen cómo ordenar la colección de grupos generada por el objeto <xref:System.ComponentModel.GroupDescription>. Esto es análogo a la forma en que las propiedades <xref:System.Windows.Data.ListCollectionView> con el mismo nombre describen cómo se ordenan los elementos de datos.

 Dos nuevas propiedades estáticas de la clase <xref:System.Windows.Data.PropertyGroupDescription>, <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> y <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, se pueden usar para los casos más comunes.

 Por ejemplo, el siguiente código XAML agrupa los datos por edad, ordena los grupos de edad en orden ascendente y agrupa los elementos de cada grupo de edad por apellido.

```xaml
<GroupDescriptions>
     <PropertyGroupDescription 
         PropertyName="Age" 
         CustomSort= 
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

 **Compatibilidad con teclado en pantalla** La compatibilidad con teclado en pantalla permite el seguimiento del foco en aplicaciones WPF, ya que invoca y descarta automáticamente el nuevo teclado en pantalla de Windows 10 cuando un control que acepta entrada de texto recibe la entrada táctil.

 En versiones anteriores de .NET Framework, las aplicaciones WPF no pueden optar por el seguimiento del foco sin deshabilitar la compatibilidad con lápiz o movimiento táctil en WPF.  Como resultado, las aplicaciones WPF deben elegir entre compatibilidad táctil completa en WPF o basarse en la promoción del mouse de Windows.

 **PPP por monitor** Para admitir la reciente proliferación de entornos con valores altos o híbridos de PPP para las aplicaciones WPF, WPF en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] habilita el reconocimiento de monitor. Consulte [los ejemplos y la guía para desarrolladores](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) en GitHub para obtener más información sobre cómo activar el reconocimiento de PPP por monitor en la aplicación WPF.

 En versiones anteriores de .NET Framework, las aplicaciones WPF tienen habilitado el reconocimiento de PPP del sistema. En otras palabras, el sistema operativo escala la interfaz de usuario de la aplicación según corresponda, en función del valor de PPP del monitor en el que se representa la aplicación. ,

 Para aplicaciones que se ejecutan en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], puede deshabilitar los cambios de PPP por monitor en las aplicaciones WPF. Para ello, agregue una instrucción de configuración en la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación de la siguiente manera:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Workflow Foundation se ha mejorado en las áreas siguientes:

 **Compatibilidad con expresiones de C# e IntelliSense en el Diseñador de WF rehospedado** A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], WF admite expresiones de C# tanto en el diseñador de Visual Studio como en los flujos de trabajo de código. El Diseñador de flujo de trabajo rehospedado es una característica clave de WF que permite que el Diseñador de flujo de trabajo esté en una aplicación fuera de Visual Studio (por ejemplo, en WPF).  Windows Workflow Foundation permite admitir expresiones de C# e IntelliSense en el Diseñador de flujo de trabajo rehospedado. Para obtener más información, consulte el [blog de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).

 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` En las versiones de .NET Framework anteriores a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], IntelliSense del Diseñador de WF se interrumpe cuando un cliente vuelve a compilar un proyecto de flujo de trabajo desde Visual Studio. Aunque la compilación del proyecto es correcta, los tipos de flujo de trabajo no se encuentran en el diseñador y en la ventana **Lista de errores** aparecen advertencias de IntelliSense que indican los tipos de flujo de trabajo que faltan. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] soluciona este problema y hace que IntelliSense esté disponible.

 **Las aplicaciones V1 de flujo de trabajo con seguimiento del flujo de trabajo ahora se ejecutan en modo FIPS** Los equipos que tienen habilitado el modo de cumplimiento de FIPS ahora pueden ejecutar correctamente una aplicación de versión 1 de flujo de trabajo con el seguimiento del flujo de trabajo habilitado. Para habilitar este escenario, debe realizar el cambio siguiente en el archivo app.config:

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

 Si este escenario no está habilitado, al ejecutar la aplicación se sigue generando una excepción con el mensaje "Esta implementación no forma parte de los algoritmos criptográficos validados por Windows Platform FIPS".

 **Mejoras en el flujo de trabajo al usar la actualización dinámica con el Diseñador de flujo de trabajo de Visual Studio** El Diseñador de flujo de trabajo, el Diseñador de actividad de diagrama de flujo y otros diseñadores de actividad de flujo de trabajo ahora cargan y muestran correctamente los flujos de trabajo guardados después de llamar al método <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>. En versiones de .NET Framework anteriores a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la carga de un archivo XAML en Visual Studio para un flujo de trabajo guardado después de llamar a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> puede producir los problemas siguientes:

- El Diseñador de flujo de trabajo no se puede cargar el archivo XAML correctamente (cuando <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> se encuentra al final de la línea).

- El Diseñador de actividad de diagrama de flujo u otros diseñadores de actividad de flujo de trabajo pueden mostrar todos los objetos en sus ubicaciones predeterminadas en lugar de los valores de la propiedad adjunta.

<a name="ClickOnce"></a> 
### <a name="clickonce"></a>ClickOnce
 Se ha actualizado ClickOnce para que admita TLS 1.1 y TLS 1.2 además del protocolo 1.0, que ya se admite. ClickOnce detecta automáticamente qué protocolo se requiere; no es necesario realizar ningún paso adicional en la aplicación ClickOnce para habilitar la compatibilidad con TLS 1.1 y 1.2.

<a name="UWPConvert"></a> 
### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Conversión de aplicaciones de Windows Forms y WPF a aplicaciones de UWP
 Windows ahora ofrece funciones para llevar aplicaciones existentes de escritorio de Windows, incluidas aplicaciones de Windows Forms y WPF, a la Plataforma universal de Windows (UWP). Esta tecnología actúa como un puente, ya que permite migrar gradualmente su base de código existente a UWP, lo que lleva su aplicación a todos los dispositivos Windows 10.

 Las aplicaciones de escritorio convertidas obtienen una identidad de aplicación similar a la identidad de aplicación de las aplicaciones de UWP, lo que hace que las API de UWP sean accesibles para habilitar características como iconos dinámicos y notificaciones. La aplicación sigue comportándose como antes y se ejecuta como una aplicación de plena confianza. Una vez convertida la aplicación, se puede agregar un proceso de contenedor de la aplicación al proceso de plena confianza existente para agregar una interfaz de usuario adaptable. Cuando todas las funciones se hayan movido al proceso de contenedor de la aplicación, se puede quitar el proceso de plena confianza y la nueva aplicación de UWP estará disponible para todos los dispositivos Windows 10.

<a name="Debug462"></a> 
### <a name="debugging-improvements"></a>Mejoras en la depuración
 La *API de depuración no administrada* se ha mejorado en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] para que realice análisis adicionales cuando se produzca una excepción <xref:System.NullReferenceException>, de modo que sea posible determinar qué variable de una sola línea de código fuente es `null`.   Para admitir este escenario, se han agregado las API siguientes a la API de depuración no administrada.

- Las interfaces [ICorDebugCode4](../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) e [ICorDebugVariableHomeEnum](../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md), que exponen las ubicaciones nativas de las variables administradas. Esto permite a los depuradores realizar un análisis de flujo de código cuando se produce una excepción <xref:System.NullReferenceException> y trabajar hacia atrás para determinar la variable administrada que se corresponde con la ubicación nativa que era `null`.

- El método [ICorDebugType2::GetTypeID](../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) proporciona una asignación para ICorDebugType a [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), lo que permite al depurador obtener un valor [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) sin una instancia de ICorDebugType. Después, las API existentes en [COR_TYPEID](../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) pueden usarse para determinar el diseño de clase del tipo.

<a name="v461"></a> 
## <a name="whats-new-in-the-net-framework-461"></a>Novedades de .NET Framework 4.6.1
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] incluye nuevas características en las áreas siguientes:

- [Criptografía](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [Generación de perfiles](#Profile461)

- [NGen](#NGEN461)

 Para obtener más información sobre [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], vea uno de los temas siguientes:

- La [lista de cambios de .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=622964)

- [Compatibilidad de aplicaciones en 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

- [Diferencia de la API de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=622989) (en GitHub)

<a name="Crypto"></a> 
### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Cifrado: compatibilidad con certificados X509 que contienen ECDSA
 La versión 4.6 de .NET Framework agrega compatibilidad con RSACng para certificados X509. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] agrega compatibilidad para certificados X509 ECDSA (Elliptic Curve Digital Signature Algorithm).

 ECDSA ofrece un mejor rendimiento y es un algoritmo de cifrado más seguro que RSA, lo que lo convierte en una excelente elección cuando están en juego la escalabilidad y el rendimiento de la seguridad de capa de transporte (TLS). La implementación de .NET Framework encapsula las llamadas en funciones de Windows existentes.

 El ejemplo de código siguiente muestra lo fácil que es generar una firma para una secuencia de bytes mediante la nueva compatibilidad para certificados X509 de ECDSA incluidos en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].

 [!code-csharp[whatsnew.461.crypto#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
 [!code-vb[whatsnew.461.crypto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

 Esto ofrece un contraste marcado para el código necesario para generar una firma en .NET Framework 4.6.

 [!code-csharp[whatsnew.461.crypto#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
 [!code-vb[whatsnew.461.crypto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461"></a> 
### <a name="adonet"></a>ADO.NET
 Se agregó lo siguiente a ADO.NET:

 Compatibilidad con Always Encrypted para claves protegidas por hardware ADO.NET ahora permite almacenar claves maestras de la columna Always Encrypted de forma nativa en módulos de seguridad de hardware (HSM). Con esta compatibilidad, los clientes pueden aprovechar las claves asimétricas almacenadas en HSM sin tener que escribir proveedores de almacenes de clave maestra de la columna personalizada ni registrarlos en las aplicaciones.

 Los clientes necesitan instalar el proveedor CSP proporcionado por el fabricante HSM o los proveedores de almacén de claves de CNG en los servidores de aplicación o en los equipos cliente para tener acceso a los datos que Always Encrypted ha protegido con las claves maestras de columna almacenadas en un HSM.

 La mejora del comportamiento de la conexión <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> para SqlClient AlwaysOn ahora proporciona automáticamente una conexión más rápida a un grupo de disponibilidad AlwaysOn (AG). Detecta de forma transparente si la aplicación se conecta a un grupo de disponibilidad AlwaysOn (AG) en una subred diferente y detecta rápidamente el servidor activo actual y proporciona una conexión al servidor. Antes de esta versión, una aplicación tenía que establecer la cadena de conexión para incluir `"MultisubnetFailover=true"` e indicar que se conecta a un grupo de disponibilidad AlwaysOn. Sin establecer la palabra clave de conexión en `true`, una aplicación podría experimentar un tiempo de espera mientras se conecta a un grupo de disponibilidad AlwaysOn. Con esta versión, la aplicación ya *no* necesita establecer <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> en `true`. Para obtener más información sobre la compatibilidad de SqlClient con grupos de disponibilidad AlwaysOn, vea [Compatibilidad de SqlClient para alta disponibilidad y recuperación ante desastres](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

<a name="WPF461"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 Windows Presentation Foundation incluye una serie de mejoras y cambios.

 Rendimiento mejorado Se ha corregido el retraso de activación de eventos de función táctil en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Además, al escribir un control <xref:System.Windows.Controls.RichTextBox> ya no se bloquea el subproceso de representación durante la entrada rápida.

 Mejoras en el corrector ortográfico El corrector ortográfico en WPF se ha actualizado en Windows 8.1 y en versiones posteriores para aprovechar la compatibilidad del sistema operativo con la corrección ortográfica de idiomas adicionales.  No hay ningún cambio en la funcionalidad en las versiones de Windows anteriores a Windows 8.1.

 Como en versiones anteriores de .NET Framework, el idioma de un control <xref:System.Windows.Controls.TextBox> o un bloque <xref:System.Windows.Controls.RichTextBox> se detecta mediante la búsqueda de información en el orden siguiente:

- `xml:lang`, si está presente.

- Idioma de entrada actual.

- Referencia cultural del subproceso actual.

 Para obtener más información sobre la compatibilidad de idioma en WPF, vea la [entrada de blog de WPF sobre las características de .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkID=691819).

 Compatibilidad adicional con diccionarios personalizados por el usuario En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], WPF reconoce los diccionarios personalizados que se registran de forma global. Esta funcionalidad está disponible además de la posibilidad de registrarlos por control.

 En versiones anteriores de WPF, los diccionarios personalizados no reconocían palabras excluidas ni listas de autocorrección. Ahora se admiten en Windows 8.1 y Windows 10 mediante el uso de archivos que se pueden colocar en el directorio `%AppData%\Microsoft\Spelling\<language tag>`.  Las reglas siguientes se aplican a estos archivos:

- Los archivos deben tener las extensiones .dic (para palabras agregadas), .exc (para las palabras excluidas) o .acl (para la autocorrección).

- Los archivos deben ser texto sin formato UTF-16 LE que comienza con la marca BOM (Byte Order Mark).

- Cada línea debe constar de una palabra (en las listas de palabras agregadas y excluidas) o un par de autocorrección con las palabras separadas por una barra vertical ("&#124;") (en la lista de palabras de Autocorrección).

- Estos archivos se consideran de solo lectura y el sistema no los modifica.

> [!NOTE]
>  Estos nuevos formatos de archivos no son compatibles directamente con las API de corrección ortográfica de WPF, y los diccionarios personalizados proporcionados a WPF en las aplicaciones deben continuar usando los archivos .lex.

 Ejemplos Hay una serie de [ejemplos de WPF](https://msdn.microsoft.com/library/ms771633.aspx) en MSDN. Más de 200 de los ejemplos más populares (según su utilización) se moverán a un [repositorio de GitHub de código abierto](https://github.com/Microsoft/WPF-Samples). Ayúdenos a mejorar nuestros ejemplos enviando una solicitud de extracción o abriendo un [problema de GitHub](https://github.com/Microsoft/WPF-Samples/issues).

 En el caso de las extensiones de DirectX, WPF incluye un [paquete NuGet](http://go.microsoft.com/fwlink/?LinkID=691342) que proporciona nuevas implementaciones de <xref:System.Windows.Interop.D3DImage> que facilitan la tarea de interoperar con contenido de DX10 y DX11. El código para este paquete se ha abierto y está disponible [en GitHub](https://github.com/Microsoft/WPFDXInterop).

<a name="WWF461"></a> 
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: transacciones
 El método <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> ahora puede usar un administrador de transacciones distribuidas que no sea MSDTC para promocionar la transacción. Para ello, especifique un identificador GUID de promoción de transacción a la nueva sobrecarga <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType>. Si esta operación se realiza correctamente, hay limitaciones de las capacidades de la transacción. Una vez que se activa un promotor de transacciones que no sea MSDTC, los métodos siguientes inician una <xref:System.Transactions.TransactionPromotionException> porque estos métodos requieren promoción a MSDTC:

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

 Una vez que se activa un promotor de transacciones que no sea MSDTC, debe usarse para futuras inscripciones duraderas a través de los protocolos que define. El <xref:System.Guid> del promotor de transacción puede obtenerse con la propiedad <xref:System.Transactions.Transaction.PromoterType%2A>. Cuando se promueve la transacción, el promotor de transacciones proporciona una matriz <xref:System.Byte> que representa el token promocionado. Una aplicación puede obtener el token promocionado de una transacción promocionada que no sea de MSDTC con el método <xref:System.Transactions.Transaction.GetPromotedToken%2A>.

 Los usuarios de la nueva sobrecarga <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> deben seguir una secuencia de llamadas específica para completar correctamente la operación de promoción. Estas reglas están registradas en la documentación del método.

<a name="Profile461"></a> 
### <a name="profiling"></a>Generación de perfiles
 La API de generación de perfiles no administrada se ha mejorado como se indica a continuación:

 Mejor compatibilidad para tener acceso a archivos PDB en la interfaz [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) En ASP.Net 5, cada vez es más común que los ensamblados se compilen en memoria mediante Roslyn. Para desarrolladores que crean herramientas de generación de perfiles, esto significa que los PDB serializados históricamente en disco ya no estén presentes. Las herramientas del generador de perfiles suelen usar archivos PDB para asignar código a las líneas de código fuente para tareas como el análisis de rendimiento de línea por línea o de cobertura de código. La interfaz [ICorProfilerInfo7](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) ahora incluye dos nuevos métodos, [ICorProfilerInfo7::GetInMemorySymbolsLength](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) e [ICorProfilerInfo7::ReadInMemorySymbols](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), para proporcionar estas herramientas del generador de perfiles con acceso a los datos de PDB en memoria. Usando las nuevas API, un generador de perfiles puede obtener el contenido de un PDB en memoria como una matriz de bytes y luego procesarlo o serializarlo en el disco.

 Mejor instrumentación con la interfaz ICorProfiler Los generadores de perfiles que utilizan la funcionalidad ReJit de la API `ICorProfiler` para la instrumentación dinámica ahora pueden modificar algunos metadatos. Anteriormente dichas herramientas podían instrumentar IL en cualquier momento, pero los metadatos solo se podían modificar en tiempo de carga del módulo. Dado que IL hace referencia a los metadatos, esto limita los tipos de instrumentación que se podían hacer. Hemos solucionado algunos de esos límites agregando el método [ICorProfilerInfo7::ApplyMetaData](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) para admitir un subconjunto de ediciones de metadatos después de que el módulo se cargue, en particular agregando nuevos registros `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec` y `UserString`. Este cambio permite una mayor variedad de instrumentación sobre la marcha.

<a name="NGEN461"></a> 
### <a name="native-image-generator-ngen-pdbs"></a>PDB del generador de imágenes nativas (NGEN)
 El seguimiento de eventos de varios equipos permite a los clientes generar perfiles de un programa en la máquina A y mirar los datos de generación de perfiles con la asignación de la línea de origen en la máquina B. Al usar versiones anteriores de .NET Framework, el usuario copiaría todos los módulos y las imágenes nativas de la máquina con generación de perfiles a la máquina de análisis que contiene el archivo PDB de IL para crear la asignación de código fuente a nativo. Aunque este proceso puede funcionar bien cuando los archivos son relativamente pequeños, como en aplicaciones de teléfono, los archivos pueden ser muy grandes en sistemas de escritorio y requieren mucho tiempo para copiarse.

 Con los archivos PDB de NGen, NGen puede crear un archivo PDB que contenga la asignación de IL a nativo sin una dependencia del archivo PDB de IL. En nuestro escenario de seguimiento de eventos de varias máquinas, todo lo que se necesita es copiar la imagen nativa PDB generada por la máquina A a la máquina B y utilizar [Depurar API de acceso de interfaz](https://msdn.microsoft.com/library/ee8x173s.aspx) para leer la asignación de origen al IL del archivo PDB de IL y la asignación del IL a nativo del archivo PDB de imágenes nativas. La combinación de ambas asignaciones permite asignar código fuente a nativo. Dado que el PDB de imagen nativa es mucho menor que todos los módulos y las imágenes nativas, el proceso de copiar de la máquina A a la máquina B es mucho más rápido.

<a name="v46"></a> 
## <a name="whats-new-in-net-2015"></a>Novedades de .NET 2015
 .NET 2015 presenta [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y .NET Core. Algunas características nuevas se aplican a ambos, y otras son específicas de [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] o [!INCLUDE[net_core](../../../includes/net-core-md.md)].

- **ASP.NET 5**

     .NET Framework 2015 incluye ASP.NET 5, que es una implementación .NET eficiente para la compilación de aplicaciones modernas basadas en la nube. ASP.NET 5 es modular, por lo que puede incluir solo aquellas características que se necesitan en la aplicación. Puede hospedarse en IIS o autohospedarse en un proceso personalizado y se pueden ejecutar aplicaciones con diferentes versiones de .NET Framework en el mismo servidor. Incluye un nuevo sistema de configuración de entorno que está diseñado para la implementación de la nube.

     MVC, Web API y Web Pages están unificados en un marco único llamado MVC 6. Las aplicaciones de ASP.NET 5 se compilan con las nuevas herramientas de Visual Studio 2015. Las aplicaciones existentes funcionarán en el nuevo .NET Framework; sin embargo, para compilar una aplicación que use MVC 6 o SignalR 3, debe usar el sistema de proyectos de Visual Studio 2015.

     Para obtener información, vea [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).

- **Actualizaciones de ASP.NET**

    - **API basada en tareas para el vaciado de respuestas asincrónicas**

         Ahora, ASP.NET proporciona una API sencilla basada en tareas para el vaciado de respuestas asincrónicas, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType>, que permite vaciar las respuestas de forma asincrónica con el soporte `async/await` de su lenguaje.

    - `Model binding supports task-returning methods`

         ASP.NET agregó en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] la característica Enlace de modelos, que habilita un enfoque extensible y centrado en el código en las operaciones de datos basadas en CRUD de las páginas de formularios Web Forms y los controles de usuario. Ahora el sistema Enlace de modelos es compatible con los métodos de enlace de modelos que devuelven <xref:System.Threading.Tasks.Task>. Esta característica permite que los desarrolladores de formularios Web Forms aprovechen las ventajas que presenta la escalabilidad de la asincronía con la facilidad del sistema de enlace de datos al usar las versiones más recientes de ORM, incluido Entity Framework.

         El enlace de modelos asincrónicos se controla con la opción de configuración `aspnet:EnableAsyncModelBinding`.

        ```xml
        <appSettings>
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
        </appSettings>
        ```

         En las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], el valor predeterminado es `true`. En las aplicaciones que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y que tienen como destino una versión anterior de .NET Framework, el valor predeterminado es `false`. Se puede habilitar estableciendo la opción de configuración en `true`.

    - **Compatibilidad con HTTP/2 (Windows 10)**

         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) es una nueva versión del protocolo HTTP que proporciona un uso mucho mejor de la conexión (menos recorridos de ida y vuelta entre el cliente y el servidor), lo que permite una latencia más baja para los usuarios al cargar páginas web.  Las páginas web (no de servicios) aprovechan HTTP/2 al máximo, porque el protocolo se optimizó para la solicitud de varios artefactos como parte de una sola experiencia. La compatibilidad para HTTP/2 se agregó a ASP.NET en .NET Framework 4.6. Como la funcionalidad de red existe en varios niveles, se necesitaban nuevas características en Windows, IIS y ASP.NET para habilitar HTTP/2. Debe ejecutar Windows 10 para usar HTTP/2 con ASP.NET.

         También se admite HTTP/2, y está activado de forma predeterminada en las aplicaciones de la Plataforma universal de Windows (UWP) de Windows 10 que usan la API <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>.

         Para proporcionar una forma de usar la característica [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) en aplicaciones de ASP.NET, se ha agregado un método nuevo con dos sobrecargas, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> y <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, a la clase <xref:System.Web.HttpResponse>.

        > [!NOTE]
        >  Mientras que ASP.NET 5 admite HTTP/2, la compatibilidad con la característica PUSH PROMISE aún no se ha agregado.

         El explorador y el servidor web (IIS en Windows) hacen todo el trabajo. No tiene que hacer el trabajo más farragoso para los usuarios.

         La mayoría de [los principales navegadores admiten HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), por lo que probablemente los usuarios se beneficiarán de la compatibilidad con HTTP/2 si el servidor lo admite.

    - **Compatibilidad con el Protocolo de enlace de tokens**

         Google y Microsoft colaboraron en un nuevo sistema de autenticación llamado [Protocolo de enlace de tokens](https://github.com/TokenBinding/Internet-Drafts). La premisa es que los tokens de autenticación (en la memoria caché del navegador) pueden ser robados y usados por delincuentes para acceder a recursos seguros (por ejemplo, su cuenta bancaria) sin necesidad de contraseña ni de otra información privilegiada. El nuevo protocolo tiene como objetivo mitigar este problema.

         El Protocolo de enlace de tokens se implementará en Windows 10 como una característica del explorador. Las aplicaciones de ASP.NET participarán en el protocolo para validar la legitimidad de los tokens de autenticación. Las implementaciones de cliente y de servidor establecen la protección de extremo a extremo especificada por el protocolo.

    - **Algoritmos hash de cadena aleatoria**

         En .NET Framework 4.5, se introdujo [un algoritmo hash de cadena aleatorio](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md). pero no era compatible con ASP.NET porque algunas características de ASP.NET dependían de un código hash estable. En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ya se admiten los algoritmos hash de cadena aleatoria. Para habilitar esta característica, use la opción de configuración `aspnet:UseRandomizedStringHashAlgorithm`.

        ```xml
        <appSettings>
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
        </appSettings>
        ```

- **ADO.NET**

     ADO .NET ahora es compatible con la característica Always Encrypted disponible en SQL Server 2016 Community Technology Preview 2 (CTP2). Con Always Encrypted, SQL Server puede realizar operaciones en los datos cifrados y, lo mejor de todo, es que la clave de cifrado reside, junto con la aplicación, en el entorno de confianza del cliente y no en el servidor. Always Encrypted protege los datos del cliente para que los administradores de bases de datos no tengan acceso a los datos de texto sin formato. El cifrado y descifrado de datos ocurre de forma transparente en el nivel de controlador, lo que minimiza los cambios que deben realizarse en las aplicaciones existentes. Para obtener más información, vea [Always Encrypted (motor de base de datos)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) y [Always Encrypted (desarrollo de cliente)](/sql/relational-databases/security/encryption/always-encrypted-client-development).

- **Compilador JIT de 64 bits para código administrado**

     .NET Framework 4.6 incluye una nueva versión del compilador JIT de 64 bits (llamado originalmente RyuJIT). El nuevo compilador de 64 bits proporciona importantes mejoras de rendimiento con respecto al antiguo compilador JIT de 64 bits. El nuevo compilador de 64 bits está habilitado para los procesos de 64 bits que se ejecutan en .NET Framework 4.6. La aplicación se ejecutará en un proceso de 64 bits si se ha compilado como aplicación de 64 bits o AnyCPU y se está ejecutando en un sistema operativo de 64 bits. Aunque se hayan tomado precauciones para efectuar la transición al nuevo compilador de la manera más transparente posible, es posible que se produzcan cambios en el comportamiento. Nos gustaría que se pusiera en contacto con nosotros si encuentra algún problema al usar el nuevo compilador JIT. Póngase en contacto con nosotros a través de [Microsoft Connect](http://connect.microsoft.com/) si detecta algún problema que pueda estar relacionado con el nuevo compilador JIT de 64 bits.

     El nuevo compilador JIT de 64 bits también incluye características de aceleración SIMD de hardware al acoplarse con tipos SIMD habilitados para SIMD en el espacio de nombres <xref:System.Numerics>, que puede producir notables mejoras en el rendimiento.

- **Mejoras en el cargador de ensamblados**

     Ahora el cargador de ensamblados usa la memoria de un modo más eficaz al descargar ensamblados de IL después de cargar una imagen NGEN correspondiente. Este cambio reduce la memoria virtual, que es bastante útil en las aplicaciones de 32 bits de gran tamaño (por ejemplo, Visual Studio), y también guarda la memoria física.

- **Cambios en la biblioteca de clases base**

     Se agregaron muchas nuevas API a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] para habilitar escenarios clave. Incluyen los siguientes cambios y adiciones:

    - **Implementaciones de IReadOnlyCollection\<T>**

         Las colecciones adicionales implementan <xref:System.Collections.Generic.IReadOnlyCollection%601>, como <xref:System.Collections.Generic.Queue%601> y <xref:System.Collections.Generic.Stack%601>.

    - **CultureInfo.CurrentCulture y CultureInfo.CurrentUICulture**

         Las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> ahora son de lectura y escritura, en lugar de solo lectura. Si asigna un nuevo objeto <xref:System.Globalization.CultureInfo> a estas propiedades, también cambian la referencia cultural del subproceso actual definida por la propiedad `Thread.CurrentThread.CurrentCulture` y la referencia cultural del subproceso de la interfaz usuario actual definida por las propiedades `Thread.CurrentThread.CurrentUICulture`.

    - **Mejoras en la recolección de elementos no utilizados (GC)**

         La clase <xref:System.GC> ahora incluye los métodos <xref:System.GC.TryStartNoGCRegion%2A> y <xref:System.GC.EndNoGCRegion%2A> que permiten impedir la recolección de elementos no usados durante la ejecución de una ruta crítica.

         Una nueva sobrecarga del método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> permite controlar si el montón del objeto pequeño y el montón del objeto grande se exploran y compactan o si solo se exploran.

    - **Tipos habilitados para SIMD**

         El espacio de nombres <xref:System.Numerics> incluye ahora varios tipos habilitados para SIMD, como <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> y <xref:System.Numerics.Vector4>.

         Como el nuevo compilador JIT de 64 bits también incluye características de aceleración de hardware SIMD, hay mejoras de rendimiento considerablemente importantes al usar los tipos habilitados para SIMD con el nuevo compilador JIT de 64 bits.

    - **Actualizaciones de criptografía**

         La API <xref:System.Security.Cryptography?displayProperty=nameWithType> se está actualizando para que sea compatible con las [API de criptografía CNG de Windows](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx). Las versiones anteriores de .NET Framework dependían totalmente de una [versión anterior de las API de criptografía de Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) como base para la implementación de <xref:System.Security.Cryptography?displayProperty=nameWithType>. Recibimos solicitudes para admitir la API de CNG, ya que admite [algoritmos de criptografía modernos](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), que son importantes para determinadas categorías de aplicaciones.

         .NET Framework 4.6 incluye las siguientes mejoras para admitir las API de criptografía de CNG de Windows:

        - Un conjunto de métodos de extensión para los certificados X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` y `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, que devuelven, siempre que sea posible, una implementación basada en CNG en lugar de una implementación basada en CAPI (algunas tarjetas inteligentes, entre otros, siguen necesitando CAPI, mientras que las API controlan la reserva).

        - La clase <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>, que proporciona una implementación de CNG del algoritmo RSA.

        - Mejoras en la API de RSA, de modo que las acciones habituales ya no necesitan ninguna conversión. Por ejemplo, el cifrado de datos con un objeto <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> necesita un código similar al siguiente en las versiones anteriores de .NET Framework.

             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
             [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

             El código que usa las nuevas API de criptografía en .NET Framework 4.6 se puede reescribir del siguiente modo para evitar la conversión.

             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
             [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

    - **Compatibilidad con la conversión de fechas y horas a o desde la hora de Unix**

         Se han agregado los siguientes métodos nuevos a la estructura <xref:System.DateTimeOffset> para admitir la conversión de valores de fecha y hora a o desde la hora de Unix:

        - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

        - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - **Modificadores de compatibilidad**

         La nueva clase <xref:System.AppContext> agrega una nueva característica de compatibilidad que permite a los autores de bibliotecas proporcionar a sus usuarios un mecanismo uniforme para cancelar la participación de la nueva funcionalidad. Establece un contrato flexible entre los componentes para poder comunicar una solicitud de cancelación de la participación. Esta capacidad normalmente es importante cuando se realiza un cambio en la funcionalidad existente. Por el contrario, la nueva funcionalidad participa de forma implícita.

         Con <xref:System.AppContext>, las bibliotecas definen y exponen modificadores de compatibilidad, mientras que el código que depende de ellas puede configurar dichos modificadores para que afecten al comportamiento de la biblioteca. De forma predeterminada, las bibliotecas proporcionan la nueva funcionalidad y solo la modifican (es decir, ofrecen la funcionalidad anterior) si el modificador está establecido.

         Una aplicación (o una biblioteca) puede declarar el valor de un modificador (que es siempre un valor <xref:System.Boolean>) que define una biblioteca dependiente. El modificador siempre es implícitamente `false`. Cuando el modificador se establece en `true`, se habilita. Cuando el modificador se establece explícitamente en `false`, proporciona el nuevo comportamiento.

        ```csharp
        AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
        ```

         La biblioteca debe comprobar si un consumidor declaró el valor del conmutador y, después, actuar en consecuencia.

        ```csharp
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

        - *Modificador*.*espacio de nombres*.*nombre del modificador*

        - *Modificador*.*biblioteca*.*nombre del modificador*

    - **Cambios en el modelo asincrónico basado en tareas (TAP)**

         Para las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], los objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> heredan la referencia cultural y la referencia cultural de interfaz de usuario del subproceso que realiza la llamada. No se ve afectado el comportamiento de las aplicaciones que tienen como destino las versiones anteriores de .NET Framework o que no especifican una versión concreta de .NET Framework. Para obtener más información, vea la sección "Referencia cultural y operaciones asincrónicas basadas en tareas" del tema sobre la clase <xref:System.Globalization.CultureInfo>.

         La clase <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> le permite representar datos de ambiente locales de un flujo de control asincrónico determinado, por ejemplo, un método `async`. Se puede usar para conservar los datos en todos los subprocesos. También puede definir un método de devolución de llamada que se le notifique al cambiar los datos de ambiente, ya sea porque se ha cambiado la propiedad <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> de forma explícita o porque el subproceso ha encontrado una transición de contexto.

         Se han agregado tres prácticos métodos, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType>, al patrón asincrónico basado en tareas (TAP) para que devuelva las tareas completadas en un estado determinado.

         La clase <xref:System.IO.Pipes.NamedPipeClientStream> ahora admite la comunicación asincrónica con su nuevo método <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. .

    - **EventSource ahora permite escribir en el Registro de eventos**

         Ahora puede usar la clase <xref:System.Diagnostics.Tracing.EventSource> para registrar mensajes administrativos u operativos en el registro de eventos, además de cualquier sesión ETW existente que se haya creado en el equipo. Anteriormente, tenía que usar el paquete de NuGet Microsoft.Diagnostics.Tracing.EventSource para poder aprovechar esta funcionalidad, que ahora está integrada en .NET Framework 4.6.

         El paquete de NuGet y .NET Framework 4.6 se han actualizado con las siguientes características:

        - **Eventos dinámicos**

             Permite eventos definidos "sobre la marcha" sin crear métodos de eventos.

        - **Cargas enriquecidas**

             Permite que las matrices y clases con atributos especiales, así como los tipos primitivos, se pasen como carga

        - **Seguimiento de actividad**

             Hace que los eventos de inicio y de detención etiqueten eventos entre ellos con un identificador que representa todas las actividades actualmente activas.

         Para admitir estas características, se ha agregado el método <xref:System.Diagnostics.Tracing.EventSource.Write%2A> sobrecargado a la clase <xref:System.Diagnostics.Tracing.EventSource>.

- **Windows Presentation Foundation (WPF)**

    - **Mejoras en el HDPI**

         Se ha mejorado la compatibilidad con HDPI en WPF en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Se han hecho cambios en el redondeo del diseño para reducir las instancias de recorte en los controles que contienen bordes. De forma predeterminada, esta característica solo está habilitada si se establece <xref:System.Runtime.Versioning.TargetFrameworkAttribute> en .NET 4.6.  Las aplicaciones que tienen como destino versiones anteriores de .NET Framework y que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] pueden participar en el nuevo comportamiento agregando la siguiente línea a la sección [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:

        ```xml
        <AppContextSwitchOverrides
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
        />
        ```

         Actualmente, las ventanas de WPF que ocupan varios monitores con diferentes valores de PPP (configuración de varios PPP) se representan completamente sin regiones oscurecidas. Puede deshabilitar este comportamiento agregando la siguiente línea a la sección `<appSettings>` del archivo app.config:

        ```xml
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>
        ```

         Se ha agregado a <xref:System.Windows.Input.Cursor?displayProperty=nameWithType> compatibilidad para cargar automáticamente el cursor derecho según la configuración de PPP.

    - **Mejor si es táctil**

         Los informes de los clientes en [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) acerca del comportamiento impredecible de la función táctil se han tratado en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Ahora, el umbral de doble punteo de las aplicaciones de WPF y de la Tienda Windows es el mismo en Windows 8.1 y versiones superiores.

    - **Compatibilidad con las ventanas secundarias transparentes**

         En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], WPF admite las ventanas secundarias transparentes en Windows 8.1 y versiones superiores, de manera que puede crear ventanas secundarias transparentes y no rectangulares en las ventanas de nivel superior. Puede habilitar esta característica estableciendo la propiedad <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> en `true`.

- **Windows Communication Foundation (WCF)**

    - **Compatibilidad con SSL**

         WCF ahora admite la versión con SSL TLS 1.1 y TLS 1.2, además de SSL 3.0 y TLS 1.0, al usar NetTcp con la autenticación de cliente y la seguridad de transporte. Ahora se puede seleccionar el protocolo que se quiere usar o bien deshabilitar protocolos antiguos menos seguros; para ello, establezca la propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> o agregue lo siguiente a un archivo de configuración.

        ```xml
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

    - **Enviar mensajes con diferentes conexiones HTTP**

         Ahora WCF permite que los usuarios se aseguren de que se han enviado determinados mensajes con diferentes conexiones HTTP subyacentes. Existen dos modos para hacer esto:

        - **Usar un prefijo de nombre de grupo de conexión**

             Los usuarios pueden especificar una cadena que WCF usará como prefijo del nombre del grupo de conexión. Se envían dos mensajes con prefijos diferentes por distintas conexiones HTTP subyacentes. Establezca el prefijo agregando un par clave-valor a la propiedad <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> del mensaje. La clave es "httpTransporteConexiónGrupoNombrePrefijo"; el valor es el prefijo deseado.

        - **Usar distintos generadores de canales**

             Los usuarios también pueden habilitar una característica que garantiza que los mensajes enviados por canales creados por distintos generadores de canales usen diferentes conexiones HTTP subyacentes. Para habilitar esta característica, los usuarios deben establecer el siguiente valor `appSetting` en `true`:

            ```xml
            <appSettings>
               <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
            </appSettings>
            ```

- **Windows Workflow Foundation (WWF)**

     Ahora puede especificar los segundos durante los que un servicio de flujo de trabajo retendrá una solicitud de operación fuera de servicio cuando haya un marcador que no sea de protocolo pendiente antes de que expire la solicitud. Un marcador "no de protocolo" es un marcador que no está relacionado con las actividades de recepción pendientes. Algunas actividades crean marcadores no de protocolo dentro de su implementación, por lo que es posible que no sea obvio que exista un marcador no de protocolo. Entre ellas se encuentran Estado y Selección. Si tiene un servicio de flujo de trabajo implementado con un equipo de estado o que contiene una actividad de selección, lo más probable es que tenga marcadores no de protocolo. Especifique el intervalo agregando una línea como la siguiente a la sección `appSettings` del archivo app.config:

    ```xml
    <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
    ```

     El valor predeterminado es de 60 segundos. Si `value` se establece en 0, las solicitudes fuera de servicio se rechazan inmediatamente con un error que contiene un texto similar a este:

    ```
    Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees. 
    ```

     Este es el mismo mensaje que aparece si recibe un mensaje de operación fuera de servicio y no hay ningún marcador que no sea de protocolo.

     Si el valor del elemento `FilterResumeTimeoutInSeconds` es distinto de cero, hay marcadores no de protocolo y el intervalo de tiempo de espera expira, se produce un error en la operación con un mensaje de tiempo de espera.

- **Transacciones**

     Ahora puede incluir el identificador de transacción distribuida para la transacción que provocó que se produjera una excepción derivada de <xref:System.Transactions.TransactionException>. Para ello, agregue la siguiente clave a la sección `appSettings` del archivo app.config:

    ```xml
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/> 
    ```

     El valor predeterminado es `false`.

- **Redes**

    - **Reutilización del socket**

         Windows 10 incluye un nuevo algoritmo de red de alta escalabilidad que optimiza los recursos del equipo con la reutilización de los puertos locales para las conexiones TCP salientes. .NET Framework 4.6 es compatible con este algoritmo y permite que las aplicaciones de .NET aprovechen el nuevo comportamiento. En versiones anteriores de Windows había un límite de conexiones simultáneas artificial (normalmente de 16.384, el tamaño predeterminado del intervalo de puertos dinámicos) y esto podía limitar la escalabilidad de un servicio provocando el agotamiento de puertos durante la carga.

         Se han agregado dos API nuevas a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] para permitir la reutilización de puertos, lo que elimina de forma eficaz el límite de 64 K de las conexiones simultáneas:

        - El valor de enumeración <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType>.

        - Propiedad <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType>

         De forma predeterminada, la propiedad <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> es `false`, a menos que el valor `HWRPortReuseOnSocketBind` de la clave del Registro `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` se establezca en 0x1. Para habilitar la reutilización del puerto local en las conexiones HTTP, establezca la propiedad <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> en `true`. Esto hace que todas las conexiones de socket TCP salientes de <xref:System.Net.Http.HttpClient> y <xref:System.Net.HttpWebRequest> usen una nueva opción de socket de Windows 10, [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), que permite la reutilización del puerto local.

         Los desarrolladores que crean una aplicación solo de sockets pueden especificar la opción <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> al llamar a un método (como <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>) para que los sockets de salida reutilicen los puertos locales durante el enlace.

    - **Compatibilidad con nombres de dominio internacionales y PunyCode**

         Se ha agregado una nueva propiedad, <xref:System.Uri.IdnHost%2A>, a la clase <xref:System.Uri> para ofrecer una mejor compatibilidad con los nombres de dominio internacionales y PunyCode.

- **Cambio de tamaño en controles de Windows Forms**

     Esta característica se amplió en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] para incluir los tipos <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.ToolStripSplitButton> y el rectángulo especificado por la propiedad <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> que se usa al dibujar un <xref:System.Drawing.Design.UITypeEditor>.

     Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **Compatibilidad para codificaciones de páginas de códigos**

      [!INCLUDE[net_core](../../../includes/net-core-md.md)] primarily supports the Unicode encodings and by default provides limited support for code page encodings. You can add support for code page encodings available in the .NET Framework but unsupported in [!INCLUDE[net_core](../../../includes/net-core-md.md)] by registering code page encodings with the <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType> method. For more information, see <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.

- **.NET Native**

     Las aplicaciones de Windows para Windows 10 que tienen como destino [!INCLUDE[net_core](../../../includes/net-core-md.md)] y están escritas en C# o Visual Basic pueden aprovechar una nueva tecnología que compila las aplicaciones en código nativo en lugar de IL. Generan aplicaciones que se caracterizan por un inicio y tiempos de ejecución más rápidos. Para obtener más información, consulte [Compilar aplicaciones con .NET Native](../../../docs/framework/net-native/index.md). Para obtener información general sobre .NET Native en la que se examina cómo difiere de la compilación JIT y de NGEN, y lo que eso conlleva para el código, vea [.NET Native y compilación](../../../docs/framework/net-native/net-native-and-compilation.md).

     Las aplicaciones se compilan en código nativo de forma predeterminada cuando se compilan con Visual Studio 2015. Para obtener más información, vea [Introducción a .NET Native](../../../docs/framework/net-native/getting-started-with-net-native.md).

     Para admitir la depuración de aplicaciones .NET Native, se agregó una serie de interfaces y enumeraciones nuevas a la API de depuración no administrada. Para obtener más información, consulte el tema [Depuración (Referencia de la API no administrada)](../../../docs/framework/unmanaged-api/debugging/index.md).

- **Paquetes de .NET Framework de código abierto**

      [!INCLUDE[net_core](../../../includes/net-core-md.md)] packages such as the immutable collections, [SIMD APIs](http://go.microsoft.com/fwlink/?LinkID=518639), and networking APIs such as those found in the <xref:System.Net.Http> namespace are now available as open source packages on [GitHub](https://github.com/). To access the code, see [NetFx on GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). For more information and how to contribute to these packages, see [.NET Core and Open-Source](../../../docs/framework/get-started/net-core-and-open-source.md), [.NET Home Page on GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).

 [Volver al principio](#introduction)

<a name="v452"></a> 
## <a name="whats-new-in-the-net-framework-452"></a>Novedades de .NET Framework 4.5.2

- **Nuevas API para aplicaciones de ASP.NET.** Los nuevos métodos <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> y <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> le permiten inspeccionar y modificar encabezados y códigos de estado cuando se vuelca la respuesta de la aplicación cliente. Puede usar estos métodos en lugar de los eventos <xref:System.Web.HttpApplication.PreSendRequestHeaders> y <xref:System.Web.HttpApplication.PreSendRequestContent>, ya que son más eficientes y fiables.

     El método <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> permite programar pequeños elementos de trabajo en segundo plano. ASP.NET realiza un seguimiento de estos elementos y evita que IIS termine el proceso de trabajo de manera abrupta hasta que se completen todos los elementos de trabajo en segundo plano. Este método no se puede invocar desde fuera del dominio de una aplicación administrada de ASP.NET.

     Las nuevas propiedades <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> y <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> devuelven valores booleanos que indican si los encabezados de respuesta se han escrito. Puede usar estas propiedades para comprobar si se realizan correctamente las llamadas a las API como <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (que producen excepciones si se han escrito los encabezados).

- **Cambio de tamaño en controles de Windows Forms** Esta característica se ha ampliado. Ahora se puede usar el valor de PPP del sistema para cambiar el tamaño de componentes de los siguientes controles adicionales (por ejemplo, la flecha desplegable en cuadros combinados):

     <xref:System.Windows.Forms.ComboBox>    <xref:System.Windows.Forms.ToolStripComboBox>    <xref:System.Windows.Forms.ToolStripMenuItem>    <xref:System.Windows.Forms.Cursor>    <xref:System.Windows.Forms.DataGridView>    <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

     Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

- **Nueva característica de flujo de trabajo.** Un administrador de recursos que usa el método <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> (y, por lo tanto, implementa la interfaz <xref:System.Transactions.IPromotableSinglePhaseNotification>) puede usar el nuevo método <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> para pedir lo siguiente:

    - Promocionar la transacción a una transacción de MSDTC (Coordinador de transacciones distribuidas de Microsoft).

    - Reemplace <xref:System.Transactions.IPromotableSinglePhaseNotification> con una <xref:System.Transactions.ISinglePhaseNotification>, que es una inscripción duradera que admite confirmaciones de fase única.

     Esto puede realizarse en el mismo dominio de la aplicación y no requiere que ningún código sin administrar adicional interactúe con MSDTC para realizar la promoción. Solo se puede llamar al nuevo método cuando existe una llamada pendiente de <xref:System.Transactions?displayProperty=nameWithType> al método <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote` que está implementado por una inscripción que puede promocionarse.

- **Mejoras de generación de perfiles.** Las siguientes API de generación de perfiles no administradas proporcionan una generación de perfiles más sólida:

     [COR_PRF_ASSEMBLY_REFERENCE_INFO Structure](../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) [COR_PRF_HIGH_MONITOR Enumeration](../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) [GetAssemblyReferences Method](../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) [GetEventMask2 Method](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) [SetEventMask2 Method](../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) [AddAssemblyReference Method](../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

     Las implementaciones de `ICorProfiler` anteriores eran compatibles con la carga diferida de ensamblados dependientes. Las nuevas API de generación de perfiles requieren que los ensamblados dependientes insertados por el generador de perfiles se carguen inmediatamente, en lugar de cargarse cuando la aplicación se haya inicializado por completo. Este cambio no afecta a los usuarios de las API de `ICorProfiler` existentes.

- **Mejoras en la depuración.** Las API de depuración no administradas proporcionan una mejor integración con un generador de perfiles. Ahora se puede acceder a metadatos insertados por el generador de perfiles, así como a variables locales y código producidos por solicitudes de ReJIT del compilador en la depuración de volcados.

     [SetWriteableMetadataUpdateMode Method](../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) [EnumerateLocalVariablesEx Method](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) [GetLocalVariableEx Method](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) [GetCodeEx Method](../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) [GetActiveReJitRequestILCode Method](../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md) [GetInstrumentedILMap Method](../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **Cambios en el seguimiento de eventos.** .NET Framework 4.5.2 permite realizar el seguimiento de actividades fuera del proceso, basado en Seguimiento de eventos para Windows (ETW), para una mayor área expuesta. Esto permite a los proveedores de Administración avanzada de energía (APM) proporcionar herramientas sencillas que realicen un seguimiento preciso de solicitudes y actividades individuales en distintos subprocesos.  Estos eventos solo se desencadenan cuando son habilitados por los controladores de ETW; por lo tanto, los cambios no afectan a código de ETW escrito anteriormente o a código que se ejecute cuando ETW esté deshabilitado.

- **Promover una transacción y convertirla en una inscripción duradera**

     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> es una API nueva que se ha agregado a .NET Framework 4.5.2 y 4.6:

    ```csharp
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                              IPromotableSinglePhaseNotification promotableNotification,
                                              ISinglePhaseNotification enlistmentNotification,
                                              EnlistmentOptions enlistmentOptions)
    ```

     El método se puede usar con una inscripción creada previamente por <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> en respuesta al método <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Pide a `System.Transactions` que promueva la transacción a una transacción MSDTC y que "convierta" la inscripción que se puede promover en una inscripción duradera. Cuando este método finalice correctamente, `System.Transactions` ya no hará referencia a la interfaz <xref:System.Transactions.IPromotableSinglePhaseNotification> y todas las notificaciones futuras llegarán a la interfaz <xref:System.Transactions.ISinglePhaseNotification> proporcionada. La inscripción en cuestión debe actuar como inscripción duradera y admitir el registro y la recuperación de transacciones. Vea <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> para obtener más información. Además, la inscripción debe admitir <xref:System.Transactions.ISinglePhaseNotification>.  *Solo* se puede llamar a este método al procesar una llamada de <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Si no es el caso, se produce una excepción <xref:System.Transactions.TransactionException>.

 [Volver al principio](#introduction)

<a name="v451"></a> 
## <a name="whats-new-in-the-net-framework-451"></a>Novedades de .NET Framework 4.5.1
 **Actualizaciones de abril de 2014**:

- [Visual Studio 2013 Update 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) incluye actualizaciones para las plantillas de la Biblioteca de clases portable para garantizar la compatibilidad en los escenarios siguientes:

    - Puede usar las API de Windows en tiempo de ejecución en bibliotecas portables cuyo destino sea Windows 8.1, Windows Phone 8.1 y Windows Phone Silverlight 8.1.

    - Puede incluir XAML (tipos de Windows.UI.XAML) en las bibliotecas portables cuyo destino es Windows 8.1 o Windows Phone 8.1. Se admiten las siguientes plantillas de XAML: página en blanco, diccionario de recursos, control basado en modelo y control de usuario.

    - Se puede crear un componente de Windows en tiempo de ejecución portable (archivo .winmd) para usarlo en aplicaciones de la Tienda que tengan como destino Windows 8.1 y Windows Phone 8.1.

    - Puede cambiar el destino de una biblioteca de clases de la Tienda Windows o la Tienda de Windows Phone como biblioteca de clases portable.

     Para obtener más información sobre estos cambios, vea [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

- El conjunto de contenido de .NET Framework ahora incluye documentación para [!INCLUDE[net_native](../../../includes/net-native-md.md)], que es una tecnología de precompilación para crear e implementar aplicaciones de Windows. [!INCLUDE[net_native](../../../includes/net-native-md.md)] compila aplicaciones directamente en código nativo, en lugar de hacerlo en un lenguaje intermedio (IL), lo que mejora el rendimiento. Para obtener información detallada, vea [Compilar aplicaciones con .NET Native](../../../docs/framework/net-native/index.md).

- [.NET Framework Reference Source](http://referencesource.microsoft.com/) proporciona una nueva experiencia de navegación y mejores funciones. Ahora puede navegar en línea por el código fuente de .NET Framework, [descargar la referencia](http://referencesource.microsoft.com/download.html) para visualizarlo sin conexión y examinar los orígenes (incluidas revisiones y actualizaciones) durante la depuración. Para obtener más información, vea la entrada de blog [A new look for .NET Reference Source](https://blogs.msdn.microsoft.com/dotnet/2014/02/24/a-new-look-for-net-reference-source/) (Un nuevo aspecto para el origen de referencia de .NET).

 Estas son las principales características nuevas y mejoras realizadas en .NET Framework 4.5.1:

- Redirección automática de enlace de ensamblados. A partir de [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], cuando se compila una aplicación cuyo destino es [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], se pueden agregar al archivo de configuración de la aplicación redirecciones de enlace si la aplicación o sus componentes hacen referencia a varias versiones del mismo ensamblado. Esta característica también se puede habilitar en proyectos que tienen como destino versiones anteriores de .NET Framework. Para obtener más información, vea [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).

- Capacidad de recopilar información de diagnóstico para ayudar a los desarrolladores a mejorar el rendimiento de las aplicaciones de servidor y en la nube. Para obtener más información, vea los métodos <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> y <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> de la clase <xref:System.Diagnostics.Tracing.EventSource>.

- Capacidad de compactar explícitamente el montón de objetos grandes (LOH) durante la recolección de elementos no utilizados. Para obtener más información, vea la propiedad <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>.

- Mejoras adicionales de rendimiento como, por ejemplo, la suspensión de la aplicación ASP.NET, mejoras de JIT con varios núcleos o reducción del tiempo de inicio de la aplicación tras una actualización de .NET Framework. Para obtener información detallada, vea las entradas de blog relativas al [anuncio de .NET Framework 4.5.1](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/) y la [suspensión de aplicaciones ASP.NET](https://blogs.msdn.microsoft.com/dotnet/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting/).

 Las mejoras en Windows Forms son las siguientes:

- Cambio de tamaño en controles de Windows Forms. Puede usar el valor de PPP del sistema para cambiar el tamaño de los componentes de controles (por ejemplo, los iconos que aparecen en una cuadrícula de propiedades); para ello, active esta opción con una entrada en el archivo de configuración de la aplicación (app.config). Actualmente, esta característica es compatible con los siguientes controles de Windows Forms:

     <xref:System.Windows.Forms.PropertyGrid>    <xref:System.Windows.Forms.TreeView>    Algunos aspectos de <xref:System.Windows.Forms.DataGridView> (consulte la lista completa de controles compatibles en [Nuevas características en 4.5.2](#v452))

     Para activar esta característica, agregue un nuevo elemento \<appSettings> al archivo de configuración (app.config) y establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true`:

    ```xml
    <appSettings>
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
    </appSettings>
    ```

 Algunas de las mejoras realizadas durante la depuración de las aplicaciones de .NET Framework en [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] son:

- Valores devueltos en el depurador de Visual Studio. Al depurar una aplicación administrada en [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], en la ventana Automático se muestran los valores y tipos devueltos de los métodos. Esta información está disponible para el escritorio, la Tienda Windows y las aplicaciones Windows Phone. Para obtener más información, vea [Examinar los valores devueltos de llamadas a métodos](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) en MSDN Library.

- Editar y continuar en aplicaciones de 64 bits. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] admite la característica Editar y continuar en aplicaciones administradas de 64 bits para el escritorio, la Tienda Windows y Windows Phone. Las limitaciones existentes siguen en vigor para las aplicaciones de 32 bits y 64 bits (vea la última sección del artículo [Cambios admitidos en el código (C#)](/visualstudio/debugger/supported-code-changes-csharp)).

- Depuración asincrónica. Para facilitar la depuración de aplicaciones asincrónicas en [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], la pila de llamadas oculta el código de infraestructura proporcionado por los compiladores para permitir la programación asincrónica y, además, encadena los principales marcos lógicos para que pueda seguir la ejecución lógica del programa con mayor claridad. La ventana Tareas reemplaza a la ventana Tareas paralelas, donde se muestran las tareas relacionadas con un punto de interrupción determinado, así como las demás tareas que actualmente están activas o programadas en la aplicación. Puede obtener más información sobre esta característica en la sección "Async-aware debugging" (Depuración asincrónica) de la publicación sobre [el anuncio de .NET Framework 4.5.1](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/).

- Mayor compatibilidad con las excepciones de los componentes de Windows en tiempo de ejecución. En [!INCLUDE[win81](../../../includes/win81-md.md)], las excepciones que se inician en aplicaciones de la Tienda Windows conservan información sobre el error que provocó la excepción, incluso entre diferentes lenguajes. Puede obtener más información sobre esta característica en la sección "Windows Store app development" (Desarrollo de aplicaciones de la Tienda Windows) de la publicación del [anuncio de .NET Framework 4.5.1](https://blogs.msdn.microsoft.com/dotnet/2013/06/26/announcing-the-net-framework-4-5-1-preview/). 

 A partir de [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], puede utilizar la [herramienta de optimización guiada por perfiles administrados (Mpgo.exe)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) para optimizar las aplicaciones de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], así como las aplicaciones de escritorio.

 Para conocer las nuevas características de ASP.NET 4.5.1, vea [ASP.NET 4.5.1 y Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) en el sitio de ASP.NET.

 [Volver al principio](#introduction)

<a name="core"></a> 
## <a name="whats-new-in-the-net-framework-45"></a>Novedades de .NET Framework 4.5

### <a name="core-new-features-and-improvements"></a>Principales características nuevas y mejoras

- Capacidad para reducir los reinicios del sistema mediante la detección y cierre de las aplicaciones de .NET Framework 4 durante la implementación. Vea [Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5](../../../docs/framework/deployment/reducing-system-restarts.md).

- Compatibilidad con matrices mayores de 2 gigabytes (GB) en plataformas de 64 bits. Esta característica se puede habilitar en el archivo de configuración de la aplicación. Consulte el elemento [\<gcAllowVeryLargeObjects>](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), donde también se indican otras restricciones de tamaño de objeto y de tamaño de matriz.

- Mayor rendimiento a través de la recolección de elementos no utilizados en segundo plano en el caso de los servidores. Cuando se usa la recolección de elementos no utilizados de los servidores en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], se habilita automáticamente la recolección de elementos no utilizados en segundo plano. Vea la sección sobre la recolección de elementos no utilizados en segundo plano de los servidores del tema [Fundamentals of Garbage Collection](../../../docs/standard/garbage-collection/fundamentals.md) (Fundamentos de la recolección de elementos no utilizados).

- Compilación Just-in-time (JIT) en segundo plano, que se encuentra disponible opcionalmente en los procesadores de varios núcleos para mejorar el rendimiento de la aplicación. Vea <xref:System.Runtime.ProfileOptimization>.

- Capacidad para limitar el tiempo durante el cual el motor de expresiones regulares intentará resolver una expresión regular antes de agotar el tiempo de espera. Vea la propiedad <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType>.

- Capacidad para definir la referencia cultural predeterminada de un dominio de aplicación. Vea la descripción de la clase <xref:System.Globalization.CultureInfo>.

- Compatibilidad de la consola con la codificación Unicode (UTF-16). Vea la descripción de la clase <xref:System.Console>.

- Compatibilidad con el control de versiones de ordenación cultural de cadenas y datos de comparación. Vea la descripción de la clase <xref:System.Globalization.SortVersion>.

- Mayor rendimiento al recuperar recursos. Vea [Empaquetar e implementar recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).

- Mejoras en la compresión Zip para reducir el tamaño de un archivo comprimido. Vea el espacio de nombres <xref:System.IO.Compression?displayProperty=nameWithType>.

- Capacidad de personalizar un contexto de reflexión para invalidar el comportamiento predeterminado de reflexión a través de la clase <xref:System.Reflection.Context.CustomReflectionContext>.

- Compatibilidad con la versión 2008 del estándar de internacionalización de nombres de dominio de las aplicaciones (IDNA) cuando se utiliza la clase <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> en [!INCLUDE[win8](../../../includes/win8-md.md)].

- Delegación de comparación de cadenas en el sistema operativo, que implementa Unicode 6.0, cuando se usa .NET Framework en [!INCLUDE[win8](../../../includes/win8-md.md)]. Al ejecutarse en otras plataformas, .NET Framework incluye sus propios datos de comparación de cadenas, que implementan Unicode 5.x. Vea la clase <xref:System.String> y la sección Comentarios de la clase <xref:System.Globalization.SortVersion>.

- Capacidad para calcular los códigos hash de cadenas en cada dominio de aplicación. Vea el elemento [\<UseRandomizedStringHashAlgorithm>](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).

- Compatibilidad con la reflexión de tipos dividida entre las clases <xref:System.Type> y <xref:System.Reflection.TypeInfo>. Vea [Reflection in the .NET Framework for Windows Store Apps](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md) (Reflexión en .NET Framework para aplicaciones de la Tienda Windows).

### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Managed Extensibility Framework (MEF) cuenta con las siguientes características nuevas:

- Compatibilidad con los tipos genéricos.

- Modelo de programación basado en convenciones que permite crear elementos basándose en convenciones de nomenclatura en lugar de en atributos.

- Ámbitos múltiples.

- Un subconjunto de MEF que puede usar cuando cree aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Este subconjunto está disponible como un [paquete descargable](http://go.microsoft.com/fwlink/?LinkId=256238) en la galería de NuGet. Para instalar el paquete, abra el proyecto en Visual Studio, elija **Administrar paquetes de NuGet** en el menú **Proyecto** y busque en línea el paquete `Microsoft.Composition`.

 Para obtener más información, vea [Managed Extensibility Framework (MEF)](../../../docs/framework/mef/index.md).

### <a name="asynchronous-file-operations"></a>Operaciones de archivo asincrónicas
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], se agregaron nuevas características asincrónicas a los lenguajes C# y Visual Basic. Estas características agregan un modelo basado en tareas para realizar operaciones asincrónicas. Para utilizar este nuevo modelo, use los métodos asincrónicos de las clases de E/S. Vea [E/S de archivos asincrónica](../../../docs/standard/io/asynchronous-file-i-o.md).

<a name="tools"></a> 
### <a name="tools"></a>Herramientas
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], el generador de archivos de recursos (Resgen.exe) permite crear un archivo .resw para su uso en aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] desde un archivo .resources incrustado en un ensamblado de .NET Framework. Para obtener más información, vea [Resgen.exe (Resource File Generator)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) (Resgen.exe [generador de archivos de recursos]).

 La optimización guiada por perfiles administrados (Mpgo.exe) permite mejorar el tiempo de inicio de la aplicación, la utilización de la memoria (el tamaño del espacio de trabajo) y el rendimiento mediante la optimización de los ensamblados de imagen nativos. La herramienta de línea de comandos genera datos de perfil para los ensamblados nativos de aplicación de la imagen. Vean [Mpgo.exe (Managed Profile Guided Optimization Tool)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) (Mpgo.exe [herramienta de optimización guiada por perfiles administrados]). A partir de [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], puede utilizar Mpgo.exe para optimizar las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] así como las aplicaciones de escritorio.

<a name="parallel"></a> 
### <a name="parallel-computing"></a>Informática en paralelo
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] cuenta con varias características y mejoras nuevas para el procesamiento informático en paralelo. Entre estas se incluyen un rendimiento mejorado, mayor control, mejor compatibilidad con la programación asincrónica, una nueva biblioteca de flujo de datos y mejor compatibilidad para la depuración y el análisis de rendimiento en paralelo. Vea la entrada [What’s New for Parallelism in .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) (Novedades de paralelismo en .NET 4.5) de la sección sobre Programación en paralelo del blog sobre .NET.

<a name="web"></a> 
### <a name="web"></a>Web
 ASP.NET 4.5 y 4.5.1 incorporan el enlace de modelos de formularios Web Forms, compatibilidad con WebSocket, controladores asincrónicos, mejoras de rendimiento y muchas otras características. Para obtener más información, vea los siguientes recursos:

- [ASP.NET 4.5 y Visual Studio 2012](http://msdn.microsoft.com/library/ac9bb7f6-f094-4af7-bad0-acf49a5dbc55) en MSDN Library.

- [ASP.NET 4.5.1 y Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) en el sitio de ASP.NET.

<a name="networking"></a> 
### <a name="networking"></a>Redes
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] proporciona una nueva interfaz de programación para aplicaciones HTTP. Para obtener más información, vea los nuevos espacios de nombres <xref:System.Net.Http?displayProperty=nameWithType> y <xref:System.Net.Http.Headers?displayProperty=nameWithType>.

 También se incluye compatibilidad con una nueva interfaz de programación para aceptar e interactuar con una conexión WebSocket mediante el objeto <xref:System.Net.HttpListener> existente y las clases relacionadas. Para obtener más información, vea el nuevo espacio de nombres <xref:System.Net.WebSockets> y la clase <xref:System.Net.HttpListener>.

 Además, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] incluye las siguientes mejoras de red:

- Compatibilidad de URI conforme a RFC. Para obtener más información, vea <xref:System.Uri> y las clases relacionadas.

- Compatibilidad con el análisis de nombres de dominio internacionalizados (IDN). Para obtener más información, vea <xref:System.Uri> y las clases relacionadas.

- Compatibilidad con la internacionalización de direcciones de correo electrónico (EAI). Para obtener más información, vea el espacio de nombres <xref:System.Net.Mail>.

- Compatibilidad mejorada de IPv6. Para obtener más información, vea el espacio de nombres <xref:System.Net.NetworkInformation>.

- Compatibilidad con el socket de modo dual. Para obtener más información, vea las clases <xref:System.Net.Sockets.Socket> y <xref:System.Net.Sockets.TcpListener>.

<a name="client"></a> 
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Windows Presentation Foundation (WPF) contiene cambios y mejoras en las áreas siguientes:

- El nuevo control <xref:System.Windows.Controls.Ribbon.Ribbon>, que permite implementar una interfaz de usuario en forma de cinta que incluye una barra de herramientas de acceso rápido, un menú de aplicación y pestañas.

- La nueva interfaz <xref:System.ComponentModel.INotifyDataErrorInfo>, que admite la validación de datos sincrónica y asincrónica.

- Nuevas características para las clases <xref:System.Windows.Controls.VirtualizingPanel> y <xref:System.Windows.Threading.Dispatcher>.

- Rendimiento mejorado al mostrar conjuntos grandes de datos agrupados y al acceder a colecciones en subprocesos que no son de interfaz de usuario.

- Enlace de datos a propiedades estáticas, enlace de datos a tipos personalizados que implementan la interfaz <xref:System.Reflection.ICustomTypeProvider> y recuperación de información de enlace de datos desde una expresión de enlace.

- Reposición de los datos a medida que cambian los valores (modelado dinámico).

- Capacidad de comprobar si el contexto de datos de un contenedor de elementos está desconectado.

- Capacidad de establecer la cantidad de tiempo que debe transcurrir entre los cambios de propiedad y las actualizaciones del origen de datos.

- Compatibilidad mejorada para implementar patrones de eventos débiles. Además, los eventos ahora pueden aceptar extensiones de marcado.

<a name="windows_communication_foundation"></a> 
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], se han agregado las características siguientes para facilitar la creación y el mantenimiento de aplicaciones de Windows Communication Foundation (WCF):

- Simplificación de los archivos de configuración generados.

- Compatibilidad con el desarrollo del contrato en primer lugar.

- Capacidad de configurar el modo de compatibilidad de ASP.NET más fácilmente.

- Cambios en los valores de propiedad de transporte predeterminados para reducir las probabilidades de tener que establecerlos.

- Actualizaciones de la clase <xref:System.Xml.XmlDictionaryReaderQuotas> que reducen las probabilidades de tener que configurar manualmente cuotas para los lectores de diccionarios XML.

- Validación de los archivos de configuración de WCF por parte de Visual Studio dentro del proceso de compilación, para que se puedan detectar errores de configuración antes de ejecutar la aplicación.

- Nueva compatibilidad con streaming asincrónico.

- Nueva asignación del protocolo HTTPS para facilitar la exposición de un extremo a través de HTTPS con Internet Information Services (IIS).

- Capacidad de generar metadatos en un solo documento WSDL anexando `?singleWSDL` a la dirección URL del servicio.

- Compatibilidad con Websockets para permitir una comunicación bidireccional verdadera a través de los puertos 80 y 443 con características de rendimiento similares a las del transporte TCP.

- Compatibilidad para configurar servicios en el código.

- Información sobre herramientas del editor XML.

- Compatibilidad con el almacenamiento en caché de <xref:System.ServiceModel.ChannelFactory>.

- Compatibilidad con la compresión de codificadores binarios.

- Compatibilidad con un transporte UDP que permite a los desarrolladores escribir servicios que utilizan mensajería de tipo "desencadenar y omitir”. Un cliente envía un mensaje a un servicio y no espera ninguna respuesta de él.

- Capacidad de admitir varios modos de autenticación en un único extremo de WCF mediante el uso de transporte HTTP y seguridad de transporte.

- Compatibilidad con los servicios WCF que utilizan nombres de dominio internacionalizados (IDN).

 Para obtener más información, vea [Novedades de Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).

<a name="windows_workflow_foundation"></a> 
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)
 Se han agregado varias características nuevas a Windows Workflow Foundation (WF) en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], incluidas las siguientes:

- Flujos de trabajo de máquina de estados, que se incluyeron primero como parte de .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](http://go.microsoft.com/fwlink/?LinkID=215092)). Esta actualización incluía varias clases y actividades nuevas que permitían a los desarrolladores crear flujos de trabajo de máquina de estados. Estas clases y actividades se actualizaron para [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] con objeto de incluir:

    - Capacidad de establecer puntos de interrupción en estados

    - Capacidad de copiar y pegar transiciones en el Diseñador de flujo de trabajo

    - Compatibilidad del diseñador para la creación de transiciones de desencadenador compartidas

    - Actividades para crear flujos de trabajo de máquina de estados, incluidas: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> y <xref:System.Activities.Statements.Transition>

- Características mejoradas del Diseñador de flujo de trabajo, como las siguientes:

    - Funcionalidades de búsqueda de flujo de trabajo mejoradas en Visual Studio, incluidas **Búsqueda rápida** y **Buscar en archivos**.

    - Capacidad de crear automáticamente una actividad Secuencia cuando una segunda actividad secundaria se agrega a una actividad del contenedor y para incluir ambas actividades en la actividad Secuencia.

    - Compatibilidad con el movimiento panorámico, que permite cambiar la parte visible de un flujo de trabajo sin usar las barras de desplazamiento.

    - Una nueva vista **Esquema del documento**, en la que se muestran los componentes de un flujo de trabajo en una vista de esquema con forma de árbol y que le permite seleccionar un componente en la vista **Esquema del documento**.

    - Capacidad de agregar anotaciones a las actividades.

    - Capacidad de definir y consumir delegados de actividad mediante el Diseñador de flujo de trabajo.

    - Conexión e inserción automáticas para actividades y transiciones en los flujos de trabajo de máquina de estados y diagrama de flujo.

- Almacenamiento de la información de estado de vista de un flujo de trabajo en un único elemento del archivo XAML, para poder encontrar y editar fácilmente la información de estado de vista.

- Una actividad de contenedor NoPersistScope para evitar que se conserven las actividades secundarias.

- Compatibilidad con expresiones de C#:

    - Los proyectos de flujo de trabajo que usan Visual Basic utilizarán las expresiones de Visual Basic, y los proyectos de flujo de trabajo de C# utilizarán las expresiones de C#.

    - Los proyectos de flujo de trabajo de C# creados en Visual Studio 2010 y que tengan expresiones de Visual Basic son compatibles con los proyectos de flujo de trabajo de C# que usan expresiones de C#.

- Mejoras del control de versiones:

    - La nueva clase <xref:System.Activities.WorkflowIdentity>, que proporciona una asignación entre una instancia de flujo de trabajo guardada y su definición de flujo de trabajo.

    - Ejecución en paralelo de varias versiones de flujo de trabajo en el mismo host, incluido <xref:System.ServiceModel.Activities.WorkflowServiceHost>.

    - En la actualización dinámica, la capacidad de modificar la definición de una instancia de flujo de trabajo guardada.

- Desarrollo de servicios de flujo de trabajo de contrato en primer lugar, que proporciona compatibilidad para generar automáticamente actividades que busquen coincidencias en un contrato de servicio existente.

 Para obtener más información, vea [Novedades de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).

<a name="tailored"></a> 
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]
 Las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] están diseñadas para factores de forma específicos y aprovechan la eficacia del sistema operativo Windows. Un subconjunto de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o 4.5.1 está disponible para compilar aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] para Windows mediante C# o Visual Basic. Este subconjunto se denomina [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] y se explica en una [introducción](http://go.microsoft.com/fwlink/?LinkId=228491) del Centro de desarrollo de Windows.

<a name="portable"></a> 
### <a name="portable-class-libraries"></a>Bibliotecas de clases portables
 El proyecto de Biblioteca de clases portable de [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] (y versiones posteriores) permite escribir y compilar ensamblados administrados capaces de funcionar en múltiples plataformas de .NET Framework. Un proyecto de Biblioteca de clases portable le permite elegir las plataformas de destino (como Windows Phone y [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]). Los tipos y miembros disponibles en el proyecto se restringen automáticamente a los tipos y miembros comunes de estas plataformas. Para obtener más información, consulte [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

## <a name="see-also"></a>Vea también
 [.NET Framework y versiones fuera de banda](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Novedades de accesibilidad en .NET Framework](whats-new-in-accessibility.md)   
 [Novedades de Visual Studio 2017](/visualstudio/ide/whats-new-in-visual-studio)   
 [ASP.NET](/aspnet)   
 [What's New in Visual C++](/cpp/what-s-new-for-visual-cpp-in-visual-studio) (Novedades de Visual C++) 
