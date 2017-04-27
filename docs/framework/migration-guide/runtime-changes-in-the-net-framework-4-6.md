---
title: "Cambios en tiempo de ejecución en .NET Framework 4.6 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6
- application compatibility
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 77002c3d1b6553156c225b3efba9a2f29009915a
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-46"></a>Cambios en tiempo de ejecución en .NET Framework 4.6
En casos poco frecuentes, los cambios en tiempo de ejecución pueden afectar a las aplicaciones existentes que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en una versión posterior del tiempo de ejecución de .NET Framework. También conllevan comportamientos diferentes en las aplicaciones que se ejecutan en distintos entornos en tiempo de ejecución de .NET Framework. Incluyen cambios en las áreas siguientes:  
  
-   [Principal](#Core)  
  
-   [Data](#Data)  
  
-   [Redes](#Networking)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [Instalación e implementación](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [El nuevo compilador JIT de 64 bits](#RyuJIT)  
  
<a name="Core"></a>   
## <a name="core"></a>Principal  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|A partir de [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la clase <xref:System.Globalization.PersianCalendar> usa el algoritmo Hijri solar.|El algoritmo Hijri solar produce resultados idénticos al calendario persa actualmente en uso en Irán y Afganistán. También produce resultados que son idénticos al algoritmo anterior para las fechas de 1800 en el calendario gregoriano a 2023 en el calendario gregoriano. Las fechas que están fuera de ese intervalo pueden verse afectadas si la clase <xref:System.Globalization.PersianCalendar> se utiliza para realizar conversiones de fecha (por ejemplo, entre las fechas del calendario gregoriano y las fechas del calendario persa) o para determinar si un determinado año es un año bisiesto.<br /><br /> Debido al cambio, el valor de propiedad <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName> ha cambiado de 21 de marzo de 0622 a 22 de marzo de 0622 para sistemas en los que está instalado [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].<br /><br /> Para obtener más información, consulte el tema <xref:System.Globalization.PersianCalendar>.|Secundaria|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|Para el dominio de aplicación predeterminado, el valor de propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> procede de <xref:System.Runtime.Versioning.TargetFrameworkAttribute>, si existe, a menos que se defina explícitamente asignando un nombre a la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>.  En versiones anteriores de .NET Framework, el valor del atributo <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> es `null` a menos que se ejecute una serie de rutas de acceso de código especial o se cree un dominio de aplicación no predeterminado sin especificar explícitamente su plataforma de destino en la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>.<br /><br /> Para los dominios de aplicación no predeterminados, no cambia la forma en que se determina el valor de propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>. Si no se asigna explícitamente ningún valor a la propiedad <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>, el dominio de aplicación no predeterminado hereda del dominio de aplicación predeterminado el nombre de la plataforma de destino.|Para el dominio de aplicación predeterminado, <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> puede devolver un valor distinto de null cuando antes devolvía `null`. Este es el comportamiento deseable.|Borde|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|Si los certificados instalados en el sistema no son compatibles con .NET Framework, cuando se pasa un valor de `True` para el argumento `verbose` se devuelve una cadena válida. En versiones anteriores de .NET Framework, si se intenta acceder a la información de clave pública para los certificados no admitidos, en algunos casos se produce una excepción.|Este método es solo informativo; las notas de documentación que se generan pueden no ser coherentes entre las versiones de .NET Framework. Este cambio solo afecta a las aplicaciones que llaman al método `ToString(True)` y que tienen instalados certificados no compatibles con .NET Framework. Al devolver una cadena en lugar de producir una excepción, este cambio hace que el método sea más sólido.|Borde|  
|seguimiento de eventos para Windows (ETW)|En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y 4.6.1, el entorno en tiempo de ejecución produce <xref:System.ArgumentException> cuando dos nombres de evento solamente se distinguen por un sufijo "Start" o "Stop" (como cuando un evento se denomina `LogUser` y otro se denomina `LogUserStart`). En este caso, el entorno en tiempo de ejecución no puede crear el origen de eventos, que no puede emitir ningún registro.|Asegúrese de que no haya nombres de dos eventos que se diferencien únicamente por un sufijo "Start" o "Stop".<br /><br /> Este requisito desaparece a partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]; el entorno en tiempo de ejecución puede eliminar la ambigüedad de los nombres de evento que se diferencian únicamente por el sufijo "Start".|Borde|  
|Reflexión y COM distribuido (DCOM)|Los objetos de reflexión ya no se pueden pasar desde el código administrado a los clientes DCOM fuera de proceso. Este cambio afecta a los tipos siguientes: <xref:System.Reflection.Assembly>; <xref:System.Reflection.MemberInfo> y los tipos derivados, incluidos <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Type> y <xref:System.Reflection.TypeInfo>; <xref:System.Reflection.MethodBody>; <xref:System.Reflection.Module>, y <xref:System.Reflection.ParameterInfo>.|Las llamadas a [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx) para el objeto devuelven `E_NOINTERFACE`.|Secundaria|  
  
<a name="Data"></a>   
## <a name="data"></a>Datos  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Una conexión TCP/IP a una base de datos de SQL Server que se resuelve en `localhost`|A partir de [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], el intento de conexión produce el error "Error relacionado con la red o específico de la instancia mientras se establecía una conexión con el servidor SQL Server. No se encontró el servidor o éste no estaba accesible. Compruebe que el nombre de la instancia es correcto y que SQL Server está configurado para admitir conexiones remotas. (proveedor: interfaces de red de SQL, error: 26 -	Error al buscar el servidor o instancia especificado)"|Se ha resuelto este problema, y se ha restaurado el comportamiento anterior, en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]. Para conectarse a una base de datos de SQL Server que se resuelve en `localhost`, actualiza a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)].|Secundaria|  
  
<a name="Networking"></a>   
## <a name="networking"></a>Redes  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Valores de fecha y hora en la clase <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>.|Para cumplir con [RFC822](http://www.ietf.org/rfc/rfc0822.txt) y [RFC2822](http://www.ietf.org/rfc/rfc2822.txt), ahora un valor con formato de fecha y hora tiene una hora de dos dígitos. Antes la hora tenía un solo dígito para los valores anteriores a las 10:00 AM.|Este cambio afecta a los siguientes escenarios de uso:<br /><br /> -...Comparar las longitudes o códigos hash de objetos <xref:System.Net.Mime.ContentDisposition> serializados en diferentes versiones de .NET Framework.<br />-   Comparar el valor devuelto del método <xref:System.Net.Mime.ContentDisposition.ToString%2A> o la representación de cadenas de los valores de propiedades de fecha y hora <xref:System.Net.Mime.ContentDisposition> en las versiones de .NET Framework.|Secundaria|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Servicios de WCF que usan NETTCP con seguridad SSL y autenticación de certificados|.NET Framework 4.6 añade TLS 1.1 y TLS 1.2 a la lista de protocolos predeterminados de SSL de WCF. Cuando los equipos cliente y servidor tienen .NET Framework 4.6 o posterior instalado, se usa TLS 1.2 para la negociación.|TLS 1.2 no admite la autenticación de certificado MD5. Como consecuencia, si un cliente utiliza un certificado MD5, el cliente de WCF no se podrá conectar al servicio WCF. Para obtener más información, consulte [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md) (Mitigación: servicios de WCF y autenticación de certificados).|Secundaria|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Representación de la ventana en un escenario de varios monitores|La ventana en su totalidad se representa sin recortes al extenderse más allá de una pantalla en un escenario de varios monitores.|Vea [Mitigación: representación de ventanas de WPF](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md).|Secundaria|  
|El corrector ortográfico en los controles de WPF habilitados para texto|Al ejecutarse en Windows 10, es posible que el corrector ortográfico no funcione, puesto que las funciones de revisión ortográfica de la plataforma solo están disponibles en los idiomas que aparecen en la lista de idiomas de entrada.|En Windows 10, al agregar un idioma a la lista de teclados disponibles, Windows descarga e instala automáticamente un paquete de características previa petición (Feature on Demand, FOD) que proporciona funciones de revisión ortográfica. Al agregar el idioma a la lista de idiomas de entrada, se admitirá el corrector ortográfico.|Secundaria|  
  
<a name="Setup"></a>   
## <a name="setup-and-deployment"></a>Instalación e implementación  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Control de versiones de producto|Control de versiones del producto ha cambiado desde las versiones anteriores de .NET Framework y especialmente .NET Framework 4, 4.5, 4.5.1 y 4.5.2. Para obtener más información, consulte [Mitigación: Control de versiones de producto](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Vea [Mitigación: Control de versiones de producto](../../../docs/framework/migration-guide/mitigation-product-versioning.md).|Medium|  
  
<a name="ClickOnce"></a>   
## <a name="clickonce"></a>ClickOnce  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Aplicaciones publicadas con ClickOnce que usan un certificado de firma de código SHA-256.|Las aplicaciones ClickOnce que tienen como destino [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] o versiones anteriores y que están firmadas con un certificado SHA-256 ya no tienen una dependencia en tiempo de ejecución en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o versiones posteriores.|Antes, para firmar una aplicación ClickOnce que tenía como destino [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] o versiones anteriores con un certificado de SHA-256, se requería la presencia de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o una versión posterior en el sistema de destino. Esto producía errores en los casos en que no estaba presente. Este cambio elimina esa dependencia y permite usar certificados de SHA-256 para firmar las aplicaciones ClickOnce que tienen como destino [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] y versiones anteriores.|Secundaria|  
  
<a name="RyuJIT"></a>   
## <a name="the-new-64-bit-jit-compiler"></a>El nuevo compilador JIT de 64 bits  
  
|Característica|Cambio|Impacto|Ámbito|  
|-------------|------------|------------|-----------|  
|Compilación JIT de 64 bits|A partir de .NET Framework 4.6, se utiliza un nuevo compilador JIT de 64 bits para la compilación Just-In-Time. Este cambio no afecta al compilador JIT de 32 bits.|En algunos casos, se produce una excepción inesperada o se observa un comportamiento diferente que si al ejecutar una aplicación con el compilador de 32 bits o el compilador JIT de 64 bits antiguo. **Nota:** Todos estos problemas se han solucionado en el nuevo compilador de 64 bits publicado con .NET Framework 4.6.2. También se han abordado la mayoría en las versiones de servicio de .NET Framework 4.6 y 4.6.1 que se incluyen con Windows Update. <br /><br /> Para obtener más información, vea [Mitigación: nuevo compilador JIT de 64 bits](../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md).|Borde|  
|Control de excepciones (devolución desde una región `try`)|A diferencia del compilador Just-In-Time JIT64 anterior, el nuevo compilador JIT de 64 bits no admite una instrucción `ret` de nivel de integridad en una región `try`.|La especificación ECMA-335 no permite devolver desde una región `try`, y ningún compilador administrado conocido genera tal IL. Sin embargo, el compilador JIT64 ejecutará dicho IL si se genera mediante la emisión de reflexión.<br /><br /> Si la aplicación genera un IL que incluye un código de operación `ret` en una región `try`, puede:<br /><br /> -Elegir como destino .NET Framework 4.5 o agregar el elemento [ \<useLegacyJIT >](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) al archivo de configuración de la aplicación, usar el compilador JIT antiguo y evitar el cambio.<br />-Actualizar el IL generado para devolver después a la región `try`.<br />-|Borde|
