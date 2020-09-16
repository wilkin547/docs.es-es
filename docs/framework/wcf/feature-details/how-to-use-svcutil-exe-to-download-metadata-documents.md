---
title: Procedimiento para usar Svcutil.exe para descargar documentos de metadatos
description: Aprenda a usar Svcutil.exe para descargar metadatos de servicios en ejecución y guardar los metadatos en archivos locales.
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 6877d860a4465947268d6535b9edeb9856d4d689
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554311"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Procedimiento para usar Svcutil.exe para descargar documentos de metadatos
Puede utilizar Svcutil.exe para descargar metadatos de los servicios en ejecución y para guardar los metadatos en archivos locales. Para los esquemas de dirección URL HTTP y HTTPS, Svcutil.exe intenta recuperar metadatos mediante WS-MetadataExchange y la [detección de servicios Web XML](/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)). Para todos los otros esquemas de URL, Svcutil.exe utiliza sólo WS-MetadataExchange.  
  
 De forma predeterminada, Svcutil.exe utiliza los enlaces definidos en la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings>. Para configurar el enlace utilizado para WS-MetadataExchange, debe definir un extremo de cliente en el archivo de configuración para Svcutil.exe (svcutil.exe.config) que utiliza el contrato `IMetadataExchange` y que tiene el mismo nombre que el esquema del Identificador uniforme de recursos (URI) de la dirección del extremo de metadatos.  
  
> [!CAUTION]
> Al ejecutar Svcutil.exe para obtener los metadatos de un servicio que expone dos contratos de servicio diferentes, cada uno de los cuales contiene una operación con el mismo nombre, Svcutil.exe muestra un error que dice "no se pueden obtener metadatos de...". Por ejemplo, si tiene un servicio que expone un contrato de servicio denominado `ICarService` que tiene una operación `Get(Car c)` y el mismo servicio expone un contrato de servicio denominado `IBookService` que tiene una operación `Get(Book b)` . Para solucionar este problema, siga uno de estos procedimientos:
>
> - Cambie el nombre de una de las operaciones.
> - Establezca el <xref:System.ServiceModel.OperationContractAttribute.Name%2A> en un nombre distinto.
> - Establezca el espacio de nombres de una de las operaciones en un espacio de nombres distinto mediante la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Para descargar metadatos mediante Svcutil.exe  
  
1. Busque la herramienta Svcutil.exe en la ubicación siguiente:  
  
     C:\Archivos de programa\Microsoft SDKs\Windows\v1.0.\bin  
  
2. En el símbolo del sistema, inicie la herramienta mediante el formato siguiente.  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Debe especificar la opción `/t:metadata` para descargar los metadatos. De lo contrario, se generan el código de cliente y la configuración.  
  
3. El `url` argumento <>especifica la dirección URL a un extremo de servicio que proporciona metadatos o a un documento de metadatos hospedado en línea. El `epr` argumento <> especifica la ruta de acceso a un archivo XML que contiene un WS-Addressing `EndpointAddress` para un punto de conexión de servicio que admite WS-MetadataExchange.  
  
 Para obtener más opciones sobre el uso de esta herramienta para la descarga de metadatos, vea [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente descarga los documentos de metadatos de un servicio en ejecución.  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Vea también

- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
