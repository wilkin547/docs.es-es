---
title: Filtrar Obtener un certificado (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 21e9e0609ed63c4398f2df7ba718f8af17464b0a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332487"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Filtrar Obtener un certificado (WCF)
Para usar cualquiera de Windows Communication Foundation (WCF) características de los usan certificados X.509, ha de obtener primero los certificados.  
  
### <a name="to-obtain-an-x509-certificate"></a>Para obtener un certificado X.509.  
  
1. Elija una de las siguientes opciones:  
  
    -   Adquiera un certificado de una entidad emisora de certificados, como VeriSign, Inc.  
  
    -   Configure su propio servicio de certificados y haga que una entidad de certificación los firme. [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Server Datacenter y Windows 2000 Datacenter Server incluyen servicios de certificados que admiten la infraestructura de clave pública (PKI). En Windows Server 2008, use la [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) rol para administrar una entidad de certificación.  
  
    -   Configure su propio servicio de certificados y asegúrese de que los certificados no estén firmados.  
  
    > [!NOTE]
    >  Elija el método que elija, el destinatario de la solicitud SOAP que contiene el certificado X.509 debe confiar en el certificado X.509. Esto significa que el certificado X.509 o un emisor en la cadena de certificados está en el almacén de certificados de gente de confianza y que el certificado X.509 no está en el almacén de certificados que no son de confianza.  
  
## <a name="see-also"></a>Vea también

- [Trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Filtrar para crear certificados temporales que puedan usarse durante las operaciones de desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
