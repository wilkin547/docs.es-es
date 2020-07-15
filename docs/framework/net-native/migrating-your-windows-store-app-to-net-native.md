---
title: Migrar la aplicación de la Tienda Windows a .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
ms.openlocfilehash: 5e5c655d0e8d6f1730f27d35525692e110b3c80c
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309201"
---
# <a name="migrate-your-windows-store-app-to-net-native"></a>Migrar la aplicación de la tienda Windows a .NET Native

.NET Native proporciona la compilación estática de aplicaciones en la tienda Windows o en el equipo del desarrollador. Esto difiere de la compilación dinámica para las aplicaciones de la Tienda Windows realizada por el compilador Just-in-time (JIT) o el [generador de imágenes nativas (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) en el dispositivo. A pesar de las diferencias, .NET Native intenta mantener la compatibilidad con [.net para aplicaciones de la tienda Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29). En su mayor parte, todo lo que funciona en .NET para aplicaciones de la tienda Windows también funciona con .NET Native.  Sin embargo, en algunos casos, puede encontrar cambios de comportamiento. En este documento se describen estas diferencias entre las aplicaciones estándar de .NET para la tienda Windows y .NET Native en las siguientes áreas:

- [Diferencias de tiempo de ejecución generales](#Runtime)

- [Diferencias de programación dinámicas](#Dynamic)

- [Otras diferencias relacionadas con la reflexión](#Reflection)

- [Escenarios no compatibles e interfaces API](#Unsupported)

- [Diferencias de Visual Studio](#VS)

<a name="Runtime"></a>

## <a name="general-runtime-differences"></a>Diferencias de tiempo de ejecución generales

- Las excepciones, como <xref:System.TypeLoadException> , que inicia el compilador JIT cuando una aplicación se ejecuta en el Common Language Runtime (CLR) suelen producir errores en tiempo de compilación cuando se procesan por .net Native.

- No llame al método <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> desde un subproceso de interfaz de usuario de una aplicación. Esto puede producir un interbloqueo en .NET Native.

- No confíe en el orden de invocación de constructores de clases estáticas. En .NET Native, el orden de invocación es diferente del orden en el tiempo de ejecución estándar. (Incluso con el tiempo de ejecución estándar, no debe confiar en el orden de ejecución de los constructores de clases estáticas).

- Un bucle infinito sin hacer una llamada (por ejemplo, `while(true);`) en cualquier subproceso puede hacer que la aplicación se detenga. De igual modo, las esperas largas o infinitas pueden detener la aplicación.

- Ciertos ciclos de inicialización genéricos no producen excepciones en .NET Native. Por ejemplo, el código siguiente produce una excepción <xref:System.TypeLoadException> en el CLR estándar. En .NET Native, no.

  [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]

- En algunos casos, .NET Native proporciona implementaciones diferentes de .NET Framework bibliotecas de clases. Un objeto devuelto desde un método siempre implementará los miembros del tipo devuelto. Sin embargo, dado que su implementación de respaldo es diferente, es posible que no pueda convertirlo en el mismo conjunto de tipos como lo haría en otras plataformas de .NET Framework. Por ejemplo, en algunos casos, es posible que no pueda convertir el objeto de interfaz <xref:System.Collections.Generic.IEnumerable%601> devuelto por métodos como <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> o <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> a `T[]`.

- La caché de WinInet no está habilitada de forma predeterminada en .NET para aplicaciones de la tienda Windows, pero está en .NET Native. Esto mejora el rendimiento, pero tiene implicaciones en el conjunto de trabajo. No es necesaria ninguna acción por parte del desarrollador.

<a name="Dynamic"></a>

## <a name="dynamic-programming-differences"></a>Diferencias de programación dinámicas

.NET Native vincula estáticamente en el código del .NET Framework para que el código de la aplicación sea local para obtener el máximo rendimiento. Sin embargo, el tamaño de los archivos binarios debe seguir siendo reducido para dar cabida a la totalidad de .NET Framework. El compilador de .NET Native resuelve esta limitación mediante el uso de un reductor de dependencia que quita las referencias a código no utilizado. Sin embargo, es posible que .NET Native no mantenga ni genere información de tipo y código cuando esa información no se pueda inferir de forma estática en tiempo de compilación, sino que se recupere dinámicamente en tiempo de ejecución.

.NET Native habilita la reflexión y la programación dinámica. Sin embargo, no todos los tipos se pueden marcar para la reflexión, porque esto haría que el tamaño del código generado fuese demasiado grande (sobre todo porque se admite el reflejo en las API públicas en .NET Framework). El compilador de .NET Native toma decisiones inteligentes sobre qué tipos deben admitir la reflexión y mantiene los metadatos y genera código solo para esos tipos.

Por ejemplo, el enlace de datos requiere una aplicación para poder asignar los nombres de propiedad a las funciones. En .NET para aplicaciones de la Tienda Windows, Common Language Runtime utiliza automáticamente la reflexión para proporcionar esta capacidad para tipos administrados y tipos nativos disponibles públicamente. En .NET Native, el compilador incluye automáticamente los metadatos de los tipos a los que se enlazan los datos.

El compilador .NET Native también puede controlar tipos genéricos usados comúnmente como <xref:System.Collections.Generic.List%601> y <xref:System.Collections.Generic.Dictionary%602> , que funcionan sin necesidad de ninguna sugerencia ni Directiva. La palabra clave [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) también se admite dentro de ciertos límites.

> [!NOTE]
> Debe probar exhaustivamente todas las rutas de código dinámicas al migrar la aplicación a .NET Native.

La configuración predeterminada para .NET Native es suficiente para la mayoría de los desarrolladores, pero algunos desarrolladores pueden querer ajustar sus configuraciones mediante un archivo de directivas en tiempo de ejecución (.rd.xml). Además, en algunos casos, el compilador .NET Native no puede determinar qué metadatos deben estar disponibles para la reflexión y se basa en sugerencias, especialmente en los casos siguientes:

- Algunas construcciones como <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> y <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> no se pueden determinar estáticamente.

- Dado que el compilador no puede determinar la creación de instancias, un tipo genérico que desee reflejar tiene que especificarse mediante directivas de tiempo de ejecución. Esto no es solo porque se debe incluir todo el código, sino también porque la reflexión en tipos genéricos puede formar un ciclo infinito (por ejemplo, cuando se invoca un método genérico en un tipo genérico).

> [!NOTE]
> Las directivas de tiempo de ejecución se definen en un archivo de directivas de tiempo de ejecución (.rd.xml). Para obtener información general sobre el uso de este archivo, vea [Getting Started](getting-started-with-net-native.md) (Introducción). Para obtener información sobre las directivas de tiempo de ejecución, vea [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).

.NET Native también incluye herramientas de generación de perfiles que ayudan al desarrollador a determinar qué tipos fuera del conjunto predeterminado deben admitir la reflexión.

<a name="Reflection"></a>

## <a name="other-reflection-related-differences"></a>Otras diferencias relacionadas con la reflexión

Hay varias diferencias relacionadas con la reflexión en el comportamiento entre .NET para aplicaciones de la tienda Windows y .NET Native.

En .NET Native:

- No se admite la reflexión privada sobre los tipos y miembros de la biblioteca de clases de .NET Framework. Sin embargo, puede reflejar sobre sus propios tipos y miembros privados, así como sobre los tipos y miembros de bibliotecas de terceros.

- La propiedad <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> devuelve correctamente `false` para un objeto <xref:System.Reflection.ParameterInfo> que representa un valor devuelto. En .NET para aplicaciones de la Tienda Windows, devuelve `true`. El lenguaje intermedio (IL) no admite esto directamente y se deja la interpretación en el lenguaje.

- Los miembros públicos de las estructuras <xref:System.RuntimeFieldHandle> y <xref:System.RuntimeMethodHandle> no son compatibles. Estos tipos solo son compatibles con LINQ, árboles de expresión e inicialización de matrices estáticas.

- <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> y <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> incluyen miembros ocultos en clases base y, por tanto, se pueden invalidar sin necesidad de hacerlo de forma explícita. Esto también es así para otros métodos [RuntimeReflectionExtensions.GetRuntime*](xref:System.Reflection.RuntimeReflectionExtensions) .

- <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>y <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> no producen errores al intentar crear ciertas combinaciones (por ejemplo, una matriz de `byref` objetos).

- No se puede utilizar la reflexión para invocar a los miembros que tienen parámetros de puntero.

- No se puede utilizar la reflexión para obtener o establecer un campo de puntero.

- Cuando el número de argumentos es incorrecto y el tipo de uno de los argumentos es incorrecto, .NET Native produce una excepción <xref:System.ArgumentException> en lugar de un <xref:System.Reflection.TargetParameterCountException> .

- Por lo general, no se admite la serialización binaria de excepciones. Como resultado, se pueden agregar objetos no serializables al diccionario <xref:System.Exception.Data%2A?displayProperty=nameWithType> .

<a name="Unsupported"></a>

## <a name="unsupported-scenarios-and-apis"></a>Escenarios no compatibles e interfaces API

En las secciones siguientes se enumeran varios escenarios e interfaces API no compatibles con el desarrollo general, la interoperabilidad y las tecnologías como HTTPClient y Windows Communication Foundation (WCF):

- [Desarrollo general](#General)

- [HttpClient](#HttpClient)

- [Interop](#Interop)

- [Interfaces API no compatibles](#APIs)

<a name="General"></a>

### <a name="general-development-differences"></a>Diferencias de desarrollo generales

**Tipos de valor**

- Si invalida los métodos <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> y <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> para un tipo de valor, no llame a las implementaciones de la clase base. En .NET para aplicaciones de la Tienda Windows, estos métodos se basan en la reflexión. En tiempo de compilación, .NET Native genera una implementación que no se basa en la reflexión en tiempo de ejecución. Esto significa que si no se invalidan estos dos métodos, funcionarán según lo esperado, ya que .NET Native genera la implementación en tiempo de compilación. Sin embargo, si se invalidan estos métodos, pero se llama a la implementación de la clase base, se produce una excepción.

- No se admiten tipos de valor mayores de 1 megabyte.

- Los tipos de valor no pueden tener un constructor sin parámetros en .NET Native. (C# y Visual Basic prohíben los constructores sin parámetros en los tipos de valor. pero estos pueden crearse en IL).

**Matrices**

- No se admiten matrices con límite inferior distinto de cero. Normalmente, estas matrices se crean mediante una llamada a la sobrecarga <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> .

- No se admite la creación dinámica de matrices multidimensionales. Estas matrices se crean normalmente mediante una llamada a una sobrecarga del método <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> que incluye un parámetro `lengths` , o mediante una llamada al método <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> .

- No se admiten matrices multidimensionales que tengan cuatro o más dimensiones; es decir, que el valor de su propiedad <xref:System.Array.Rank%2A?displayProperty=nameWithType> sea de cuatro o más. En su lugar, use [matrices escalonadas](../../csharp/programming-guide/arrays/jagged-arrays.md) (una matriz de matrices). Por ejemplo, `array[x,y,z]` no es válido, pero `array[x][y][z]` sí lo es.

- No se admite varianza en matrices multidimensionales, ya que causa una excepción <xref:System.InvalidCastException> en tiempo de ejecución.

**Genéricos**

- La expansión infinita de tipos genéricos produce un error del compilador. Por ejemplo, este código produce un error al compilar:

  [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]

**Punteros**

- No se admiten las matrices de punteros.

- No se puede utilizar la reflexión para obtener o establecer un campo de puntero.

**Serialización**

No se admite el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> . En su lugar, use el atributo <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .

**Recursos**

No se admite el uso de recursos localizados con la clase <xref:System.Diagnostics.Tracing.EventSource> . La propiedad <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> no define los recursos localizados.

**Delegados**

No se admite`Delegate.BeginInvoke` ni `Delegate.EndInvoke` .

**Otras API**

- La propiedad [TypeInfo. GUID](xref:System.Type.GUID) produce una <xref:System.PlatformNotSupportedException> excepción si <xref:System.Runtime.InteropServices.GuidAttribute> no se aplica un atributo al tipo. El GUID se utiliza principalmente para la compatibilidad con COM.

- El <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> método analiza correctamente las cadenas que contienen fechas cortas en .net Native. Sin embargo, no mantiene la compatibilidad con los cambios en el análisis de fecha y hora que se describen en los artículos [KB2803771](https://support.microsoft.com/kb/2803771) y [KB2803755](https://support.microsoft.com/kb/2803755)de Microsoft Knowledge Base.

- <xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")`se redondea correctamente en .net Native. En algunas versiones de CLR, la cadena resultante se trunca en lugar de redondearse.

<a name="HttpClient"></a>

### <a name="httpclient-differences"></a>Diferencias de HttpClient

En .NET Native, la <xref:System.Net.Http.HttpClientHandler> clase usa internamente WinInet (a través de la <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> clase) en lugar de las <xref:System.Net.WebRequest> <xref:System.Net.WebResponse> clases y usadas en las aplicaciones estándar de .net para la tienda Windows.  WinINet no admite todas las opciones de configuración que admite la clase <xref:System.Net.Http.HttpClientHandler> .  Como resultado:

- Algunas de las propiedades de la funcionalidad de <xref:System.Net.Http.HttpClientHandler> devuelven `false` en .net Native, mientras que devuelven `true` en las aplicaciones estándar de .net para la tienda Windows.

- Algunos de los descriptores de acceso de la propiedad de configuración `get` siempre devuelven un valor fijo en .net Native que es diferente del valor configurable predeterminado en .net para aplicaciones de la tienda Windows.

En las subsecciones siguientes se tratan algunas otras diferencias de comportamiento.

**Proxy**

La <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> clase no admite la configuración o invalidación del proxy en función de cada solicitud.  Esto significa que todas las solicitudes de .NET Native usar el servidor proxy configurado por el sistema o ningún servidor proxy, dependiendo del valor de la <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> propiedad.  En .NET para aplicaciones de la Tienda Windows, el servidor proxy se define mediante la propiedad <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> .  En .NET Native, si <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> se establece en un valor distinto de, se `null` produce una <xref:System.PlatformNotSupportedException> excepción.  La <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> propiedad devuelve `false` en .net Native, mientras que devuelve `true` en el .NET Framework estándar para las aplicaciones de la tienda Windows.

**Redireccionamiento automático**

La <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> clase no permite configurar el número máximo de redirecciones automáticas.  El valor predeterminado de la propiedad <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> es de 50 en las aplicaciones estándar de .NET para la Tienda Windows y se puede modificar. En .NET Native, el valor de esta propiedad es 10 y, al intentar modificarlo, se produce una <xref:System.PlatformNotSupportedException> excepción.  La <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> propiedad devuelve `false` en .net Native, mientras que devuelve `true` en .net para aplicaciones de la tienda Windows.

**Descompresión automática**

.NET para aplicaciones de la Tienda Windows permite establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> en <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, en <xref:System.Net.DecompressionMethods.Deflate> y <xref:System.Net.DecompressionMethods.GZip>, o en <xref:System.Net.DecompressionMethods.None>.  .NET Native solo admite <xref:System.Net.DecompressionMethods.Deflate> junto con <xref:System.Net.DecompressionMethods.GZip> , o <xref:System.Net.DecompressionMethods.None> .  Si se intenta establecer la propiedad <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> en <xref:System.Net.DecompressionMethods.Deflate> o <xref:System.Net.DecompressionMethods.GZip> , la propiedad se establece, de forma silenciosa, en <xref:System.Net.DecompressionMethods.Deflate> y <xref:System.Net.DecompressionMethods.GZip>.

**Cookies**

La administración de cookies se realiza simultáneamente mediante <xref:System.Net.Http.HttpClient> y WinINet.  Las cookies de <xref:System.Net.CookieContainer> se combinan con las cookies de la caché de cookies de WinINet.  Si se elimina una cookie de <xref:System.Net.CookieContainer> , se evita que <xref:System.Net.Http.HttpClient> envíe la cookie, pero si WinINet ya ha visto la cookie y el usuario no ha eliminado las cookies, WinINet la envía.  No es posible eliminar una cookie de WinINet mediante programación con las API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>o <xref:System.Net.CookieContainer> .  Si se establece la propiedad <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> en `false` , solo se consigue que <xref:System.Net.Http.HttpClient> deje de enviar cookies; puede que WinINet siga incluyendo sus cookies en la solicitud.

**Credenciales**

En .NET para aplicaciones de la Tienda Windows, las propiedades <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> y <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> trabajan de forma independiente.  Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> acepta cualquier objeto que implemente la interfaz <xref:System.Net.ICredentials> .  En .NET Native, si se establece la <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> propiedad en, `true` la <xref:System.Net.Http.HttpClientHandler.Credentials%2A> propiedad se convierte en `null` .  Además, la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> solo se puede establecer en `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>o en un objeto de tipo <xref:System.Net.NetworkCredential>.  Si se asigna cualquier otro objeto <xref:System.Net.ICredentials> (el más conocido es <xref:System.Net.CredentialCache>) a la propiedad <xref:System.Net.Http.HttpClientHandler.Credentials%2A> , se produce una excepción <xref:System.PlatformNotSupportedException>.

**Otras características no compatibles o no configurables**

En .NET Native:

- El valor de la propiedad <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> es siempre <xref:System.Net.Http.ClientCertificateOption.Automatic>.  En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es <xref:System.Net.Http.ClientCertificateOption.Manual>.

- La propiedad <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> no es configurable.

- La propiedad <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> es siempre `true`.  En .NET para aplicaciones de la Tienda Windows, el valor predeterminado es `false`.

- El encabezado `SetCookie2` de las respuestas se omite como obsoleto.

<a name="Interop"></a>
### <a name="interop-differences"></a>Diferencias de interoperabilidad
 **Interfaces API desusadas**

 Hay una serie de interfaces API poco utilizadas para la interoperabilidad con código administrado que están desusadas. Cuando se usa con .NET Native, estas API pueden producir <xref:System.NotImplementedException> una <xref:System.PlatformNotSupportedException> excepción o, o producir un error del compilador. En .NET para aplicaciones de la Tienda Windows, estas API se marcan como obsoletas, aunque al llamarlas se genera una advertencia del compilador en lugar de un error del compilador.

 Las API desusadas para el `VARIANT` cálculo de referencias incluyen:

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>

 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>se admite, pero produce una excepción en algunos escenarios, como cuando se usa con [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) o `byref` variantes.

 Las API desusadas para la compatibilidad con [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) incluyen:

- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>

Las API en desuso para eventos COM clásicos incluyen:

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>

Las API en desuso en la <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interfaz, que no se admiten en .net Native, incluyen:

- <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (todos los miembros)
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (todos los miembros)
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (todos los miembros)
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>

Otras características de interoperabilidad no compatibles incluyen:

- <xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (todos los miembros)
- <xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (todos los miembros)
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>

 API de serialización de uso poco frecuente:

- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>

 **Compatibilidad con la invocación de plataforma y la interoperabilidad COM**

 La mayoría de los escenarios de invocación de plataforma e interoperabilidad COM todavía se admiten en .NET Native. En particular, se admite toda la interoperabilidad con las API de Windows en tiempo de ejecución (WinRT) y todo el cálculo de referencias necesarias para Windows en tiempo de ejecución. Esto incluye compatibilidad de cálculo de referencias para:

- Matrices (incluido <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)

- `BStr`

- Delegados

- Cadenas (Unicode, ANSI y HSTRING)

- Structs (`byref` y `byval`)

- Uniones

- Identificadores de Win32

- Todas las construcciones de WinRT

- Compatibilidad parcial para calcular referencias de tipos de variante. Se admite lo siguiente:

  - <xref:System.Boolean>

  - <xref:System.Byte>

  - <xref:System.Decimal>

  - <xref:System.Double>

  - <xref:System.Int16>

  - <xref:System.Int32>

  - <xref:System.Int64>

  - <xref:System.SByte>

  - <xref:System.Single>

  - <xref:System.UInt16>

  - <xref:System.UInt32>

  - <xref:System.UInt64>

  - `BStr`

  - [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)

Sin embargo, .NET Native no admite lo siguiente:

- Uso de eventos COM clásicos

- Implementación de la interfaz <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> en un tipo administrado

- Implementación de la interfaz [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) en un tipo administrado a través del atributo <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> . Sin embargo, no puede llamar a objetos COM a través de `IDispatch` y el objeto administrado no puede implementar `IDispatch` .

No se admite el uso de la reflexión para invocar un método de invocación de plataforma. Puede evitar esta limitación si encapsula la llamada de método en otro método y utiliza la reflexión para llamar en su lugar al contenedor.

<a name="APIs"></a>

### <a name="other-differences-from-net-apis-for-windows-store-apps"></a>Otras diferencias de las API de .NET para aplicaciones de la Tienda Windows

En esta sección se enumeran las API restantes que no se admiten en .NET Native. El conjunto más grande de las API no compatibles son las API de Windows Communication Foundation (WCF).

**DataAnnotations (System.ComponentModel.DataAnnotations)**

Los tipos de los <xref:System.ComponentModel.DataAnnotations> <xref:System.ComponentModel.DataAnnotations.Schema> espacios de nombres y no se admiten en .net Native. Entre ellos se incluyen los siguientes tipos que están presentes en .NET para aplicaciones de la tienda Windows para Windows 8:

- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>

 **Visual Basic**

Visual Basic no se admite actualmente en .NET Native. Los siguientes tipos de los <xref:Microsoft.VisualBasic> <xref:Microsoft.VisualBasic.CompilerServices> espacios de nombres y no están disponibles en .net Native:

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>

**Contexto de reflexión (espacio de nombres System.Reflection.Context)**

La <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> clase no se admite en .net Native.

**RTC (System.Net.Http.Rtc)**

La `System.Net.Http.RtcRequestFactory` clase no se admite en .net Native.

**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**

Los tipos de los [espacios de nombres System. ServiceModel. *](xref:System.ServiceModel) no se admiten en .net Native. Entre ellos se incluyen los siguientes tipos:

- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>

### <a name="differences-in-serializers"></a>Diferencias en los serializadores

Las siguientes diferencias conciernen a la serialización y deserialización con las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>y <xref:System.Xml.Serialization.XmlSerializer> :

- En .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no se puede serializar o deserializar una clase derivada que tiene un miembro de clase base cuyo tipo no es un tipo de serialización raíz. Por ejemplo, en el siguiente código, si se intenta serializar o deserializar `Y` , se genera un error:

  [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]

  El tipo `InnerType` es desconocido para el serializador, dado que los miembros de la clase base no se recorren durante la serialización.

- <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no pueden serializar una clase o estructura que implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> . Por ejemplo, los siguientes tipos no se producen error al serializar o deserializar:

- <xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar el valor del objeto siguiente, puesto que desconoce el tipo exacto del objeto que se va a serializar:

- <xref:System.Xml.Serialization.XmlSerializer> produce un error al serializar o deserializar si el tipo del objeto serializado es <xref:System.Xml.XmlQualifiedName>.

- Todos los serializadores (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>y <xref:System.Xml.Serialization.XmlSerializer>) producen error al general código de serialización para el tipo <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> o para un tipo que contenga <xref:System.Xml.Linq.XElement>. En su lugar, muestran errores en tiempo de compilación.

- No se garantiza que los siguientes constructores de los tipos de serialización funcionen del modo esperado:

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29>

- <xref:System.Xml.Serialization.XmlSerializer> produce un error al general código para un tipo que tiene métodos con cualquiera de los siguientes atributos:

  - <xref:System.Runtime.Serialization.OnSerializingAttribute>

  - <xref:System.Runtime.Serialization.OnSerializedAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializingAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializedAttribute>

- <xref:System.Xml.Serialization.XmlSerializer> no aceptan la interfaz de serialización personalizada <xref:System.Xml.Serialization.IXmlSerializable> . Si tiene una clase que implementa esta interfaz, <xref:System.Xml.Serialization.XmlSerializer> considera el tipo como un tipo de objeto CLR estándar (POCO) y solo serializa sus propiedades públicas.

- Serializar un objeto sin formato <xref:System.Exception> no funciona bien con <xref:System.Runtime.Serialization.DataContractSerializer> y <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> .

<a name="VS"></a>

## <a name="visual-studio-differences"></a>Diferencias de Visual Studio

**Excepciones y depuración**

Cuando se ejecutan aplicaciones compiladas mediante .NET Native en el depurador, las excepciones de primera oportunidad están habilitadas para los siguientes tipos de excepción:

- <xref:System.MemberAccessException>

- <xref:System.TypeAccessException>

**Compilar aplicaciones**

Use las herramientas de compilación x86 que se utilizan de manera predeterminada en Visual Studio. No recomendamos el uso de las herramientas de MSBuild AMD64, ya que podrían crear problemas de compilación. Estas herramientas se encuentran en C:\Archivos de programa (x86)\MSBuild\12.0\bin\amd64.

**Generadores de perfiles**

- El generador de perfiles de CPU de Visual Studio CPU y el generador de perfiles de memoria de XAML no muestran correctamente Just-My-Code (solo mi código).

- El generador de perfiles de memoria de XAML no muestra con precisión los datos del montón administrado.

- El generador de perfiles de CPU no identifica correctamente los módulos y muestra nombres de función prefijados.

**Proyectos de biblioteca de prueba unitaria**

No se admite la habilitación de .NET Native en una biblioteca de pruebas unitarias para un proyecto de aplicaciones de la tienda Windows y hace que el proyecto no se compile.

## <a name="see-also"></a>Consulte también

- [Introducción](getting-started-with-net-native.md)
- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Información general de .NET para aplicaciones de la tienda Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)
- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
