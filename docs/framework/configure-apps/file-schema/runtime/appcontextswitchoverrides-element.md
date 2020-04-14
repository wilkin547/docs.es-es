---
title: Elemento AppContextSwitchOverrides
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 95ae438e9fb52cc584d18a981bffb66147eb4a77
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242821"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides> elemento

Define uno o varios modificadores usados por la clase <xref:System.AppContext> para proporcionar un mecanismo para cancelar la participación con nueva funcionalidad.

[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<AppContextSwitchOverrides>**

## <a name="syntax"></a>Sintaxis

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`value`|Atributo necesario.<br /><br /> Define uno o varios nombres de conmutador y sus valores booleanos asociados.|

### <a name="value-attribute"></a>valor Atributo

|Valor|Descripción|
|-----------|-----------------|
|"nombre-valor"|Un nombre de conmutador predefinido`true` junto `false`con su valor ( o ). Varios pares de nombre/valor del conmutador están separados por punto y coma (";"). Para obtener una lista de nombres de modificador predefinidos admitidos por .NET Framework, vea la sección Comentarios.|

### <a name="child-elements"></a>Elementos secundarios
 Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|

## <a name="remarks"></a>Observaciones
 A partir de .NET Framework `<AppContextSwitchOverrides>` 4.6, el elemento de un archivo de configuración permite a los llamadores de una API determinar si su aplicación puede aprovechar la nueva funcionalidad o conservar la compatibilidad con versiones anteriores de una biblioteca. Por ejemplo, si el comportamiento de una API ha `<AppContextSwitchOverrides>` cambiado entre dos versiones de una biblioteca, el elemento permite a los llamadores de esa API excluirse del nuevo comportamiento en las versiones de la biblioteca que admiten la nueva funcionalidad. Para las aplicaciones que llaman a las `<AppContextSwitchOverrides>` API de .NET Framework, el elemento también puede permitir que los llamadores cuyas aplicaciones tienen como destino una versión anterior de .NET Framework opten por una nueva funcionalidad si su aplicación se ejecuta en una versión de .NET Framework que incluye esa funcionalidad.

 El `value` atributo `<AppContextSwitchOverrides>` del elemento consta de una sola cadena que consta de uno o varios pares de nombre/valor delimitados por punto y coma.  Cada nombre identifica un modificador de compatibilidad y su`true` `false`valor correspondiente es un valor booleano ( o ) que indica si el modificador está establecido. De forma predeterminada, `false`el modificador es , y las bibliotecas proporcionan la nueva funcionalidad. Sólo proporcionan la funcionalidad anterior si se establece el switch `true`(es decir, su valor es ). Esto permite a las bibliotecas proporcionar un nuevo comportamiento para una API existente, al tiempo que permite a los llamadores que dependen del comportamiento anterior optar por no participar en la nueva funcionalidad.

 .NET Framework admite los siguientes modificadores:

|Cambiar nombre|Descripción|Introducida|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controla si Windows Presentation Foundation usa un algoritmo heredado para el diseño de control. Para más información, consulte [Mitigación: diseño de WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controla si el algoritmo predeterminado utilizado para firmar partes de un paquete por PackageDigitalSignatureManager es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Cuando se `false`establece en , permite la depuración de proyectos de flujo de trabajo basados en XAML con Visual Studio cuando FIPS está habilitado. Sin él, <xref:System.NullReferenceException> se produce a las llamadas a métodos en el System.Activities ensamblado.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controla si la suma de comprobación de una instancia de flujo de trabajo en el depurador utiliza MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Controla si el hash de suma de comprobación de flujo de trabajo usa`true`el algoritmo SHA1 introducido como predeterminado en .NET Framework 4.7`false`( ), o si usa el algoritmo SHA256 predeterminado introducido como predeterminado en .NET Framework 4.8 ( ).<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controla si los seguimientos de pila se obtienen cuando se utilizan PDB portátiles pueden incluir información de línea y archivos de origen. `false`para incluir información de archivo de origen y línea; de `true`lo contrario, .|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controla <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> si el método produce <xref:System.Drawing.Icon> una excepción cuando un objeto tiene marcos PNG. Para más información, consulte [Mitigación: marcos PNG en objetos de icono](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina si <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> el <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> método elimina correctamente los objetos cuando se agregan a la colección. `true`para mantener el comportamiento heredado; `false` para eliminar todos los objetos de fuente privados. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Controla si el <xref:System.Windows.Forms.PrintPreviewDialog> rendimiento de la está optimizada para impresoras de red. Para obtener más información, vea [Introducción al control PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Controla si se aplican las comprobaciones de intervalo de año para las eras de calendario japonesas. `true`para aplicar comprobaciones de `false` intervalo de año y deshabilitarlas (el comportamiento predeterminado). Para obtener más información, consulte [Trabajar con calendarios](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Controla si sólo "1" se reconoce como el primer año de una era de calendario japonés en las operaciones de análisis. `true`reconocer sólo "1"; `false` para reconocer "1" o Gannen (el comportamiento predeterminado). Para obtener más información, consulte [Trabajar con calendarios](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Controla si el primer año de una era de calendario japonés se representa como "1" o Gannen en las operaciones de formato. `true`para formatear el primer año de la era como "1"; `false` para formatearlo como Gannen (el comportamiento predeterminado). Para obtener más información, consulte [Trabajar con calendarios](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controla si las operaciones asincrónicas no fluyen desde el contexto del subproceso que realiza la llamada. Para obtener más información, consulte [CurrentCulture y CurrentUICulture fluyen entre tareas.](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controla <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> si el método intenta hacer coincidir el tipo de notificación solo con la última entrada DNS. Para más información, consulte [Mitigación: Método X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Controla si se debe permitir AuthorizationContext.Empty para devolver un objeto mutable.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Controla si `MAX_PATH` las rutas de acceso <xref:System.IO.PathTooLongException>más largas que (260 caracteres) producen un archivo . Para obtener más información, consulte [Compatibilidad con rutas largas](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controla si la clase utiliza rutinas <xref:System.IO.Compression.DeflateStream> nativas del sistema operativo para la descompresión. `false`utilizar API nativas; `true` para utilizar <xref:System.IO.Compression.DeflateStream> la implementación.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Utiliza la barra\\diagonal inversa (" ") en lugar de <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> la barra diagonal ("/") como separador de ruta de acceso en la propiedad. Para obtener más información, vea [Mitigación: Separador de ruta ZipArchiveEntry.FullName](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controla si las excepciones del sistema operativo <xref:System.IO.Ports.SerialPort> que se producen en subprocesos en segundo plano creados con secuencias finalizan el proceso.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controla si se usa la normalización de <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> la ruta de acceso heredada y los métodos admiten las rutas de acceso URI. Para obtener más información, consulte [Mitigación: normalización](../../../migration-guide/mitigation-path-normalization.md) y mitigación de rutas [de acceso: comprobaciones](../../../migration-guide/mitigation-path-colon-checks.md)de puntos de ruta .|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controla si una prueba de <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> igualdad compara la <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> propiedad de un objeto con la propiedad del segundo objeto. Para obtener más información, vea [Implementación incorrecta de MemberDescriptor.Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deshabilita la validación del identificador de objeto (OID) de uso de clave mejorada de certificados (EKU). Una extensión de uso mejorado de clave (EKU) es una colección de identificadores de objetos (OID) que indica las aplicaciones que usan la clave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deshabilita la mitigación de TLS1.0 Browser Exploit Against SSL/TLS (BEAST) deshabilitando el uso de SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controla <xref:System.Net.ServicePointManager?displayProperty=nameWithType> si <xref:System.Net.Security.SslStream?displayProperty=nameWithType> las clases y pueden utilizar el protocolo SSL 3.0. Para más información, consulte [Mitigación: protocolos TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deshabilita las versiones DE TLS de SystemDefault que vuelven a un valor predeterminado de Tls12, Tls11, Tls.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deshabilita las alertas del lado del servidor TLS SslStream.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Controla si los parámetros de ByRef SafeArray`false`en eventos de interoperabilidad COM`true`se calculan de nuevo en código nativo ( ) o si el cálculo de referencias en código nativo está deshabilitado ( ).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controla si [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializa algunos caracteres de control en función de los estándares ECMAScript V6 y V8. Para más información, vea [Mitigación: Serialización del caracteres de control con DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controla <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> si el admite varios ajustes o solo un solo ajuste para una zona horaria. Si `true`, utiliza <xref:System.TimeZoneInfo> el tipo para serializar y deserializar datos de fecha y hora; de lo contrario, utiliza el <xref:System.TimeZone> tipo, que no admite varias reglas de ajuste.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Controla <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> si utiliza un tamaño de matriz mayor durante la serialización y deserialización de objetos. Establezca este `true` modificador para mejorar el rendimiento de la serialización y <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>la deserialización de gráficos de objetos grandes por tipos como . |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controla <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29> si el constructor establece <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> la propiedad del nuevo objeto con una referencia de objeto existente. Para más información, vea [Mitigation: Constructor ClaimsIdentity](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controla si el intento <xref:System.Security.Cryptography.AesCryptoServiceProvider> de reutilizar <xref:System.Security.Cryptography.CryptographicException>un descifrador produce un archivo . Para obtener más información, vea [AesCryptoServiceProvider descifrador proporciona una transformación reutilizable](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controla si el valor de la [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) propiedad es un [IntPtr](xref:System.IntPtr) que representa la ubicación de memoria de un identificador de ventana o si es un identificador de ventana (un HWND). Para más información, vea [Mitigación: CspParameters.ParentWindowHandle espera HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Controla si el uso de clases de <xref:System.Security.Cryptography.CryptographicException> criptografía administradas en modo FIPS produce un (`true`) o se basa en la implementación de bibliotecas del sistema (`false`).|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedCMS es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Controla <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> si el método controla correctamente todas`false`las curvas con nombre admitidas por el sistema operativo ( ) o vuelve al comportamiento heredado.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedXML es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina si `TransportWithMessageCredential` el modo de seguridad permite mensajes con un encabezado "to" sin signo. Este es un interruptor opt-in. Para obtener más información, vea [Cambios en tiempo de ejecución en .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controla <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> si el <xref:System.ArgumentException> constructor produce un `null`si uno de los elementos es .|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina si el intento de utilizar certificados X509 con un proveedor de almacenamiento de claves CSG produce una excepción. Para obtener más información, vea Seguridad de [transporte WCF admite certificados almacenados mediante CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Cuando se usa el transporte HTTP con un `true` servicio autohospedado, establecer `Connection: close` este valor para que WCF ignore una aplicación que agrega el encabezado a los encabezados de respuesta para una solicitud. Establecer este `false` valor para `Connection: close` permitir agregar el encabezado a los encabezados de respuesta, lo que resulta en el cierre del socket de solicitud después de que se ha enviado una respuesta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Controla los interbloqueos resultantes de restringir las instancias de un servicio de reentrada a un único subproceso de ejecución a la vez.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Junto `Switch.System.Net.DontEnableSchUseStrongCrypto`con , determina si la seguridad de mensajes WCF usa TLS 1.1 y TLS 1.2.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Un valor `false` de establece la configuración predeterminada para permitir que el sistema operativo elija el protocolo. Un valor `true` de establece el valor predeterminado en el protocolo más alto disponible. (También disponible en la rama de mantenimiento de versiones anteriores de framework)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina si el algoritmo de firma de mensajes predeterminado para los mensajes MSMQ en WCF es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controla si WCF usa un hash SHA1 o SHA256 para generar nombres aleatorios para canalizaciones con nombre.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Controla si se va a producir una [excepción NullReferenceException](xref:System.NullReferenceException) cuando el mensaje de excepción es null.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controla si las excepciones producidas en el <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> inicio del servicio se propagan al llamador del método.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Controla <xref:System.Threading.Timer> si las instancias aprovechan las mejoras de rendimiento para entornos de gran escala. Si `true`, las mejoras de rendimiento están habilitadas; si `false` (el valor predeterminado), están deshabilitados.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina si ciertos caracteres codificados porcentuales que a veces se descodificaban ahora se dejan codificados de forma coherente. Si `true`, se decodifican; de `false`lo contrario, .|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina el control de caracteres bidireccionales Unicode en URI. `true`para despojarlos de los URI; `false` para preservarlos y codificarlos porcentualmente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina si Windows Presentation Foundation aplica`true`un algoritmo antiguo`false`( ) o \*un nuevo algoritmo ( ) para asignar espacio a -columns. Para más información, vea [Mitigación: Asignación del espacio del control de cuadrícula a columnas de estrella](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Controla si un selector o un control de ficha siempre actualiza el valor de su propiedad de valor seleccionada antes de generar el evento de selección modificado.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina si la representación de selección no <xref:System.Windows.Controls.TextBox> basada <xref:System.Windows.Controls.PasswordBox> en adorno está`false`disponible para los controles y para evitar`true`el texto ocluido ( ), o si el texto se representa solo en la capa Adorner ( ).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Controla si la`true``false` <xref:System.Windows.Data.Binding?displayProperty=nameWithType> clase utiliza incorrectamente los indexadores IList personalizados ( ) o correctamente ( ).|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina si se producen cambios de PPP `false`por sistema (un valor de `true`) o por monitor (un valor de ).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Controla si las mejoras en <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> el tamaño de los controles en`true`un cuando WPFWPF se ejecuta en modo compatible con el monitor están deshabilitadas ( ) o habilitadas (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina si el desarrollador necesita <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> controlar especialmente la acción cuando el texto de control está presente. `true`para manejar <xref:System.Windows.Forms.DomainUpDown.UpButton> la acción; `false` para <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> que <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> las acciones estén correctamente sincronizadas.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Opta por el código que <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> permite a una implementación personalizada <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> filtrar mensajes de forma segura sin producir una excepción cuando se llama al método. Para más información, consulte [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina si <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> la propiedad devuelve el control de código <xref:System.Windows.Forms.ToolStripMenuItem> fuente cuando el usuario abre el menú desde un control anidado. `true`para `null`devolver , el comportamiento heredado; `false` para devolver el control de código fuente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Controla si la compatibilidad`true`con la invocación de información sobre herramientas está deshabilitada ( ) o habilitada (`false`). Habilitar la compatibilidad con la invocación de `Switch.UseLegacyAccessibilityFeatures` `Switch.UseLegacyAccessibilityFeatures.2`información `Switch.UseLegacyAccessibilityFeatures.3` sobre herramientas también `false`requiere que las características de accesibilidad heredadas definidas por , , y todas se deshabiliten (establecidas en ).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina si una `WM_POINTER`pila táctil/stylus basada en opcional está habilitada en aplicaciones WPFWPF. Para obtener más información, consulte [Mitigación: compatibilidad con lápiz táctil y lápiz basado en punteros](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina si el algoritmo hash predeterminado utilizado para las sumas de comprobación es SHA256 (`false`) o SHA1 (`true`).<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controla si se produce una [excepción NullReferenceException](xref:System.NullReferenceException) heredada en lugar de la excepción que indica más específicamente la causa de la excepción (por ejemplo, [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o [FileNotFoundException](xref:System.IO.FileNotFoundException). Está pensado para su uso por código que depende del control de [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Controla si el hash de suma de comprobación de archivos XOML en compilaciones de proyectos de flujo de trabajo usa el algoritmo MD5 (`true`) o si usan el algoritmo SHA256 introducido como predeterminado en .NET Framework 4.8.<br>Debido a problemas de colisión con MD5, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Controla si el hash de suma de comprobación`true`por SqlTrackingService usa el algoritmo MD5 ( ) para las cadenas almacenadas en caché o si usa el algoritmo SHA256 introducido como predeterminado en .NET Framework 4.8.<br>Debido a problemas de colisión con MD5, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Controla si el hash de suma de comprobación`true`por el tiempo de ejecución de flujo de trabajo usa el algoritmo MD5 ( ) para las definiciones de flujo de trabajo almacenadas en caché o si usa el algoritmo SHA256 introducido como predeterminado en .NET Framework 4.8.<br>Debido a problemas de colisión con MD5, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Controla si las características de accesibilidad disponibles a partir de .NET Framework 4.7.1 están habilitadas o deshabilitadas. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Controla si las características de accesibilidad disponibles en .NET Framework 4.7.2 están habilitadas (`false`) o deshabilitadas (`true`). Si `true` `Switch.UseLegacyAccessibilityFeatures` , también `true` debe ser habilitar las características de accesibilidad de .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Controla si las características de accesibilidad introducidas en`false`.NET Framework`true`4.8 están habilitadas ( ) o deshabilitadas ( ). Si `true` `Switch.UseLegacyAccessibilityFeatures` , `Switch.UseLegacyAccessibilityFeatures.2` y `true`también debe ser .|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Controla si la información sobre herramientas se muestra cuando un`true`usuario pasa el cursor del mouse sobre un`false`control WPF ( ), o si se muestran tanto en el foco del teclado como mediante la tecla de método abreviado de teclado ( , el comportamiento predeterminado). Para las aplicaciones que se ejecutan en .NET Framework 4.8 pero `Switch.UseLegacyAccessibilityFeatures`destinadas a `Switch.UseLegacyAccessibilityFeatures.2` `Switch.UseLegacyAccessibilityFeatures.3` `false`versiones anteriores de .NET Framework, habilitar el foco del teclado y la compatibilidad con teclas de método abreviado requiere que , , y todos se establezcan en .|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Controla si la validación de esquema XSD omite las secuencias de claves vacías en las claves compuestas. Para obtener más información, vea [Mitigación: validación de esquemas XML](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|

> [!NOTE]
> En lugar `AppContextSwitchOverrides` de agregar un elemento a un archivo de configuración de `static` la aplicación, `Shared` también puede establecer <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> los modificadores mediante programación mediante una llamada al método (en C- ) o (en Visual Basic).

 Los desarrolladores de bibliotecas también pueden definir modificadores personalizados para permitir que los llamadores opten por no cambiar la funcionalidad introducida en versiones posteriores de sus bibliotecas. Para obtener más información, vea la clase <xref:System.AppContext>.

## <a name="switches-in-aspnet-applications"></a>Interruptores en aplicaciones ASP.NET

Puede configurar una aplicación de ASP.NET para [ \<](../appsettings/add-element-for-appsettings.md) usar la configuración de compatibilidad agregando un elemento Agregar>a la [ \<](../appsettings/index.md) sección appSettings>del archivo web.config.

En el ejemplo `<add>` siguiente se utiliza `<appSettings>` el elemento para agregar dos valores a la sección de un archivo web.config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Ejemplo

 En el ejemplo `AppContextSwitchOverrides` siguiente se utiliza el elemento `Switch.System.Globalization.NoAsyncCurrentCulture`para definir un único modificador de compatibilidad de aplicación, , que impide que la referencia cultural fluya entre subprocesos en llamadas a métodos asincrónicos.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 En el ejemplo `AppContextSwitchOverrides` siguiente se utiliza el elemento `Switch.System.Globalization.NoAsyncCurrentCulture` `Switch.System.IO.BlockLongPaths`para definir dos modificadores de compatibilidad de aplicaciones y . Un punto y coma separa los dos pares nombre/valor.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>Consulte también

- <xref:System.AppContext?displayProperty=nameWithType>
- [\<> en tiempo de ejecución elemento](runtime-element.md)
- [\<configuración> Elemento](../configuration-element.md)
