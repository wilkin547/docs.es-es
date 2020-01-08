---
title: Cómo obtener un certificado (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 485741f98c4a120669eafe85d3a3810374f61378
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347149"
---
# <a name="how-to-obtain-a-certificate-wcf"></a>Cómo obtener un certificado (WCF)
Para usar cualquiera de las características de Windows Communication Foundation (WCF) de que usan certificados X. 509, primero tiene que obtener certificados.  
  
### <a name="to-obtain-an-x509-certificate"></a>Para obtener un certificado X.509.  
  
1. Elija una de las siguientes opciones:  
  
    - Adquiera un certificado de una entidad emisora de certificados, como VeriSign, Inc.  
  
    - Configure su propio servicio de certificados y haga que una entidad de certificación los firme. Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter y Windows 2000 Datacenter Server incluyen servicios de servidor de certificados que admiten la infraestructura de clave pública (PKI). En Windows Server 2008, use el rol [servicios de certificados de Active Directory](https://go.microsoft.com/fwlink/?LinkID=153483) para administrar una entidad de certificación.  
  
    - Configure su propio servicio de certificados y asegúrese de que los certificados no estén firmados.  
  
    > [!NOTE]
    > Elija el método que elija, el destinatario de la solicitud SOAP que contiene el certificado X.509 debe confiar en el certificado X.509. Esto significa que el certificado X.509 o un emisor en la cadena de certificados está en el almacén de certificados de gente de confianza y que el certificado X.509 no está en el almacén de certificados que no son de confianza.  
  
## <a name="see-also"></a>Vea también

- [Trabajo con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Creación de certificados temporales que puedan utilizarse durante las operaciones de desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
