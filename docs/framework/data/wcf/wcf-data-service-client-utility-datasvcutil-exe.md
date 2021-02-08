---
description: 'Más información acerca de: utilidad de cliente de WCF Data Service (DataSvcUtil.exe)'
title: Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 1e232538284072d82eed3f1b9e8d41f2ae950adf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791704"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Utilidad del cliente de Servicio de datos de WCF (DataSvcUtil.exe)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

DataSvcUtil.exe es una herramienta de línea de comandos proporcionada por Servicios de datos de WCF que utiliza una fuente de Open Data Protocol (OData) y genera las clases de servicio de datos de cliente necesarias para tener acceso a un servicio de datos desde una aplicación cliente de .NET Framework. Esta utilidad puede generar las clases de datos utilizando los siguientes orígenes de metadatos:

- El URI de la raíz de un servicio de datos. La utilidad solicita el documento de metadatos de servicio, que describe el modelo de datos expuesto por el servicio de datos. Para obtener más información, consulte [AtomPub (RFC5023)](https://tools.ietf.org/html/rfc5023#section-8).

- Un archivo de modelo de datos (. CSDL) definido mediante el lenguaje de definición de esquemas conceptuales (CSDL), tal como se define en la especificación de [ \[ formato de archivo de definición de \] esquemas conceptuales MC-CSDL](/openspecs/windows_protocols/mc-csdl/c03ad8c3-e8b7-4306-af96-a9e52bb3df12) .

- Un archivo .edmx creado mediante las herramientas de Entity Data Model que se proporcionan con Entity Framework. Para obtener más información, consulte la especificación [ \[ \] de formato de empaquetado MC-EDMX: Entity Data Model para Data Services](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16) .

Para obtener más información, vea [Cómo: generar manualmente clases del servicio de datos del cliente](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

La herramienta de DataSvcUtil.exe se instala en el directorio .NET Framework. En muchos casos, se encuentra en *C:\Windows\Microsoft.NET\Framework\v4.0*. En el caso de los sistemas de 64 bits, se encuentra en *C:\Windows\Microsoft.NET\Framework64\v4.0*. También puede tener acceso a la herramienta de DataSvcUtil.exe desde Símbolo del sistema para desarrolladores para Visual Studio.

## <a name="syntax"></a>Sintaxis

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parámetros

|Opción|Descripción|
|------------|-----------------|
|`/dataservicecollection`|Especifica que también se genera el código necesario para enlazar los objetos a los controles.|
|`/help`<br /><br /> o bien<br /><br /> `/?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|`/in:` *\<file>*|Especifica el archivo .csdl o .edmx o un directorio donde se encuentra el archivo.|
|`/language:`[VB&#124;CSharp]|Especifica el lenguaje de los archivos de código fuente generados. El lenguaje predeterminado es C#.|
|`/nologo`|Evita que se muestre el mensaje de copyright.|
|`/out:` *\<file>*|Especifica el nombre del archivo de código fuente que contiene las clases de servicio de datos de cliente generadas.|
|`/uri:` *\<string>*|El URI de la fuente de OData.|
|`/version:`[1,0&#124;2,0]|Especifica la versión más alta aceptada de OData. La versión se determina en función del `DataServiceVersion` atributo del elemento de servicio de datos en los metadatos del servicio de datos devueltos. Para obtener más información, vea [control de versiones del servicio de datos](data-service-versioning-wcf-data-services.md). Al especificar el `/dataservicecollection` parámetro, también debe especificar `/version:2.0` para habilitar el enlace de datos.|

## <a name="see-also"></a>Vea también

- [Generar la biblioteca cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md)
- [Procedimiento para agregar una referencia a un servicio de datos](how-to-add-a-data-service-reference-wcf-data-services.md)
