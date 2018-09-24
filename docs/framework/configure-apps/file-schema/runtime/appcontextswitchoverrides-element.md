---
title: '&lt;AppContextSwitchOverrides&gt; elemento'
ms.custom: updateeachrelease
ms.date: 09/19/2018
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c06b63c492d31d1391b53a36ced5b5c7277f5ad6
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027378"
---
# <a name="ltappcontextswitchoverridesgt-element"></a>&lt;AppContextSwitchOverrides&gt; elemento
Define uno o varios modificadores usados por la clase <xref:System.AppContext> para proporcionar un mecanismo para cancelar la participación con nueva funcionalidad.  
  
 \<configuration>  
 \<en tiempo de ejecución >  
\<AppContextSwitchOverrides >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`value`|Atributo necesario.<br /><br /> Define uno o más nombres de conmutador y los valores booleanos asociados.|  
  
### <a name="value-attribute"></a>valor de atributo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|"nombre = valor"|Un nombre de conmutador predefinidas junto con su valor (`true` o `false`). Varios pares de nombre/valor de conmutador están separados por punto y coma (";"). Para obtener una lista de nombres de conmutador predefinidos admitidos por .NET Framework, vea la sección Comentarios.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de .NET Framework 4.6, el `<AppContextSwitchOverrides>` elemento en un archivo de configuración permite que los llamadores de una API para determinar si su aplicación puede aprovechar las funcionalidades nuevas o mantener la compatibilidad con versiones anteriores de una biblioteca. Por ejemplo, si el comportamiento de una API ha cambiado entre dos versiones de una biblioteca, el `<AppContextSwitchOverrides>` elemento permite que los llamadores de la API que opten por el nuevo comportamiento en las versiones de la biblioteca que admiten la funcionalidad nueva. Para las aplicaciones que llaman a las API de .NET Framework, el `<AppContextSwitchOverrides>` elemento también puede permitir que los llamadores cuyas aplicaciones tengan como destino una versión anterior de .NET Framework para participar en la nueva funcionalidad, si su aplicación se ejecuta en una versión de .NET Framework que incluye que funcionalidad.  
  
 El `value` atributo de la `<AppContextSwitchOverrides>` elemento consta de una sola cadena que consta de uno o más pares de nombre-valor delimitada por punto y coma.  Cada nombre identifica un modificador de compatibilidad y su valor correspondiente es un valor booleano (`true` o `false`) que indica si el modificador está establecido. De forma predeterminada, el modificador es `false`, y las bibliotecas proporcionan la funcionalidad nueva. Sólo ofrecen la funcionalidad anterior si el modificador está establecido (es decir, su valor es `true`). Esto permite que las bibliotecas para proporcionar el nuevo comportamiento de una API existente mientras que los llamadores que dependen del comportamiento anterior para dejar de participar en la nueva funcionalidad.  
  
 .NET Framework admite los siguientes modificadores:  
  
|Nombre del conmutador|Descripción|Introdujo|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controla si Windows Presentation Foundation usa un algoritmo heredado para el diseño del control. Para más información, consulte [Mitigación: diseño de WPF](~/docs/framework/migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controla si el algoritmo predeterminado usado para firmar los elementos de un paquete por PackageDigitalSignatureManager es SHA1 o SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Cuando se establece en `false`, permite la depuración de proyectos de flujo de trabajo basado en XAML con Visual Studio cuando se habilita FIPS. Sin él, un <xref:System.NullReferenceException> se produce en las llamadas a métodos en el ensamblado de System.Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controla si la suma de comprobación para una instancia de flujo de trabajo en el depurador utiliza MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controla si los seguimientos de pila obtener al usar archivos PDB portátiles puede incluir información de archivo y la línea de código fuente. `false` para incluir información de archivo y la línea de código fuente; en caso contrario, `true`.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controles si el <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> método produce una excepción cuando un <xref:System.Drawing.Icon> objeto tiene marcos PNG. Para más información, consulte [Mitigación: marcos PNG en objetos de icono](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|  
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina si <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> los objetos se eliminan correctamente cuando se agrega a la colección por el <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> método. `true` para mantener el comportamiento heredado; `false` para desechar todos los objetos de fuente privada. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`</br>`OptimizePrintPreview`|Controles si el rendimiento de la <xref:System.Windows.Forms.PrintPreviewDialog> está optimizado para las impresoras de red. Para obtener más información, consulte [información general del control PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controla si las operaciones asincrónicas no fluye desde el contexto del subproceso que realiza la llamada. Para obtener más información, consulte [CurrentCulture y CurrentUICulture fluyen entre tareas](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controles si el <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> método intenta hacer coincidir el tipo de notificación solo con la última entrada DNS. Para más información, consulte [Mitigación: Método X509CertificateClaimSet.FindClaims](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Controla si se permite AuthorizationContext.Empty devolver un objeto mutable.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Controles si las rutas de acceso más de `MAX_PATH` throw (260 caracteres) un <xref:System.IO.PathTooLongException>. Para obtener más información, consulte [largo de ruta de acceso de soporte](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controla si se utilizan las rutinas de sistema operativo nativas para la descompresión mediante el <xref:System.IO.Compression.DeflateStream> clase. `false` Para usar las API nativas; `true` para usar el <xref:System.IO.Compression.DeflateStream> implementación.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Usa la barra diagonal inversa ("\\") en lugar de la barra diagonal ("/") como separador de ruta de acceso en el <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> propiedad. Para obtener más información, consulte [mitigación: separador de ruta de acceso de ZipArchiveEntry.FullName](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controla si el funcionamiento de las excepciones del sistema que se producen en los subprocesos en segundo plano creados con <xref:System.IO.Ports.SerialPort> secuencias finalizan el proceso.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controla si se usa la normalización heredada de la ruta de acceso y las rutas de acceso URI son compatibles con el <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> métodos. Para obtener más información, consulte [mitigación: normalización del trazado](~/docs/framework/migration-guide/mitigation-path-normalization.md) y [mitigación: comprobaciones de dos puntos de ruta de acceso](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controla si una prueba de igualdad compara el <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> propiedad de un objeto con el <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> propiedad del segundo objeto. Para obtener más información, consulte [implementación incorrecta de MemberDescriptor.Equals](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deshabilita la validación de identificador (OID) de objetos de uso mejorado de clave (EKU) de certificados. Una extensión de uso mejorado de clave (EKU) es una colección de identificadores de objetos (OID) que indica las aplicaciones que usan la clave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deshabilita la mitigación de TLS 1.0 explorador contra vulnerabilidades de seguridad frente a SSL/TLS (BEAST) al deshabilitar el uso de SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controles si el <xref:System.Net.ServicePointManager?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType> las clases pueden utilizar el protocolo SSL 3.0. Para más información, consulte [Mitigación: protocolos TLS](~/docs/framework/migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deshabilita las versiones de SystemDefault TLS revertir a un valor predeterminado de Tls, en Tls11, Tls12.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deshabilita las alertas de servidor SslStream TLS.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controles si el [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializa algunos caracteres de control según los estándares de ECMAScript V6 y V8. Para más información, vea [Mitigación: Serialización del caracteres de control con DataContractJsonSerializer](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controles si el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite solo un ajuste único o varios ajustes para una zona horaria. Si `true`, usa el <xref:System.TimeZoneInfo> escriba para serializar y deserializar los datos de fecha y hora; en caso contrario, usa el <xref:System.TimeZone> tipo, que no admite varias reglas de ajuste.|.NET Framework 4.6.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controles si el <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> constructor establece el nuevo objeto <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> propiedad con una referencia de objeto existente. Para más información, vea [Mitigation: Constructor ClaimsIdentity](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controles si el intento de reutilizar una <xref:System.Security.Cryptography.AesCryptoServiceProvider> descifrador produce un <xref:System.Security.Cryptography.CryptographicException>. Para obtener más información, consulte [descifrador AesCryptoServiceProvider proporciona una transformación reutilizable](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controles si el valor de la [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) propiedad es una [IntPtr](xref:System.IntPtr) que representa la ubicación de memoria de una ventana de controlar, o si es un identificador de ventana (HWND). Para más información, vea [Mitigación: CspParameters.ParentWindowHandle espera HWND](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedCMS es SHA1 o SHA256. |.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedXML es SHA1 o SHA256. |.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina si el `TransportWithMessageCredential` modo de seguridad permite a los mensajes con unsigned "a" encabezado. Se trata de un conmutador de inclusión. Para obtener más información, consulte [cambios de Runtime de .NET Framework 4.6.1](https://msdn.microsoft.com/library/mt592686.aspx#WCF).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controles si el <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor produce una <xref:System.ArgumentException> si uno de los elementos es `null`.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina que si el intento de usar X509 certificados con un proveedor de almacenamiento de claves CSG inicia una excepción. Para obtener más información, consulte [seguridad de transporte WCF es compatible con los certificados almacenados con CNG](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Cuando se usa el transporte HTTP con un servicio autohospedado, establecer este valor en `true` hace que WCF pasar por alto la adición de una aplicación la `Connection: close` encabezado a los encabezados de respuesta para una solicitud. Establecer este valor en `false` permite agregar la `Connection: close` encabezado a los encabezados de respuesta, lo que resulta en el socket de la solicitud de cierre después de que se ha enviado una respuesta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Controla los interbloqueos que resultan de la restricción de las instancias de un servicio reentrante a un único subproceso de ejecución a la vez.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Junto con `Switch.System.Net.DontEnableSchUseStrongCrypto`, determina si la seguridad de mensajes WCF usa TLS 1.1 y TLS 1.2.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Un valor de `false` establece la configuración predeterminada para permitir que el sistema operativo elija el protocolo. Un valor de `true` establece el valor predeterminado para el protocolo más alto disponible. (También disponible en la rama de versiones anteriores de framework de mantenimiento)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina si el mensaje predeterminado que se firma el algoritmo para los mensajes de MSMQ en WCF es SHA1 o SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controla si WCF usa un SHA1 o un código hash SHA256 para generar nombres aleatorios para canalizaciones con nombre.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Controla si se debe producir una [NullReferenceException](xref:System.NullReferenceException) cuando el mensaje de excepción es null.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controla si las excepciones producidas durante el inicio del servicio se propagan al llamador de la <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> método.|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina si algunos caracteres codificados por porcentaje que en ocasiones se descodificaban ahora se codifican sistemáticamente izquierda. Si `true`, descodificado; de lo contrario, `false`.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina el tratamiento de caracteres bidireccionales de Unicode en URI. `true` para quitarlos de URI; `false` para conservar y ellos codificar por ciento.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina si Windows Presentation Foundation se aplica un algoritmo anterior (`true`) o un nuevo algoritmo (`false`) en la asignación de espacio para \*-las columnas. Para más información, vea [Mitigación: Asignación del espacio del control de cuadrícula a columnas de estrella](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Si un selector o una pestaña de control siempre actualiza el valor de su propiedad de valor seleccionado antes de generar la selección de controles de evento de cambio.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina si está disponible para la representación no adorno la selección basada en el <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.PasswordBox> controles para evitar que el texto ocluido (`false`), o si el texto se representa en la capa de adornos (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina si se producen cambios de PPP en un sistema por (un valor de `false`) o por monitor (un valor de `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina si el desarrollador necesita controlar especialmente el <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> acción cuando el texto del control está presente. `true` para controlar la <xref:System.Windows.Forms.DomainUpDown.UpButton> acción; `false` para el <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> y <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> acciones que se deben estar correctamente sincronizados.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|No participa en el código que permite un personalizado <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementación para filtrar los mensajes de forma segura sin producir una excepción cuando el <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> se llama al método. Para más información, consulte [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina si el <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> propiedad devuelve el control de código fuente cuando el usuario abre el menú de un anidado <xref:System.Windows.Forms.ToolStripMenuItem> control. `true` para devolver `null`, el comportamiento heredado; `false` para devolver el control de código fuente.|.NET Framework 4.7.2|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina si un elemento opcional `WM_POINTER`-pila de lápiz/entrada táctil en función está habilitada en las aplicaciones de WPF. Para obtener más información, consulte [mitigación: basada en puntero táctil y compatibilidad con el lápiz](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina si el algoritmo de hash predeterminado usado para las sumas de comprobación es SHA256 (`false`) o SHA1 (`true`).|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controla si un legado [NullReferenceException](xref:System.NullReferenceException) se produce en lugar de la excepción que se indica más específicamente la causa de la excepción (como un [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o un [ FileNotFoundException](xref:System.IO.FileNotFoundException). Se está diseñado para su uso por código que dependa del control la [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.UseLegacyAccessibilityFeatures`|Controles si disponible a partir de .NET Framework 4.7.1 de características de accesibilidad están habilitados o deshabilitados. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Si la accesibilidad de las características disponibles en .NET Framework 4.7.2 se habilitan los controles (`false`) o deshabilitado (`true`). Si `true`, `Switch.UseLegacyAccessibilityFeatures` también debe ser `true` para habilitar las características de accesibilidad de .NET Framework 4.7.1.|.NET Framework 4.7.2|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Controla si se omiten las secuencias de claves vacías en las claves compuestas por la validación de esquema XSD. Para obtener más información, consulte [mitigación: validación de esquemas XML](~/docs/framework/migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|  
  
> [!NOTE]
>  En lugar de agregar un `AppContextSwitchOverrides` elemento a un archivo de configuración de la aplicación, también puede establecer los modificadores mediante programación llamando a la `static` (en C#) o `Shared` (en Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> método.  
  
 Los desarrolladores de bibliotecas también pueden definir los modificadores personalizados para permitir que los llamadores rechazar introducida en versiones posteriores de sus bibliotecas de funcionalidad que ha cambiado. Para obtener más información, vea la clase <xref:System.AppContext>.  
  
## <a name="switches-in-aspnet-applications"></a>Modificadores en aplicaciones ASP.NET

Puede configurar una aplicación ASP.NET para usar la configuración de compatibilidad mediante la adición de un [ \<Agregar >](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) elemento a la [ \<appSettings >](~/docs/framework/configure-apps/file-schema/appsettings/index.md) sección del archivo web.config. 

En el ejemplo siguiente se usa el `<add>` elemento para agregar dos valores para el `<appSettings>` sección de un archivo web.config:

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se usa el `AppContextSwitchOverrides` elemento para definir un modificador de compatibilidad de aplicación único `Switch.System.Globalization.NoAsyncCurrentCulture`, que evita que referencia cultural que fluyen a través de subprocesos en las llamadas de método asincrónico.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
   </runtime>  
</configuration>  
```  
  
 En el ejemplo siguiente se usa el `AppContextSwitchOverrides` elemento para definir dos modificadores de compatibilidad de aplicaciones, `Switch.System.Globalization.NoAsyncCurrentCulture` y `Switch.System.IO.BlockLongPaths`. Tenga en cuenta que un punto y coma separa los dos pares de nombre/valor.  
  
```xml  
<configuration>  
    <runtime>  
       <AppContextSwitchOverrides   
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.AppContext?displayProperty=nameWithType>  
 [\<en tiempo de ejecución > elemento](runtime-element.md)  
 [Elemento \<configuration>](../configuration-element.md)
