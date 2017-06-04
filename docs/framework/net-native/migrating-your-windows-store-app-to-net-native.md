---
title: "Migrar la aplicaci&#243;n de la Tienda&#160;Windows a .NET Native | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
caps.latest.revision: 29
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 29
---
# Migrar la aplicaci&#243;n de la Tienda&#160;Windows a .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] proporciona la compilación estática de aplicaciones en la Tienda Windows o en el equipo del desarrollador. Esto difiere de la compilación dinámica para las aplicaciones de la Tienda Windows realizada por el compilador Just\-in\-time \(JIT\) o el [generador de imágenes nativas \(Ngen.exe\)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) en el dispositivo. A pesar de las diferencias, [!INCLUDE[net_native](../../../includes/net-native-md.md)] intenta mantener la compatibilidad con [.NET para aplicaciones de la Tienda Windows](http://msdn.microsoft.com/library/windows/apps/br230302.aspx). En general, lo que funciona en .NET para aplicaciones de la Tienda Windows también funciona en [!INCLUDE[net_native](../../../includes/net-native-md.md)].  Sin embargo, en algunos casos, puede encontrar cambios de comportamiento. En este documento se describen las diferencias entre las aplicaciones estándar de .NET para la Tienda Windows y [!INCLUDE[net_native](../../../includes/net-native-md.md)] en las siguientes áreas:  
  
-   [Diferencias de tiempo de ejecución generales](#Runtime)  
  
-   [Diferencias de programación dinámicas](#Dynamic)  
  
-   [Otras diferencias relacionadas con la reflexión](#Reflection)  
  
-   [Escenarios no compatibles e interfaces API](#Unsupported)  
  
-   [Diferencias de Visual Studio](#VS)  
  
<a name="Runtime"></a>   
## Diferencias de tiempo de ejecución generales  
  
-   Las excepciones \(por ejemplo, <xref:System.TypeLoadException>\) que se producen por el compilador JIT cuando una aplicación se ejecuta en Common Language Runtime \(CLR\) suelen generar errores en tiempo de compilación cuando las procesa [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
-   No llame al método <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=fullName> desde un subproceso de interfaz de usuario de una aplicación. Esto puede provocar un interbloqueo en [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
-   No confíe en el orden de invocación de constructores de clases estáticas. En [!INCLUDE[net_native](../../../includes/net-native-md.md)], el orden de invocación es diferente del orden en el tiempo de ejecución estándar. \(Incluso con el tiempo de ejecución estándar, no debe confiar en el orden de ejecución de los constructores de clases estáticas\).  
  
-   Un bucle infinito sin hacer una llamada \(por ejemplo, `while(true);`\) en cualquier subproceso puede hacer que la aplicación se detenga. De igual modo, las esperas largas o infinitas pueden detener la aplicación.  
  
-   Ciertos ciclos de inicialización genérica no producen excepciones en [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Por ejemplo, el código siguiente produce una excepción <xref:System.TypeLoadException> en el CLR estándar. Pero no ocurre así en [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   En algunos casos, [!INCLUDE[net_native](../../../includes/net-native-md.md)] proporciona implementaciones diferentes de las bibliotecas de clases de.NET Framework. Un objeto devuelto desde un método siempre implementará los miembros del tipo devuelto. Sin embargo, dado que su implementación de respaldo es diferente, es posible que no pueda convertirlo en el mismo conjunto de tipos como lo haría en otras plataformas de .NET Framework. Por ejemplo, en algunos casos, es posible que no pueda convertir el objeto de interfaz <xref:System.Collections.Generic.IEnumerable%601> devuelto por métodos como <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=fullName> o <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=fullName> a `T[]`.  
  
-   La caché de WinInet no está habilitada de forma predeterminada en .NET para aplicaciones de la Tienda Windows, pero lo está en [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Esto mejora el rendimiento, pero tiene implicaciones en el conjunto de trabajo. No es necesaria ninguna acción por parte del desarrollador.  
  
<a name="Dynamic"></a>   
## Diferencias de programación dinámicas  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] vincula estáticamente el código de .NET Framework para que el código de la aplicación local obtenga un rendimiento máximo. Sin embargo, el tamaño de los archivos binarios debe seguir siendo reducido para dar cabida a la totalidad de .NET Framework. El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] resuelve esta limitación mediante el uso de un reductor de dependencia que quita las referencias a código no utilizado. Sin embargo, es posible que [!INCLUDE[net_native](../../../includes/net-native-md.md)] no pueda mantener o generar cierto código e información de tipos cuando dicha información no se pueda inferir de forma estática en tiempo de compilación, sino que se recupere dinámicamente en tiempo de ejecución.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] habilita la reflexión y la programación dinámica. Sin embargo, no todos los tipos se pueden marcar para la reflexión, porque esto haría que el tamaño del código generado fuese demasiado grande \(sobre todo porque se admite el reflejo en las API públicas en .NET Framework\). El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] toma decisiones inteligentes acerca de qué tipos deben admitir la reflexión y mantiene los metadatos y genera código solo para esos tipos.  
  
 Por ejemplo, el enlace de datos requiere una aplicación para poder asignar los nombres de propiedad a las funciones. En .NET para aplicaciones de la Tienda Windows, Common Language Runtime utiliza automáticamente la reflexión para proporcionar esta capacidad para tipos administrados y tipos nativos disponibles públicamente. En [!INCLUDE[net_native](../../../includes/net-native-md.md)], el compilador incluye automáticamente metadatos para tipos a los que se enlazan datos.  
  
 El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] también puede controlar tipos genéricos comúnmente utilizados como <xref:System.Collections.Generic.List%601> y <xref:System.Collections.Generic.Dictionary%602>, que funcionan sin necesidad de directivas ni indicaciones. La palabra clave [dynamic](../Topic/dynamic%20\(C%23%20Reference\).md) también se admite dentro de ciertos límites.  
  
> [!NOTE]
>  Pruebe exhaustivamente todas las rutas de código dinámico cuando traslade su aplicación a [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 La configuración predeterminada de [!INCLUDE[net_native](../../../includes/net-native-md.md)] es suficiente para la mayoría de los desarrolladores, pero algunos quizá deseen ajustar al máximo sus configuraciones mediante el uso de un archivo de directivas de tiempo de ejecución \(.rd.xml\). Además, en algunos casos, el compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] no es capaz de determinar qué metadatos deben estar disponibles para la reflexión y tiene que basarse en las indicaciones, especialmente en los casos siguientes:  
  
-   Algunas construcciones como <xref:System.Type.MakeGenericType%2A?displayProperty=fullName> y <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=fullName> no se pueden determinar estáticamente.  
  
-   Dado que el compilador no puede determinar la creación de instancias, un tipo genérico que desee reflejar tiene que especificarse mediante directivas de tiempo de ejecución. Esto no es solo porque se debe incluir todo el código, sino también porque la reflexión en tipos genéricos puede formar un ciclo infinito \(por ejemplo, cuando se invoca un método genérico en un tipo genérico\).  
  
> [!NOTE]
>  Las directivas de tiempo de ejecución se definen en un archivo de directivas de tiempo de ejecución \(.rd.xml\). Para obtener información general sobre el uso de este archivo, vea [Introducción](../../../docs/framework/net-native/getting-started-with-net-native.md). Para obtener información sobre las directivas de tiempo de ejecución, vea [Referencia del archivo de configuración de directivas en tiempo de ejecución \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] también incluye herramientas de generación de perfiles con las que los desarrolladores pueden determinar más fácilmente qué tipos aparte del conjunto predeterminado deben admitir la reflexión.  
  
<a name="Reflection"></a>   
## Otras diferencias relacionadas con la reflexión  
 Hay otra serie de diferencias relacionadas con la reflexión en el comportamiento entre .NET para aplicaciones de la Tienda Windows y [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 En [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
-   No se admite la reflexión privada sobre los tipos y miembros de la biblioteca de clases de .NET Framework. Sin embargo, puede reflejar sobre sus propios tipos y miembros privados, así como sobre los tipos y miembros de bibliotecas de terceros.  
  
-   La propiedad <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=fullName> devuelve correctamente `false` para un objeto <xref:System.Reflection.ParameterInfo> que representa un valor devuelto. En .NET para aplicaciones de la Tienda Windows, devuelve `true`. El lenguaje intermedio \(IL\) no admite esto directamente y se deja la interpretación al lenguaje.  
  
-   Los miembros públicos de las estructuras <xref:System.RuntimeFieldHandle> y <xref:System.RuntimeMethodHandle> no son compatibles. Estos tipos solo son compatibles con LINQ, árboles de expresión e inicialización de matrices estáticas.  
  
-   <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=fullName> y <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=fullName> incluyen miembros ocultos en clases base y, por tanto, se pueden invalidar sin necesidad de hacerlo de forma explícita. Esto también es así para otros métodos [RuntimeReflectionExtensions.GetRuntime\*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx).  
  
-   <xref:System.Type.MakeArrayType%2A?displayProperty=fullName> y <xref:System.Type.MakeByRefType%2A?displayProperty=fullName> no producirán un error al intentar crear ciertas combinaciones \(por ejemplo, una matriz de byrefs\).  
  
-   No se puede utilizar la reflexión para invocar a los miembros que tienen parámetros de puntero.  
  
-   No se puede utilizar la reflexión para obtener o establecer un campo de puntero.  
  
-   Cuando el número de argumentos es incorrecto y el tipo de uno de los argumentos es incorrecto, [!INCLUDE[net_native](../../../includes/net-native-md.md)] produce <xref:System.ArgumentException> en lugar de <xref:System.Reflection.TargetParameterCountException>.  
  
-   Por lo general, no se admite la serialización binaria de excepciones. Como resultado, se pueden agregar objetos no serializables al diccionario <xref:System.Exception.Data%2A?displayProperty=fullName>.  
  
<a name="Unsupported"></a>   
## Escenarios no compatibles e interfaces API  
 En las secciones siguientes se enumeran varios escenarios e interfaces API no compatibles con el desarrollo general, la interoperabilidad y las tecnologías como HTTPClient y Windows Communication Foundation \(WCF\):  
  
-   [Desarrollo general](#General)  
  
-   [HttpClient](#HttpClient)  
  
-   [Interop](#Interop)  
  
-   [Interfaces API no compatibles](#APIs)  
  
<a name="General"></a>   
### Diferencias de desarrollo generales  
 **Tipos de valor**  
  
-   Si invalida los métodos <xref:System.ValueType.Equals%2A?displayProperty=fullName> y <xref:System.ValueType.GetHashCode%2A?displayProperty=fullName> para un tipo de valor, no llame a las implementaciones de la clase base. En .NET para aplicaciones de la Tienda Windows, estos métodos se basan en la reflexión. En tiempo de compilación, [!INCLUDE[net_native](../../../includes/net-native-md.md)] genera una implementación que no se basa en la reflexión en tiempo de ejecución. Esto significa que si no se invalidan estos dos métodos, funcionarán del modo esperado, ya que [!INCLUDE[net_native](../../../includes/net-native-md.md)] genera la implementación en tiempo de compilación. Sin embargo, si se invalidan estos métodos, pero se llama a la implementación de la clase base, se produce una excepción.  
  
-   No se admiten tipos de valor superiores a un megabyte.  
  
-   Los tipos de valor no pueden tener un constructor predeterminado en [!INCLUDE[net_native](../../../includes/net-native-md.md)]. \(C\# y Visual Basic prohíben los constructores predeterminados en tipos de valor, pero estos pueden crearse en IL\).  
  
 **Matrices**  
  
-   No se admiten matrices con límite inferior distinto de cero. Normalmente, estas matrices se crean mediante una llamada a la sobrecarga [Array.CreateInstance\(Type, Int32\[\], Int32\<xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=fullName>.  
  
-   No se admite la creación dinámica de matrices multidimensionales. Estas matrices se crean normalmente mediante una llamada a una sobrecarga del método <xref:System.Array.CreateInstance%2A?displayProperty=fullName> que incluye un parámetro `lengths`, o mediante una llamada al método <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=fullName>.  
  
-   No se admiten matrices multidimensionales que tengan cuatro o más dimensiones; es decir, que el valor de su propiedad <xref:System.Array.Rank%2A?displayProperty=fullName> sea de cuatro o más. En su lugar, use [matrices escalonadas](../Topic/Jagged%20Arrays%20\(C%23%20Programming%20Guide\).md) \(una matriz de matrices\). Por ejemplo, `array[x,y,z]` no es válido, pero `array[x][y][z]` sí lo es.  
  
-   No se admite varianza en matrices multidimensionales, ya que causa una excepción <xref:System.InvalidCastException> en tiempo de ejecución.  
  
 **Genéricos**  
  
-   La expansión infinita de tipos genéricos produce un error del compilador. Por ejemplo, este código produce un error al compilar:  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 **Punteros**  
  
-   No se admiten las matrices de punteros.  
  
-   No se puede utilizar la reflexión para obtener o establecer un campo de puntero.  
  
 **Serialización**  
  
 No se admite el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29>. En su lugar, use el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29>.  
  
 **Recursos**  
  
 No se admite el uso de recursos localizados con la clase <xref:System.Diagnostics.Tracing.EventSource>. La propiedad <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=fullName> no define los recursos localizados.  
  
 **Delegados**  
  
 No se admite `Delegate.BeginInvoke` ni `Delegate.EndInvoke`.  
  
 **Async**  
  
 No se admite la lógica de subprocesos en las sobrecargas de la tarea IAsync.  
  
 **Otras API**  
  
-   La propiedad <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=fullName> produce una excepción <xref:System.PlatformNotSupportedException> si no se aplica al tipo un atributo <xref:System.Runtime.InteropServices.GuidAttribute>. El GUID se utiliza principalmente para la compatibilidad con COM.  
  
-   El método <xref:System.DateTime.Parse%2A?displayProperty=fullName> analiza correctamente las cadenas que contienen fechas cortas en [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Sin embargo, no mantiene la compatibilidad con los cambios en el análisis de fecha y hora que se describen en los artículos [KB2803771](http://support.microsoft.com/kb/2803771) y [KB2803755](http://support.microsoft.com/kb/2803755) de Microsoft Knowledge Base.  
  
-   <xref:System.Numerics.BigInteger.ToString%2A?displayProperty=fullName> `("E")` se redondea correctamente en [!INCLUDE[net_native](../../../includes/net-native-md.md)]. En algunas versiones de CLR, la cadena resultante se trunca en lugar de redondearse.  
  
<a name="HttpClient"></a>   
### Diferencias de HttpClient  
 En [!INCLUDE[net_native](../../../includes/net-native-md.md)], la clase <xref:System.Net.Http.HttpClientHandler> usa internamente WinINet \(a través de la clase [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx)\) en lugar de las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> usadas en las aplicaciones de .NET para la Tienda Windows estándar.  WinINet no admite todas las opciones de configuración que admite la clase <xref:System.Net.Http.HttpClientHandler>.  Como resultado:  
  
-   Algunas de las propiedades de capacidad en <xref:System.Net.Http.HttpClientHandler> devuelven `false` en [!INCLUDE[net_native](../../../includes/net-native-md.md)], mientras que devuelven `true` en las aplicaciones estándar de .NET para la Tienda Windows.  
  
-   Algunos de los descriptores de acceso `get` de la propiedad de configuración siempre devuelven un valor fijo en [!INCLUDE[net_native](../../../includes/net-native-md.md)] que es diferente al valor configurable predeterminado en .NET para aplicaciones de la Tienda Windows.  
  
 En las subsecciones siguientes se tratan algunas otras diferencias de comportamiento.  
  
 **Proxy**  
  
 La clase [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) no admite la configuración o la invalidación del proxy por solicitud.  Esto significa que todas las solicitudes hechas en [!INCLUDE[net_native](../../../includes/net-native-md.md)] utilizan el servidor proxy configurado por el sistema o ningún servidor proxy, en función del valor de la propiedad <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=fullName>.  En .NET para aplicaciones de la Tienda Windows, el servidor proxy se define mediante la propiedad <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=fullName>.  En [!INCLUDE[net_native](../../../includes/net-native-md.md)], si se ajusta <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=fullName> a un valor distinto de `null`, se produce una excepción <xref:System.PlatformNotSupportedException>.  La propiedad <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=fullName> devuelve `false` en [!INCLUDE[net_native](../../../includes/net-native-md.md)], mientras que devuelve `true` en las aplicaciones estándar de .NET Framework para la Tienda Windows.  
  
 **Redireccionamiento automático**  
  
 La clase [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) no permite el número máximo de redirecciones automáticas que se van a configurar.  El valor predeterminado de la propiedad <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=fullName> es de 50 en las aplicaciones estándar de .NET para la Tienda Windows y se puede modificar. En [!INCLUDE[net_native](../../../includes/net-native-md.md)], el valor de esta propiedad es de 10, y si se intenta modificar, se produce una excepción <xref:System.PlatformNotSupportedException>.  La propiedad <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=fullName> devuelve `false` en [!INCLUDE[net_native](../../../includes/net-native-md.md)], mientras que devuelve `true` en .NET para aplicaciones de la Tienda Windows.  
  
 **Descompresión automática**  
  
 .NET para aplicaciones de la Tienda Windows permite establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=fullName> en <xref:System.Net.DecompressionMethods>, <xref:System.Net.DecompressionMethods>, en <xref:System.Net.DecompressionMethods> y <xref:System.Net.DecompressionMethods>, o en <xref:System.Net.DecompressionMethods>.[!INCLUDE[net_native](../../../includes/net-native-md.md)] solo admite <xref:System.Net.DecompressionMethods> con <xref:System.Net.DecompressionMethods> o <xref:System.Net.DecompressionMethods>.  Si se intenta establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> en <xref:System.Net.DecompressionMethods> o <xref:System.Net.DecompressionMethods>, la propiedad se establece, de forma silenciosa, en <xref:System.Net.DecompressionMethods> y <xref:System.Net.DecompressionMethods>.  
  
 **Cookies**  
  
 La administración de cookies se realiza simultáneamente mediante <xref:System.Net.Http.HttpClient> y WinINet.  Las cookies de <xref:System.Net.CookieContainer> se combinan con las cookies de la caché de cookies de WinINet.  Si se elimina una cookie de <xref:System.Net.CookieContainer>, se evita que <xref:System.Net.Http.HttpClient> envíe la cookie, pero si WinINet ya ha visto la cookie y el usuario no ha eliminado las cookies, WinINet la envía.  No es posible eliminar una cookie de WinINet mediante programación con las API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler> o <xref:System.Net.CookieContainer>.  Si se establece la propiedad <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=fullName> en `false`, solo se consigue que <xref:System.Net.Http.HttpClient> deje de enviar cookies; puede que WinINet siga incluyendo sus cookies en la solicitud.  
  
 **Credenciales**  
  
 En .NET para aplicaciones de la Tienda Windows, las propiedades <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=fullName> y <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=fullName> trabajan de forma independiente.  Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> acepta cualquier objeto que implemente la interfaz <xref:System.Net.ICredentials>.  En [!INCLUDE[net_native](../../../includes/net-native-md.md)], si se establece la propiedad <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> en `true`, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> pasa a ser `null`.  Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> solo se puede establecer en `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A> o en un objeto de tipo <xref:System.Net.NetworkCredential>.  Si se asigna cualquier otro objeto <xref:System.Net.ICredentials> \(el más conocido es <xref:System.Net.CredentialCache>\) a la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A>, se produce una excepción <xref:System.PlatformNotSupportedException>.  
  
 **Otras características no compatibles o no configurables**  
  
 En [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
-   El valor de la propiedad <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=fullName> es siempre <xref:System.Net.Http.ClientCertificateOption>.  En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es <xref:System.Net.Http.ClientCertificateOption>.  
  
-   La propiedad <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=fullName> no es configurable.  
  
-   La propiedad <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=fullName> es siempre `true`.  En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es `false`.  
  
-   El encabezado `SetCookie2` de las respuestas se omite como obsoleto.  
  
<a name="Interop"></a>   
### Diferencias de interoperabilidad  
 **Interfaces API desusadas**  
  
 Hay una serie de interfaces API poco utilizadas para la interoperabilidad con código administrado que están desusadas. Cuando se utilizan con [!INCLUDE[net_native](../../../includes/net-native-md.md)], estas API pueden producir una excepción <xref:System.NotImplementedException> o <xref:System.PlatformNotSupportedException>, o tener como resultado un error del compilador. En .NET para aplicaciones de la Tienda Windows, estas API se marcan como obsoletas, aunque al llamarlas se genera una advertencia del compilador en lugar de un error del compilador.  
  
 Interfaces API desusadas para el cálculo de referencias de `VARIANT`:  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.VarEnum?displayProperty=fullName>|  
  
 Se admite <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>, pero genera una excepción en algunas situaciones, como cuando se usa con [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) o con las variantes de byref.  
  
 API en desuso API para compatibilidad de [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx):  
  
|Tipo|Miembro|  
|----------|-------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.ClassInterfaceType>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.ClassInterfaceType>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=fullName>|Atributo no compatible|  
  
 Interfaces API obsoletas para eventos COM clásicos:  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 Interfaces API obsoletas en la interfaz <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=fullName>, que no es compatible con [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
|Tipo|Miembro|  
|----------|-------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=fullName>|Todos los miembros.|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=fullName>|Todos los miembros.|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=fullName>|Todos los miembros.|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>|  
  
 Otras características de interoperabilidad no compatibles:  
  
|Tipo|Miembro|  
|----------|-------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=fullName>|Todos los miembros.|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=fullName>|Todos los miembros.|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType>|  
  
 Interfaces API de cálculo de referencias rara vez utilizadas:  
  
|Tipo|Miembro|  
|----------|-------------|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29>|  
  
 **Compatibilidad con la invocación de plataforma y la interoperabilidad COM**  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] sigue admitiendo la mayoría de escenarios de invocación de plataforma e interoperabilidad COM. En particular, se admite toda la interoperabilidad con las API de Windows en tiempo de ejecución \(WinRT\) y todo el cálculo de referencias necesarias para Windows en tiempo de ejecución. Esto incluye compatibilidad de cálculo de referencias para:  
  
-   Matrices \(incluido <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>\)  
  
-   `BStr`  
  
-   Delegados  
  
-   Cadenas \(Unicode, Ansi y HSTRING\)  
  
-   Structs \(`byref` y `byval`\)  
  
-   Uniones  
  
-   Identificadores de Win32  
  
-   Todas las construcciones de WinRT  
  
-   Compatibilidad parcial para calcular referencias de tipos de variante. Se admiten los siguientes tipos:  
  
    -   <xref:System.Boolean>  
  
    -   <xref:System.Byte>  
  
    -   <xref:System.Decimal>  
  
    -   <xref:System.Double>  
  
    -   <xref:System.Int16>  
  
    -   <xref:System.Int32>  
  
    -   <xref:System.Int64>  
  
    -   <xref:System.SByte>  
  
    -   <xref:System.Single>  
  
    -   <xref:System.UInt16>  
  
    -   <xref:System.UInt32>  
  
    -   <xref:System.UInt64>  
  
    -   `BStr`  
  
    -   [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509.aspx)  
  
 Sin embargo, [!INCLUDE[net_native](../../../includes/net-native-md.md)] no admite:  
  
-   Uso de eventos COM clásicos  
  
-   Implementación de la interfaz <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=fullName> en un tipo administrado  
  
-   Implementación de la interfaz [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) en un tipo administrado a través del atributo <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=fullName>. Tenga en cuenta no obstante que no puede llamar a objetos COM mediante `IDispatch` y que el objeto administrado no puede implementar `IDispatch`.  
  
 No se admite el uso de la reflexión para invocar un método de invocación de plataforma. Puede evitar esta limitación si encapsula la llamada de método en otro método y utiliza la reflexión para llamar en su lugar al contenedor.  
  
<a name="APIs"></a>   
### Otras diferencias de las API de .NET para aplicaciones de la Tienda Windows  
 En esta sección se enumeran las API restantes que no son compatibles con [!INCLUDE[net_native](../../../includes/net-native-md.md)]. El grupo más grande de las API no compatibles son las de Windows Communication Foundation \(WCF\).  
  
 **DataAnnotations \(System.ComponentModel.DataAnnotations\)**  
  
 Los tipos de los espacios de nombres <xref:System.ComponentModel.DataAnnotations> y <xref:System.ComponentModel.DataAnnotations.Schema> no son compatibles con [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Entre estos se incluyen los siguientes tipos que están presentes en .NET para aplicaciones de la Tienda Windows destinadas a Windows 8:  
  
||  
|-|  
|<xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EditableAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=fullName>|  
  
 **Visual Basic**  
  
 Visual Basic no es compatible actualmente con [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Los siguientes tipos de los espacios de nombres <xref:Microsoft.VisualBasic> y <xref:Microsoft.VisualBasic.CompilerServices> no están disponibles en [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
||  
|-|  
|<xref:Microsoft.VisualBasic.CallType?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.Constants?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.Strings?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=fullName>|  
  
 **Contexto de reflexión \(espacio de nombres System.Reflection.Context\)**  
  
 La clase <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=fullName> no es compatible con [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **RTC \(System.Net.Http.Rtc\)**  
  
 La clase <xref:System.Net.Http.RtcRequestFactory?displayProperty=fullName> no es compatible con [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **Windows Communication Foundation \(WCF\) \(System.ServiceModel.\*\)**  
  
 Los tipos de los [espacios de nombres System.ServiceModel.\*](http://msdn.microsoft.com/library/gg145010.aspx) no son compatibles con [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Entre ellos se incluyen los siguientes:  
  
||  
|-|  
|<xref:System.ServiceModel.ActionNotSupportedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=fullName>|  
|<xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.ChannelFactory?displayProperty=fullName>|  
|<xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationException?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationState?displayProperty=fullName>|  
|<xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.DuplexClientBase%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointAddress?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointNotFoundException?displayProperty=fullName>|  
|<xref:System.ServiceModel.EnvelopeVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.ExceptionDetail?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultCode?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultException?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultException%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultReason?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultReasonText?displayProperty=fullName>|  
|<xref:System.ServiceModel.HttpBindingBase?displayProperty=fullName>|  
|<xref:System.ServiceModel.HttpClientCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.HttpTransportSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.IClientChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.ICommunicationObject?displayProperty=fullName>|  
|<xref:System.ServiceModel.IContextChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=fullName>|  
|<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.IExtension%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.IExtensionCollection%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.InstanceContext?displayProperty=fullName>|  
|<xref:System.ServiceModel.InvalidMessageContractException?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageHeader%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageHeaderException?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageParameterAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageSecurityVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetHttpBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetTcpBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetTcpSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationContext?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationContextScope?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationFormatStyle?displayProperty=fullName>|  
|<xref:System.ServiceModel.ProtocolException?displayProperty=fullName>|  
|<xref:System.ServiceModel.QuotaExceededException?displayProperty=fullName>|  
|<xref:System.ServiceModel.SecurityMode?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServerTooBusyException?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServiceActivationException?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.TcpClientCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.TcpTransportSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.TransferMode?displayProperty=fullName>|  
|<xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=fullName>|  
|<xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.AddressHeader?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.FaultConverter?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IInputChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IInputSession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IOutputSession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ISession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.Message?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageFault?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageHeader?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageProperties?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageState?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.RequestContext?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.ClientCredentials?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.ContractDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.FaultDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageDirection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.OperationDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecurityVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.TrustVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=fullName>|  
  
### Diferencias en los serializadores  
 Las siguientes diferencias conciernen a la serialización y deserialización con las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y <xref:System.Xml.Serialization.XmlSerializer>:  
  
-   En [!INCLUDE[net_native](../../../includes/net-native-md.md)], <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> generan error al serializar o deserializar una clase derivada que tiene un miembro de clase base cuyo tipo no es un tipo de serialización de raíz. Por ejemplo, en el siguiente código, si se intenta serializar o deserializar `Y`, se genera un error:  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     El tipo `InnerType` es desconocido para el serializador, dado que los miembros de la clase base no se recorren durante la serialización.  
  
-   <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no pueden serializar una clase o estructura que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601>. Por ejemplo, los siguientes tipos no se producen error al serializar o deserializar:  
  
  
  
-   <xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar el valor del objeto siguiente, puesto que desconoce el tipo exacto del objeto que se va a serializar:  
  
  
  
-   <xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar o deserializar si el tipo del objeto serializado es <xref:System.Xml.XmlQualifiedName>.  
  
-   Todos los serializadores \(<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y <xref:System.Xml.Serialization.XmlSerializer>\) producen error al general código de serialización para el tipo <xref:System.Xml.Linq.XElement?displayProperty=fullName> o para un tipo que contenga <xref:System.Xml.Linq.XElement>. En su lugar, muestran errores en tiempo de compilación.  
  
-   No se garantiza que los siguientes constructores de los tipos de serialización funcionen del modo esperado:  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=fullName>  
  
    -   [XmlSerializer.XmlSerializer\(Type, Type\<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=fullName>  
  
    -   [XmlSerializer.XmlSerializer\(Type, XmlAttributeOverrides, Type\<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=fullName>  
  
-   <xref:System.Xml.Serialization.XmlSerializer> produce un error al general código para un tipo que tiene métodos con cualquiera de los siguientes atributos:  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <xref:System.Xml.Serialization.XmlSerializer> no aceptan la interfaz de serialización personalizada <xref:System.Xml.Serialization.IXmlSerializable>. Si tiene una clase que implementa esta interfaz, <xref:System.Xml.Serialization.XmlSerializer> considera el tipo como un tipo de objeto CLR estándar \(POCO\) y solo serializa sus propiedades públicas.  
  
-   Serializar un objeto <xref:System.Exception> simple, como el siguiente, no funciona bien con <xref:System.Runtime.Serialization.DataContractSerializer> ni con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:  
  
  
  
<a name="VS"></a>   
## Diferencias de Visual Studio  
 **Excepciones y depuración**  
  
 Cuando se ejecutan aplicaciones compiladas mediante el uso de [!INCLUDE[net_native](../../../includes/net-native-md.md)] en el depurador, se habilitan las primeras excepciones para los siguientes tipos de excepción:  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 **Compilación de aplicaciones**  
  
 Use las herramientas de compilación x86 que se utilizan de manera predeterminada en Visual Studio. No recomendamos el uso de las herramientas de MSBuild AMD64, ya que podrían crear problemas de compilación. Estas herramientas se encuentran en C:\\Archivos de programa \(x86\)\\MSBuild\\12.0\\bin\\amd64.  
  
 **Generadores de perfiles**  
  
-   El generador de perfiles de CPU de Visual Studio CPU y el generador de perfiles de memoria de XAML no muestran correctamente Just\-My\-Code \(solo mi código\).  
  
-   El generador de perfiles de memoria de XAML no muestra con precisión los datos del montón administrado.  
  
-   El generador de perfiles de CPU no identifica correctamente los módulos y muestra nombres de función prefijados.  
  
 **Proyectos de biblioteca de prueba unitaria**  
  
 No se admite la habilitación de [!INCLUDE[net_native](../../../includes/net-native-md.md)] en una biblioteca de prueba unitaria para un proyecto de aplicaciones de la Tienda Windows; provoca que el proyecto no se pueda compilar.  
  
## Vea también  
 [Introducción](../../../docs/framework/net-native/getting-started-with-net-native.md)   
 [Referencia del archivo de configuración de directivas en tiempo de ejecución \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Información general de .NET para aplicaciones de la Tienda Windows](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)   
 [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)