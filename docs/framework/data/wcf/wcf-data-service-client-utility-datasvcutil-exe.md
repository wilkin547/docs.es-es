---
title: Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 97e9502176e0cc2f36d67ee3dc8e8d0739a009b2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790197"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)

Herramienta datasvcutil. exe es una herramienta de línea de comandos que proporciona WCF Data Services que consume [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] una fuente y genera las clases de servicio de datos de cliente necesarias para tener acceso a un servicio de datos desde una aplicación cliente de .NET Framework. Esta utilidad puede generar las clases de datos utilizando los siguientes orígenes de metadatos:

- El URI de la raíz de un servicio de datos. La utilidad solicita el documento de metadatos de servicio, que describe el modelo de datos expuesto por el servicio de datos. Para obtener más información, [consulte OData: Documento](https://go.microsoft.com/fwlink/?LinkId=186070)de metadatos de servicio.

- Un archivo de modelo de datos (. CSDL) definido mediante el lenguaje de definición de esquemas conceptuales (CSDL) [, tal y\]como se define en \[MC-CSDL: Especificación de formato](https://go.microsoft.com/fwlink/?LinkID=159072) de archivo de definición de esquemas conceptuales.

- Un archivo .edmx creado mediante las herramientas de Entity Data Model que se proporcionan con Entity Framework. Para obtener más información, consulte [ \[MC-EDMX\]: Entity Data Model para la especificación de](https://go.microsoft.com/fwlink/?LinkID=178833) formato de empaquetado de Data Services.

Para obtener más información, consulte [Cómo Generar manualmente las clases](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)del servicio de datos del cliente.

La herramienta herramienta datasvcutil. exe se instala en el directorio .NET Framework. En muchos casos, se encuentra en *C:\Windows\Microsoft.NET\Framework\v4.0*. En el caso de los sistemas de 64 bits, se encuentra en *C:\Windows\Microsoft.NET\Framework64\v4.0*. También puede tener acceso a la herramienta herramienta datasvcutil. exe desde Símbolo del sistema para desarrolladores para Visual Studio.

## <a name="syntax"></a>Sintaxis

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parámetros

|Opción|DESCRIPCIÓN|
|------------|-----------------|
|`/dataservicecollection`|Especifica que también se genera el código necesario para enlazar los objetos a los controles.|
|`/help`<br /><br /> -o bien-<br /><br /> `/?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|`/in:` *\<file>*|Especifica el archivo .csdl o .edmx o un directorio donde se encuentra el archivo.|
|`/language:`[VB&#124;CSharp]|Especifica el lenguaje de los archivos de código fuente generados. El lenguaje predeterminado es C#.|
|`/nologo`|Evita que se muestre el mensaje de copyright.|
|`/out:` *\<file>*|Especifica el nombre del archivo de código fuente que contiene las clases de servicio de datos de cliente generadas.|
|`/uri:` *\<string>*|El URI de la fuente de OData.|
|`/version:`[1.0&#124;2.0]|Especifica la versión más alta aceptada de OData. La versión se determina en función del `DataServiceVersion` atributo del elemento de servicio de datos en los metadatos del servicio de datos devueltos. Para obtener más información, vea [control de versiones del servicio de datos](data-service-versioning-wcf-data-services.md). Al especificar el parámetro `/dataservicecollection` , también debe especificar `/version:2.0` para habilitar el enlace de datos.|

## <a name="see-also"></a>Vea también

- [Generar la biblioteca cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md)
- [Cómo: Agregar una referencia de servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md)
