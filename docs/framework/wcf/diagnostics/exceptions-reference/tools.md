---
description: 'Más información sobre: herramientas'
title: Herramientas
ms.date: 03/30/2017
ms.assetid: 89c907f9-313f-408c-992a-631f1eadf1da
ms.openlocfilehash: 1400cee5c626f015d5b9a6efcd9c04411f0ba4f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686134"
---
# <a name="tools"></a>Herramientas

En este tema se enumeran todas las excepciones generadas por las herramientas de Windows Communication Foundation (WCF).

## <a name="exception-list"></a>Lista de excepciones

|Código de recurso|Cadena de recurso|
|-------------------|---------------------|
|ParametersTarget|\<enum>|
|ParametersToolConfig|\<configFile>|
|ErrInvalidPath|La ruta de acceso especificada no es válida. Compruebe el argumento especificado.|
|ParametersReference|\<file path>|
|WrnCannotLoadConfigFileForValidation|Se ha producido un error durante el procesamiento del archivo de configuración cargado de la ubicación especificada. No se pueden validar los servicios que se definen en este archivo de configuración.|
|MoreHelp|Para más ayuda, escriba "svcutil" con los argumentos especificados.|
|HelpMergeConfig|Provoca que la configuración generada se fusione con un archivo existente en lugar de sobrescribir el archivo existente.|
|ErrCannotWriteFile|No puede escribir en un archivo de salida.|
|ErrInvalidNamespaceArgument|El valor no válido especificado se pasó a la opción especificada. Especifique un espacio de nombres de destino separado por comas y par de espacio de nombres de CLR.|
|HelpImportXmlType|Configura el serializador DataContract para importar tipos que no son DataContract como tipos IXmlSerializable.|
|ErrExclusiveOptionsSpecified|No se puede utilizar la opción especificada cuando se ha especificado la otra opción especificada.|
|WrnHttpGetFailed|Error HTTP GET con el URI especificado.|
|ErrInputFileNotAssemblyOrMetadata|El archivo en la ubicación especificada leído a través del argumento de entrada especificado no parece ser un archivo de metadatos de XML o un ensamblado válido.|
|WrnUnknownMetadataFound|No puede guardar un documento de metadatos desconocido del tipo especificado.|
|ErrDirectoryContainsInvalidCharacters|El valor no válido especificado se pasó a la opción especificada. El carácter especificado no se permite en una ruta de acceso.|
|WrnCannotResolveServiceForValidation|No puede cargar un servicio con el configName especificado. Para validar un servicio, proporcione tanto el ensamblado que contiene el tipo de servicio como un ejecutable con la configuración para este servicio.|
|ErrUnexpectedValue|La opción especificada no soporta ningún valor.|
|#InvalidArg|Lo especificado contiene un argumento no válido.|
|ParametersExcludeType|\<type>|
|HelpXmlSerializer|Genere tipos de datos que utilicen XmlSerializer para la serialización y deserialización.|
|#|---------------------------------------------------------------------------------------------------------------------=|
|ErrUnexpectedError|Se produjo un error en la herramienta.|
|HelpNologo|Se suprimen el mensaje del banner y el copyright.|
|ErrInputConflictsWithTarget|El tipo de entrada leído de lo especificado no está soportado con la opción especificada establecida en el valor especificado.|
|WrnCannotLoadServiceForExport|Se produjo un error al cargar el tipo de servicio que se va a exportar.|
|HelpMetadataDownloadCategory|-= METADATA DOWNLOAD =-|
|WrnNoServiceContractTypes|No puede generar los tipos XmlSerializer para el ensamblado especificado. No se han encontrado tipos de contrato de servicios.|
|WrnCouldNotLoadTypesFromReferenceAssemblyAt|Se produjo un error al cargar tipos en un ensamblado que se cargó a partir de lo especificado. No se pueden cargar algunos tipos en el ensamblado y no están disponibles para la herramienta.|
|ErrDirectoryPointsToAFile|El valor no válido especificado se pasó a la opción especificada. El valor especificado es una ruta de acceso a un archivo.|
|Error|Error:|
|ErrDuplicateReferenceValues|El ensamblado especificado se cargó dos veces utilizando la opción especificada. Un ensamblado solo puede ser referencia una vez.|
|WrnNoXmlSerializerOperationBehavior|No puede generar XmlSerializer para el ensamblado especificado. Ningún contrato de servicios en el ensamblado se opera con XmlSerializerOperationBehavior.|
|ErrCannotCreateDirectory|No puede crear el directorio especificado.|
|ErrCouldNotLoadTypesFromAssemblyAt|No puede cargar ningún tipo en el ensamblado especificado.|
|ErrUnknownSwitch|El modificador especificado es una opción desconocida.|
|Logotipo|El logotipo de la herramienta es "Microsoft ® Service Model Metadata Tool" con versión.|
|NoCodeWasGenerated|No se generó ningún código.<br /><br /> Si estaba intentando generar un cliente, esto podría ser porque los documentos de metadatos no contenían contratos válidos o servicios<br /><br /> o porque se descubrió que todos los contratos/servicios existían en ensamblados de referencia. Compruebe que pasó todos los documentos de metadatos a la herramienta.|
|WrnUnableToLoadContractForSGen|Se produjo un error al cargar un tipo de contrato. No puede generar el tipo XmlSerializer para este contrato. Se especifican el tipo y detalles.|
|WrnOptionConflictsWithInput|La opción especificada no se puede utilizar con varios ensamblados de entrada. Se omite la opción especificada.|
|ErrUnableToImportMetadata|Se produjo un error crítico al intentar importar los metadatos.|
|ErrInvalidSerializer|Un valor de serializador no válido se pasó a la opción especificada. Se especifican los serializadores soportados.|
|SavingDownloadedMetadata|Guardando los archivos de metadatos descargados...|
|WrnNoConfigForServices|Ninguno de los ensamblados pasados eran ejecutables con archivo de configuración o ninguno de los archivos de configuración contenía servicios con el nombre de configuración especificado.|
|ErrInputConflictsWithOption|La entrada leída a partir de lo especificado no se puede utilizar con la opción especificada porque implica modos diferentes de operación de la herramienta.|
|ErrUnableToExportEndpoints|Se produjo un error al exportar el tipo de servicio especificado.|
|ErrInputSchemaParseError|Se produjo un error de análisis del esquema XML al leer a partir de lo especificado. Compruebe que el formato XML es correcto y válido.|
|ErrInputPolicyParseError|Se produjo un error de análisis de WS-Policy al leer a partir de lo especificado. Compruebe que el formato XML es correcto y válido.|
|ErrUnableToLoadReferenceType|Se produjo un error al cargar un tipo de contrato de referencia. Se ignora este tipo especificado.|
|WrnCannotLoadServiceForValidation|Se produjo un error al cargar el servicio a validar. Se especifican el tipo y detalles.|
|HelpCodeGenerationCategory|-= CODE GENERATION =-|
|RetreivingMetadataWithMexAndDisco|Intentando descargar los metadatos a partir de lo especificado utilizando intercambio de metadatos WS o DISCO.|
|ErrGeneralSchemaValidation|Se produjo un error al comprobar los esquemas XML que se generaron durante la exportación.|
|ParametersDirectory|\<directory>|
|ErrCannotLoadSpecifiedType|Ningún tipo se puede cargar para el valor especificado que se pasó a la opción especificada. Asegúrese de que el ensamblado al que pertenece este tipo se especifica utilizando la opción especificada.|
|ErrOptionModeConflict|La opción especificada no se puede utilizar con la opción especificada porque implican tipos de salida diferentes.|
|ErrIsNotAnAssembly|No puede cargar lo especificado como un ensamblado. Compruebe que este archivo es un .NET ensamblado.|
|ErrInputConflictsWithMode|La entrada leída a partir de lo especificado es incoherente con otras opciones.|
|ErrDuplicateValuePassedToTypeArg|El valor especificado se pasó varias veces a la opción especificada. Se puede especificar cada tipo solo una vez.|
|ErrInputEPRFileParseError|No puede leer la referencia del punto de conexión a partir de lo especificado. Compruebe que el formato XML es correcto y válido.|
|ErrCouldNotCreateCodeProvider|No se puede crear un proveedor de código para el valor especificado que se pasó al {1} argumento/. Compruebe que el proveedor de código se instala y configura correctamente.|
|ErrPathTooLongDirOnly|El resultante la ruta de acceso especificada es demasiado largo. Revise el argumento especificado.|
|HelpDataContractSerializer|Genere tipos de datos que utilicen el serializador DataContract para la serialización y deserialización.|
|ErrUnableToExportEndpoint|Se produjo un error al exportar el nombre de extremo especificado en el espacio de nombres especificado en el tipo de servicio especificado situado en el archivo de configuración cargado para el ensamblado.|
|HelpUsage1|Muestra el uso de la Ayuda.|
|HelpUsage2|Muestra el uso de la Ayuda.|
|HelpUsage3|Muestra el uso de la Ayuda.|
|HelpUsage4|Muestra el uso de la Ayuda.|
|HelpUsage5|Muestra el uso de la Ayuda.|
|ErrDirectoryNotFound|No se puede encontrar el directorio especificado. Compruebe que el directorio existe y que tiene los permisos adecuados para leerlo.|
|ErrUnableToLoadFile|No puede leer el archivo especificado.|
|ErrNoFilesFound|La ruta de acceso de entrada especificada no parece hacer referencia a ningún archivo existente.|
|ParametersConfig|\<configFile>|
|ErrDirectoryInsteadOfFile|La ruta de acceso de entrada especificada parece ser un directorio. La entrada debe ser direcciones URL o rutas de acceso de archivo.|
|HelpConfig|Indica a las herramientas que generen un archivo de configuración con el nombre proporcionado. Valor predeterminado: output.config.|
|ErrSingleUseSwitch|No puede especificarse la opción especificada varias veces.|
|Advertencia|Advertencia:|
|WrnAmbiguousServiceConfig|Se encontraron varias configuraciones de servicio con el nombre de configuración especificado, se especifican los ensamblados siguientes.|
|ErrInvalidInputPath|La ruta de acceso de entrada especificada no parece hacer referencia a ningún archivo existente y no parece ser un URI válido.|
|ErrUnableToLoadInputs|Se produjo un error al leer los metadatos cargados.|
|GeneratingSerializer|Generando serializadores de XML...|
|HelpToolConfig|Archivo de configuración personalizado  que se utilizará en lugar del archivo de configuración. Esto se puede utilizar para cambiar la configuración de los metadatos o registrar extensiones de configuración sin modificar el archivo de configuración de la herramienta.|
|ErrValidateInvalidUse|No puede utilizarse la opción especificada con la opción especificada.|
|WrnWSMExFailed|Error de intercambio de metadatos WS con el URI especificado.|
|HelpNoconfig|No genere la configuración.|
|HelpCodeGenerationDescription|Lo especificado puede generar contratos de servicios, clientes y tipos de datos a partir de documentos de metadatos.|
|HelpTargetMetadata|Metadatos de salida. Si la entrada es una dirección URL, Svcutil.exe guarda los metadatos en el disco y no genera el código. Si la entrada es uno o más ensamblados, Svcutil.exe genera los metadatos a partir de los tipos en los ensamblados.|
|ErrAmbiguousOptionModeConflict|La opción especificada entra en conflicto con otras opciones. Revise su uso de la herramienta.|
|ErrNotLanguageOrCodeDomType|El valor especificado que se pasó al argumento especificado no representa un lenguaje definido y no se puede cargar como un tipo CLR totalmente certificado.|
|ErrUnableToUniquifyFilename|No puede crear el nombre de archivo de salida. Se están creando demasiados archivos con el prefijo especificado.|
|ErrCannotCreateFile|No puede crear el archivo de salida especificado.|
|ErrExpectedValue|La opción especificada requiere que se especifique un valor.|
|ErrCannotDisambiguateSpecifiedTypes|Más de un tipo con el mismo nombre existe en el conjunto de ensamblados de referencia. Utilice nombres totalmente certificados de ensamblado para distinguir entre los tipos especificados para la opción especificada.|
|RetreivingMetadataWithMexOnly|Intentando descargar los metadatos a partir de la ubicación especificada utilizando intercambio de metadatos WS o DISCO. Esta dirección URL no soporta DISCO.|
|ErrInvalidTarget|El destino especificado no es válido cuando se especifica utilizando la opción especificada. Se especifican los destinos soportados.|
|ErrPathTooLong|La ruta de acceso resultante es demasiado larga. Revise los argumentos especificados.|
|HelpCommonOptionsCategory|-= COMMON OPTIONS =-|
|ParametersServiceName|\<serviceConfigName>|
|ErrNoValidInputFilesSpecified|No se especificaron archivos de entrada válidos. Especifique documentos de metadatos o archivos de ensamblado.|
|ParametersLanguage|\<language>|
|ErrUnableToLoadMetadataDocument|Se produjo un error al leer los metadatos a partir de uno de los documentos cargados. Se especifica el identificador del documento.|
|ErrConflictingInputs|El argumento de entrada especificado está en conflicto con lo especificado porque implican modos diferentes de operación de la herramienta.|
|WrnUnableToLoadContractForValidation|Se produjo un error al cargar un tipo de contrato. Se especifican el tipo y detalles.|
|WrnAttributeReflectionErrors|Se produjo un error en la reflexión de atributo para algunos de los tipos en el ensamblado que se cargaron a partir de lo especificado. Compruebe que este ensamblado se pueda cargar desde esta ubicación con los privilegios de seguridad correctos.|
|HelpMetadataExportCategory|-= METADATA EXPORT =-|
|HelpValidationCategory|-= SERVICE VALIDATION =-|
|ValidationError|Error de validación:|
|GeneratingFiles|Generando archivos…|
|ErrCannotSpecifyMultipleMappingsForNamespace|Un valor no válido especificado se pasó a la opción especificada. El espacio de nombres de destino especificado no puede estar asignado a varios espacios de nombres CLR como se ha especificado.|
|ErrCouldNotLoadReferenceAssemblyAt|No puede cargar el ensamblado de referencia especificado.|
|ParametersOut|\<file>|
|NoCodeWasGeneratedSuggestDCOnly|Para generar los contratos a partir de los esquemas, utilice la opción especificada.|
|ErrUnableToLoadInputConfig|No puede cargar el archivo de configuración especificado.|
|ErrUnexpectedDelimiter|Un delimitador de argumentos no válido (':' o '=') no puede iniciar la opción.|
|ErrMergeConfigUsedWithoutConfig|No puede utilizar la opción especificada sin especificar la otra opción especificada.|
|ErrUnableToExportContract|Se produjo un error al exportar el contrato cargado del tipo especificado.|
|GeneratingMetadata|Generando archivos de metadatos…|
|ErrNotCodeDomType|El tipo especificado que se pasó al argumento especificado no es de la clase derivada especificada.|
|WrnNoTypeForServices|Ninguno de los ensamblados que se pasaron contenían tipos de servicio con el nombre de configuración especificado.|
|ErrAssemblyLoadFailed|No puede cargar el archivo especificado como un ensamblado. Compruebe los FusionLogs para obtener información detallada.|
|NoMetadataWasGenerated|No se generó ningún archivo de metadatos. No se exportó ningún contrato de servicios.<br /><br /> Para exportar un servicio, utilice la opción especificada. Para exportar contratos de datos, especifique la opción.|
|WrnCannotResolveServiceForExport|No puede cargar un servicio con el configName especificado. Para exportar un servicio, proporcione el ensamblado que contiene el tipo de servicio y un ejecutable con la configuración para este servicio.|
|ParametersCollectionType|\<type>|
|ErrOptionConflictsWithTarget|El uso de la opción especificada no está soportado con la opción especificada establecida en el valor especificado.|
|ErrCodegenError|Se produjo un error al generar código en el lenguaje especificado.<br /><br /> El lenguaje no soporta todos los elementos de código que se están generando. Se debería utilizar otro lenguaje.|
|ErrInputWsdlParseError|Se produjo un error de análisis de WSDL al leer lo especificado. Compruebe que el formato XML es correcto y válido.|
|ErrCouldNotCreateInstance|No puede crear ninguna instancia del tipo especificado que se pasó al argumento especificado.|
|ParametersNamespace|\<string,string>|
|HelpNostdlib|No hacer referencia a las bibliotecas estándares (de forma predeterminada se hace referencia a mscorlib.dll y system.servicemodel.dll.)|
|WrnCannotLoadConfigFileForExport|Se produjo un error durante el procesamiento del archivo de configuración que se cargó a partir de lo especificado. No se pueden cargar los servicios que se definen en este archivo de configuración.|
|WrnUnableToLoadContractForExport|Se produjo un error al cargar un tipo de contrato. No se puede exportar este tipo especificado.|
