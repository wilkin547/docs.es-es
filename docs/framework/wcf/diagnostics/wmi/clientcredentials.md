---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: c3adc675bb6c1e9011459a88fd7dc8e8cf63a880
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771210"
---
# <a name="clientcredentials"></a>ClientCredentials
ClientCredentials  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ClientCredentials no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ClientCredentials tiene las propiedades siguientes:  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El certificado X.509 que utiliza el cliente para autenticarse en el servicio.  
  
### <a name="httpdigest"></a>HttpDigest  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 La credencial de resumen Http Digest actual.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 La dirección y el enlace del extremo utilizados para contactar con el servicio de tokens de seguridad local.  
  
### <a name="peer"></a>Del mismo nivel  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Las credenciales que el nodo del mismo nivel utiliza para autenticarse a otros nodos de la malla.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El certificado X.509 del servicio.  
  
### <a name="supportinteractive"></a>SupportInteractive  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Un valor booleano que especifica si la credencial admite negociación interactiva.  
  
### <a name="username"></a>UserName  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El nombre de usuario y la contraseña que el cliente utiliza para autenticarse al servicio.  
  
### <a name="windows"></a>Windows  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Las credenciales de Windows que el cliente utiliza para autenticarse al servicio.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ClientCredentials>
