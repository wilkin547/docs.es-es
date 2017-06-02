---
title: "Utilidad de cliente de WCF Data Service (DataSvcUtil.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, biblioteca de cliente"
  - "WCF Data Services, uso"
  - "WCF Data Services, generar clases de datos del cliente"
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Utilidad de cliente de WCF Data Service (DataSvcUtil.exe)
DataSvcUtil.exe es una herramienta de línea de comandos proporcionada por [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] que utiliza una fuente de [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] y genera las clases de servicio de datos de cliente necesarias para tener acceso a un servicio de datos desde una aplicación cliente de .NET Framework.  Esta utilidad puede generar las clases de datos utilizando los siguientes orígenes de metadatos:  
  
-   El URI de la raíz de un servicio de datos.  La utilidad solicita el documento de metadatos de servicio, que describe el modelo de datos expuesto por el servicio de datos.  Para obtener más información, vea el tema sobre [OData: documento de metadatos de servicios](http://go.microsoft.com/fwlink/?LinkId=186070).  
  
-   Un archivo de modelo de datos \(.csdl\) definido mediante el lenguaje de definición de esquemas conceptuales \(CSDL\), tal y como se define en [\[MC\-CSDL\]: Formato de archivos de definición de esquemas conceptuales](http://go.microsoft.com/fwlink/?LinkID=159072).  
  
-   Un archivo .edmx creado mediante las herramientas de Entity Data Model que se proporcionan con Entity Framework.  Para obtener más información, vea la especificación [\[MC\-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833).  
  
 Para obtener más información, consulta [Cómo: Generar manualmente clases del servicio de datos del cliente](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
 La herramienta DataSvcUtil.exe se instala en el directorio de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  En muchos casos, se encuentra en C:\\Windows\\Microsoft.NET\\Framework\\v4.0.  Para los sistemas de 64 bits, se encuentra en C:\\Windows\\Microsoft.NET\\Framework64\\v4.0.  También puede tener acceso a la herramienta DataSvcUtil.exe desde el símbolo del sistema de Visual Studio \(haga clic en **Inicio**, seleccione **Todos los programas**, **Microsoft Visual Studio 2010**, **Visual Studio Tools** y haga clic en **Símbolo del sistema de Visual Studio 2010**\).  
  
## Sintaxis  
  
```  
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]  
```  
  
#### Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|`/dataservicecollection`|Especifica que también se genera el código necesario para enlazar los objetos a los controles.|  
|`/help`<br /><br /> o bien<br /><br /> `/?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|`/in:` *\<archivo\>*|Especifica el archivo .csdl o .edmx o un directorio donde se encuentra el archivo.|  
|`/language:`\[VB&#124;CSharp\]|Especifica el lenguaje de los archivos de código fuente generados.  El lenguaje predeterminado es C\#.|  
|`/nologo`|Evita que se muestre el mensaje de copyright.|  
|`/out:` *\<archivo\>*|Especifica el nombre del archivo de código fuente que contiene las clases de servicio de datos de cliente generadas.|  
|`/uri:` *\<string\>*|El URI de la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].|  
|`/version:`\[1.0&#124;2.0\]|Especifica la versión superior aceptada de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  La versión se determina basándose en el atributo `DataServiceVersion` del elemento DataService en los metadatos devueltos del servicio de datos.  Para obtener más información, consulta [Control de versiones del servicio de datos](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  Al especificar el parámetro `/dataservicecollection`, también debe especificar `/version:2.0` para habilitar el enlace de datos.|  
  
## Vea también  
 [Generar la biblioteca de cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)   
 [Cómo: Agregar una referencia a un servicio de datos](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)