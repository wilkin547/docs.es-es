---
description: 'Más información acerca de: Nombres de mismo nivel e identificadores PNRP'
title: Nombres de mismo nivel e identificadores PNRP
ms.date: 03/30/2017
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
ms.openlocfilehash: ff9f77917ef05754f2373369d623b66e66b5a753
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801870"
---
# <a name="peer-names-and-pnrp-ids"></a>Nombres de mismo nivel e identificadores PNRP

Un nombre de mismo nivel representa un punto de conexión para la comunicación, que puede ser un equipo, un usuario, un grupo, un servicio o cualquier elemento asociado a un elemento del mismo nivel que se puede resolver en una dirección IPv6. El Protocolo de resolución de nombres de mismo nivel (PNRP) toma el nombre de mismo nivel estadísticamente único para la creación de un identificador PNRP, que se usa para identificar a los miembros de la nube.  
  
## <a name="peer-names"></a>Nombres de mismo nivel  

 Los nombres de mismo nivel se pueden registrar como no seguros o seguros. Los nombres no seguros son simplemente cadenas de texto que están sujetas a la suplantación de identidad, dado que cualquier usuario puede registrar un nombre no seguro duplicado. Los nombres no seguros son útiles en redes privadas o bien, en otros casos, protegidas. Los nombres seguros están protegidos con un certificado y una firma digital. Solo el publicador original podrá demostrar la propiedad de un nombre seguro.  
  
 La combinación de la nube y el ámbito proporciona un entorno razonablemente seguro para equipos del mismo nivel que participan en la actividad de PNRP. Sin embargo, el uso de un nombre seguro de mismo nivel no garantiza la seguridad global de la aplicación de red. La seguridad de la aplicación depende de la implementación.  
  
 Los nombres de mismo nivel seguros solo se registran por su propietario y están protegidos con criptografía de clave pública. Un nombre seguro de mismo nivel se considera que pertenecen a la entidad de mismo nivel que tiene la clave privada correspondiente. La propiedad se puede probar a través de la dirección de mismo nivel certificada (CPA), que se firma con la clave privada. Un usuario malintencionado no puede falsificar la propiedad de un nombre de mismo nivel sin la clave privada correspondiente.  
  
## <a name="pnrp-ids"></a>Identificadores PNRP  

 ![Id. PNRP](./media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")  
  
 Los identificadores PNRP se componen de lo siguiente:  
  
- Los 128 bits de ordenación alta, conocidos como el identificador de punto a punto (P2P), son un hash de un nombre de mismo nivel asignado al punto de conexión. El nombre de mismo nivel tiene el formato siguiente: *Authority.Classifier*. Para los nombres seguros, *Authority* es el hash de Algoritmo hash seguro 1 (SHA1) de la clave pública del nombre de mismo nivel en caracteres hexadecimales. Para los nombres no seguros, *Authority* es el carácter "0" único. *Classifier* es una cadena que identifica la aplicación. Ningún clasificador de nombre de mismo nivel puede ser mayor que 149 caracteres, incluido el terminador `null`.  
  
- Los 128 bits de orden inferior se usan para la ubicación del servicio, que es un número generado que identifica las diferentes instancias del mismo identificador P2P en la misma nube.  
  
 Esta combinación de identificador P2P y ubicación del servicio permite registrar varios identificadores PNRP desde un solo equipo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.PeerToPeer.PeerName>
- <xref:System.Net.PeerToPeer>
