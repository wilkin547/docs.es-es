---
title: Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)
description: Obtenga información sobre la utilidad de metadatos de ServiceModel, que genera código del modelo de servicio WFC a partir de documentos de metadatos y documentos de metadatos del código del modelo de servicio.
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], building
- endpoints [WCF]
- Svcutil.exe
- clients [WCF], consuming services
ms.assetid: 1abf3d9f-b420-46f1-b628-df238751f308
ms.openlocfilehash: 65013f43aa0075b6de6999741afb448c2a35afb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689932"
---
# <a name="servicemodel-metadata-utility-tool-svcutilexe"></a>Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)

La herramienta de utilidad de metadatos de ServiceModel se usa para generar código de modelo de servicio a partir de documentos de metadatos y documentos de metadatos del código del modelo de servicio.

## <a name="svcutilexe"></a>SvcUtil.exe

La herramienta de utilidad de metadatos de ServiceModel se puede encontrar en la ubicación de instalación de Windows SDK, concretamente *%ProgramFiles%\Microsoft SDKs\Windows\v6.0\Bin*.

### <a name="functionalities"></a>Funcionalidades

En la tabla siguiente se resumen las distintas funcionalidades proporcionadas por esta herramienta y el tema correspondiente en el que se explica cómo se usa:

|Tarea|Tema|
|----------|-----------|
|Genera código a partir de servicios en ejecución o de documentos de metadatos estáticos.|[Generación de un cliente WCF a partir de los metadatos de servicio](./feature-details/generating-a-wcf-client-from-service-metadata.md)|
|Exporta documentos de metadatos a partir del código compilado.|[Procedimiento para usar Svcutil.exe para exportar metadatos desde el código de servicio compilado](./feature-details/how-to-use-svcutil-exe-to-export-metadata-from-compiled-service-code.md)|
|Valida el código de servicio compilado.|[Procedimiento para usar Svcutil.exe para validar el código del servicio compilado](./feature-details/how-to-use-svcutil-exe-to-validate-compiled-service-code.md)|
|Descarga los documentos de metadatos de los servicios en ejecución.|[Procedimiento para usar Svcutil.exe para descargar documentos de metadatos](./feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)|
|Genera el código de serialización.|[Procedimiento para mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md)|

> [!CAUTION]
> SvcUtil sobrescribe los archivos existentes en un disco si los nombres proporcionados como parámetros son idénticos. Esto puede incluir archivos de código, configuración o archivos de metadatos. Para evitar esto al generar archivos de código y de configuración, utilice el `/mergeConfig` modificador.
>
> Además, los `/r` `/ct` modificadores y para los tipos de referencia son para generar contratos de datos. Estos modificadores no funcionan al utilizar XmlSerializer.

### <a name="timeout"></a>Tiempo de espera

La herramienta tiene un tiempo de espera de cinco minutos al recuperar los metadatos. Este tiempo de espera sólo se aplica a la recuperación de metadatos a través de la red. No se aplica a cualquier procesamiento de esos metadatos.

### <a name="multi-targeting"></a>Compatibilidad con múltiples versiones

La herramienta no es compatible con múltiples versiones. Si desea generar un artefacto de .NET Framework 4 a partir de *svcutil.exe*, use el *svcutil.exe* del SDK de .NET Framework 4. Para generar un .NET Framework artefacto 3,5, use el archivo ejecutable del SDK de .NET Framework 3,5.

### <a name="accessing-wsdl-documents"></a>Acceso a documentos WSDL

Cuando utiliza Svcutil para obtener acceso a un documento WSDL que contiene una referencia a un servicio de token de seguridad (STS), Svcutil realiza una llamada WS-MetadataExchange al STS. Sin embargo, el servicio puede exponer sus documentos WSDL mediante WS-MetadataExchange o HTTP GET. Por lo tanto, si el STS solo ha expuesto el documento WSDL mediante HTTP GET, se producirá un error en un cliente escrito en WinFX. En el caso de los clientes escritos en .NET Framework 3,5, SvcUtil intenta usar WS-MetadataExchange y HTTP GET para obtener el WSDL de STS.

## <a name="using-svcutilexe"></a>Utilizar Svcutil.exe

### <a name="common-usages"></a>Usos comunes

En la tabla siguiente se muestran algunas opciones de uso frecuente de esta herramienta:

|Opción|Descripción|
|------------|-----------------|
|/Directory\<directory>|Directorio en el que se crearán los archivos.<br /><br /> Valor predeterminado: el directorio actual.<br /><br /> Forma abreviada: `/d`|
|/help|Muestra la sintaxis de comandos y las opciones de la herramienta.<br /><br /> Forma abreviada: `/?`|
|/noLogo|Suprime el mensaje del banner y el copyright.|
|/svcutilConfig:\<configFile>|Especifica un archivo de configuración personalizado para utilizar en lugar del archivo App.config. Esto se puede utilizar para registrar extensiones system.serviceModel sin modificar el archivo de configuración de la herramienta.|
|/target:\<output type>|Especifica la salida que va a generar la herramienta.<br /><br /> Los valores válidos son código, metadatos o xmlSerializer.<br /><br /> Forma abreviada: `/t`|

### <a name="code-generation"></a>Generación de código

Svcutil.exe puede generar el código para los contratos de servicios, clientes y tipos de datos a partir de documentos de metadatos. Estos documentos de metadatos pueden estar en un almacenamiento duradero o recuperarse en línea. La recuperación en línea sigue el protocolo de WS-Metadata Exchange o el protocolo DISCO (para obtener detalles, vea la sección Descarga de metadatos).

Puede usar la herramienta de *SvcUtil.exe* para generar contratos de datos y de servicio basados en un documento WSDL predefinido. Use el modificador /serviceContract y especifique una dirección URL o una ubicación de archivo donde el documento de WSDL se puede descargar o encontrar. Esto genera el servicio y los contratos de datos definidos en el documento WSDL que se pueden usar para implementar un servicio de quejas. Para obtener más información, vea [Cómo: recuperar metadatos e implementar un servicio conforme](./feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md).

Para un servicio con un punto de conexión de BasicHttpContextBinding, *Svcutil.exe* genera BasicHttpBinding con el `allowCookies` atributo establecido en en `true` su lugar. Las cookies se utilizan para el contexto del servidor. Si desea administrar el contexto del cliente cuando el servicio utiliza cookies, puede modificar manualmente la configuración para usar un enlace de contexto.

> [!CAUTION]
> Svcutil.exe genera el cliente basado en el WSDL o en el archivo de directivas recibido del servicio. El nombre principal de usuario (UPN) se genera concatenando el nombre de usuario, " \@ " y un nombre de dominio completo (FQDN). Sin embargo, para los usuarios que se registraron en Active Directory, este formato no es válido y el UPN generado por la herramienta produce un error en la autenticación de Kerberos con el mensaje de error "El intento de inicio de sesión ha producido un error." Para resolver este problema, debe corregir manualmente el archivo de cliente generado por esta herramienta.

`svcutil.exe [/t:code]  <metadataDocumentPath>* | <url>* | <epr>`

|Argumento|Descripción|
|--------------|-----------------|
|`epr`|La ruta de acceso a un archivo XML que contiene un WS-Addressing EndpointReference para un extremo de servicio compatible con WS-Metadata Exchange. Para obtener más información, vea la sección Descarga de metadatos.|
|`metadataDocumentPath`|Ruta de acceso a un documento de metadatos (*WSDL* o *xsd*) que contiene el contrato que se va a importar en el código (. wsdl,. xsd,. wspolicy o. wsmex).<br /><br /> Svcutil sigue importaciones e inclusiones al especificar una dirección URL remota para los metadatos. Sin embargo, si desea procesar los archivos de metadatos en el sistema de archivos local, debe especificar todos los archivos en este argumento. De esta manera, puede usar Svcutil en un entorno de compilación donde no puede tener dependencias de red. Puede usar caracteres comodín (*. xsd, \* . WSDL) para este argumento.|
|`url`|La dirección URL a un extremo de servicio que proporciona metadatos o a un documento de metadatos hospedado en línea. Para obtener más información sobre cómo se recuperan estos documentos, vea la sección Descarga de metadatos.|

|Opción|Descripción|
|------------|-----------------|
|/async|Genera firmas del método sincrónicas y asincrónicas.<br /><br /> Valor predeterminado: generar solo firmas de método sincrónicas.<br /><br /> Forma abreviada: `/a`|
|collectionType\<type>|Especifica el tipo de colección de lista para un cliente de WCF.<br/><br /> Valor predeterminado: el tipo de colección es System. Array. <br /><br /> Forma abreviada: `/ct`|
|/config:\<configFile>|Especifica el nombre de archivo para el archivo de configuración generado.<br /><br /> Valor predeterminado: output.config|
|/dataContractOnly|Genera código solo para tipos de contrato de datos. No se generan los tipos del contrato de servicio.<br /><br /> Solo debería especificar archivos de metadatos locales para esta opción.<br /><br /> Forma abreviada: `/dconly`|
|/enableDataBinding|Implementa la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> en todos los tipos de contrato de datos para habilitar el enlace de datos.<br /><br /> Forma abreviada: `/edb`|
|/excludeType:\<type>|Especifica un nombre de tipo completo o calificado con el nombre de ensamblado que se va a excluir de los tipos de contrato a los que se hace referencia.<br /><br /> Al utilizar este modificador junto con `/r` de DLL independientes, se hace referencia al nombre completo de la clase XSD.<br /><br /> Forma abreviada: `/et`|
|/importXmlTypes|Configura el serializador de contratos de datos para importar tipos que no son de contratos de datos como tipos IXmlSerializable.|
|/internal|Genera clases que están marcadas como internas. Valor predeterminado: generar solo clases públicas.<br /><br /> Forma abreviada: `/i`|
|/Language\<language>|Especifica el lenguaje de programación a utilizar para la generación de código. Debe proporcionar un nombre de lenguaje registrado en el archivo Machine.config o el nombre completo de una clase que hereda de <xref:System.CodeDom.Compiler.CodeDomProvider> .<br /><br /> Valores: c#, cs, csharp, vb, visualbasic, c++, cpp<br /><br /> Valor predeterminado: csharp<br /><br /> Forma abreviada: `/l`|
|/mergeConfig|Combina la configuración generada en un archivo existente en lugar de sobrescribir el archivo existente.|
|/messageContract|Genera tipos de contrato de mensaje.<br /><br /> Forma abreviada: `/mc`|
|/Namespace\<string,string>|Especifica una asignación de un targetNamespace WSDL o esquema XML a un espacio de nombres CLR. El uso \* de ' ' para el targetNamespace asigna todos los targetNamespaces sin una asignación explícita a ese espacio de nombres CLR.<br /><br /> Para asegurarse de que el nombre de contrato de mensaje no produce una colisión con el nombre de la operación, debería calificar la referencia del tipo con `::` o asegurarse de que los nombres son únicos.<br /><br /> Valor predeterminado: Se deriva del espacio de nombres de destino del documento de esquema para contratos de datos. El espacio de nombres predeterminado se utiliza para todos los otros tipos generados.<br /><br /> Forma abreviada: `/n` **Nota:**  al generar tipos para usar con XmlSerializer, solo se admite una única asignación de espacio de nombres. Todos los tipos generados estarán en el espacio de nombres predeterminado o en el espacio de nombres especificado por ' * '.|
|/noConfig|No generar archivos de configuración.|
|/noStdLib|No hacer referencia a las bibliotecas estándar.<br /><br /> Valor predeterminado: Se hace referencia a Mscorlib.dll y a System.servicemodel.dll.|
|/out\<file>|Especifica el nombre de archivo para el código generado.<br /><br /> Valor predeterminado: Se deriva del nombre de definición de WSDL, nombre de servicio de WSDL o espacio de nombres de destino de uno de los esquemas.<br /><br /> Forma abreviada: `/o`|
|/Reference\<file path>|Tipos de referencia en el ensamblado especificado. Al generar clientes, utilice esta opción para especificar ensamblados que podrían contener tipos que representan los metadatos que se están importando.<br /><br /> No puede especificar contratos de mensaje y los tipos <xref:System.Xml.Serialization.XmlSerializer> utilizando este modificador.<br /><br /> Si se hace referencia a <xref:System.DateTimeOffset>, se utiliza este tipo en lugar de generar un tipo nuevo. Si la aplicación se escribe utilizando .NET Framework 3,5, SvcUtil.exe referencias <xref:System.DateTimeOffset> automáticamente.<br /><br /> Forma abreviada: `/r`|
|/serializable|Genera clases marcadas con el atributo Serializable.<br /><br /> Forma abreviada: `/s`|
|/serviceContract|Genera código para contratos de servicio únicamente. La clase de cliente y la configuración no se generarán<br /><br /> Forma abreviada: `/sc`|
|/serializer:Auto|Seleccionar automáticamente el serializador. Intenta usar el serializador de contrato de datos y usa XmlSerializer si se produce un error.<br /><br /> Forma abreviada: `/ser`|
|/serializer:DataContractSerializer|Genera tipos de datos que utilizan el serializador de contratos de datos para la serialización y deserialización.<br /><br /> Forma abreviada: `/ser:DataContractSerializer`|
|/serializer:XmlSerializer|Genera tipos de datos que usan el <xref:System.Xml.Serialization.XmlSerializer> para la serialización y deserialización.<br /><br /> Forma abreviada: `/ser:XmlSerializer`|
|/targetClientVersion|Especifique la versión de .NET Framework de destino de la aplicación. Los valores válidos son `Version30` y `Version35`. El valor predeterminado es `Version30`.<br /><br /> Forma abreviada: `/tcv`<br /><br /> `Version30`: `/tcv:Version30` Se usa si se va a generar código para los clientes que usan WinFX.<br /><br /> `Version35`: `/tcv:Version35` Se usa si se va a generar código para los clientes que utilizan .NET Framework 3,5. Al utilizar `/tcv:Version35` con el modificador `/async`, se generan tanto el método asincrónico basado en evento como el método asincrónico de devolución de llamada/basado en delegado. Además, está habilitada la compatibilidad para conjuntos de datos habilitados por LINQ y <xref:System.DateTimeOffset>.|
|/wrapped|Controla si se utiliza una grafía especial en los documentos con estilo de literales de documento con parámetros ajustados. Use el modificador **/wrapped** con la herramienta de [utilidad de metadatos del modelo de servicio (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) para especificar la grafía normal.|

> [!NOTE]
> Cuando el enlace de servicio es uno de los enlaces proporcionados por el sistema (vea [enlaces proporcionados por el sistema](system-provided-bindings.md)) y la <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> propiedad está establecida en `None` o `Sign` , SvcUtil genera un archivo de configuración mediante el [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md) elemento en lugar del elemento esperado proporcionado por el sistema. Por ejemplo, si el servicio utiliza el elemento `<wsHttpBinding>` con `ProtectionLevel` establecido en `Sign`, la configuración generada tiene `<customBinding>` en la sección de enlaces en lugar de `<wsHttpBinding>`. Para obtener más información sobre el nivel de protección, vea [Descripción del nivel de protección](understanding-protection-level.md).

### <a name="metadata-export"></a>Exportación de metadatos

Svcutil.exe puede exportar metadatos para los servicios, contratos y tipos de datos en ensamblados compilados. Para exportar los metadatos para un servicio, debe utilizar la opción `/serviceName` para especificar el servicio que desea exportar. Para exportar todos los tipos de contrato de datos dentro de un ensamblado, debe utilizar la opción `/dataContractOnly`. De forma predeterminada, los metadatos se exportan para todos los contratos de servicios en los ensamblados de entrada.

`svcutil.exe [/t:metadata] [/serviceName:<serviceConfigName>] [/dataContractOnly] <assemblyPath>*`

|Argumento|Descripción|
|--------------|-----------------|
|`assemblyPath`|Especifica la ruta de acceso a un ensamblado que contiene los servicios, contratos o tipos de contrato de datos a exportar. Los caracteres comodín de la línea de comandos estándar se pueden utilizar para proporcionar varios archivos como entrada.|

|Opción|Descripción|
|------------|-----------------|
|ServiceName\<serviceConfigName>|Especifica el nombre de configuración de un servicio que se va a exportar. Si se utiliza esta opción, se debe pasar un ensamblado ejecutable con un archivo de configuración asociado como entrada. Svcutil.exe busca la configuración de servicio en todos los archivos de configuración asociados. Si los archivos de configuración contienen cualquier tipo de extensión, los ensamblados que contienen estos tipos deben estar en la GAC o indicados de forma explícita mediante la opción `/reference`.|
|/Reference\<file path>|Agrega el ensamblado especificado al conjunto de ensamblados utilizados para resolver las referencias de tipo. Si está exportando o validando un servicio registrado en configuración que utiliza extensiones de terceros (Comportamientos, Enlaces y Elementos de enlace), utilice esta opción para buscar ensamblados de extensión que no están en la GAC.<br /><br /> Forma abreviada: `/r`|
|/dataContractOnly|Solo funciona en tipos de contrato de datos. No se procesan los contratos de servicios.<br /><br /> Solo debería especificar archivos de metadatos locales para esta opción.<br /><br /> Forma abreviada: `/dconly`|
|/excludeType:\<type>|Especifica el nombre completo o calificado con el ensamblado de un tipo que se va a excluir de la exportación. Se puede utilizar esta opción al exportar los metadatos para un servicio o un conjunto de contratos de servicios excluyan tipos de la exportación. Esta opción no se puede combinar con la opción `/dconly`.<br /><br /> Si tiene un ensamblado único que contiene varios servicios y cada uno usa clases independientes con el mismo nombre XSD, debería especificar el nombre del servicio en lugar del nombre de clase XSD para este modificador.<br /><br /> No se admiten XSD o tipos de contrato de datos.<br /><br /> Forma abreviada: `/et`|

### <a name="service-validation"></a>Validación del servicio

La validación se puede utilizar para detectar errores en implementaciones del servicio sin hospedar el servicio. Debe utilizar la opción `/serviceName` para indicar el servicio que desea validar.

`svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*`

|Argumento|Descripción|
|--------------|-----------------|
|`assemblyPath`|Especifica la ruta de acceso a un ensamblado que contiene tipos de servicio que hay que validar. El ensamblado debe tener un archivo de configuración asociado para proporcionar la configuración de servicio. Los caracteres comodín de la línea de comandos estándar se pueden utilizar para proporcionar varios ensamblados.|

|Opción|Descripción|
|------------|-----------------|
|/validate|Valida una implementación del servicio especificada por la opción `/serviceName`. Si se utiliza esta opción, se debe pasar un ensamblado ejecutable con un archivo de configuración asociado como entrada.<br /><br /> Forma abreviada: `/v`|
|ServiceName\<serviceConfigName>|Especifica el nombre de configuración de un servicio que se va a validar. Svcutil.exe busca la configuración de servicio en todos los archivos de configuración asociados de todos los ensamblados de entrada. Si los archivos de configuración contienen cualquier tipo de extensión, los ensamblados que contienen estos tipos deben estar en la GAC o indicados de forma explícita mediante la opción `/reference`.|
|/Reference\<file path>|Agrega el ensamblado especificado al conjunto de ensamblados utilizados para resolver las referencias de tipo. Si está exportando o validando un servicio registrado en configuración que utiliza extensiones de terceros (Comportamientos, Enlaces y Elementos de enlace), utilice esta opción para buscar ensamblados de extensión que no están en la GAC.<br /><br /> Forma abreviada: `/r`|
|/dataContractOnly|Solo funciona en tipos de contrato de datos. No se procesan los contratos de servicios.<br /><br /> Solo debería especificar archivos de metadatos locales para esta opción.<br /><br /> Forma abreviada: `/dconly`|
|/excludeType:\<type>|Especifica el nombre completo o calificado con el ensamblado de un tipo que se va a excluir de la validación.<br /><br /> Forma abreviada: `/et`|

### <a name="metadata-download"></a>Descarga de metadatos

Se puede utilizar Svcutil.exe para descargar los metadatos de servicios en ejecución y guardar los metadatos en archivos locales. Debe especificar la opción `/t:metadata` para descargar los metadatos. De lo contrario, se genera el código de cliente. Para esquemas URL de HTTP y HTTPS, Svcutil.exe intenta recuperar metadatos mediante WS-Metadata Exchange y DISCO. Para todos los otros esquemas de URL, Svcutil.exe utiliza solo WS-Metadata Exchange.

Svcutil emite simultáneamente las solicitudes de los metadatos siguientes para recuperar los metadatos.

- Solicitud MEX (WS-Transfer) a la dirección proporcionada

- Solicitud MEX a la dirección proporcionada con /mex anexado

- Solicitud DISCO (utilizando DiscoveryClientProtocol de ASMX) a la dirección proporcionada.

De forma predeterminada, Svcutil.exe utiliza los enlaces definidos en la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings> para realizar las solicitudes MEX. Para configurar el enlace utilizado para WS-Metadata Exchange, debe definir un extremo del cliente en configuración que utiliza el contrato de IMetadataExchange. Esto se puede definir en el archivo de configuración de Svcutil.exe o en otro archivo de configuración especificado mediante la opción `/svcutilConfig`.

`svcutil.exe /t:metadata  <url>* | <epr>`

|Argumento|Descripción|
|--------------|-----------------|
|`url`|La dirección URL a un extremo de servicio que proporciona metadatos o a un documento de metadatos hospedado en línea.|
|`epr`|La ruta de acceso a un archivo XML que contiene un WS-Addressing EndpointReference para un extremo de servicio compatible con WS-Metadata Exchange.|

### <a name="xmlserializer-type-generation"></a>Generación de tipo XmlSerializer

Los servicios y las aplicaciones cliente que utilizan tipos de datos que son serializables utilizando <xref:System.Xml.Serialization.XmlSerializer> generan y compilan el código de la serialización para esos tipos de datos en el tiempo de ejecución, lo que se puede traducir en un rendimiento de inicio lento.

> [!NOTE]
> El código de serialización generado previamente solo puede usarse en aplicaciones cliente y no en servicios.

Svcutil.exe puede generar el código de serialización C# necesario a partir de los ensamblados compilados para la aplicación, mejorando así el rendimiento de inicio de esas aplicaciones. Para obtener más información, vea [Cómo: mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).

> [!NOTE]
> Svcutil.exe solo genera el código para los tipos utilizados por los contratos de servicio situados en los ensamblados de entrada.

`svcutil.exe /t:xmlSerializer  <assemblyPath>*`

|Argumento|Descripción|
|--------------|-----------------|
|`assemblyPath`|Especifica la ruta de acceso a un ensamblado que contiene tipos de contrato de servicio. Los tipos de serialización se generan para todos los tipos Xml Serializable en cada contrato.|

|Opción|Descripción|
|------------|-----------------|
|/Reference\<file path>|Agrega el ensamblado especificado al conjunto de ensamblados utilizados para resolver las referencias de tipo.<br /><br /> Forma abreviada: `/r`|
|/excludeType:\<type>|Especifica el nombre completo o calificado con el ensamblado de un tipo que se va a excluir de la exportación o de la validación.<br /><br /> Forma abreviada: `/et`|
|/out\<file>|Especifica el nombre de archivo para el código generado. Se omite esta opción cuando se pasan varios ensamblados a la herramienta como entrada.<br /><br /> Valor predeterminado: Se deriva del nombre de ensamblado.<br /><br /> Forma abreviada: `/o`|
|/UseSerializerForFaults|Especifica que <xref:System.Xml.Serialization.XmlSerializer> se debería utilizar para leer y escribir los errores, en lugar del <xref:System.Runtime.Serialization.DataContractSerializer> predeterminado.|

## <a name="examples"></a>Ejemplos

El comando siguiente genera el código de cliente a partir de un servicio en ejecución o los documentos de metadatos en línea.

`svcutil http://service/metadataEndpoint`

El comando siguiente genera el código de cliente a partir de los documentos de metadatos locales.

`svcutil *.wsdl *.xsd /language:C#`

El comando siguiente genera los tipos de contrato de datos en Visual Basic a partir de documentos de esquema locales.

`svcutil /dconly *.xsd /language:VB`

El comando siguiente descarga los documentos de metadatos a partir de servicios en ejecución.

`svcutil /t:metadata http://service/metadataEndpoint`

El comando siguiente genera los documentos de metadatos para contratos de servicios y tipos asociados en un ensamblado.

`svcutil myAssembly.dll`

El comando siguiente genera documentos de metadatos para un servicio y todos los contratos de servicios asociados y tipos de datos en un ensamblado.

`svcutil myServiceHost.exe /serviceName:myServiceName`

El comando siguiente genera documentos de metadatos para los tipos de datos en un ensamblado.

`svcutil myServiceHost.exe /dconly`

El comando siguiente comprueba el hospedaje del servicio.

`svcutil /validate /serviceName:myServiceName myServiceHost.exe`

El comando siguiente genera los tipos de serialización para los tipos <xref:System.Xml.Serialization.XmlSerializer> utilizados por cualquier contrato de servicios en el ensamblado.

`svcutil /t:xmlserializer myContractLibrary.exe`

## <a name="maximum-nametable-character-count-quota"></a>Cuota máxima de caracteres de tabla de nombres

Al utilizar svcutil para generar metadatos para un servicio, es posible que obtenga el mensaje de error siguiente:

Error: no se pueden obtener los metadatos de `http://localhost:8000/somesservice/mex` la cuota máxima de número de caracteres de NameTable (16384) al leer los datos XML. La tabla de nombres es una estructura de datos que se emplea para almacenar las cadenas encontradas durante el procesamiento XML. Los documentos XML largos con valores de atributo, nombres de atributo y nombres de elemento no repetidos pueden hacer que se sobrepase la cuota. Esta cuota puede aumentarse cambiando la propiedad MaxNameTableCharCount en el objeto XmlDictionaryReaderQuotas usado al crear el lector XML.

Este error puede producirlo un servicio que devuelve un archivo WSDL de gran tamaño cuando se solicitan sus metadatos. El problema se produce porque se supera la cuota de caracteres de la herramienta svcutil.exe. Este valor se establece para evitar los ataques por denegación de servicio (DOS). Puede aumentar esta cuota especificando el archivo de configuración siguiente para svcutil.

El archivo de configuración siguiente muestra cómo establecer las cuotas de lector para svcutil.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
    <system.serviceModel>
        <bindings>
            <customBinding>
                <binding name="MyBinding">
                    <textMessageEncoding>
                        <readerQuotas maxDepth="2147483647" maxStringContentLength="2147483647"
                            maxArrayLength="2147483647" maxBytesPerRead="2147483647" maxNameTableCharCount="2147483647" />
                    </textMessageEncoding>
                    <httpTransport maxReceivedMessageSize="2147483647" maxBufferSize="2147483647" />
                </binding>
            </customBinding>
        </bindings>
        <client>
            <endpoint binding="customBinding" bindingConfiguration="MyBinding"
                contract="IMetadataExchange"
                name="http" />
        </client>
    </system.serviceModel>
</configuration>
```

Cree un archivo denominado svcutil.exe.config y copie en él el código de ejemplo en XML. A continuación, sitúe el archivo en el mismo directorio que svcutil.exe. La próxima vez que se ejecute svcutil.exe, usará la nueva configuración.

## <a name="security-concerns"></a>Cuestiones de seguridad

Debería utilizar la lista de control de acceso (ACL) adecuada para proteger la carpeta de instalación de Svcutil.exe, Svcutil.config y los archivos que `/svcutilConfig` señala. Esto puede evitar que se registren y se ejecuten extensiones malintencionadas.

Además, para minimizar la posibilidad de que la seguridad se vea comprometida, no debe agregar extensiones que no sean de confianza para que formen parte del sistema o utilizar proveedores de código que no sean de confianza con Svcutil.exe.

Finalmente, no debería utilizar la herramienta en el nivel medio de su aplicación, ya que puede producir la denegación de servicio al proceso actual.

## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- [Cómo crear un cliente](how-to-create-a-wcf-client.md)
