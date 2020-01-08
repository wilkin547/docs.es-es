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
ms.openlocfilehash: 2495ddbc89caf0b72cfc0e6a1647e8f2da291778
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347182"
---
# <a name="appcontextswitchoverrides-element"></a>\<elemento > AppContextSwitchOverrides

Define uno o varios modificadores usados por la clase <xref:System.AppContext> para proporcionar un mecanismo para cancelar la participación con nueva funcionalidad.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<AppContextSwitchOverrides>**

## <a name="syntax"></a>Sintaxis

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos
 En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.

### <a name="attributes"></a>Atributos

|Attribute|Descripción|
|---------------|-----------------|
|`value`|Atributo necesario.<br /><br /> Define uno o varios nombres de conmutador y sus valores booleanos asociados.|

### <a name="value-attribute"></a>Atributo de valor

|{2&gt;Value&lt;2}|Descripción|
|-----------|-----------------|
|"nombre = valor"|Un nombre de conmutador predefinido junto con su valor (`true` o `false`). Varios pares de nombre/valor de modificador se separan mediante signos de punto y coma (";"). Para obtener una lista de nombres de conmutadores predefinidos admitidos por el .NET Framework, vea la sección Comentarios.|

### <a name="child-elements"></a>Elemento secundario
 Ninguna.

### <a name="parent-elements"></a>Elemento principal

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|

## <a name="remarks"></a>Notas
 A partir de la .NET Framework 4,6, el elemento `<AppContextSwitchOverrides>` de un archivo de configuración permite a los llamadores de una API determinar si su aplicación puede aprovechar la nueva funcionalidad o mantener la compatibilidad con versiones anteriores de una biblioteca. Por ejemplo, si el comportamiento de una API ha cambiado entre dos versiones de una biblioteca, el elemento `<AppContextSwitchOverrides>` permite a los llamadores de esa API rechazar el nuevo comportamiento en las versiones de la biblioteca que admiten la nueva funcionalidad. En el caso de las aplicaciones que llaman a las API en el .NET Framework, el elemento `<AppContextSwitchOverrides>` también puede permitir que los autores de llamadas cuyas aplicaciones tengan como destino una versión anterior de la .NET Framework puedan optar a una nueva funcionalidad si su aplicación se ejecuta en una versión del .NET Framework que incluye esa funcionalidad.

 El atributo `value` del elemento `<AppContextSwitchOverrides>` está formado por una sola cadena formada por uno o varios pares de nombre/valor delimitados por punto y coma.  Cada nombre identifica un modificador de compatibilidad y su valor correspondiente es un booleano (`true` o `false`) que indica si el modificador está establecido. De forma predeterminada, el modificador es `false`y las bibliotecas proporcionan la nueva funcionalidad. Solo proporcionan la funcionalidad anterior si se establece el modificador (es decir, su valor es `true`). Esto permite que las bibliotecas proporcionen un nuevo comportamiento para una API existente, a la vez que permiten a los autores de llamadas que dependen del comportamiento anterior dejar de participar en la nueva funcionalidad.

 El .NET Framework admite los siguientes modificadores:

|Nombre del conmutador|Descripción|Introducida|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controla si Windows Presentation Foundation usa un algoritmo heredado para el diseño del control. Para más información, consulte [Mitigación: diseño de WPF](../../../migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controla si el algoritmo predeterminado que se usa para firmar partes de un paquete por PackageDigitalSignatureManager es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Cuando se establece en `false`, permite la depuración de proyectos de flujo de trabajo basados en XAML con Visual Studio cuando se habilita FIPS. Sin él, se produce una <xref:System.NullReferenceException> en las llamadas a los métodos del ensamblado System. Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controla si la suma de comprobación de una instancia de flujo de trabajo en el depurador utiliza MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|Controla si el hash de suma de comprobación de flujo de trabajo usa el algoritmo SHA1 introducido como valor predeterminado en .NET Framework 4,7 (`true`) o si usa el algoritmo SHA256 predeterminado introducido como valor predeterminado en .NET Framework 4,8 (`false`).<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controla si los seguimientos de la pila obtienen cuando el uso de archivos PDB portátiles puede incluir información de línea y de archivo de código fuente. `false` incluir la información del archivo de código fuente y de la línea; de lo contrario, `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controla si el método <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> produce una excepción cuando un objeto <xref:System.Drawing.Icon> tiene marcos PNG. Para más información, consulte [Mitigación: marcos PNG en objetos de icono](../../../migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina si <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> objetos se eliminan correctamente cuando se agregan a la colección mediante el método <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType>. `true` para mantener el comportamiento heredado; `false` eliminar todos los objetos de fuente privados. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|Controla si el rendimiento del <xref:System.Windows.Forms.PrintPreviewDialog> está optimizado para las impresoras de red. Para obtener más información, vea [PrintPreviewDialog (información general del control](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|Controla si se aplican las comprobaciones de intervalo de año para las eras del calendario japonés. `true` para aplicar las comprobaciones de intervalo de año y `false` para deshabilitarlas (comportamiento predeterminado). Para obtener más información, vea [trabajar con calendarios](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|Controla si solo "1" se reconoce como el primer año de una era de calendario japonés en las operaciones de análisis. `true` para reconocer solo "1"; `false` para reconocer "1" o gannen (comportamiento predeterminado). Para obtener más información, vea [trabajar con calendarios](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|Controla si el primer año de una era de calendario japonés se representa como "1" o gannen en operaciones de formato. `true` para dar formato al primer año de la era como "1"; `false` para formatearlo como gannen (comportamiento predeterminado). Para obtener más información, vea [trabajar con calendarios](../../../../standard/datetime/working-with-calendars.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controla si las operaciones asincrónicas no fluyen desde el contexto del subproceso que realiza la llamada. Para obtener más información, vea [flujo de CurrentCulture y CurrentUICulture entre tareas](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controla si el método <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> intenta hacer coincidir el tipo de la demanda solo con la última entrada DNS. Para más información, consulte [Mitigación: Método X509CertificateClaimSet.FindClaims](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Controla si se permite que AuthorizationContext. Empty devuelva un objeto mutable.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|Controla si las rutas de acceso de más de `MAX_PATH` (260 caracteres) producen un <xref:System.IO.PathTooLongException>. Para obtener más información, consulte [compatibilidad con rutas largas](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controla si la clase <xref:System.IO.Compression.DeflateStream> usa las rutinas de sistema operativo nativas para la descompresión. `false` para usar las API nativas; `true` usar la implementación de <xref:System.IO.Compression.DeflateStream>.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Usa la barra diagonal inversa ("\\") en lugar de la barra diagonal ("/") como separador de ruta de acceso en la propiedad <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType>. Para obtener más información, consulte [mitigación: separador de ruta de acceso ZipArchiveEntry. FullName](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controla si las excepciones del sistema operativo que se producen en subprocesos en segundo plano creadas con secuencias de <xref:System.IO.Ports.SerialPort> finalizan el proceso.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controla si se usa la normalización de rutas de acceso heredadas y los métodos <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> admiten las rutas de acceso de URI. Para obtener más información, consulte [mitigación: normalización de rutas de acceso](../../../migration-guide/mitigation-path-normalization.md) y [mitigación: comprobaciones de dos puntos de ruta](../../../migration-guide/mitigation-path-colon-checks.md)de acceso.|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controla si una prueba de igualdad compara la propiedad <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> de un objeto con la propiedad <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> del segundo objeto. Para obtener más información, vea [implementación incorrecta de MemberDescriptor. Equals](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deshabilita la validación del identificador de objetos (OID) de uso mejorado de clave (EKU) del certificado. Una extensión de uso mejorado de clave (EKU) es una colección de identificadores de objetos (OID) que indica las aplicaciones que usan la clave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deshabilita la vulnerabilidad del explorador TLS 1.0 contra la mitigación de SSL/TLS (transporte) deshabilitando el uso de SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controla si las clases <xref:System.Net.ServicePointManager?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType> pueden utilizar el protocolo SSL 3,0. Para más información, consulte [Mitigación: protocolos TLS](../../../migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deshabilita las versiones de SystemDefault TLS que se revierten a un valor predeterminado de Tls12, Tls11 y TLS.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deshabilita las alertas del lado del servidor SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|Controla si los parámetros ByRef SafeArray en los eventos de interoperabilidad COM serializan de nuevo a código nativo (`false`) o si el cálculo de referencias en código nativo está deshabilitado (`true`).|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controla si el [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializa algunos caracteres de control basados en los estándares de ECMAScript V6 y V8. Para más información, vea [Mitigación: Serialización del caracteres de control con DataContractJsonSerializer](../../../migration-guide/mitigation-serialization-control-characters.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controla si el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite varios ajustes o un solo ajuste para una zona horaria. Si `true`, utiliza el tipo de <xref:System.TimeZoneInfo> para serializar y deserializar los datos de fecha y hora; de lo contrario, utiliza el tipo de <xref:System.TimeZone>, que no admite varias reglas de ajuste.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|Controla si <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> utiliza un tamaño de matriz mayor durante la serialización y deserialización de objetos. Establezca este modificador en `true` para mejorar el rendimiento de la serialización y deserialización de gráficos de objetos grandes por tipos como <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controla si el constructor <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> establece la propiedad <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> del objeto nuevo con una referencia de objeto existente. Para más información, vea [Mitigation: Constructor ClaimsIdentity](../../../migration-guide/retargeting/4.6.1-4.6.2.md).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controla si el intento de reutilizar un descifrador de <xref:System.Security.Cryptography.AesCryptoServiceProvider> produce una <xref:System.Security.Cryptography.CryptographicException>. Para obtener más información, vea [el descifrador de AesCryptoServiceProvider proporciona una transformación reutilizable](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controla si el valor de la propiedad [CspParameters. ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) es un [IntPtr](xref:System.IntPtr) que representa la ubicación de memoria de un identificador de ventana o si es un identificador de ventana (HWND). Para más información, vea [Mitigación: CspParameters.ParentWindowHandle espera HWND](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value). |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|Controla si el uso de clases de criptografía administradas en modo FIPS produce una <xref:System.Security.Cryptography.CryptographicException> (`true`) o se basa en la implementación de las bibliotecas del sistema (`false`).|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedCMS es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|Controla si el método de <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> controla correctamente todas las curvas con nombre admitidas por el sistema operativo (`false`) o revierte al comportamiento heredado.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedXML es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina si el modo de seguridad de `TransportWithMessageCredential` permite mensajes con un encabezado "para" sin firmar. Se trata de un modificador opcional. Para obtener más información, vea [cambios en tiempo de ejecución en el .NET Framework 4.6.1](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controla si el constructor <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> inicia una <xref:System.ArgumentException> si uno de los elementos es `null`.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina si el intento de usar certificados X509 con un proveedor de almacenamiento de claves de CSG produce una excepción. Para obtener más información, vea [seguridad de transporte de WCF es compatible con los certificados almacenados mediante CNG](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Al utilizar el transporte HTTP con un servicio autohospedado, si se establece este valor en `true`, WCF omitirá una aplicación agregando el encabezado de `Connection: close` a los encabezados de respuesta de una solicitud. Establecer este valor en `false` permite agregar el encabezado de `Connection: close` a los encabezados de respuesta, lo que da como resultado el cierre del socket de la solicitud después de enviar una respuesta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Controla los interbloqueos que son el resultado de restringir las instancias de un servicio reentrante a un único subproceso de ejecución cada vez.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Junto con `Switch.System.Net.DontEnableSchUseStrongCrypto`, determina si la seguridad de mensajes de WCF usa TLS 1,1 y TLS 1,2.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Un valor de `false` establece la configuración predeterminada para permitir que el sistema operativo elija el protocolo. Un valor de `true` establece el valor predeterminado en el protocolo más alto disponible. (También disponible en la rama de servicio de versiones anteriores de .NET Framework)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina si el algoritmo de firma de mensajes predeterminado para los mensajes de MSMQ en WCF es SHA1 o SHA256.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controla si WCF usa un hash SHA1 o SHA256 para generar nombres aleatorios para las canalizaciones con nombre.<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Controla si se debe producir una excepción [NullReferenceException](xref:System.NullReferenceException) cuando el mensaje de excepción es NULL.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controla si las excepciones producidas en el inicio del servicio se propagan al llamador del método <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|Controla si <xref:System.Threading.Timer> instancias de aprovechan las mejoras de rendimiento de los entornos a gran escala. Si `true`, se habilitan las mejoras de rendimiento. Si `false` (el valor predeterminado), se deshabilitan.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina si ciertos caracteres con codificación porcentual que a veces se descodificaban se codifican ahora de forma coherente. Si `true`, se descodifican; de lo contrario, `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina el control de los caracteres Unicode bidireccionales en los URI. `true` para quitarlos de los URI; `false` para conservarlos y codificarlos por porcentaje.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina si Windows Presentation Foundation aplica un algoritmo antiguo (`true`) o un nuevo algoritmo (`false`) al asignar espacio a las columnas de \*. Para más información, vea [Mitigación: Asignación del espacio del control de cuadrícula a columnas de estrella](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Controla si un selector o control de ficha siempre actualiza el valor de su propiedad de valor seleccionada antes de generar el evento de cambio de selección.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina si la representación de la selección no basada en adornos está disponible para los controles <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.PasswordBox> para impedir el texto de ocluidos (`false`) o si el texto se representa solo en la capa de adornos (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|Controla si la clase <xref:System.Windows.Data.Binding?displayProperty=nameWithType> usa los indizadores IList personalizados de forma incorrecta (`true`) o correctos (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina si los cambios de PPP se producen en cada sistema (un valor de `false`) o cada monitor (un valor de `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|Controla si las mejoras en el tamaño de los controles de un <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> cuando se ejecuta WPF en el modo de reconocimiento de cada monitor están deshabilitadas (`true`) o habilitadas (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina si el desarrollador tiene que controlar de forma especial el <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> acción cuando el texto del control está presente. `true` para controlar la acción de <xref:System.Windows.Forms.DomainUpDown.UpButton>; `false` para que las acciones de <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> y <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> estén sincronizadas correctamente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Opta por no tener el código que permite a una implementación de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizada filtrar mensajes de forma segura sin producir una excepción cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>. Para más información, consulte [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina si la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> devuelve el control de código fuente cuando el usuario abre el menú desde un control <xref:System.Windows.Forms.ToolStripMenuItem> anidado. `true` para devolver `null`, el comportamiento heredado; `false` para devolver el control de código fuente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|Controla si la compatibilidad con la invocación de la información sobre herramientas está deshabilitada (`true`) o habilitada (`false`). Habilitar la compatibilidad con la invocación de la información sobre herramientas también requiere que las características de accesibilidad heredadas definidas por `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`y `Switch.UseLegacyAccessibilityFeatures.3` estén deshabilitadas (establecidas en `false`).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina si una pila opcional de entrada táctil o de lápiz óptico basada en `WM_POINTER`está habilitada en las aplicaciones WPF. Para obtener más información, consulte [mitigación: compatibilidad con la entrada táctil y el lápiz basados en punteros.](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina si el algoritmo hash predeterminado utilizado para las sumas de comprobación es SHA256 (`false`) o SHA1 (`true`).<br>Debido a problemas de colisión con SHA1, Microsoft recomienda SHA256.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controla si se produce una excepción [NullReferenceException](xref:System.NullReferenceException) heredada en lugar de la excepción que indica más específicamente la causa de la excepción (como [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o [FileNotFoundException](xref:System.IO.FileNotFoundException). Está pensado para su uso por parte del código que depende del control de [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|Controla si la suma de comprobación hash de los archivos XOML en las compilaciones de proyectos de flujo de trabajo usa el algoritmo MD5 (`true`) o si usa el algoritmo SHA256 introducido como valor predeterminado en .NET Framework 4,8.<br>Debido a problemas de colisión con MD5, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|Controla si la suma de comprobación hash de SqlTrackingService usa el algoritmo MD5 (`true`) para las cadenas almacenadas en caché o si usa el algoritmo SHA256 introducido como valor predeterminado en .NET Framework 4,8.<br>Debido a problemas de colisión con MD5, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|Controla si la suma de comprobación hash del tiempo de ejecución del flujo de trabajo usa el algoritmo MD5 (`true`) para las definiciones de flujo de trabajo almacenadas en caché o si usa el algoritmo SHA256 introducido como valor predeterminado en .NET Framework 4,8.<br>Debido a problemas de colisión con MD5, Microsoft recomienda SHA256.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|Controla si las características de accesibilidad disponibles a partir de .NET Framework 4.7.1 están habilitadas o deshabilitadas. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Controla si las características de accesibilidad disponibles en .NET Framework 4.7.2 están habilitadas (`false`) o deshabilitadas (`true`). Si `true`, `Switch.UseLegacyAccessibilityFeatures` también se debe `true` para habilitar las características de accesibilidad .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|Controla si las características de accesibilidad introducidas en .NET Framework 4,8 están habilitadas (`false`) o deshabilitadas (`true`). Si `true`, `Switch.UseLegacyAccessibilityFeatures` y `Switch.UseLegacyAccessibilityFeatures.2` también se deben `true`.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|Controla si la información sobre herramientas se muestra cuando un usuario mantiene el cursor del mouse sobre un control WPF (`true`) o si se muestran en el foco del teclado y a través de la tecla de método abreviado de teclado (`false`, el comportamiento predeterminado). En el caso de las aplicaciones que se ejecutan en .NET Framework 4,8 pero que tienen como destino versiones anteriores del .NET Framework, la habilitación de la compatibilidad con el foco de teclado y la tecla de método abreviado requiere que `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`y `Switch.UseLegacyAccessibilityFeatures.3` se establezcan en `false`.|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|Controla si la validación de esquemas XSD omite las secuencias de claves vacías en las claves compuestas. Para obtener más información, vea [mitigación: validación de esquemas XML](../../../migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|

> [!NOTE]
> En lugar de agregar un elemento `AppContextSwitchOverrides` a un archivo de configuración de la aplicación, también puede establecer los modificadores mediante programación llamando al método C#`static` (en) o `Shared` (en Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

 Los desarrolladores de bibliotecas también pueden definir modificadores personalizados para permitir que los autores de la llamada opten por la funcionalidad modificada introducida en versiones posteriores de sus bibliotecas. Para obtener más información, vea la clase <xref:System.AppContext>.

## <a name="switches-in-aspnet-applications"></a>Modificadores en aplicaciones ASP.NET

Puede configurar una aplicación de ASP.NET para que use la configuración de compatibilidad agregando un [\<agregar >](../appsettings/add-element-for-appsettings.md) elemento a la sección [\<appSettings >](../appsettings/index.md) del archivo Web. config.

En el ejemplo siguiente se usa el elemento `<add>` para agregar dos valores a la sección `<appSettings>` de un archivo Web. config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se usa el elemento `AppContextSwitchOverrides` para definir un solo modificador de compatibilidad de aplicaciones, `Switch.System.Globalization.NoAsyncCurrentCulture`, que impide que la referencia cultural fluya entre subprocesos en llamadas asincrónicas a métodos.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 En el ejemplo siguiente se usa el elemento `AppContextSwitchOverrides` para definir dos modificadores de compatibilidad de aplicaciones, `Switch.System.Globalization.NoAsyncCurrentCulture` y `Switch.System.IO.BlockLongPaths`. Un punto y coma separa los dos pares de nombre y valor.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- <xref:System.AppContext?displayProperty=nameWithType>
- [Elemento > en tiempo de ejecución de \<](runtime-element.md)
- [Elemento \<configuration>](../configuration-element.md)
