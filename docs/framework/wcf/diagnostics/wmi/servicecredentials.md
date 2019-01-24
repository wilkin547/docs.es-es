---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: 18100ac36b5116c2373171ff795fc23b75bbd6f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572125"
---
# <a name="servicecredentials"></a>ServiceCredentials
ServiceCredentials  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceCredentials no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceCredentials posee las siguientes propiedades:  
  
### <a name="clientcertificate"></a>ClientCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 La autenticación del certificado de cliente y la configuración de aprovisionamiento para este servicio.  
  
### <a name="issuedtokenauthentication"></a>IssuedTokenAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Los valores actuales de autenticación de token emitido para este servicio.  
  
### <a name="peer"></a>Del mismo nivel  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 La autenticación de la credencial actual y la configuración de aprovisionamiento que van a utilizar los puntos de conexión de transporte del mismo nivel.  
  
### <a name="secureconversationauthentication"></a>SecureConversationAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica los valores de conversación seguros actuales.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El certificado asociado a este servicio.  
  
### <a name="usernameauthentication"></a>UserNameAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Los valores de nombre de usuario/contraseña para este servicio.  
  
### <a name="windowsauthentication"></a>WindowsAuthentication  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Los valores de autenticación de Windows para este servicio.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Description.ServiceCredentials>
