---
title: 220 - MessageSentToTransport
ms.date: 03/30/2017
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
ms.openlocfilehash: 9f95edf42e0b1ec19d2019773def282fc279871b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948284"
---
# <a name="220---messagesenttotransport"></a>220 - MessageSentToTransport
## <a name="properties"></a>Properties (Propiedades)  
  
|||  
|-|-|  
|Id|220|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|Nivel|Información|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>DESCRIPCIÓN  
 Este evento se emite cuando el modelo de servicio envía un mensaje al transporte.  
  
> [!NOTE]
> Este evento no se emitirá para transportes unidireccionales.  
  
## <a name="message"></a>Message  
 El distribuidor envió un mensaje al transporte. Id. de correlación == '%1'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|DESCRIPCIÓN|  
|--------------------|--------------------|-----------------|  
|Correlation ID|`xs:GUID`|El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.|  
|HostReference|`xs:string`|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web. Su formato se define como ' ruta&#124;&#124;de acceso virtual del servicio de ruta de acceso virtual de la aplicación nombre del sitio web ServiceName '. Ejemplo: ' Default Web site/CalculatorApplication&#124;/CalculatorService.SVC&#124;CalculatorService '.|  
|AppDomain|`xs:string`|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
