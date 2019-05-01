---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956967"
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior
ServiceDebugBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceDebugBehavior no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceDebugBehavior posee las siguientes propiedades:  
  
### <a name="httphelppageenabled"></a>HttpHelpPageEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
