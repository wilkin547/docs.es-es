---
title: '&lt;AppContextSwitchOverrides&gt; elemento'
ms.custom: updateeachrelease
ms.date: 04/19/2018
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d16ce7f2744869c812b9988e91edd153d9cb4fd2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
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
|"nombre = valor"|Un nombre de conmutador predefinidos junto con su valor (`true` o `false`). Varios pares de nombre/valor de conmutador están separados por punto y coma (";"). Para obtener una lista de nombres predefinidos conmutador compatible con .NET Framework, vea la sección Comentarios.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 A partir de la versión 4.6 de .NET Framework, el `<AppContextSwitchOverrides>` elemento en un archivo de configuración permite a los llamadores de una API para determinar si su aplicación puede aprovechar las ventajas de la nueva funcionalidad o mantener la compatibilidad con versiones anteriores de una biblioteca. Por ejemplo, si el comportamiento de una API ha cambiado entre dos versiones de una biblioteca, el `<AppContextSwitchOverrides>` elemento permite a los llamadores de esta API para no participar en el nuevo comportamiento en las versiones de la biblioteca que admiten la funcionalidad nueva. Para las aplicaciones que llaman a las API de .NET Framework, el `<AppContextSwitchOverrides>` elemento también puede permitir que las aplicaciones cuyas destinan una versión anterior de .NET Framework no formen parte de la nueva funcionalidad si su aplicación se ejecuta en una versión de .NET Framework que incluye que los autores de llamadas funcionalidad.  
  
 El `value` atributo de la `<AppContextSwitchOverrides>` elemento consta de una sola cadena que consta de uno o más pares de nombre/valor delimitado por punto y coma.  Cada nombre identifica un modificador de compatibilidad y su valor correspondiente es un valor booleano (`true` o `false`) que indica si el modificador está establecido. De forma predeterminada, el modificador es `false`, y las bibliotecas proporcionan la nueva funcionalidad. Sólo ofrecen la funcionalidad anterior si el modificador está establecido (es decir, su valor es `true`). Esto permite que las bibliotecas proporcionar el nuevo comportamiento de una API existente mientras que los llamadores que dependen del comportamiento anterior para no participar en la nueva funcionalidad.  
  
 .NET Framework admite los siguientes modificadores:  
  
|Nombre del conmutador|Descripción|Introdujo|  
|-----------------|-----------------|----------------|  
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Controla si Windows Presentation Foundation usa heredado un algoritmo para el diseño de controles. Para más información, consulte [Mitigación: diseño de WPF](~/docs/framework/migration-guide/mitigation-wpf-layout.md).|.NET Framework 4.6|  
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|Controla si el algoritmo predeterminado usado para firmar las partes de un paquete por entre es SHA1 o SHA256.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|Cuando se establece en `false`, permite la depuración de proyectos de flujo de trabajo basado en XAML con Visual Studio cuando se habilita FIPS. Sin él, un <xref:System.NullReferenceException> se produce en las llamadas a métodos en el ensamblado de System.Activities.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|Controla si la suma de comprobación para una instancia de flujo de trabajo en el depurador utiliza MD5 o SHA1. | .NET Framework 4.7|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|Controla si los seguimientos de pila obtener al usar archivos PDB portátiles puede incluir información de archivo y la línea de código fuente. `false` para incluir información de archivo y la línea de código fuente; en caso contrario, `true`.|.NET framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|Controles si el <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> método produce una excepción cuando un <xref:System.Drawing.Icon> objeto tiene marcos PNG. Para más información, consulte [Mitigación: marcos PNG en objetos de icono](~/docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|.NET Framework 4.6|  
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|Determina si <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> objetos se desecha correctamente cuando se agrega a la colección por el <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> método. `true` para mantener el comportamiento heredado; `false` a dispose de todos los objetos de fuentes privadas. |.NET framework 4.7.2|
|`Switch.System.Drawing.Printing.`</br>`OptimizePrintPreview`|Controles si el rendimiento de la <xref:System.Windows.Forms.PrintPreviewDialog> está optimizado para las impresoras de red. Para obtener más información, consulte [información general del control PrintPreviewDialog](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md).|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|Controla si las operaciones asincrónicas no fluye desde el contexto del subproceso que realiza la llamada. Para obtener más información, consulte [CurrentCulture y CurrentUICulture fluirán tareas](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks).|.NET Framework 4.6|  
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|Controles si el <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> método intenta hacer coincidir el tipo de notificación solo con la última entrada DNS. Para más información, consulte [Mitigación: Método X509CertificateClaimSet.FindClaims](~/docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|.NET Framework 4.6.1|  
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|Controla si se permite AuthorizationContext.Empty devolver un objeto mutable.|.NET Framework 4.6|  
|`Switch.System.IO.BlockLongPaths`|Controles si las rutas de acceso más de `MAX_PATH` (260 caracteres) producen un <xref:System.IO.PathTooLongException>. Para obtener más información, consulte [largo de ruta de acceso de soporte](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support).|.NET Framework 4.6.2|  
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|Controla si se usan las rutinas de sistema operativo nativo para la descompresión por la <xref:System.IO.Compression.DeflateStream> clase. `false` Para usar las API nativas; `true` para usar el <xref:System.IO.Compression.DeflateStream> implementación.|.NET framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|Usa la barra diagonal inversa ("\\") en lugar de la barra diagonal ("/") como separador de ruta de acceso en la <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> propiedad. Para obtener más información, consulte [mitigación: separador de ruta de acceso de ZipArchiveEntry.FullName](~/docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|.NET Framework 4.6.1|  
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|Controla si operativo excepciones del sistema que se producen en subprocesos en segundo plano creados con <xref:System.IO.Ports.SerialPort> secuencias finalizan el proceso.|.NET Framework 4.7.1| 
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|Controla si se usa la normalización de la ruta de acceso heredadas y las rutas de acceso URI son compatibles con el <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> y <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> métodos. Para obtener más información, consulte [mitigación: ruta de acceso de normalización](~/docs/framework/migration-guide/mitigation-path-normalization.md) y [mitigación: comprueba de dos puntos de ruta de acceso](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|.NET Framework 4.6.2|  
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|Controla si una prueba de igualdad compara el <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> propiedad de un objeto con el <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> propiedad del segundo objeto. Para obtener más información, consulte [implementación incorrecta de MemberDescriptor.Equals](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals).|.NET Framework 4.6.2|  
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|Deshabilita la validación de identificador (OID) de objeto de uso mejorado de clave (EKU) de certificados. Una extensión de uso mejorado de clave (EKU) es una colección de identificadores de objetos (OID) que indica las aplicaciones que usan la clave.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|Deshabilita la mitigación de TLS 1.0 explorador aprovechar con SSL/TLS (BEAST) deshabilitar el uso de SCH_SEND_AUX_RECORD.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|Controles si el <xref:System.Net.ServicePointManager?displayProperty=nameWithType> y <xref:System.Net.Security.SslStream?displayProperty=nameWithType> las clases pueden utilizar el protocolo SSL 3.0. Para más información, consulte [Mitigación: protocolos TLS](~/docs/framework/migration-guide/mitigation-tls-protocols.md).|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|Deshabilita las versiones de SystemDefault TLS volver a un valor predeterminado de Tls12, Tls11, Tls.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|Deshabilita todas las alertas de SslStream TLS del servidor.|.NET Framework 4.7|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |Controles si el [DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) serializa algunos caracteres de control en función de los estándares de ECMAScript V6 y V8. Para más información, vea [Mitigación: Serialización del caracteres de control con DataContractJsonSerializer](Mitigation:%20Serialization%20of%20Control%20Characters%20with%20the%20DataContractJsonSerializer.md)| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|Controles si el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite varios ajustes o solo un ajuste único para una zona horaria. Si `true`, usa el <xref:System.TimeZoneInfo> escriba para serializar y deserializar los datos de fecha y hora; en caso contrario, usa el <xref:System.TimeZone> tipo, que no admite varias reglas de ajuste.|.NET Framework 4.6.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|Controles si el <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> constructor establece el nuevo objeto <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> propiedad con una referencia de objeto existente. Para más información, vea [Mitigation: Constructor ClaimsIdentity](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|.NET Framework 4.6.2|  
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|Controles si el intento de volver a usar un <xref:System.Security.Cryptography.AesCryptoServiceProvider> descifrador produce un <xref:System.Security.Cryptography.CryptographicException>. Para obtener más información, consulte [AesCryptoServiceProvider descifrador proporciona una transformación reutilizable](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform).|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|Controles si el valor de la [CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) propiedad es una [IntPtr](xref:System.IntPtr) que representa la ubicación de memoria de una ventana Administrar o, si es un identificador de ventana (HWND). Para más información, vea [Mitigación: CspParameters.ParentWindowHandle espera HWND](Mitigation:%20CspParameters.ParentWindowHandle%20Expects%20an%20HWND.md). |.NET Framework 4.7|   
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedCMS es SHA1 o SHA256. |.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|Determina si el valor predeterminado para algunas operaciones SignedXML es SHA1 o SHA256. |.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|Determina si el `TransportWithMessageCredential` modo de seguridad permite los mensajes con unsigned "a" encabezado. Se trata de un modificador opcional. Para obtener más información, consulte [cambios en tiempo de ejecución en .NET Framework 4.6.1](https://msdn.microsoft.com/library/mt592686.aspx#WCF).|.NET Framework 4.6.1| 
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|Controles si el <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> constructor produce una <xref:System.ArgumentException> si uno de los elementos es `null`.|.NET Framework 4.7.1| 
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|Determina que si el intento de usar X509 certificados con un proveedor de almacenamiento de claves CSG produce una excepción. Para obtener más información, consulte [seguridad de transporte WCF es compatible con los certificados almacenados con CNG](~/docs/framework/migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng).|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|Cuando se usa el transporte HTTP con un servicio hospedado por sí mismo, establecer este valor en `true` hace que WCF pasar por alto la adición de una aplicación la `Connection: close` encabezado a los encabezados de respuesta para una solicitud. Establecer este valor en `false` permite agregar la `Connection: close` encabezado a los encabezados de respuesta, lo que resulta en el socket de solicitud de cierre después de que se ha enviado una respuesta.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|Interbloqueos de identificadores que son el resultado de la restricción de instancias de un servicio reentrante a un único subproceso de ejecución a la vez.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|Junto con `Switch.System.Net.DontEnableSchUseStrongCrypto`, determina si la seguridad de mensajes WCF usa TLS 1.1 y 1.2 de TLS.|.NET Framework 4.7 |    
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|Un valor de `false` establece la configuración predeterminada para permitir que el sistema operativo elegir el protocolo. Un valor de `true` establece el valor predeterminado para el protocolo más alto disponible. (También disponible en la rama de versiones anteriores de framework de mantenimiento)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|Determina si el mensaje predeterminado que se firma el algoritmo para mensajes de MSMQ en WCF es SHA1 o SHA256.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|Controla si WCF usa un SHA1 o un algoritmo hash SHA256 para generar nombres aleatorios para canalizaciones con nombre.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|Controla si se debe producir una [NullReferenceException](xref:System.NullReferenceException) cuando el mensaje de excepción es null.|.NET Framework 4.7|  
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|Controla si las excepciones producidas en el inicio del servicio se propagan al autor de llamada de la <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> método.|.NET Framework 4.7.1|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|Determina si determinados caracteres codificados en porcentaje que a veces se descodificación ahora se codifican constantemente izquierda. Si `true`, son descodificados; en caso contrario, `false`.|.NET framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Determina el tratamiento de caracteres Unicode bidireccional URI. `true` para quitarlos de URI; `false` para conservar y ellos codificar por ciento.|.NET framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Determina si Windows Presentation Foundation se aplica un algoritmo anterior (`true`) o un nuevo algoritmo (`false`) en la asignación de espacio para \*-columnas. Para más información, vea [Mitigación: Asignación del espacio del control de cuadrícula a columnas de estrella](Mitigation:%20Grid%20Control's%20Space%20Allocation%20to%20Star-columns.md). |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|Evento de cambio de si un selector o una pestaña de control siempre actualiza el valor de su propiedad value seleccionada antes de generar la selección de controles.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|Determina si la representación de selección en función de adorno no está disponible para el <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.PasswordBox> controles para evitar que el texto ocluido (`false`), o si se representa texto sólo en el nivel de adorno (`true`).|.NET framework 4.7.2|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|Determina si se producen cambios de PPP en un sistema por (un valor de `false`) o por el monitor (un valor de `true`).|.NET Framework 4.6.2|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|Determina si el desarrollador debe controlar específicamente el <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> acción cuando hay texto del control. `true` para controlar la <xref:System.Windows.Forms.DomainUpDown.UpButton> acción; `false` para el <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> y <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> acciones que se deben estar correctamente sincronizados.|.NET framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|Participar en el código que permite un personalizado <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementación para filtrar los mensajes de forma segura sin producir una excepción cuando el <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> se llama al método. Para más información, consulte [Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|.NET Framework 4.6.1|  
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|Determina si el <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> propiedad devuelve el control de código fuente cuando el usuario abre el menú de anidada <xref:System.Windows.Forms.ToolStripMenuItem> control. `true` para devolver `null`, el comportamiento heredado; `false` para devolver el control de código fuente.|.NET framework 4.7.2|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|Determina si un elemento opcional `WM_POINTER`-pila táctil/lápiz según está habilitada en las aplicaciones de WPF. Para obtener más información, vea [mitigación: basada en puntero táctil y compatibilidad con el lápiz](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md)|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|Determina si el algoritmo hash predeterminado para las sumas de comprobación es SHA256 (`false`) o SHA1 (`true`).|.NET framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|Controla si un heredado [NullReferenceException](xref:System.NullReferenceException) se produce en lugar de la excepción que indica más específicamente la causa de la excepción (como un [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) o un [ FileNotFoundException](xref:System.IO.FileNotFoundException). Se está pensado para su uso por código que depende de control de la [NullReferenceException](xref:System.NullReferenceException). | .NET Framework 4.7 |
|`Switch.UseLegacyAccessibilityFeatures`|Controles si disponible a partir de .NET Framework 4.7.1 de características de accesibilidad están habilitados o deshabilitados. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|Controles si accesibilidad características que están disponibles en .NET Framework 4.7.2 están habilitadas (`false`) o deshabilitado (`true`). Si `true`, `Switch.UseLegacyAccessibilityFeatures` también debe `true` para habilitar las características de accesibilidad de .NET Framework 4.7.1.|.NET framework 4.7.2|
|`System.Xml.`<br /><br /> `IgnoreEmptyKeySequences`|Controla si se omiten las secuencias de claves vacías en las claves compuestas por la validación de esquemas XSD. Para obtener más información, consulte [mitigación: validación de esquemas XML](~/docs/framework/migration-guide/mitigation-xml-schema-validation.md).|.NET Framework 4.6|  
  
> [!NOTE]
>  En lugar de agregar un `AppContextSwitchOverrides` elemento a un archivo de configuración de la aplicación, también puede establecer los parámetros mediante programación mediante una llamada a la `static` (en C#) o `Shared` (en Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> método.  
  
 Los desarrolladores de bibliotecas también pueden definir los modificadores personalizados para permitir que los llamadores rechazar la funcionalidad que ha cambiado introducida en versiones posteriores de sus bibliotecas. Para obtener más información, vea la clase <xref:System.AppContext>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `AppContextSwitchOverrides` elemento para definir un modificador de compatibilidad de aplicación único, `Switch.System.Globalization.NoAsyncCurrentCulture`, que evita que referencia cultural que fluyen a través de subprocesos en las llamadas de método asincrónico.  
  
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
