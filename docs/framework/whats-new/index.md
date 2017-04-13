---
title: "Novedades de .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "04/07/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "lo nuevo [.NET Framework]"
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
caps.latest.revision: 292
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 287
---
# Novedades de .NET Framework
<a name="introduction"></a>En este artículo se resume las características nuevas y mejoras en las siguientes versiones de .NET Framework:  
  
 [.NET framework 4.6.2](#v462)   
 [.NET framework 4.6.1](#v461)   
 [.NET 2015 y .NET Framework 4.6](#v46)   
 [.NET framework 4.5.2](#v452)   
 [.NET framework 4.5.1](#v451)   
 [.NET framework 4.5](#core)  
  
 Este artículo no proporciona información completa sobre cada una de las características nuevas y puede estar sujeto a cambios. Para obtener información general acerca de .NET Framework, vea [Introducción](../../../docs/framework/get-started/index.md). Para las plataformas compatibles, consulte [requisitos del sistema](../../../docs/framework/get-started/system-requirements.md). Para obtener vínculos de descarga e instrucciones de instalación, consulte [Guía de instalación](../../../docs/framework/install/guide-for-developers.md).  
  
> [!NOTE]
>  El equipo de .NET Framework también publica características fuera de banda con NuGet para ampliar la compatibilidad de plataforma e introducir nuevas funciones, como las colecciones inmutables y tipos de vector habilitados para SIMD. Para obtener más información, consulte [API y las bibliotecas de clases adicionales](../../../ml/index.xml) y [.NET Framework y versiones fuera de banda](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md). Vea una [lista completa de paquetes de NuGet](http://blogs.msdn.com/b/dotnet/p/nugetpackages.aspx) para .NET Framework, o suscríbase a [nuestra fuente](https://nuget.org/api/v2/curated-feeds/dotnetframework/Packages/).  
  
<a name="v462"></a>   
## <a name="introducing-the-net-framework-462"></a>Introducción a .NET Framework 4.6.2  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] se basa en la versión 4.6 y 4.6.1 de .NET Framework e incorpora muchas correcciones y varias características nuevas, sin dejar de ser un producto muy estable.  
  
### <a name="downloading-and-installing-the-net-framework-462"></a>Descarga e instalación de .NET Framework 4.6.2  
 Puede descargar [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] en las siguientes ubicaciones:  
  
-   [Instalador de .NET framework 4.6.2 Web](http://go.microsoft.com/fwlink/?LinkId=780597)  
  
-   [Instalador de .NET Framework 4.6.2 sin conexión](http://go.microsoft.com/fwlink/?LinkId=780601)  
  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] puede instalarse en Windows 10, Windows 8.1, Windows 7 y las plataformas de servidor correspondientes a partir de Windows Server 2008 R2 SP1. Puede instalar [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] mediante el instalador web o el instalador sin conexión. La manera recomendada para la mayoría de los usuarios es usar el programa de instalación web.  
  
 Puede tener como destino la [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] en Visual Studio 2012 o posterior al instalar el [paquete de desarrollador de .NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=780617).  
  
### <a name="whats-new-in-the-net-framework-462"></a>Novedades de .NET Framework 4.6.2  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] incluye nuevas características en las áreas siguientes:  
  
-   [ASP.NET](#ASPNET462)  
  
-   [Categorías de caracteres](#Strings)  
  
-   [Criptografía](#Crypto462)  
  
-   [SqlClient](#SQLClient)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF462)  
  
-   [Windows Workflow Foundation (WF)](#WF462)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [Conversión de formularios Windows Forms y aplicaciones de WPF a las aplicaciones UWP](#UWPConvert)  
  
-   [Mejoras en la depuración](#Debug462)  
  
 Para obtener una lista de las nuevas API se agrega a la [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], consulte [cambios de la API de .NET Framework 4.6.2](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) en GitHub. Para obtener una lista de mejoras y correcciones de errores en el [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], consulte [cambios de la API de .NET Framework 4.6.2](http://go.microsoft.com/fwlink/?LinkId=708778) en GitHub.  Para obtener más información, consulte [anuncio de .NET Framework 4.6.2](https://blogs.msdn.microsoft.com/dotnet/2016/08/02/announcing-net-framework-4-6-2/) en el Blog. NET.  
  
<a name="ASPNET462"></a>   
### <a name="aspnet"></a>ASP.NET  
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ASP.NET incluye las siguientes mejoras:  
  
 **Compatibilidad mejorada para los mensajes de error localizado de validadores de anotación de datos**  
 Los validadores de anotación de datos permiten realizar la validación agregando uno o varios atributos a una propiedad de clase. El atributo <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> elemento define el texto del mensaje de error si se produce un error de validación. A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], ASP.NET facilita la tarea de localizar mensajes de error. Los mensajes de error se localizarán si:  
  
1.  El <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> se proporciona en el atributo de validación.  
  
2.  El archivo de recursos está almacenado en la carpeta App_LocalResources.  
  
3.  El nombre del archivo de recursos localizados tiene la forma `DataAnnotation.Localization.{` *nombre*`}.resx`, donde *nombre* es un nombre de referencia cultural en el formato *languageCode*`-`*CódigoDePaís/* o *languageCode*.  
  
4.  El nombre de clave del recurso es la cadena asignada a la <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=fullName> atributo y su valor es el mensaje de error localizado.  
  
 Por ejemplo, el siguiente atributo de anotación de datos define el mensaje de error de la referencia cultural de forma predeterminada para una clasificación no válida.  
  
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
  
 A continuación, puede crear un archivo de recursos, DataAnnotation.Localization.fr.resx, cuya clave es la cadena de mensaje de error y cuyo valor es el mensaje de error localizado. El archivo debe encontrarse en el `App.LocalResources` carpeta. Por ejemplo, la siguiente es la clave y su valor en un mensaje de error de idioma localizado de francés (fr):  
  
|Nombre|Valor|  
|----------|-----------|  
|La clasificación debe estar entre 1 y 10.|Tenga en cuenta la deberá efectuarse componen entre 1 y 10.|  
  
 Este archivo puede, a continuación  
  
 Además, la localización de anotaciones de datos es extensible. Los desarrolladores pueden conectar su propio proveedor de localizador de cadena mediante la implementación de la <xref:System.Web.Globalization.IStringLocalizerProvider> interfaz para almacenar la cadena de localización en algún lugar distinto de en un archivo de recursos.  
  
 **Compatibilidad asincrónica con los proveedores de almacén de estado de sesión**  
 Actualmente, ASP.NET permite el uso de métodos de devolución de tareas con proveedores de almacenes de estados de sesión, lo que permite que las aplicaciones ASP.NET aprovechen las ventajas de escalabilidad de la asincronía. A admite proveedores de almacén de operaciones asincrónicas con el estado de sesión, ASP.NET incluye una nueva interfaz, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=fullName>, que hereda de <xref:System.Web.IHttpModule> y permite a los desarrolladores implementar sus propios proveedores de almacén de estado de sesión módulo y async sesión. La interfaz se define de la siguiente manera:  
  
```csharp  
  
public interface ISessionStateModule : IHttpModule {  
    void ReleaseSessionState(HttpContext context);  
    Task ReleaseSessionStateAsync(HttpContext context);  
}  
  
```  
  
 Además, el <xref:System.Web.SessionState.SessionStateUtility> clase incluye dos nuevos métodos <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> y <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, que se puede utilizar para admitir las operaciones asincrónicas.  
  
 **Compatibilidad con Async proveedores de caché de resultados**  
 A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], pueden usarse métodos de devolución de tarea con proveedores de caché de resultados para proporcionar las ventajas de escalabilidad de la asincronía.  Los proveedores que implementan estos métodos reducen el bloqueo de subprocesos en un servidor web y mejoran la escalabilidad de un servicio de ASP.NET.  
  
 Se han agregado las API siguientes para ofrecer compatibilidad con proveedores de caché de resultados asincrónicos:  
  
-   El <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=fullName> (clase), que se hereda de <xref:System.Web.Caching.OutputCacheProvider?displayProperty=fullName> y permite a los desarrolladores implementar un proveedor de caché de resultados asincrónico.  
  
-   El <xref:System.Web.Caching.OutputCacheUtility> clase, que proporciona métodos auxiliares para configurar la caché de resultados.  
  
-   18 de nuevos métodos de la <xref:System.Web.HttpCachePolicy?displayProperty=fullName>clase. Entre ellos se incluyen <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A>, y <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.  
  
-   2 nuevos métodos de la <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=fullName> clase: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> y <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.  
  
-   2 nuevos métodos de la <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=fullName> clase: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> y <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.  
  
-   2 nuevos métodos de la <xref:System.Web.HttpCacheVaryByParams?displayProperty=fullName> clase: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> y <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.  
  
-   En el <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=fullName> (clase), el <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A> método.  
  
-   En el <xref:System.Web.Caching.CacheDependency>, <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A> método.  
  
<a name="Strings"></a>   
### <a name="character-categories"></a>Categorías de caracteres  
 Los caracteres de la [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] se clasifican según la [del estándar Unicode, versión 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/). En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], los caracteres están clasificados según las categorías de caracteres Unicode 6.3.  
  
 Compatibilidad con Unicode 8.0 se limita a la clasificación de caracteres mediante la <xref:System.Globalization.CharUnicodeInfo> de clases y tipos y métodos que se basan en ella. Estos incluyen el <xref:System.Globalization.StringInfo> clase sobrecargados <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName> método y el [clases de carácter](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) reconocidos por el motor de expresiones regulares de .NET Framework.  La comparación y la ordenación de caracteres y cadenas no se ven afectadas por este cambio y siguen dependiendo del sistema operativo subyacente o, en el caso de los sistemas Windows 7, de los datos de caracteres proporcionados por .NET Framework.  
  
 Para realizar cambios en las categorías de caracteres de Unicode 6.0 a 7.0 de Unicode, consulte [el estándar Unicode, versión 7.0.0](http://www.unicode.org/versions/Unicode7.0.0/) en el sitio Web del consorcio Unicode. Para cambios de 7.0 de Unicode a Unicode 8.0, consulte [el estándar Unicode, versión 8.0.0](http://www.unicode.org/versions/Unicode8.0.0/) en el sitio Web del consorcio Unicode.  
  
<a name="Crypto462"></a>   
### <a name="cryptography"></a>Criptografía  
 **Compatibilidad con X509 certificados contenedor DSA FIPS 186 3**  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] agrega compatibilidad con certificados X509 de DSA (algoritmo de firma digital) cuyas claves superan el límite de 1024 bits de FIPS 186-2.  
  
 Además de admitir los tamaños de clave más grandes de FIPS 186-3, [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] permite calcular firmas con la familia SHA-2 de algoritmos hash (SHA256, SHA384 y SHA512). FIPS 186 3 proporciona compatibilidad con el nuevo <xref:System.Security.Cryptography.DSACng?displayProperty=fullName> clase.  
  
 De acuerdo con los cambios recientes en el <xref:System.Security.Cryptography.RSA> clase en .NET Framework 4.6 y <xref:System.Security.Cryptography.ECDsa> clase en .NET Framework 4.6.1, el <xref:System.Security.Cryptography.DSA> abstracta de la clase base en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] tiene métodos adicionales para permitir que los llamadores pueden utilizar esta funcionalidad sin conversión alguna. Puede llamar a la <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=fullName> método de extensión para firmar datos, como se muestra en el ejemplo siguiente.  
  
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
  
 Puede llamar a la <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=fullName> método de extensión para comprobar los datos firmados, como se muestra en el ejemplo siguiente.  
  
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
  
 **Una mayor claridad para entradas ECDiffieHellman rutinas de derivación de claves**  
 .NET Framework 3.5 incluía compatibilidad para el acuerdo de claves Diffie-Hellman de curva elíptica con tres rutinas diferentes de función de derivación de claves (KDF). Se configuraron las entradas para las rutinas y las rutinas de sí mismos, a través de propiedades en el <xref:System.Security.Cryptography.ECDiffieHellmanCng> objeto. Pero como no todas las rutinas leían todas las propiedades de entrada, esto podía provocar confusión al desarrollador.  
  
 Para solucionarlo en el [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], los tres métodos siguientes se agregaron a la <xref:System.Security.Cryptography.ECDiffieHellman> clase base para mayor claridad representan estas rutinas KDF y sus entradas:  
  
|Método ECDiffieHellman|Descripción|  
|----------------------------|-----------------|  
|[DeriveKeyFromHash (Byte ECDiffieHellmanPublicKey, HashAlgorithmName,\[\], Byte\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante la fórmula<br /><br /> HASH(secretPrepend || *x* || secretAppend)<br /><br /> HASH (secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> donde *x* es el resultado del algoritmo de Diffie-Hellman de CE calculado.|  
|[DeriveKeyFromHmac (Byte ECDiffieHellmanPublicKey, HashAlgorithmName,\[\], Byte\[\], Byte\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante la fórmula<br /><br /> HMAC (hmacKey, secretPrepend || *x* || secretAppend)<br /><br /> HMAC (hmacKey, secretPrepend OrElse *x* secretAppend OrElse)<br /><br /> donde *x* es el resultado del algoritmo de Diffie-Hellman de CE calculado.|  
|[DeriveKeyTls (ECDiffieHellmanPublicKey, Byte\[\], Byte\<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante el algoritmo de derivación de función pseudoaleatoria (PRF) de TLS.|  
  
 **Soporte técnico para el cifrado simétrico de clave persistente**  
 La biblioteca de criptografía (CNG) de Windows agrega compatibilidad para almacenar claves simétricas persistentes y para usar claves simétricas almacenadas en el hardware, y [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] hace posible que los desarrolladores usen esta característica.  Como el concepto de nombres de clave y proveedores de clave depende de la implementación, el uso de esta característica obliga a emplear el constructor de los tipos de la implementación concreta, en lugar del enfoque de fábrica preferido (por ejemplo, llamar a `Aes.Create`).  
  
 Existe compatibilidad de guardado de clave de cifrado simétrico de AES (<xref:System.Security.Cryptography.AesCng>) y 3DES (<xref:System.Security.Cryptography.TripleDESCng>) algoritmos. Por ejemplo:  
  
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
  
 **Compatibilidad con SignedXml hash SHA-2**  
 El [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] agrega compatibilidad para la <xref:System.Security.Cryptography.Xml.SignedXml> algoritmos de síntesis de clases para los métodos de firma RSA-SHA256, SHA384 RSA y SHA512 RSA PKCS&#1; y referencia SHA256, SHA384 y SHA512.  
  
 Las constantes URI se exponen en <xref:System.Security.Cryptography.Xml.SignedXml>:  
  
|Campo SignedXml|Constante|  
|---------------------|--------------|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|  
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|  
  
 Todos los programas que han registrado un personalizado <xref:System.Security.Cryptography.SignatureDescription> controlador en <xref:System.Security.Cryptography.CryptoConfig> para agregar compatibilidad para estos algoritmos, seguirán funcionando como lo hacían en el pasado, pero dado que hay ahora plataforma de manera predeterminada, el <xref:System.Security.Cryptography.CryptoConfig> registro ya no es necesario.  
  
<a name="SQLClient"></a>   
### <a name="sqlclient"></a>SqlClient  
 Proveedor de datos de .NET framework para SQL Server (<xref:System.Data.SqlClient?displayProperty=fullName>) incluye las siguientes características nuevas en el [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:  
  
 **Agrupación de conexiones y los tiempos de espera de las bases de datos de SQL Azure**  
 Cuando se habilita la agrupación de conexiones y se produce un error de tiempo de espera u otro tipo de error de inicio de sesión, se almacena en caché una excepción que se produce en todos los intentos de conexión posteriores que se realicen en un plazo de entre 5 segundos y 1 minuto.  Para obtener más información, consulte [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
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
  
 **Mejoras para siempre cifrados**  
 SQLClient presenta dos mejoras para Always Encrypted:  
  
-   Para mejorar el rendimiento de las consultas con parámetros en las columnas de una base de datos cifrada, ahora se almacenan en caché los metadatos de cifrado de los parámetros de consulta. Con el <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=fullName> propiedad establecida en `true` (que es el valor predeterminado), si se llama varias veces a la misma consulta, el cliente recupera metadatos de parámetros desde el servidor de una sola vez.  
  
-   Entradas de clave de cifrado de columna en la caché de la clave ahora se expulsan después de un intervalo de tiempo configurable, establecer mediante el <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=fullName> propiedad.  
  
<a name="WCF"></a>   
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Communication Foundation se ha mejorado en las áreas siguientes:  
  
 **Compatibilidad de seguridad de transporte WCF para certificados almacenados con CNG**  
 La seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows. En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], esta compatibilidad está limitada al uso de certificados con una clave pública que tenga un exponente con una longitud no superior a 32 bits. Cuando una aplicación tiene [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] como destino, esta característica está activada de forma predeterminada.  
  
 Para aplicaciones que tienen como destino el [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] y anterior pero se ejecutan en el [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], se puede habilitar esta característica, agregue la línea siguiente a la [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sección del archivo app.config o web.config.  
  
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
  
 **Mejor compatibilidad para varias reglas de ajuste del horario de verano por la clase DataContractJsonSerializer**  
 Los clientes pueden usar una opción de configuración de aplicación para determinar si la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> clase admite varias reglas de ajuste para una sola zona horaria. Esta característica es opcional. Para habilitarla, agregue la siguiente opción de configuración al archivo app.config:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />  
</runtime>  
  
```  
  
 Cuando se habilita esta característica, un <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> de objeto usa la <xref:System.TimeZoneInfo> escriba en lugar de la <xref:System.TimeZone> tipo para deserializar los datos de fecha y hora. <xref:System.TimeZoneInfo> admite varias reglas de ajuste, lo que permite trabajar con datos históricos zona horaria;   <xref:System.TimeZone> no.  
  
 Para obtener más información sobre la <xref:System.TimeZoneInfo> estructura y los ajustes de zona horaria, vea [información general de la zona horaria](../../../docs/standard/datetime/time-zone-overview.md).  
  
 **Soporte para preservar UTC hora serializar y deserializar con la clase XMLSerializer**  
 Normalmente, cuando la <xref:System.Xml.Serialization.XmlSerializer> clase se utiliza para serializar una UTC <xref:System.DateTime> valor, crea una cadena serializada de tiempo que conserva la fecha y hora, pero supone que la hora es local.  Por ejemplo, si crea una instancia de fecha y hora UTC llamando al código siguiente:  
  
```csharp  
DateTime utc = new DateTime(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc);  
```  
  
```vb  
Dim utc As New Date(2016, 11, 07, 3, 0, 0, DateTimeKind.Utc)  
```  
  
 el resultado es la cadena de tiempo serializada "03:00:00.0000000-08:00" para un sistema con ocho horas con retraso con respecto a la hora UTC.  Además, los valores serializados siempre se deserializan como valores de fecha y hora locales.  
  
 Puede utilizar una opción de configuración de aplicación para determinar si la <xref:System.Xml.Serialization.XmlSerializer> conserva la información de zona horaria UTC al serializar y deserializar <xref:System.DateTime> valores:  
  
```xml  
  
<runtime>  
     <AppContextSwitchOverrides   
          value="Switch.System.Runtime.Serialization.DisableSerializeUTCDateTimeToTimeAndDeserializeUTCTimeToUTCDateTime=false" />  
</runtime>  
  
```  
  
 Cuando se habilita esta característica, un <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> de objeto usa la <xref:System.TimeZoneInfo> escriba en lugar de la <xref:System.TimeZone> tipo para deserializar los datos de fecha y hora. <xref:System.TimeZoneInfo> admite varias reglas de ajuste, lo que permite trabajar con datos históricos zona horaria;   <xref:System.TimeZone> no.  
  
 Para obtener más información sobre la <xref:System.TimeZoneInfo> estructura y los ajustes de zona horaria, vea [información general de la zona horaria](../../../docs/standard/datetime/time-zone-overview.md).  
  
 **NetNamedPipeBinding mejor coincidencia**  
 WCF tiene una nueva opción de la aplicación que se puede establecer en las aplicaciones cliente para garantizar que siempre se conecten al servicio que escucha en el URI que mejor coincida con el que solicitan. Con esta configuración de la aplicación establecida en `false` (valor predeterminado), es posible que los clientes que usan <xref:System.ServiceModel.NetNamedPipeBinding> para intentar conectarse a un servicio de escucha en un URI que es una subcadena del URI solicitado.  
  
 Por ejemplo, un cliente intenta conectarse a un servicio que escucha en `net.pipe://localhost/Service1`, pero un servicio diferente en ese equipo que se ejecuta con privilegios de administrador escucha en `net.pipe://localhost`. Con esta opción de la aplicación establecida en `false`, el cliente intentará conectarse al servicio incorrecto. Después de establecer la opción de la aplicación en `true`, el cliente siempre se conectará al mejor servicio.  
  
> [!NOTE]
>  Los clientes que usan <xref:System.ServiceModel.NetNamedPipeBinding> encontrar servicios basados en la dirección base del servicio (si existe) en lugar de la dirección del extremo completo. Para garantizar que esta opción siempre funcione, el servicio debe usar una dirección base única.  
  
 Para habilitar este cambio, agregue la siguiente opción de la aplicación al archivo App.config o Web.config de la aplicación cliente:  
  
```xml  
  
<configuration>  
    <appSettings>  
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />  
    </appSettings>  
</configuration>  
  
```  
  
 **SSL 3.0 no es un protocolo predeterminado**  
 Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, SSL 3.0 ya no es el protocolo predeterminado para negociar una conexión segura. En la mayoría de los casos, esto no debería afectar a las aplicaciones existentes, porque TLS 1.0 está incluido en la lista de protocolos para NetTcp. Todos los clientes deberían poder negociar una conexión usando como mínimo TLS 1.0.      Si se requiere Ssl3, use uno de los siguientes mecanismos de configuración para agregarlo a la lista de protocolos negociados.  
  
-   El <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> propiedad  
  
-   El <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName> propiedad  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) section  
  
-   The [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) section of the [<>\>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) section  
  
<a name="WPF462"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Presentation Foundation se ha mejorado en las áreas siguientes:  
  
 **Ordenación de grupo**  
 Una aplicación que utiliza un <xref:System.Windows.Data.CollectionView> objeto para agrupar los datos ahora declarar explícitamente cómo ordenar los grupos. La ordenación explícita resuelve el problema de la ordenación no intuitiva que se produce cuando una aplicación agrega o elimina grupos dinámicamente, o cuando cambia el valor de las propiedades de elementos implicadas en la agrupación. También puede mejorar el rendimiento del proceso de creación de grupos, ya que mueve las comparaciones de las propiedades de agrupación de la ordenación de la colección completa a la ordenación de los grupos.  
  
 Para admitir la ordenación de grupo, la nueva <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=fullName> y <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=fullName> propiedades describen cómo ordenar el conjunto de grupos generados por la <xref:System.ComponentModel.GroupDescription> objeto. Esto es análogo a la forma en el mismo nombre <xref:System.Windows.Data.ListCollectionView> propiedades describen cómo se ordenan los elementos de datos.  
  
 Dos nuevas propiedades estáticas de la <xref:System.Windows.Data.PropertyGroupDescription> (clase), <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> y <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, se puede usar para los casos más comunes.  
  
 Por ejemplo, el siguiente código XAML agrupa los datos por edad, ordena los grupos de edad en orden ascendente y agrupa los elementos de cada grupo de edad por apellido.  
  
```xaml  
  
<GroupDescriptions>  
     <PropertyGroupDescription   
         PropertyName=”Age”   
         CustomSort=   
              ”{x:Static PropertyGroupDescription.CompareNamesAscending}”/>  
     </PropertyGroupDescription>  
</GroupDescriptions>  
  
<SortDescriptions>  
     <SortDescription PropertyName=”LastName”/>  
</SortDescriptions>  
  
```  
  
 **Compatibilidad de teclado programable**  
 La compatibilidad con teclado en pantalla permite el seguimiento del foco en aplicaciones WPF, ya que invoca y descarta automáticamente el nuevo teclado en pantalla de Windows 10 cuando un control que acepta entrada de texto recibe la entrada táctil.  
  
 En versiones anteriores de .NET Framework, las aplicaciones WPF no pueden optar por el seguimiento del foco sin deshabilitar la compatibilidad con lápiz o movimiento táctil en WPF.  Como resultado, las aplicaciones WPF deben elegir entre compatibilidad táctil completa en WPF o basarse en la promoción del mouse de Windows.  
  
 **PPP por monitor**  
 Para admitir la reciente proliferación de entornos con valores altos o híbridos de PPP para las aplicaciones WPF, WPF en [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] habilita el reconocimiento de monitor. Consulte la [ejemplos y guía para desarrolladores de](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) en GitHub para obtener más información acerca de cómo habilitar la aplicación WPF para convertirse en distinguen los PPP por monitor.  
  
 En versiones anteriores de .NET Framework, las aplicaciones WPF tienen habilitado el reconocimiento de PPP del sistema. En otras palabras, el sistema operativo escala la interfaz de usuario de la aplicación según corresponda, en función del valor de PPP del monitor en el que se representa la aplicación. ,  
  
 Para aplicaciones que se ejecutan bajo la [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], puede deshabilitar los cambios de PPP por monitor en las aplicaciones de WPF mediante la adición de una instrucción de configuración para la [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) archivo de sección de la configuración de la aplicación, como sigue:  
  
```xml  
  
<runtime>  
   <AppContextSwitchOverrides value=”Switch.System.Windows.DoNotScaleForDpiChanges=false”/>  
</runtime>  
  
```  
  
<a name="WF462"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 En [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], Windows Workflow Foundation se ha mejorado en las áreas siguientes:  
  
 **Compatibilidad con IntelliSense en el Diseñador de WF Re-hosted y de expresiones de C#**  
 A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], WF admite expresiones de C# en el diseñador de Visual Studio y en los flujos de trabajo de código. El Diseñador de flujo de trabajo rehospedado es una característica clave de WF que permite que el Diseñador de flujo de trabajo esté en una aplicación fuera de Visual Studio (por ejemplo, en WPF).  Windows Workflow Foundation permite admitir expresiones de C# e IntelliSense en el Diseñador de flujo de trabajo rehospedado. Para obtener más información, consulte el [blog de Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkID=809042&clcid=0x409).  
  
 `Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio`  
 En las versiones de .NET Framework anteriores a [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], IntelliSense del Diseñador de WF se interrumpe cuando un cliente vuelve a compilar un proyecto de flujo de trabajo desde Visual Studio. Mientras que la compilación del proyecto es correcta, los tipos de flujo de trabajo no se encuentran en el diseñador y las advertencias de IntelliSense para los tipos de flujo de trabajo que faltan aparecen en la **lista de errores** ventana. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] soluciona este problema y hace que IntelliSense esté disponible.  
  
 **Flujo de trabajo V1 aplicaciones con el seguimiento del flujo de trabajo ahora se ejecutan en modo FIPS**  
 Los equipos que tienen habilitado el modo de cumplimiento de FIPS ahora pueden ejecutar correctamente una aplicación de versión 1 de flujo de trabajo con el seguimiento del flujo de trabajo habilitado. Para habilitar este escenario, debe realizar el cambio siguiente en el archivo app.config:  
  
```xml  
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />  
```  
  
 Si este escenario no está habilitado, al ejecutar la aplicación se sigue generando una excepción con el mensaje "Esta implementación no forma parte de los algoritmos criptográficos validados por Windows Platform FIPS".  
  
 **Mejoras de flujo de trabajo cuando se usa la actualización dinámica con el Diseñador de flujo de trabajo de Visual Studio**  
 El Diseñador de flujo de trabajo, Diseñador de actividades FlowChart y otros diseñadores de actividad de flujo de trabajo ahora cargar y mostrar correctamente los flujos de trabajo que se han guardado después de llamar a la <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> método. En las versiones de .NET Framework anteriores a la [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], cargar un archivo XAML en Visual Studio para un flujo de trabajo que se ha guardado después de llamar a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=fullName> puede producir los problemas siguientes:  
  
-   El Diseñador de flujo de trabajo no se puede cargar el archivo XAML correctamente (cuando el <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=fullName> está al final de la línea).  
  
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
 El *no administrada de la API de depuración* se ha mejorado en el [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] para realizar análisis adicionales cuando un <xref:System.NullReferenceException> se produce por lo que es posible determinar qué variable en una sola línea de código fuente es `null`.   Para admitir este escenario, se han agregado las API siguientes a la API de depuración no administrada.  
  
-   El [ICorDebugCode4](../../../ocs/framework/unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md), y [ICorDebugVariableHomeEnum](../../../ocs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interfaces, que exponen los hogares nativos de las variables administradas. Esto permite a los depuradores realizar un análisis de flujo de código cuando un <xref:System.NullReferenceException> se produce y trabajando hacia atrás para determinar la variable administrada que corresponde a la ubicación nativa que estaba `null`.  
  
-   El [ICorDebugType2::GetTypeID](../Topic/ICorDebugType2::GetTypeID%20Method.md) método proporciona una asignación ICorDebugType a [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md), que permite al depurador obtener un [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) sin una instancia de la ICorDebugType. Las API existentes en [COR_TYPEID](../../../ocs/framework/unmanaged-api/debugging/cor-typeid-structure.md) puede utilizarse para determinar el diseño de clase del tipo.  
  
<a name="v461"></a>   
## <a name="whats-new-in-the-net-framework-461"></a>Novedades de .NET Framework 4.6.1  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] incluye nuevas características en las áreas siguientes:  
  
-   [Criptografía](#Crypto)  
  
-   [ADO.NET](#ADO.NET461)  
  
-   [Windows Presentation Foundation (WPF)](#WPF461)  
  
-   [Windows Workflow Foundation](#WWF461)  
  
-   [Generación de perfiles](#Profile461)  
  
-   [NGen](#NGEN461)  
  
 Para obtener más información sobre [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], vea uno de los temas siguientes:  
  
-   El [lista de .NET Framework 4.6.1 de cambios](http://go.microsoft.com/fwlink/?LinkId=622964)  
  
-   [Compatibilidad de aplicaciones en 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)  
  
-   [La diferencia de la API de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=622989) (en GitHub)  
  
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
  
 Compatibilidad con Always Encrypted para claves protegidas por hardware  
 ADO.NET ahora permite almacenar claves maestras de la columna Always Encrypted de forma nativa en módulos de seguridad de hardware (HSM). Con esta compatibilidad, los clientes pueden aprovechar las claves asimétricas almacenadas en HSM sin tener que escribir proveedores de almacenes de clave maestra de la columna personalizada ni registrarlos en las aplicaciones.  
  
 Los clientes necesitan instalar el proveedor CSP proporcionado por el fabricante HSM o los proveedores de almacén de claves de CNG en los servidores de aplicación o en los equipos cliente para tener acceso a los datos que Always Encrypted ha protegido con las claves maestras de columna almacenadas en un HSM.  
  
 Mejorar <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> comportamiento de la conexión para AlwaysOn  
 SqlClient ahora proporciona automáticamente una conexión más rápida a un grupo de disponibilidad AlwaysOn (AG). Detecta de forma transparente si la aplicación se conecta a un grupo de disponibilidad AlwaysOn (AG) en una subred diferente y detecta rápidamente el servidor activo actual y proporciona una conexión al servidor. Antes de esta versión, una aplicación tenía que establecer la cadena de conexión para incluir `“MultisubnetFailover=true”` e indicar que se conecta a un grupo de disponibilidad AlwaysOn. Sin establecer la palabra clave de conexión en `true`, una aplicación podría experimentar un tiempo de espera mientras se conecta a un grupo de disponibilidad AlwaysOn. Con esta versión, una aplicación hace *no* debe establecer <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> a `true` ya. Para obtener más información sobre la compatibilidad de SqlClient para grupos de disponibilidad AlwaysOn, consulte [compatibilidad de SqlClient para alta disponibilidad y recuperación ante desastres](../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).  
  
<a name="WPF461"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 Windows Presentation Foundation incluye una serie de mejoras y cambios.  
  
 Rendimiento mejorado  
 Se ha corregido el retraso de activación de eventos touch en [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Además, se escribe en un <xref:System.Windows.Controls.RichTextBox> control ya no bloquea el subproceso de representación durante la entrada rápida.  
  
 Mejoras en el corrector ortográfico  
 El corrector ortográfico en WPF se ha actualizado en Windows 8.1 y en versiones posteriores para aprovechar la compatibilidad del sistema operativo con la corrección ortográfica de idiomas adicionales.  No hay ningún cambio en la funcionalidad en las versiones de Windows anteriores a Windows 8.1.  
  
 Versiones anteriores de .NET Framework, el idioma de un <xref:System.Windows.Controls.TextBox> control ora <xref:System.Windows.Controls.RichTextBox> bloque detecta busca información en el orden siguiente:  
  
-   `xml:lang`, si está presente.  
  
-   Idioma de entrada actual.  
  
-   Referencia cultural del subproceso actual.  
  
 Para obtener información adicional sobre la compatibilidad de idioma en WPF, vea el [entrada de blog WPF sobre características de .NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkID=691819).  
  
 Compatibilidad adicional con diccionarios personalizados por el usuario  
 En [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], WPF reconoce los diccionarios personalizados que se registran de forma global. Esta funcionalidad está disponible además de la posibilidad de registrarlos por control.  
  
 En versiones anteriores de WPF, los diccionarios personalizados no reconocían palabras excluidas ni listas de autocorrección. Ahora se admiten en Windows 8.1 y Windows 10 mediante el uso de archivos que se pueden colocar en el directorio `%AppData%\Microsoft\Spelling\<language tag>`.  Las reglas siguientes se aplican a estos archivos:  
  
-   Los archivos deben tener las extensiones .dic (para palabras agregadas), .exc (para las palabras excluidas) o .acl (para la autocorrección).  
  
-   Los archivos deben ser texto sin formato UTF-16 LE que comienza con la marca BOM (Byte Order Mark).  
  
-   Cada línea deben constar de una palabra (en las listas de palabras agregadas y excluidos) o un par de Autocorrección con las palabras separadas por una barra vertical ("|") (en la lista de palabras de Autocorrección).  
  
-   Estos archivos se consideran de solo lectura y el sistema no los modifica.  
  
> [!NOTE]
>  Estos nuevos formatos de archivos no son compatibles directamente con las API de corrección ortográfica de WPF, y los diccionarios personalizados proporcionados a WPF en las aplicaciones deben continuar usando los archivos .lex.  
  
 Muestras  
 Hay una serie de [ejemplos de WPF](https://msdn.microsoft.com/library/ms771633.aspx) en MSDN. Más de 200 de los ejemplos más conocidos (según su uso) se moverá a una [repositorio de GitHub de origen abierto](https://github.com/Microsoft/WPF-Samples). Ayúdenos a mejorar nuestros ejemplos enviarnos una solicitud de extracción o abrir un [GitHub problema](https://github.com/Microsoft/WPF-Samples/issues).  
  
 Extensiones de DirectX  
 WPF incluye una [paquete NuGet](http://go.microsoft.com/fwlink/?LinkID=691342) que proporciona nuevas implementaciones de <xref:System.Windows.Interop.D3DImage> que faciliten para interoperar con DX10 y Dx11 contenido. El código para este paquete ha estado abierto con origen y está disponible [en GitHub](https://github.com/Microsoft/WPFDXInterop).  
  
<a name="WWF461"></a>   
### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: transacciones  
 El <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> método ahora puede utilizar un administrador de transacciones distribuidas que no sea de MSDTC para promover la transacción. Para ello, especifica un identificador GUID transacción promotor al nuevo <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> sobrecarga. Si esta operación se realiza correctamente, hay limitaciones de las capacidades de la transacción. Una vez que se da de alta un promotor de transacciones de MSDTC no los métodos siguientes inician un <xref:System.Transactions.TransactionPromotionException> porque estos métodos requieren que la promoción a MSDTC:  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=fullName>  
  
-   <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=fullName>  
  
 Una vez que se activa un promotor de transacciones que no sea MSDTC, debe usarse para futuras inscripciones duraderas a través de los protocolos que define. El <xref:System.Guid> de la transacción promotor puede obtenerse mediante la <xref:System.Transactions.Transaction.PromoterType%2A> propiedad. Cuando se promueve la transacción, el promotor transacciones proporciona un <xref:System.Byte> matriz que representa el token promovido. Una aplicación puede obtener el token promocionado de una transacción promocionada no MSDTC con el <xref:System.Transactions.Transaction.GetPromotedToken%2A> método.  
  
 Los usuarios de la nueva <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=fullName> sobrecarga debe seguir una secuencia de llamada específica en orden para completar correctamente la operación de promoción. Estas reglas están registradas en la documentación del método.  
  
<a name="Profile461"></a>   
### <a name="profiling"></a>Generación de perfiles  
 La API de generación de perfiles no administrada se ha mejorado como se indica a continuación:  
  
 Mejor compatibilidad para tener acceso a los archivos PDB en el [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) (interfaz)  
 En ASP.Net 5, cada vez es más común que los ensamblados se compilen en memoria mediante Roslyn. Para desarrolladores que crean herramientas de generación de perfiles, esto significa que los PDB serializados históricamente en disco ya no estén presentes. Las herramientas del generador de perfiles suelen usar archivos PDB para asignar código a las líneas de código fuente para tareas como el análisis de rendimiento de línea por línea o de cobertura de código. El [ICorProfilerInfo7](../../../ocs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) interfaz ahora incluye dos nuevos métodos [ICorProfilerInfo7::GetInMemorySymbolsLength](../Topic/ICorProfilerInfo7::GetInMemorySymbolsLength%20Method.md) y [ICorProfilerInfo7::ReadInMemorySymbols](../Topic/ICorProfilerInfo7::ReadInMemorySymbols.md), para proporcionar acceso a los datos de la PDB en memoria, estas herramientas del generador de perfiles mediante el uso de las nuevas API, un generador de perfiles puede obtener el contenido de un PDB en memoria como una matriz de bytes y, a continuación, procesarlos o serializarlo en el disco.  
  
 Mejor instrumentación con la interfaz ICorProfiler  
 Los generadores de perfiles que utilizan la funcionalidad ReJit de la API `ICorProfiler` para la instrumentación dinámica ahora pueden modificar algunos metadatos. Anteriormente dichas herramientas podían instrumentar IL en cualquier momento, pero los metadatos solo se podían modificar en tiempo de carga del módulo. Dado que IL hace referencia a los metadatos, esto limita los tipos de instrumentación que se podían hacer. Hemos soluciona algunos de esos límites agregando el [ICorProfilerInfo7::ApplyMetaData](../Topic/ICorProfilerInfo7::ApplyMetaData%20Method.md) admite un subconjunto de las ediciones de metadatos después de que el módulo se carga, en particular al agregar un nuevo método `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec`, y `UserString` registros. Este cambio permite una mayor variedad de instrumentación sobre la marcha.  
  
<a name="NGEN461"></a>   
### <a name="native-image-generator-ngen-pdbs"></a>PDB del generador de imágenes nativas (NGEN)  
 El seguimiento de eventos de varios equipos permite a los clientes generar perfiles de un programa en la máquina A y mirar los datos de generación de perfiles con la asignación de la línea de origen en la máquina B. Al usar versiones anteriores de .NET Framework, el usuario copiaría todos los módulos y las imágenes nativas de la máquina con generación de perfiles a la máquina de análisis que contiene el archivo PDB de IL para crear la asignación de código fuente a nativo. Aunque este proceso puede funcionar bien cuando los archivos son relativamente pequeños, como en aplicaciones de teléfono, los archivos pueden ser muy grandes en sistemas de escritorio y requieren mucho tiempo para copiarse.  
  
 Con los archivos PDB de NGen, NGen puede crear un archivo PDB que contenga la asignación de IL a nativo sin una dependencia del archivo PDB de IL. En nuestro escenario de seguimiento de eventos de varios equipos, todo lo que se necesita es copiar la imagen nativa PDB generado por el equipo al equipo B y utilizar [API de acceso a interfaz de depuración](https://msdn.microsoft.com/en-us/library/ee8x173s.aspx) para leer la asignación de origen al IL del PDB de IL y asignación de IL a nativo de la PDB imágenes nativas. La combinación de ambas asignaciones permite asignar código fuente a nativo. Dado que el PDB de imagen nativa es mucho menor que todos los módulos y las imágenes nativas, el proceso de copiar de la máquina A a la máquina B es mucho más rápido.  
  
<a name="v46"></a>   
## <a name="whats-new-in-net-2015"></a>Novedades de .NET 2015  
 .NET 2015 presenta [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y .NET Core. Algunas características nuevas se aplican a ambos, y otras son específicas de [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] o [!INCLUDE[net_core](../../../includes/net-core-md.md)].  
  
-   **ASP.NET 5**  
  
     .NET Framework 2015 incluye ASP.NET 5, que es una plataforma .NET eficiente para la compilación de aplicaciones modernas basadas en la nube. La plataforma es modular, por lo que puede incluir solo aquellas características que se necesitan en la aplicación. Puede hospedarse en IIS o autohospedarse en un proceso personalizado y se pueden ejecutar aplicaciones con diferentes versiones de .NET Framework en el mismo servidor. Incluye un nuevo sistema de configuración de entorno que está diseñado para la implementación de la nube.  
  
     MVC, Web API y Web Pages están unificados en un marco único llamado MVC 6. Las aplicaciones de ASP.NET 5 se compilan con las nuevas herramientas de Visual Studio 2015. Las aplicaciones existentes funcionarán en el nuevo .NET Framework; sin embargo, para compilar una aplicación que use MVC 6 o SignalR 3, debe usar el sistema de proyectos de Visual Studio 2015.  
  
     Para obtener información, consulte [ASP.NET 5](http://go.microsoft.com/fwlink/?LinkId=518238).  
  
-   **Actualizaciones de ASP.NET**  
  
    -   **API basada en tareas para el vaciado de respuesta asincrónica**  
  
         Ahora, ASP.NET proporciona una API sencilla basada en tareas para vaciar la respuesta asincrónica, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=fullName>, que permite que las respuestas se guarden de forma asincrónica mediante el lenguaje `async/await` admite.  
  
    -   `Model binding supports task-returning methods`  
  
         ASP.NET agregó en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] la característica Enlace de modelos, que habilita un enfoque extensible y centrado en el código en las operaciones de datos basadas en CRUD de las páginas de formularios Web Forms y los controles de usuario. Admite ahora el sistema de enlace de modelos <xref:System.Threading.Tasks.Task>-métodos de enlace del modelo. Esta característica permite que los desarrolladores de formularios Web Forms aprovechen las ventajas que presenta la escalabilidad de la asincronía con la facilidad del sistema de enlace de datos al usar las versiones más recientes de ORM, incluido Entity Framework.  
  
         El enlace de modelos asincrónicos se controla con la opción de configuración `aspnet:EnableAsyncModelBinding`.  
  
        ```  
  
        <appSettings>  
           <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />  
        </appSettings>  
  
        ```  
  
         En las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], el valor predeterminado es `true`. En las aplicaciones que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] y que tienen como destino una versión anterior de .NET Framework, el valor predeterminado es `false`. Se puede habilitar estableciendo la opción de configuración en `true`.  
  
    -   **Compatibilidad HTTP/2 (Windows 10)**  
  
         [HTTP/2](http://www.wikipedia.org/wiki/HTTP/2) es una nueva versión del protocolo HTTP que proporciona el uso mucho mejor de conexión (menos de ida y vuelta entre cliente y servidor), lo que produce menor latencia cargar páginas web para los usuarios.  Las páginas web (no de servicios) aprovechan HTTP/2 al máximo, porque el protocolo se optimizó para la solicitud de varios artefactos como parte de una sola experiencia. La compatibilidad para HTTP/2 se agregó a ASP.NET en .NET Framework 4.6. Como la funcionalidad de red existe en varios niveles, se necesitaban nuevas características en Windows, IIS y ASP.NET para habilitar HTTP/2. Debe ejecutar Windows 10 para usar HTTP/2 con ASP.NET.  
  
         HTTP/2 también se admite y activado de forma predeterminada para Windows Universal de 10 Windows aplicaciones de la plataforma (UWP) que utilizan el <xref:System.Net.Http.HttpClient?displayProperty=fullName> API.  
  
         Para proporcionar una manera de usar el [PUSH_PROMISE](http://http2.github.io/http2-spec/#PUSH_PROMISE) de características en aplicaciones de ASP.NET, un nuevo método con dos sobrecargas, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> y <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, se ha agregado a la <xref:System.Web.HttpResponse> clase.  
  
        > [!NOTE]
        >  Mientras que ASP.NET 5 admite HTTP/2, la compatibilidad con la característica PUSH PROMISE aún no se ha agregado.  
  
         El explorador y el servidor web (IIS en Windows) hacen todo el trabajo. No tiene que hacer el trabajo más farragoso para los usuarios.  
  
         La mayoría de los [principales exploradores admiten HTTP/2](http://www.wikipedia.org/wiki/HTTP/2), por lo que es probable que los usuarios se beneficiarán de la compatibilidad con HTTP/2 si el servidor lo admite.  
  
    -   **Compatibilidad con el protocolo de enlace de Token**  
  
         Google y Microsoft colaboraron en un nuevo enfoque para la autenticación, denominada el [protocolo de enlace de Token](https://github.com/TokenBinding/Internet-Drafts). La premisa es que los tokens de autenticación (en la memoria caché del explorador) pueden robados y usados por delincuentes para obtener acceso a recursos seguros en caso contrario (por ejemplo, su cuenta bancaria) sin necesidad de contraseña ni otra información privilegiada. El nuevo protocolo tiene como objetivo mitigar este problema.  
  
         El Protocolo de enlace de tokens se implementará en Windows 10 como una característica del explorador. Las aplicaciones de ASP.NET participarán en el protocolo para validar la legitimidad de los tokens de autenticación. Las implementaciones de cliente y de servidor establecen la protección de extremo a extremo especificada por el protocolo.  
  
    -   **Algoritmos de hash de una cadena aleatoria**  
  
         .NET Framework 4.5 introdujo un [algoritmo de hash de una cadena aleatoria](https://msdn.microsoft.com/library/jj152924.aspx). pero no era compatible con ASP.NET porque algunas características de ASP.NET dependían de un código hash estable. En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ya se admiten los algoritmos hash de cadena aleatoria. Para habilitar esta característica, use la opción de configuración `aspnet:UseRandomizedStringHashAlgorithm`.  
  
        ```  
  
        <appSettings>  
           <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />  
        </appSettings>  
  
        ```  
  
-   **ADO.NET**  
  
     ADO .NET ahora es compatible con la característica Always Encrypted disponible en SQL Server 2016 Community Technology Preview 2 (CTP2). Con Always Encrypted, SQL Server puede realizar operaciones en los datos cifrados y, lo mejor de todo, es que la clave de cifrado reside, junto con la aplicación, en el entorno de confianza del cliente y no en el servidor. Always Encrypted protege los datos del cliente para que los administradores de bases de datos no tengan acceso a los datos de texto sin formato. El cifrado y descifrado de datos ocurre de forma transparente en el nivel de controlador, lo que minimiza los cambios que deben realizarse en las aplicaciones existentes. Para obtener más información, consulte [siempre cifrados (motor de base de datos)](https://msdn.microsoft.com/library/mt163865\(v=sql.130\).aspx) y [siempre cifrados (desarrollo de cliente)](https://msdn.microsoft.com/library/mt147923\(v=sql.130\).aspx).  
  
-   **Compilador JIT de&64; bits para código administrado**  
  
     .NET Framework 4.6 incluye una nueva versión del compilador JIT de 64 bits (llamado originalmente RyuJIT). El nuevo compilador de 64 bits proporciona importantes mejoras de rendimiento con respecto al antiguo compilador JIT de 64 bits. El nuevo compilador de 64 bits está habilitado para los procesos de 64 bits que se ejecutan en .NET Framework 4.6. La aplicación se ejecutará en un proceso de 64 bits si se ha compilado como aplicación de 64 bits o AnyCPU y se está ejecutando en un sistema operativo de 64 bits. Aunque se hayan tomado precauciones para efectuar la transición al nuevo compilador de la manera más transparente posible, es posible que se produzcan cambios en el comportamiento. Nos gustaría que se pusiera en contacto con nosotros si encuentra algún problema al usar el nuevo compilador JIT. Póngase en contacto con nosotros a través de [Microsoft Connect](http://connect.microsoft.com/) si detecta un problema que puede estar relacionadas con el nuevo compilador JIT de 64 bits.  
  
     El nuevo compilador JIT de 64 bits también incluye características de aceleración de hardware SIMD cuando se acopla con tipos habilitados para SIMD en el <xref:System.Numerics> espacio de nombres, que puede producir mejoras de buen rendimiento.  
  
-   **Mejoras del cargador de ensamblado**  
  
     Ahora el cargador de ensamblados usa la memoria de un modo más eficaz al descargar ensamblados de IL después de cargar una imagen NGEN correspondiente. Este cambio reduce la memoria virtual, que es bastante útil en las aplicaciones de 32 bits de gran tamaño (por ejemplo, Visual Studio), y también guarda la memoria física.  
  
-   **Cambios de la biblioteca de clases base**  
  
     Se agregaron muchas nuevas API a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] para habilitar escenarios clave. Incluyen los siguientes cambios y adiciones:  
  
    -   **IReadOnlyCollection<> \</> \> implementaciones**  
  
         Las colecciones adicionales implementan <xref:System.Collections.Generic.IReadOnlyCollection%601> como <xref:System.Collections.Generic.Queue%601> y <xref:System.Collections.Generic.Stack%601>.  
  
    -   **CultureInfo.CurrentCulture y CultureInfo.CurrentUICulture**  
  
         El <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> propiedades ahora son de lectura y escritura en lugar de sólo lectura. Si asigna un nuevo <xref:System.Globalization.CultureInfo> objeto a estas propiedades, la referencia cultural del subproceso actual definida por el `Thread.CurrentThread.CurrentCulture` propiedad y la interfaz de usuario actual del subproceso de referencia cultural definida por el `Thread.CurrentThread.CurrentUICulture` propiedades también cambian.  
  
    -   **Mejoras en la colección de elementos no utilizados (GC)**  
  
         El <xref:System.GC> ahora incluye la clase <xref:System.GC.TryStartNoGCRegion%2A> y <xref:System.GC.EndNoGCRegion%2A> métodos que permiten impedir la recolección de elementos no utilizados durante la ejecución de una ruta crítica.  
  
         Una nueva sobrecarga de la <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=fullName> método le permite controlar si el montón de objeto pequeño y montón de objeto grande se exploran y compactan o si solo se exploran.  
  
    -   **Tipos habilitados para SIMD**  
  
         El <xref:System.Numerics> espacio de nombres incluye ahora varios tipos habilitados para SIMD, como <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3>, y <xref:System.Numerics.Vector4>.  
  
         Como el nuevo compilador JIT de 64 bits también incluye características de aceleración de hardware SIMD, hay mejoras de rendimiento considerablemente importantes al usar los tipos habilitados para SIMD con el nuevo compilador JIT de 64 bits.  
  
    -   **Actualizaciones de criptografía**  
  
         El <xref:System.Security.Cryptography?displayProperty=fullName> API se está actualizando para admitir la [API de criptografía de Windows CNG](https://msdn.microsoft.com/library/windows/desktop/aa376214.aspx). Las versiones anteriores de .NET Framework han confiado por completo en un [una versión anterior de la API de criptografía de Windows](https://msdn.microsoft.com/library/windows/desktop/aa380255.aspx) como base para la <xref:System.Security.Cryptography?displayProperty=fullName> implementación. Recibimos solicitudes para admitir la API de CNG, ya que admite [algoritmos de criptografía modernos](https://msdn.microsoft.com/library/windows/desktop/bb204775.aspx#suite_b_support), que son importantes para determinadas categorías de aplicaciones.  
  
         .NET Framework 4.6 incluye las siguientes mejoras para admitir las API de criptografía de CNG de Windows:  
  
        -   Un conjunto de métodos de extensión para los certificados X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` y `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, que devuelven, siempre que sea posible, una implementación basada en CNG en lugar de una implementación basada en CAPI (algunas tarjetas inteligentes, entre otros, siguen necesitando CAPI, mientras que las API controlan la reserva).  
  
        -   El <xref:System.Security.Cryptography.RSACng?displayProperty=fullName> (clase), que proporciona una implementación de CNG del algoritmo RSA.  
  
        -   Mejoras en la API de RSA, de modo que las acciones habituales ya no necesitan ninguna conversión. Por ejemplo, cifrado de datos mediante un <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> objeto requiere código similar al siguiente en versiones anteriores de .NET Framework.  
  
             [!code-csharp[WhatsNew.Casting#1](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
             [!code-vb[WhatsNew.Casting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]  
  
             El código que usa las nuevas API de criptografía en .NET Framework 4.6 se puede reescribir del siguiente modo para evitar la conversión.  
  
             [!code-csharp[WhatsNew.Casting#2](../../../samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
             [!code-vb[WhatsNew.Casting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]  
  
    -   **Compatibilidad para convertir las fechas y horas a o desde la hora de Unix**  
  
         Se agregaron los nuevos métodos siguientes a la <xref:System.DateTimeOffset> estructura para admitir la conversión de valores de fecha y hora a o desde la hora Unix:  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=fullName>  
  
        -   <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=fullName>  
  
    -   **Modificadores de compatibilidad**  
  
         El nuevo <xref:System.AppContext> clase agrega una nueva característica de compatibilidad que permite a los autores de bibliotecas proporcionar un mecanismo de desactivación uniforme para la nueva funcionalidad para sus usuarios. Establece un contrato flexible entre los componentes para poder comunicar una solicitud de cancelación de la participación. Esta capacidad normalmente es importante cuando se realiza un cambio en la funcionalidad existente. Por el contrario, la nueva funcionalidad participa de forma implícita.  
  
         Con <xref:System.AppContext>, las bibliotecas definen y exponen modificadores de compatibilidad, mientras que el código que depende de ellas pueden configurar dichos modificadores para influir en el comportamiento de la biblioteca. De forma predeterminada, las bibliotecas proporcionan la nueva funcionalidad y solo la modifican (es decir, ofrecen la funcionalidad anterior) si el modificador está establecido.  
  
         Una aplicación (o una biblioteca) puede declarar el valor de un modificador (que es siempre un <xref:System.Boolean> valor) que define una biblioteca dependiente. El modificador siempre es implícitamente `false`. Cuando el modificador se establece en `true`, se habilita. Cuando el modificador se establece explícitamente en `false`, proporciona el nuevo comportamiento.  
  
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
  
        -   *Switch*.* espacio de nombres*.* nombre del conmutador*  
  
        -   *Switch*.* library*.* nombre del conmutador*  
  
    -   **Cambios en el modelo asincrónico basado en tareas (TAP)**  
  
         Para las aplicaciones que tienen como destino el [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> objetos heredan la referencia cultural y la referencia cultural de la interfaz de usuario del subproceso que realiza la llamada. No se ve afectado el comportamiento de las aplicaciones que tienen como destino las versiones anteriores de .NET Framework o que no especifican una versión concreta de .NET Framework. Para obtener más información, consulte la sección "Referencia cultural y operaciones asincrónicas basadas en tareas" de la <xref:System.Globalization.CultureInfo> tema de la clase.  
  
         El <xref:System.Threading.AsyncLocal%601?displayProperty=fullName> clase le permite representar datos ambiente locales a un flujo de control asincrónico determinado, como un `async` método. Se puede usar para conservar los datos en todos los subprocesos. También puede definir un método de devolución de llamada que recibirá una notificación cada vez que cambian los datos de ambientales ya sea porque la <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=fullName> explícitamente se ha cambiado la propiedad, o porque el subproceso encontró una transición de contexto.  
  
         Tres métodos útiles, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=fullName>, y <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=fullName>, se han agregado a la tarea de modelo asincrónico basado (TAP) para devolver las tareas completadas en un estado determinado.  
  
         El <xref:System.IO.Pipes.NamedPipeClientStream> clase ahora admite la comunicación asincrónica con sus nuevos <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. .  
  
    -   **EventSource ahora admite operaciones de escritura al registro de eventos**  
  
         Ahora puede usar el <xref:System.Diagnostics.Tracing.EventSource> mensajes de clase al registro operativo o administrativo en el registro de eventos, además a cualquier sesión de ETW existente creada en el equipo. Anteriormente, tenía que usar el paquete de NuGet Microsoft.Diagnostics.Tracing.EventSource para poder aprovechar esta funcionalidad, que ahora está integrada en .NET Framework 4.6.  
  
         El paquete de NuGet y .NET Framework 4.6 se han actualizado con las siguientes características:  
  
        -   **Eventos dinámicos**  
  
             Permite eventos definidos "sobre la marcha" sin crear métodos de eventos.  
  
        -   **Cargas enriquecido**  
  
             Permite que las matrices y clases con atributos especiales, así como los tipos primitivos, se pasen como carga  
  
        -   **Seguimiento de actividad**  
  
             Hace que los eventos de inicio y de detención etiqueten eventos entre ellos con un identificador que representa todas las actividades actualmente activas.  
  
         Para admitir estas características, sobrecargados <xref:System.Diagnostics.Tracing.EventSource.Write%2A> método se ha agregado a la <xref:System.Diagnostics.Tracing.EventSource> clase.  
  
-   **Windows Presentation Foundation (WPF)**  
  
    -   **Mejoras de HDPI**  
  
         Se ha mejorado la compatibilidad con HDPI en WPF en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Se han hecho cambios en el redondeo del diseño para reducir las instancias de recorte en los controles que contienen bordes. De forma predeterminada, esta característica está habilitada sólo si su <xref:System.Runtime.Versioning.TargetFrameworkAttribute> se establece en .NET 4.6.  Las aplicaciones que las versiones anteriores de framework de destino, pero se ejecutan en el [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] puede participar en el nuevo comportamiento agregando la siguiente línea a la [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sección del archivo app.config:  
  
        ```  
  
        <AppContextSwitchOverrides  
        value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"  
        />  
  
        ```  
  
         Actualmente, las ventanas de WPF que ocupan varios monitores con diferentes valores de PPP (configuración de varios PPP) se representan completamente sin regiones oscurecidas. Puede deshabilitar este comportamiento agregando la siguiente línea a la sección `<appSettings>` del archivo app.config:  
  
        ```  
  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
  
        ```  
  
         Compatibilidad para cargar automáticamente el cursor derecho basándose en la configuración de PPP se ha agregado a <xref:System.Windows.Input.Cursor?displayProperty=fullName>.  
  
    -   **Es mejor táctil**  
  
         Notifica al cliente [conectar](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) que toque genera un comportamiento impredecible se han abordado en la [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Ahora, el umbral de doble punteo de las aplicaciones de WPF y de la Tienda Windows es el mismo en Windows 8.1 y versiones superiores.  
  
    -   **Compatibilidad con la ventana secundaria transparente**  
  
         En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], WPF admite las ventanas secundarias transparentes en Windows 8.1 y versiones superiores, de manera que puede crear ventanas secundarias transparentes y no rectangulares en las ventanas de nivel superior. Puede habilitar esta característica estableciendo la <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=fullName> propiedad `true`.  
  
-   **Windows Communication Foundation (WCF)**  
  
    -   **Compatibilidad con SSL**  
  
         WCF ahora admite la versión con SSL TLS 1.1 y TLS 1.2, además de SSL 3.0 y TLS 1.0, al usar NetTcp con la autenticación de cliente y la seguridad de transporte. Ahora se puede seleccionar el protocolo que se quiere usar o bien deshabilitar protocolos antiguos menos seguros; Esto puede realizarse estableciendo el <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> propiedad o agregando lo siguiente en un archivo de configuración.  
  
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
  
    -   **Envío de mensajes con distintas conexiones HTTP**  
  
         Ahora WCF permite que los usuarios se aseguren de que se han enviado determinados mensajes con diferentes conexiones HTTP subyacentes. Existen dos modos para hacer esto:  
  
        -   **Utilizando un prefijo de nombre de grupo de conexión**  
  
             Los usuarios pueden especificar una cadena que WCF usará como prefijo del nombre del grupo de conexión. Se envían dos mensajes con prefijos diferentes por distintas conexiones HTTP subyacentes. Establezca el prefijo agregando un par de clave y valor para el mensaje <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=fullName> propiedad. La clave es "HttpTransportConnectionGroupNamePrefix"; el valor es el prefijo deseado.  
  
        -   **Uso de diferentes generadores de canales**  
  
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
  
     Ahora puede incluir el identificador de transacción distribuida para la transacción que ha provocado una excepción derivada de <xref:System.Transactions.TransactionException> que se produzca. Para ello, agregue la siguiente clave a la sección `appSettings` del archivo app.config:  
  
    ```  
    <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>   
    ```  
  
     El valor predeterminado es `false`.  
  
-   **Funciones de red**  
  
    -   **Reutilización de socket**  
  
         Windows 10 incluye un nuevo algoritmo de red de alta escalabilidad que optimiza los recursos del equipo con la reutilización de los puertos locales para las conexiones TCP salientes. .NET Framework 4.6 es compatible con este algoritmo y permite que las aplicaciones de .NET aprovechen el nuevo comportamiento. En versiones anteriores de Windows había un límite de conexiones simultáneas artificial (normalmente de 16.384, el tamaño predeterminado del intervalo de puertos dinámicos) y esto podía limitar la escalabilidad de un servicio provocando el agotamiento de puertos durante la carga.  
  
         Se han agregado dos API nuevas a [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] para permitir la reutilización de puertos, lo que elimina de forma eficaz el límite de 64 K de las conexiones simultáneas:  
  
        -   El <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> valor de enumeración.  
  
        -   El <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> propiedad.  
  
         De forma predeterminada, el <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> propiedad es `false` a menos que la `HWRPortReuseOnSocketBind` valor de la `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` clave del registro se establece en 0 x 1. Para habilitar la reutilización de puerto local en las conexiones HTTP, establezca el <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=fullName> propiedad `true`. Esto hace que todas las conexiones de socket TCP salientes de <xref:System.Net.Http.HttpClient> y <xref:System.Net.HttpWebRequest> a usar una nueva opción de socket de Windows 10, [SO_REUSE_UNICASTPORT](https://msdn.microsoft.com/library/windows/desktop/ms740532.aspx), que permite la reutilización de puerto local.  
  
         Los programadores que crean una aplicación sólo sockets pueden especificar la <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> opción al llamar a un método como <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=fullName> para que los sockets salientes reutilización puertos locales durante el enlace.  
  
    -   **Compatibilidad con nombres de dominio internacionales y PunyCode**  
  
         Una nueva propiedad, <xref:System.Uri.IdnHost%2A>, se ha agregado a la <xref:System.Uri> clase para admitir mejor los nombres de dominio internacionales y PunyCode.  
  
-   **Cambiar el tamaño en controles de formularios Windows Forms.**  
  
     Esta característica se ha ampliado en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] para incluir el <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.ToolStripSplitButton> tipos y el rectángulo especificado por el <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> propiedad que se usa al dibujar un <xref:System.Drawing.Design.UITypeEditor>.  
  
     Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):  
  
    ```  
  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
  
    ```  
  
-   **Compatibilidad para codificaciones de páginas de código**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)] admite principalmente las codificaciones Unicode y, de forma predeterminada, proporciona compatibilidad limitada para las codificaciones de páginas de códigos. Puede agregar compatibilidad para codificaciones de páginas de código disponibles en .NET Framework pero no se admiten en [!INCLUDE[net_core](../../../includes/net-core-md.md)] registrando codificaciones de páginas de código con el <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=fullName> método. Para obtener más información, consulte [System.Text.CodePagesEncodingProvider](https://msdn.microsoft.com/en-us/library/system.text.codepagesencodingprovider.aspx).  
  
-   **.NET native**  
  
     Las aplicaciones de Windows para Windows 10 que tienen como destino [!INCLUDE[net_core](../../../includes/net-core-md.md)] y están escritas en C# o Visual Basic pueden aprovechar una nueva tecnología que compila las aplicaciones en código nativo en lugar de IL. Generan aplicaciones que se caracterizan por un inicio y tiempos de ejecución más rápidos. Para obtener más información, consulte [compilar aplicaciones con .NET Native](../../../docs/framework/net-native/index.md). Para obtener información general sobre .NET Native que examina cómo difiere de la compilación JIT y NGEN y lo que eso significa que el código, consulte [.NET Native y compilación](../../../docs/framework/net-native/net-native-and-compilation.md).  
  
     Las aplicaciones se compilan en código nativo de forma predeterminada cuando se compilan con Visual Studio 2015. Para obtener más información, consulte [Introducción a .NET Native](../../../docs/framework/net-native/getting-started-with-net-native.md).  
  
     Para admitir la depuración de aplicaciones .NET Native, se agregó una serie de interfaces y enumeraciones nuevas a la API de depuración no administrada. Para obtener más información, consulte el [depuración (referencia de la API no administrada)](../../../ml/index.xml) tema.  
  
-   **Paquetes de .NET Framework de código abierto**  
  
     [!INCLUDE[net_core](../../../includes/net-core-md.md)]paquetes, como las colecciones inmutables, [API SIMD](http://go.microsoft.com/fwlink/?LinkID=518639), y API de red como los que se encuentran en la <xref:System.Net.Http> ahora están disponibles como paquetes de código abierto en el espacio de nombres [GitHub](https://github.com/). Para obtener acceso al código, vea [NetFx en GitHub](http://go.microsoft.com/fwlink/?LinkID=518634). Para que obtener más información y saber cómo contribuyen a estos paquetes, consulte [de código abierto y .NET Core](../../../docs/framework/get-started/net-core-and-open-source.md), [página principal de .NET en GitHub](http://go.microsoft.com/fwlink/?LinkID=518635).  
  
 [Volver al principio](#introduction)  
  
<a name="v452"></a>   
## <a name="whats-new-in-the-net-framework-452"></a>Novedades de .NET Framework 4.5.2  
  
-   **Nuevas API para aplicaciones de ASP.NET.** El nuevo <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=fullName> y <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=fullName> métodos le permiten inspeccionar y modificar encabezados de respuesta y el código de estado cuando se vuelca la respuesta a la aplicación cliente. Puede usar estos métodos en lugar de la <xref:System.Web.HttpApplication.PreSendRequestHeaders> y <xref:System.Web.HttpApplication.PreSendRequestContent> eventos; son más eficaz y confiable.  
  
     El <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=fullName> método le permite programar elementos de trabajo de fondo pequeño. ASP.NET realiza un seguimiento de estos elementos y evita que IIS termine el proceso de trabajo de manera abrupta hasta que se completen todos los elementos de trabajo en segundo plano. Este método no se puede invocar desde fuera del dominio de una aplicación administrada de ASP.NET.  
  
     El nuevo <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=fullName> y <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=fullName> propiedades devuelven valores booleanos que indican si se han escrito los encabezados de respuesta. Puede utilizar estas propiedades para asegurarse de que las llamadas a API como <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=fullName> (que producen excepciones si se han escrito los encabezados) se realizará correctamente.  
  
-   **Cambiar el tamaño en controles de formularios Windows Forms.** Esta característica se ha ampliado. Ahora se puede usar el valor de PPP del sistema para cambiar el tamaño de componentes de los siguientes controles adicionales (por ejemplo, la flecha desplegable en cuadros combinados):  
  
     <xref:System.Windows.Forms.ComboBox>   
     <xref:System.Windows.Forms.ToolStripComboBox>   
     <xref:System.Windows.Forms.ToolStripMenuItem>   
     <xref:System.Windows.Forms.Cursor>   
     <xref:System.Windows.Forms.DataGridView>   
     <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
     Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
-   **Nueva característica de flujo de trabajo.** Un administrador de recursos que está utilizando el <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> (método) (y, por tanto, implementa el <xref:System.Transactions.IPromotableSinglePhaseNotification> interfaz) puede usar el nuevo <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> método para pedir lo siguiente:  
  
    -   Promocionar la transacción a una transacción de MSDTC (Coordinador de transacciones distribuidas de Microsoft).  
  
    -   Reemplace <xref:System.Transactions.IPromotableSinglePhaseNotification> con una <xref:System.Transactions.ISinglePhaseNotification>, que es una inscripción duradera que admite confirmaciones de fase única.  
  
     Esto puede realizarse en el mismo dominio de la aplicación y no requiere que ningún código sin administrar adicional interactúe con MSDTC para realizar la promoción. Se puede llamar al nuevo método solo cuando hay una llamada pendiente de <xref:System.Transactions?displayProperty=fullName> a la <xref:System.Transactions.IPromotableSinglePhaseNotification> `Promote` método implementado por la inscripción puede promover.  
  
-   **Mejoras de generación de perfiles.** Las siguientes API de generación de perfiles no administradas proporcionan una generación de perfiles más sólida:  
  
     [COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)](../../../ocs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)   
     [COR_PRF_HIGH_MONITOR (enumeración)](../../../ocs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)   
     [Getassemblyreferences (método)](../Topic/ICorProfilerCallback6::GetAssemblyReferences%20Method.md)   
     [GetEventMask2 (método)](../Topic/ICorProfilerInfo5::GetEventMask2%20Method.md)   
     [SetEventMask2 (método)](../Topic/ICorProfilerInfo5::SetEventMask2%20Method.md)   
     [AddAssemblyReference (método)](../Topic/ICorProfilerAssemblyReferenceProvider::AddAssemblyReference%20Method.md)  
  
     Las implementaciones de `ICorProfiler` anteriores eran compatibles con la carga diferida de ensamblados dependientes. Las nuevas API de generación de perfiles requieren que los ensamblados dependientes insertados por el generador de perfiles se carguen inmediatamente, en lugar de cargarse cuando la aplicación se haya inicializado por completo. Este cambio no afecta a los usuarios de las API de `ICorProfiler` existentes.  
  
-   **Mejoras en la depuración.** Las API de depuración no administradas proporcionan una mejor integración con un generador de perfiles. Ahora se puede acceder a metadatos insertados por el generador de perfiles, así como a variables locales y código producidos por solicitudes de ReJIT del compilador en la depuración de volcados.  
  
     [SetWriteableMetadataUpdateMode (método)](../Topic/ICorDebugProcess7::SetWriteableMetadataUpdateMode%20Method.md)   
     [EnumerateLocalVariablesEx (método)](../Topic/ICorDebugILFrame4::EnumerateLocalVariablesEx%20Method.md)   
     [GetLocalVariableEx (método)](../Topic/ICorDebugILFrame4::GetLocalVariableEx%20Method.md)   
     [GetCodeEx (método)](../Topic/ICorDebugILFrame4::GetCodeEx%20Method.md)   
     [Getactiverejitrequestilcode (método)](../Topic/ICorDebugFunction3::GetActiveReJitRequestILCode%20Method.md)   
     [Getinstrumentedilmap (método)](../Topic/ICorDebugILCode2::GetInstrumentedILMap%20Method.md)  
  
-   **Cambios en el seguimiento de eventos.** .NET Framework 4.5.2 permite realizar el seguimiento de actividades fuera del proceso, basado en Seguimiento de eventos para Windows (ETW), para una mayor área expuesta. Esto permite a los proveedores de Administración avanzada de energía (APM) proporcionar herramientas sencillas que realicen un seguimiento preciso de solicitudes y actividades individuales en distintos subprocesos.  Estos eventos solo se desencadenan cuando son habilitados por los controladores de ETW; por lo tanto, los cambios no afectan a código de ETW escrito anteriormente o a código que se ejecute cuando ETW esté deshabilitado.  
  
-   **Promoción de una transacción y se convierte en una inscripción duradera**  
  
     <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=fullName> es una nueva API que se agregan a .NET Framework 4.5.2 y 4.6:  
  
    ```  
  
    [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
    public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,  
                                              IPromotableSinglePhaseNotification promotableNotification,  
                                              ISinglePhaseNotification enlistmentNotification,  
                                              EnlistmentOptions enlistmentOptions)  
  
    ```  
  
     El método se puede usar una inscripción que se creó anteriormente mediante <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=fullName> en respuesta a la <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> método. Pide a `System.Transactions` que promueva la transacción a una transacción MSDTC y que "convierta" la inscripción que se puede promover en una inscripción duradera. Cuando este método finaliza correctamente, el <xref:System.Transactions.IPromotableSinglePhaseNotification> interfaz ya no se hace referencia por `System.Transactions`, y las notificaciones futuras llegarán en proporcionado <xref:System.Transactions.ISinglePhaseNotification> interfaz. La inscripción en cuestión debe actuar como inscripción duradera y admitir el registro y la recuperación de transacciones. Consulte <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=fullName> para obtener más información. Además, debe admitir la inscripción <xref:System.Transactions.ISinglePhaseNotification>.  Este método puede *sólo* llamará al procesar una <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=fullName> llamar. Si no es el caso, un <xref:System.Transactions.TransactionException> excepción.  
  
 [Volver al principio](#introduction)  
  
<a name="v451"></a>   
## <a name="whats-new-in-the-net-framework-451"></a>Novedades de .NET Framework 4.5.1  
 **Actualizaciones de abril de 2014**:  
  
-   [Visual Studio 2013 Update 2](http://go.microsoft.com/fwlink/p/?LinkId=393658) incluye actualizaciones para las plantillas de biblioteca de clases Portable para admitir estos escenarios:  
  
    -   Puede usar las API de Windows en tiempo de ejecución en bibliotecas portables cuyo destino sea Windows 8.1, Windows Phone 8.1 y Windows Phone Silverlight 8.1.  
  
    -   Puede incluir XAML (tipos de Windows.UI.XAML) en las bibliotecas portables cuyo destino es Windows 8.1 o Windows Phone 8.1. Se admiten las siguientes plantillas de XAML: página en blanco, diccionario de recursos, control basado en modelo y control de usuario.  
  
    -   Se puede crear un componente de Windows en tiempo de ejecución portable (archivo .winmd) para usarlo en aplicaciones de la Tienda que tengan como destino Windows 8.1 y Windows Phone 8.1.  
  
    -   Puede cambiar el destino de una biblioteca de clases de la Tienda Windows o la Tienda de Windows Phone como biblioteca de clases portable.  
  
     Para obtener más información acerca de estos cambios, consulte [biblioteca de clases Portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).  
  
-   El conjunto de contenido de .NET Framework ahora incluye documentación para [!INCLUDE[net_native](../../../includes/net-native-md.md)], que es una tecnología de precompilación para crear e implementar aplicaciones de Windows. [!INCLUDE[net_native](../../../includes/net-native-md.md)] compila aplicaciones directamente en código nativo, en lugar de hacerlo en un lenguaje intermedio (IL), lo que mejora el rendimiento. Para obtener más información, consulte [compilar aplicaciones con .NET Native](../../../docs/framework/net-native/index.md).  
  
-   El [origen de referencia de .NET Framework](http://referencesource.microsoft.com/) proporciona una nueva experiencia de exploración y una funcionalidad mejorada. Ahora puede examinar el código de origen de .NET Framework en línea, [descargar la referencia](http://referencesource.microsoft.com/download.html) para verla sin conexión y de paso a través de los orígenes (incluidas las revisiones y actualizaciones) durante la depuración. Para obtener más información, consulte la entrada de blog [un nuevo aspecto para .NET Reference Source](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx).  
  
 Estas son las principales características nuevas y mejoras realizadas en .NET Framework 4.5.1:  
  
-   Redirección automática de enlace de ensamblados. A partir de [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], cuando se compila una aplicación cuyo destino es [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], se pueden agregar al archivo de configuración de la aplicación redirecciones de enlace si la aplicación o sus componentes hacen referencia a varias versiones del mismo ensamblado. Esta característica también se puede habilitar en proyectos que tienen como destino versiones anteriores de .NET Framework. Para obtener más información, consulte [Cómo: habilitar y deshabilitar redireccionamiento de enlace automático](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).  
  
-   Capacidad de recopilar información de diagnóstico para ayudar a los desarrolladores a mejorar el rendimiento de las aplicaciones de servidor y en la nube. Para obtener más información, consulte el <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> y <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> métodos en el <xref:System.Diagnostics.Tracing.EventSource> clase.  
  
-   Capacidad de compactar explícitamente el montón de objetos grandes (LOH) durante la recolección de elementos no utilizados. Para obtener más información, consulte el <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=fullName> propiedad.  
  
-   Mejoras adicionales de rendimiento como, por ejemplo, la suspensión de la aplicación ASP.NET, mejoras de JIT con varios núcleos o reducción del tiempo de inicio de la aplicación tras una actualización de .NET Framework. Para obtener más información, consulte el [anuncio de .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx) y [suspender la aplicación ASP.NET](http://blogs.msdn.com/b/dotnet/archive/2013/10/09/asp-net-app-suspend-responsive-shared-net-web-hosting.aspx) entrada de blog.  
  
 Las mejoras en Windows Forms son las siguientes:  
  
-   Cambio de tamaño en controles de Windows Forms. Puede usar el valor de PPP del sistema para cambiar el tamaño de los componentes de controles (por ejemplo, los iconos que aparecen en una cuadrícula de propiedades); para ello, active esta opción con una entrada en el archivo de configuración de la aplicación (app.config). Actualmente, esta característica es compatible con los siguientes controles de Windows Forms:  
  
     <xref:System.Windows.Forms.PropertyGrid>   
     <xref:System.Windows.Forms.TreeView>   
     Algunos aspectos de la <xref:System.Windows.Forms.DataGridView> (consulte [nuevas características en 4.5.2](#v452) de controles compatibles)  
  
     Para habilitar esta característica, agregue un nuevo <> \> elemento al archivo de configuración (app.config) y establezca el `EnableWindowsFormsHighDpiAutoResizing` elemento `true`:  
  
    ```  
    <appSettings>  
       <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />  
    </appSettings>  
    ```  
  
 Algunas de las mejoras realizadas durante la depuración de las aplicaciones de .NET Framework en [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] son:  
  
-   Valores devueltos en el depurador de Visual Studio. Al depurar una aplicación administrada en [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], en la ventana Automático se muestran los valores y tipos devueltos de los métodos. Esta información está disponible para el escritorio, la Tienda Windows y las aplicaciones Windows Phone. Para obtener más información, consulte [examinar los valores devueltos de llamadas al método](http://msdn.microsoft.com/library/e3245b37-8e2e-4200-ba84-133726e95f1f\(v=vs.120\).aspx) en MSDN Library.  
  
-   Editar y continuar en aplicaciones de 64 bits. [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] admite la característica Editar y continuar en aplicaciones administradas de 64 bits para el escritorio, la Tienda Windows y Windows Phone. Las limitaciones existentes siguen en vigor para las aplicaciones de 32 bits y 64 bits (vea la última sección de la [cambios admitidos en el código (C#)](http://msdn.microsoft.com/library/ms164927\(v=vs.120\).aspx) artículo).  
  
-   Depuración asincrónica. Para facilitar la depuración de aplicaciones asincrónicas en [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], la pila de llamadas oculta el código de infraestructura proporcionado por los compiladores para permitir la programación asincrónica y, además, encadena los principales marcos lógicos para que pueda seguir la ejecución lógica del programa con mayor claridad. La ventana Tareas reemplaza a la ventana Tareas paralelas, donde se muestran las tareas relacionadas con un punto de interrupción determinado, así como las demás tareas que actualmente están activas o programadas en la aplicación. Encontrará información acerca de esta característica en la sección "depuración asincrónica" de la [anuncio de .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
-   Mayor compatibilidad con las excepciones de los componentes de Windows en tiempo de ejecución. En [!INCLUDE[win81](../../../includes/win81-md.md)], las excepciones que se inician en aplicaciones de la Tienda Windows conservan información sobre el error que provocó la excepción, incluso entre diferentes lenguajes. Encontrará información acerca de esta característica en la sección "Desarrollo de aplicaciones de la tienda de Windows" de la [anuncio de .NET Framework 4.5.1](http://blogs.msdn.com/b/dotnet/archive/2013/06/26/announcing-the-net-framework-4-5-1-preview.aspx).  
  
 A partir de [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], puede utilizar el [perfil interactiva herramienta de optimización administrados (Mpgo.exe)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md) optimizar [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones, así como aplicaciones de escritorio.  
  
 Para las nuevas características de ASP.NET 4.5.1, consulte [ASP.NET 4.5.1 y Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) en el sitio ASP.NET.  
  
 [Volver al principio](#introduction)  
  
<a name="core"></a>   
## <a name="whats-new-in-the-net-framework-45"></a>Novedades de .NET Framework 4.5  
  
### <a name="core-new-features-and-improvements"></a>Principales características nuevas y mejoras  
  
-   Capacidad para reducir los reinicios del sistema mediante la detección y cierre de las aplicaciones de .NET Framework 4 durante la implementación. Consulte [sistema de reducir los reinicios durante las instalaciones de .NET Framework 4.5](../../../docs/framework/deployment/reducing-system-restarts.md).  
  
-   Compatibilidad con matrices mayores de 2 gigabytes (GB) en plataformas de 64 bits. Esta característica se puede habilitar en el archivo de configuración de la aplicación. Consulte la [ <> \> elemento](../../../docs/framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), donde también indican otras restricciones de tamaño del objeto y el tamaño de la matriz.  
  
-   Mayor rendimiento a través de la recolección de elementos no utilizados en segundo plano en el caso de los servidores. Cuando se usa la recolección de elementos no utilizados de los servidores en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], se habilita automáticamente la recolección de elementos no utilizados en segundo plano. Consulte la sección de recolección de elementos no utilizados de servidor de fondo de la [Fundamentos de la recopilación de elementos no utilizados](../../../docs/standard/garbage-collection/fundamentals.md) tema.  
  
-   Compilación Just-in-time (JIT) en segundo plano, que se encuentra disponible opcionalmente en los procesadores de varios núcleos para mejorar el rendimiento de la aplicación. Consulte <xref:System.Runtime.ProfileOptimization>.  
  
-   Capacidad para limitar el tiempo durante el cual el motor de expresiones regulares intentará resolver una expresión regular antes de agotar el tiempo de espera. Consulte la <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=fullName> propiedad.  
  
-   Capacidad para definir la referencia cultural predeterminada de un dominio de aplicación. Consulte la <xref:System.Globalization.CultureInfo> clase.  
  
-   Compatibilidad de la consola con la codificación Unicode (UTF-16). Consulte la <xref:System.Console> clase.  
  
-   Compatibilidad con el control de versiones de ordenación cultural de cadenas y datos de comparación. Consulte la <xref:System.Globalization.SortVersion> clase.  
  
-   Mayor rendimiento al recuperar recursos. Consulte [empaquetar e implementar recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).  
  
-   Mejoras en la compresión Zip para reducir el tamaño de un archivo comprimido. Consulte la <xref:System.IO.Compression?displayProperty=fullName> espacio de nombres.  
  
-   Capacidad de personalizar un contexto de reflexión para invalidar el comportamiento predeterminado de reflexión a través de la <xref:System.Reflection.Context.CustomReflectionContext> clase.  
  
-   Compatibilidad con la versión 2008 de nombres de dominio internacionalizados en las aplicaciones (IDNA) estándar cuando el <xref:System.Globalization.IdnMapping?displayProperty=fullName> clase se utiliza en [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
-   Delegación de comparación de cadenas en el sistema operativo, que implementa Unicode 6.0, cuando se usa .NET Framework en [!INCLUDE[win8](../../../includes/win8-md.md)]. Al ejecutarse en otras plataformas, .NET Framework incluye sus propios datos de comparación de cadenas, que implementan Unicode 5.x. Consulte la <xref:System.String> (clase) y la sección Comentarios de la <xref:System.Globalization.SortVersion> clase.  
  
-   Capacidad para calcular los códigos hash de cadenas en cada dominio de aplicación. See [<>\> Element](../../../docs/framework/configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).  
  
-   Compatibilidad con la reflexión dividirse entre tipos <xref:System.Type> y <xref:System.Reflection.TypeInfo> clases. Consulte [reflexión en .NET Framework para aplicaciones de la tienda de Windows](../../../docs/framework/reflection-and-codedom/reflection-for-windows-store-apps.md).  
  
### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)  
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Managed Extensibility Framework (MEF) cuenta con las siguientes características nuevas:  
  
-   Compatibilidad con los tipos genéricos.  
  
-   Modelo de programación basado en convenciones que permite crear elementos basándose en convenciones de nomenclatura en lugar de en atributos.  
  
-   Ámbitos múltiples.  
  
-   Un subconjunto de MEF que puede usar cuando cree aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Este subconjunto está disponible como un [paquete descargable](http://go.microsoft.com/fwlink/?LinkId=256238) desde la Galería de NuGet. Para instalar el paquete, abra el proyecto en Visual Studio, elija **administrar paquetes de NuGet** desde el **proyecto** menú y busque en línea el `Microsoft.Composition` paquete.  
  
 Para obtener más información, consulte [Managed Extensibility Framework (MEF)](../../../docs/framework/mef/index.md).  
  
### <a name="asynchronous-file-operations"></a>Operaciones de archivo asincrónicas  
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], se agregaron nuevas características asincrónicas a los lenguajes C# y Visual Basic. Estas características agregan un modelo basado en tareas para realizar operaciones asincrónicas. Para utilizar este nuevo modelo, use los métodos asincrónicos de las clases de E/S. Consulte [E/S de archivos asincrónica](../../../docs/standard/io/e-s-de-archivos-asincrónica.md).  
  
<a name="tools"></a>   
### <a name="tools"></a>Herramientas  
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], el generador de archivos de recursos (Resgen.exe) permite crear un archivo .resw para su uso en aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] desde un archivo .resources incrustado en un ensamblado de .NET Framework. Para obtener más información, consulte [Resgen.exe (generador de archivos de recursos)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).  
  
 La optimización guiada por perfiles administrados (Mpgo.exe) permite mejorar el tiempo de inicio de la aplicación, la utilización de la memoria (el tamaño del espacio de trabajo) y el rendimiento mediante la optimización de los ensamblados de imagen nativos. La herramienta de línea de comandos genera datos de perfil para los ensamblados nativos de aplicación de la imagen. Consulte [Mpgo.exe (herramienta de optimización guiada por perfiles administrados)](../../../docs/framework/tools/mpgo-exe-managed-profile-guided-optimization-tool.md). A partir de [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], puede utilizar Mpgo.exe para optimizar las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] así como las aplicaciones de escritorio.  
  
<a name="parallel"></a>   
### <a name="parallel-computing"></a>Informática en paralelo  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] cuenta con varias características y mejoras nuevas para el procesamiento informático en paralelo. Entre estas se incluyen un rendimiento mejorado, mayor control, mejor compatibilidad con la programación asincrónica, una nueva biblioteca de flujo de datos y mejor compatibilidad para la depuración y el análisis de rendimiento en paralelo. Vea la entrada [Novedades de paralelismo en .NET 4.5](http://go.microsoft.com/fwlink/?LinkId=235061) en el blog Parallel Programming with .NET.  
  
<a name="web"></a>   
### <a name="web"></a>Web  
 ASP.NET 4.5 y 4.5.1 incorporan el enlace de modelos de formularios Web Forms, compatibilidad con WebSocket, controladores asincrónicos, mejoras de rendimiento y muchas otras características. Para obtener más información, vea los siguientes recursos:  
  
-   [ASP.NET 4.5 y Visual Studio 2012](../Topic/ASP.NET%20Core%20and%20Visual%20Studio%202015.md) en MSDN Library.  
  
-   [ASP.NET 4.5.1 y Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094) en el sitio ASP.NET.  
  
<a name="networking"></a>   
### <a name="networking"></a>Redes  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] proporciona una nueva interfaz de programación para aplicaciones HTTP. Para obtener más información, vea el nuevo <xref:System.Net.Http?displayProperty=fullName> y <xref:System.Net.Http.Headers?displayProperty=fullName> los espacios de nombres.  
  
 También se incluye una nueva interfaz de programación para aceptar e interactuar con una conexión WebSocket utilizando existente compatibilidad con <xref:System.Net.HttpListener> y las clases relacionadas. Para obtener más información, vea el nuevo <xref:System.Net.WebSockets> espacio de nombres y el <xref:System.Net.HttpListener> clase.  
  
 Además, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] incluye las siguientes mejoras de red:  
  
-   Compatibilidad de URI conforme a RFC. Para obtener más información, consulte <xref:System.Uri> y las clases relacionadas.  
  
-   Compatibilidad con el análisis de nombres de dominio internacionalizados (IDN). Para obtener más información, consulte <xref:System.Uri> y las clases relacionadas.  
  
-   Compatibilidad con la internacionalización de direcciones de correo electrónico (EAI). Para obtener más información, consulte el <xref:System.Net.Mail> espacio de nombres.  
  
-   Compatibilidad mejorada de IPv6. Para obtener más información, consulte el <xref:System.Net.NetworkInformation> espacio de nombres.  
  
-   Compatibilidad con el socket de modo dual. Para obtener más información, consulte el <xref:System.Net.Sockets.Socket> y <xref:System.Net.Sockets.TcpListener> clases.  
  
<a name="client"></a>   
### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], Windows Presentation Foundation (WPF) contiene cambios y mejoras en las áreas siguientes:  
  
-   El nuevo <xref:System.Windows.Controls.Ribbon.Ribbon> control, que le permite implementar una interfaz de usuario de la cinta de opciones que hospeda una barra de herramientas de acceso rápido, un menú de la aplicación y pestañas.  
  
-   El nuevo <xref:System.ComponentModel.INotifyDataErrorInfo> interfaz, que admite la validación de datos sincrónica y asincrónica.  
  
-   Nuevas características para la <xref:System.Windows.Controls.VirtualizingPanel> y <xref:System.Windows.Threading.Dispatcher> clases.  
  
-   Rendimiento mejorado al mostrar conjuntos grandes de datos agrupados y al acceder a colecciones en subprocesos que no son de interfaz de usuario.  
  
-   Enlace de datos a propiedades estáticas, enlace de datos personalizado a tipos que implementan la <xref:System.Reflection.ICustomTypeProvider> interfaz y la recuperación de información de enlace de datos de una expresión de enlace.  
  
-   Reposición de los datos a medida que cambian los valores (modelado dinámico).  
  
-   Capacidad de comprobar si el contexto de datos de un contenedor de elementos está desconectado.  
  
-   Capacidad de establecer la cantidad de tiempo que debe transcurrir entre los cambios de propiedad y las actualizaciones del origen de datos.  
  
-   Compatibilidad mejorada para implementar patrones de eventos débiles. Además, los eventos ahora pueden aceptar extensiones de marcado.  
  
<a name="windows_communication_foundation"></a>   
### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
 En [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], se han agregado las características siguientes para facilitar la creación y el mantenimiento de aplicaciones de Windows Communication Foundation (WCF):  
  
-   Simplificación de los archivos de configuración generados.  
  
-   Compatibilidad con el desarrollo del contrato en primer lugar.  
  
-   Capacidad de configurar el modo de compatibilidad de ASP.NET más fácilmente.  
  
-   Cambios en los valores de propiedad de transporte predeterminados para reducir las probabilidades de tener que establecerlos.  
  
-   Actualizaciones de la <xref:System.Xml.XmlDictionaryReaderQuotas> clase para reducir la probabilidad de que tendrá que configurar manualmente cuotas para los lectores de diccionario XML.  
  
-   Validación de los archivos de configuración de WCF por parte de Visual Studio dentro del proceso de compilación, para que se puedan detectar errores de configuración antes de ejecutar la aplicación.  
  
-   Nueva compatibilidad con streaming asincrónico.  
  
-   Nueva asignación del protocolo HTTPS para facilitar la exposición de un extremo a través de HTTPS con Internet Information Services (IIS).  
  
-   Capacidad de generar metadatos en un solo documento WSDL anexando `?singleWSDL` a la dirección URL del servicio.  
  
-   Compatibilidad con Websockets para permitir una comunicación bidireccional verdadera a través de los puertos 80 y 443 con características de rendimiento similares a las del transporte TCP.  
  
-   Compatibilidad para configurar servicios en el código.  
  
-   Información sobre herramientas del editor XML.  
  
-   <xref:System.ServiceModel.ChannelFactory> almacenamiento en caché de soporte técnico.  
  
-   Compatibilidad con la compresión de codificadores binarios.  
  
-   Compatibilidad con un transporte UDP que permite a los desarrolladores escribir servicios que utilizan mensajería de tipo "desencadenar y omitir”. Un cliente envía un mensaje a un servicio y no espera ninguna respuesta de él.  
  
-   Capacidad de admitir varios modos de autenticación en un único extremo de WCF mediante el uso de transporte HTTP y seguridad de transporte.  
  
-   Compatibilidad con los servicios WCF que utilizan nombres de dominio internacionalizados (IDN).  
  
 Para obtener más información, consulte [¿qué novedades presenta Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173).  
  
<a name="windows_workflow_foundation"></a>   
### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)  
 Se han agregado varias características nuevas a Windows Workflow Foundation (WF) en [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], incluidas las siguientes:  
  
-   Estado de flujos de trabajo de equipo, que se incluyeron primero como parte de .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](http://go.microsoft.com/fwlink/?LinkID=215092)). Esta actualización incluía varias clases y actividades nuevas que permitían a los desarrolladores crear flujos de trabajo de máquina de estados. Estas clases y actividades se actualizaron para [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] con objeto de incluir:  
  
    -   Capacidad de establecer puntos de interrupción en estados  
  
    -   Capacidad de copiar y pegar transiciones en el Diseñador de flujo de trabajo  
  
    -   Compatibilidad del diseñador para la creación de transiciones de desencadenador compartidas  
  
    -   Actividades para crear flujos de trabajo de máquina de Estados, incluyendo: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State>, y <xref:System.Activities.Statements.Transition>.  
  
-   Características mejoradas del Diseñador de flujo de trabajo, como las siguientes:  
  
    -   Capacidades de búsqueda de flujo de trabajo en Visual Studio, mejoradas incluidas **búsqueda rápida** y **buscar en archivos**.  
  
    -   Capacidad de crear automáticamente una actividad Secuencia cuando una segunda actividad secundaria se agrega a una actividad del contenedor y para incluir ambas actividades en la actividad Secuencia.  
  
    -   Compatibilidad con el movimiento panorámico, que permite cambiar la parte visible de un flujo de trabajo sin usar las barras de desplazamiento.  
  
    -   Un nuevo **esquema del documento** vista que muestra los componentes de un flujo de trabajo en una vista de esquema de tipo árbol y le permite seleccionar un componente en el **esquema del documento** vista.  
  
    -   Capacidad de agregar anotaciones a las actividades.  
  
    -   Capacidad de definir y consumir delegados de actividad mediante el Diseñador de flujo de trabajo.  
  
    -   Conexión e inserción automáticas para actividades y transiciones en los flujos de trabajo de máquina de estados y diagrama de flujo.  
  
-   Almacenamiento de la información de estado de vista de un flujo de trabajo en un único elemento del archivo XAML, para poder encontrar y editar fácilmente la información de estado de vista.  
  
-   Una actividad de contenedor NoPersistScope para evitar que se conserven las actividades secundarias.  
  
-   Compatibilidad con expresiones de C#:  
  
    -   Los proyectos de flujo de trabajo que usan Visual Basic utilizarán las expresiones de Visual Basic, y los proyectos de flujo de trabajo de C# utilizarán las expresiones de C#.  
  
    -   Los proyectos de flujo de trabajo de C# creados en Visual Studio 2010 y que tengan expresiones de Visual Basic son compatibles con los proyectos de flujo de trabajo de C# que usan expresiones de C#.  
  
-   Mejoras del control de versiones:  
  
    -   El nuevo <xref:System.Activities.WorkflowIdentity> (clase), que proporciona una asignación entre una instancia de flujo de trabajo persistentes y su definición de flujo de trabajo.  
  
    -   Ejecución en paralelo de varias versiones de flujo de trabajo en el mismo host, incluido <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
    -   En la actualización dinámica, la capacidad de modificar la definición de una instancia de flujo de trabajo guardada.  
  
-   Desarrollo de servicios de flujo de trabajo de contrato en primer lugar, que proporciona compatibilidad para generar automáticamente actividades que busquen coincidencias en un contrato de servicio existente.  
  
 Para obtener más información, consulte [¿qué novedades presenta Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176).  
  
<a name="tailored"></a>   
### [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]  
 Las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] están diseñadas para factores de forma específicos y aprovechan la eficacia del sistema operativo Windows. Un subconjunto de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o 4.5.1 está disponible para compilar aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] para Windows mediante C# o Visual Basic. Este subconjunto se denomina [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] se trata de un [Introducción](http://go.microsoft.com/fwlink/?LinkId=228491) en el centro de desarrollo de Windows.  
  
<a name="portable"></a>   
### <a name="portable-class-libraries"></a>Bibliotecas de clases portables  
 El proyecto de Biblioteca de clases portable de [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)] (y versiones posteriores) permite escribir y compilar ensamblados administrados capaces de funcionar en múltiples plataformas de .NET Framework. Un proyecto de Biblioteca de clases portable le permite elegir las plataformas de destino (como Windows Phone y [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]). Los tipos y miembros disponibles en el proyecto se restringen automáticamente a los tipos y miembros comunes de estas plataformas. Para obtener más información, consulte [biblioteca de clases Portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).  
  
## <a name="see-also"></a>Vea también  
 [.NET Framework y versiones fuera de banda](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)   
 [Novedades en Visual Studio 2013](http://msdn.microsoft.com/library/bb386063\(v=vs.120\).aspx)   
 [ASP.NET 4.5.1 y herramientas Web para Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=309094)   
 [ASP.NET y Visual Studio para Web](../Topic/ASP.NET%20and%20Visual%20Studio%20for%20Web.md)   
 [Novedades en Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=228173)   
 [Novedades en Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=228176)   
 [Novedades en Visual C++](http://msdn.microsoft.com/library/hh409293\(v=vs.120\).aspx)