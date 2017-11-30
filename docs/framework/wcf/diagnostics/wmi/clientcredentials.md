---
title: ClientCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 68a2fa36c8a4fa1fde3ca8d8aaf1898060ea972f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="clientcredentials"></a>ClientCredentials
ClientCredentials  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
 Tipo de acceso: solo lectura  
  
 El certificado X.509 que utiliza el cliente para autenticarse en el servicio.  
  
### <a name="httpdigest"></a>HttpDigest  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La credencial de Http Digest actual.  
  
### <a name="issuedtoken"></a>IssuedToken  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La dirección y el enlace del extremo utilizados para contactar con el servicio de tokens de seguridad local.  
  
### <a name="peer"></a>Del mismo nivel  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Las credenciales que el nodo del mismo nivel utiliza para autenticarse a otros nodos de la malla.  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El certificado X.509 del servicio.  
  
### <a name="supportinteractive"></a>SupportInteractive  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Un valor booleano que especifica si la credencial admite negociación interactiva.  
  
### <a name="username"></a>UserName  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El nombre de usuario y la contraseña que el cliente utiliza para autenticarse al servicio.  
  
### <a name="windows"></a>Windows  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Las credenciales de Windows que el cliente utiliza para autenticarse al servicio.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.ClientCredentials>
