---
title: Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: f79991ef7f5d88cf87d1635e8c415ffd2c8b69cd
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "43253370"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)

DataSvcUtil.exe es una herramienta de línea de comandos proporcionada por WCF Data Services que consume una [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuente y genera las clases de servicio de datos de cliente que son necesarios para tener acceso a un servicio de datos desde una aplicación de cliente de .NET Framework. Esta utilidad puede generar las clases de datos utilizando los siguientes orígenes de metadatos:

-   El URI de la raíz de un servicio de datos. La utilidad solicita el documento de metadatos de servicio, que describe el modelo de datos expuesto por el servicio de datos. Para obtener más información, consulte [OData: documento de metadatos del servicio](http://go.microsoft.com/fwlink/?LinkId=186070).

-   Un archivo de modelo de datos (.csdl) definido utilizando el lenguaje de definición de esquemas conceptuales (CSDL), tal como se define en el [ \[MC-CSDL\]: formato de archivo de definición de esquemas conceptuales](http://go.microsoft.com/fwlink/?LinkID=159072) especificación.

-   Un archivo .edmx creado mediante las herramientas de Entity Data Model que se proporcionan con Entity Framework. Para obtener más información, consulte el [ \[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833) especificación.

Para obtener más información, consulte [Cómo: manualmente generar datos de clases del servicio cliente](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

La herramienta DataSvcUtil.exe se instala en el directorio de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. En muchos casos, este se encuentra en *C:\Windows\Microsoft.NET\Framework\v4.0*. Para sistemas de 64 bits, se encuentra en *C:\Windows\Microsoft.NET\Framework64\v4.0*. También puede acceder la herramienta DataSvcUtil.exe en línea de comandos para desarrolladores de Visual Studio.

## <a name="syntax"></a>Sintaxis

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

### <a name="parameters"></a>Parámetros

|Opción|Descripción|
|------------|-----------------|
|`/dataservicecollection`|Especifica que también se genera el código necesario para enlazar los objetos a los controles.|
|`/help`<br /><br /> o bien<br /><br /> `/?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|`/in:` *\<archivo >*|Especifica el archivo .csdl o .edmx o un directorio donde se encuentra el archivo.|
|`/language:`[VB&#124;CSharp]|Especifica el lenguaje de los archivos de código fuente generados. El lenguaje predeterminado es C#.|
|`/nologo`|Evita que se muestre el mensaje de copyright.|
|`/out:` *\<archivo >*|Especifica el nombre del archivo de código fuente que contiene las clases de servicio de datos de cliente generadas.|
|`/uri:` *\<cadena >*|El URI de la fuente de OData.|
|`/version:`[1.0&#124;2.0]|Especifica la versión superior aceptada de OData. La versión se determina según el `DataServiceVersion` atributo del elemento DataService en los metadatos del servicio de datos devueltos. Para obtener más información, consulte [versiones del servicio de datos](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). Al especificar el `/dataservicecollection` parámetro, también debe especificar `/version:2.0` para habilitar el enlace de datos.|

## <a name="see-also"></a>Vea también

- [Generar la biblioteca cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Adición de una referencia a servicios de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
